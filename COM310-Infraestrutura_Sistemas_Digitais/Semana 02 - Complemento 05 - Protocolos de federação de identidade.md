# Protocolos de federação de identidade

Começar pela escolha certa evita retrabalho e riscos. Abaixo, um quadro comparativo enxuto; depois, destrinchamos cada protocolo, fluxos, tokens e práticas de segurança.

---

| Protocolo | Finalidade | Token/troca | Principais casos | Observações |
|---|---|---|---|---|
| SAML 2.0 | Autenticação federada e SSO web | Assertions XML assinadas; bindings HTTP-Redirect/POST | SSO corporativo (SaaS como Salesforce/Workday), B2E | Maduro e amplamente suportado em apps legadas; foco em navegador |
| OpenID Connect (OIDC) | Autenticação padronizada sobre OAuth 2.0 | ID Token JWT e UserInfo; discovery/JWKS | Web e mobile modernos; login social; B2C/B2B | Simples de integrar; ótimo para apps e APIs; combina com OAuth |
| OAuth 2.0 | Autorização delegada (acesso a APIs) | Access/Refresh Tokens (JWT/opaques) | APIs, microserviços, mobile, máquina-a-máquina | Não é login por si só; use OIDC para identidade |
| WS-Federation | SSO federado legado | Mensagens WS-Fed com SAML 1.1 | Ambientes com ADFS/SharePoint antigos | Útil para compatibilidade; costuma ser alvo de migração |

> Sources: compare usar OIDC para autenticação de usuários, OAuth para autorização em APIs e SAML para SSO enterprise; WS-Fed permanece por compatibilidade.

---

## Visão geral da federação

- **Conceito:** Um Provedor de Identidade (IdP) autentica o usuário e emite um token assinado; o Provedor de Serviço (SP/RP) confia nesse token para conceder acesso.
- **Papéis:**  
  - **IdP:** autentica e assina declarações (claims).  
  - **SP/RP:** valida assinatura, audiência e condições; cria sessão local.  
  - **Usuário/Agente:** tipicamente o navegador, às vezes apps nativos.
- **Objetivos:**  
  - **SSO:** reduzir logins repetidos entre domínios.  
  - **Menos senhas locais:** centralizar políticas de autenticação (MFA, risco).  
  - **Atributos confiáveis:** enviar apenas o necessário para autorização.

---

## SAML 2.0 em profundidade

#### Componentes e metadados
- **Metadados SAML:** descrevem endpoints, certificados de assinatura/cripto, formatos de NameID e bindings.  
- **Tokens:** **Assertions** XML assinadas com **X.509**; podem ser criptografadas.

#### Fluxos
- **SP-initiated:**  
  - **Passos:** SP emite AuthnRequest → redireciona usuário ao IdP → IdP autentica → retorna SAML Response (POST) → SP valida e cria sessão.  
- **IdP-initiated:**  
  - **Passos:** Usuário inicia no IdP → IdP emite Response direto ao SP.  
  - **Atenção:** Sem request original, reforce validações de **audience**, **Recipient** e **InResponseTo** (quando aplicável).

#### Segurança e validação
- **Assinatura obrigatória:** valide cadeia X.509, algoritmo e canonicalização.  
- **Condições:** verifique **NotBefore/NotOnOrAfter**, **AudienceRestriction** e **SubjectConfirmation** (incluindo endereço/Recipient).  
- **Bindings:**  
  - **HTTP-Redirect:** leve, mas limitado pelo tamanho da URL.  
  - **HTTP-POST:** preferido para respostas (menos limites de tamanho).  
- **Single Logout (SLO):** útil, porém frágil (diversos SPs não implementam bem). Planeje fallback de sessão.

#### Casos típicos
- **SSO corporativo web:** SaaS enterprise, intranet, apps que já falam SAML.  
- **Migração gradual:** ponte para OIDC via brokers (AD FS, Keycloak, Auth0, Entra ID).

---

## OpenID Connect e OAuth 2.0 em profundidade

#### Por que dois padrões?
- **OAuth 2.0:** define autorização delegada para APIs (quem pode acessar o quê).  
- **OIDC:** camada de identidade sobre OAuth 2.0 (quem é o usuário), via **ID Token**.

#### Elementos centrais (OIDC)
- **Descoberta e chaves:** `/.well-known/openid-configuration` e **JWKS** para rotação de chaves.  
- **Tokens:**  
  - **ID Token (JWT):** contém claims de identidade (iss, sub, aud, exp, iat, nonce, amr/acr).  
  - **Access Token:** autoriza acesso a APIs; pode ser JWT ou opaco.  
  - **Refresh Token:** renova acesso de forma silenciosa; ative rotação.  
- **Endpoints:** authorization, token, userinfo, jwks, logout.  
- **Scopes/claims:** `openid`, `profile`, `email`, etc.; minimização de dados.

#### Fluxos recomendados
- **Authorization Code + PKCE (web/mobile):** mitiga interceptação de código.  
- **Device Code (IoT/TV):** quando não há navegador nativo.  
- **Client Credentials (M2M):** sem usuário, apenas clientes confidenciais.  
- (Evite/aposente: **Implicit** e **ROPC**.)

#### Proteções essenciais
- **PKCE sempre:** inclusive para clientes confidenciais modernos.  
- **state + nonce:** anti-CSRF e anti-replay em OIDC.  
- **Redirect URIs exatas:** sem curingas; use HTTPS estrito.  
- **Validação de ID Token:** verifique assinatura, `iss/aud/exp/nonce`.  
- **DPOP/mTLS:** vincule tokens ao cliente (proof-of-possession) quando possível.  
- **Consent/logout:** implemente front-/back-channel logout conforme suportado.

#### Casos típicos
- **B2C/B2B modernos:** apps SPA, mobile, APIs.  
- **Login social corporativo controlado:** via “identity brokering”.

---

## WS-Federation no que importa

- **Natureza:** protocolo de SSO baseado em redirecionamentos; muito usado com **AD FS**.  
- **Parâmetros usuais:** `wa=wsignin1.0`, `wtrealm`, `wctx`, `wreply`.  
- **Token comum:** **SAML 1.1** dentro do envelope WS-Fed.  
- **Uso hoje:** manter compatibilidade com apps Microsoft legadas; planeje migração para **OIDC**/**SAML 2.0** onde possível.  
- **Cuidados:** mensagens e mapeamento de claims variam entre implementações; documente trust e rollover de certificados.

---

## Arquiteturas, ponte entre padrões e boas práticas

#### Topologias e mediação
- **Direta (ponto-a-ponto):** SP ↔ IdP; simples, mas cresce mal.  
- **Hub-and-spoke (broker):** um broker (ex.: Entra ID, Keycloak, Auth0) traduz SAML↔OIDC/OAuth e centraliza políticas.  
- **Multi-hop:** limite cadeias longas; cada salto aumenta latência e área de ataque.

#### Governança de confiança
- **Rollover de chaves:** planeje janelas de sobreposição; monitore JWKS/metadata.  
- **Ciclo de vida de trusts:** versionamento, aprovação e expiração de certificados.  
- **Mapeamento de atributos:** defina esquema canônico; minimize PII; documente transformações.

#### Segurança aplicada
- **Assinatura e, quando necessário, criptografia de tokens/assertions.**  
- **Janelas curtas de validade:** reduzem replay; use refresh tokens com rotação/deteção.  
- **Sessão do SP:** regenere cookies no login; flags `Secure`, `HttpOnly`, `SameSite`.  
- **MFA no IdP:** passe sinalização de autenticação (acr/amr) ao RP.  
- **Resistência a phishing:** combine com **WebAuthn/passkeys** no IdP e inicie login sempre no domínio do IdP (evite links profundos frágeis).  
- **Logs e detecção:** centralize eventos (falhas de validação, erros de audiência, anomalias de origem).  
- **SLO pragmático:** onde SLO não for confiável, use **curta duração** de sessão + revogação de refresh tokens.

#### Migrações e interoperabilidade
- **De SAML/WS-Fed para OIDC:** use broker para coexistência; migre SPs por ondas.  
- **Token translation:** cuidado com perda/ganho de semântica (NameID vs sub, groups vs scopes).  
- **Compatibilidade mobile/SPAs:** prefira Authorization Code + PKCE; evite tokens em fragmentos de URL.
