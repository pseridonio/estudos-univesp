# Controle de Acesso e Mecanismos de Autenticação

## 🎯 Objetivos da Aula
- Compreender o papel crítico do controle de acesso na segurança de aplicações e infraestruturas, locais ou em nuvem.
- Diferenciar **identificação**, **autenticação** e **autorização**, entendendo como se complementam.
- Explorar os principais **mecanismos de autenticação** (senhas, tokens, certificados, biometria, smart cards).
- Conhecer **modelos de controle de acesso**: DAC, RBAC e controle centralizado (RADIUS).
- Entender a importância da **gerência de identidades** via diretórios (LDAP, Active Directory) e sua aplicação em ambientes corporativos.

---

## 1. Conceitos Fundamentais

- **Controle de Acesso**: políticas e mecanismos para impedir ou permitir acesso a recursos digitais.
- **Objetivos diretos**: garantir **disponibilidade**, **integridade** e **confidencialidade** (tríade da segurança da informação).
- **Riscos de falhas**: vazamento de dados, indisponibilidade de serviços, modificação não autorizada de informações.

---

## 2. Classificação do Controle de Acesso

| Base | Descrição | Exemplos |
|------|-----------|----------|
| **Host-based** | Proteção a arquivos, objetos e recursos do SO | Permissões de arquivos no Linux/Windows |
| **Sistema** | Restrições aplicadas a aplicações e bancos de dados | Aplicação web intermediando acesso ao DB |
| **Rede** | Filtragem de pacotes, proxies e firewalls | ACLs em roteadores, Squid proxy |

---

## 3. Elementos do Processo

- **Sujeito**: quem solicita acesso (usuário, processo, host).
- **Objeto**: recurso protegido (arquivo, tabela, serviço).
- **Monitor de Referência**: mecanismo que media e valida acesso.

---

## 4. Etapas Clássicas

1. **Identificação**: declarar quem é (username, ID).
2. **Autenticação**: provar identidade (senha, certificado, biometria).
3. **Autorização**: definir o que pode ser acessado (permissões, papéis).
4. **Prestação de contas**: registro para auditoria (logs).

---

## 5. Mecanismos de Autenticação

- **Senhas**: estáticas (fixas) ou dinâmicas (OTP).
- **Tokens e chaves criptográficas**: segundo fator de autenticação, assinatura digital.
- **Smart Cards**: com ou sem contato, capazes de armazenar/processar dados.
- **Biometria**: impressão digital, íris, voz, reconhecimento facial.

---

## 6. Modelos de Controle de Acesso

- **DAC (Discretionary Access Control)**: proprietário define permissões (ex.: ACLs em Squid).
- **RBAC (Role-Based Access Control)**: permissões associadas a papéis atribuídos a usuários.
- **Controle Centralizado**: servidor único de autenticação (ex.: RADIUS), suportando protocolos PAP, CHAP, EAP.

---

## 7. Gerência de Identidades (IdM)

- Baseada em diretórios como **LDAP** ou **Active Directory**:
  - Estrutura hierárquica (árvore).
  - Armazena atributos de usuário (nome, email, função, senha).
  - Suporta IPv4 e IPv6.
  - Pode integrar múltiplos bancos de dados.

---

## 🔍 Análise Crítica

- A aula cobre bem fundamentos e exemplos práticos, mas:
  - **Falta** abordar métodos modernos de autenticação sem senha (passwordless), como FIDO2/WebAuthn, muito utilizados atualmente.
  - **Não aprofunda** em ataques comuns contra autenticação (phishing, brute force, credential stuffing).
  - **Poderia** explorar integração com MFA (multi-factor authentication) como padrão mínimo de segurança em ambientes corporativos.
  - **Seria útil** incluir protocolos de federação de identidade (SAML, OAuth2, OpenID Connect), essenciais para SSO corporativo.

---

## 📝 Exercícios com Resolução

1. **Defina controle de acesso e relacione com a tríade da segurança.**  
   Resposta: mecanismo para permitir/negar acesso a recursos digitais, visando manter disponibilidade, integridade e confidencialidade.

2. **Explique a diferença entre identificação e autenticação.**  
   Resposta: identificação declara identidade; autenticação prova essa identidade.

3. **Dê dois exemplos de objeto em controle de acesso.**  
   Resposta: arquivo de configuração, tabela de banco de dados.

4. **Cite um exemplo prático de autenticação por algo que o usuário sabe.**  
   Resposta: senha alfanumérica.

5. **Explique a função do monitor de referência.**  
   Resposta: mediar e validar solicitações de acesso entre sujeito e objeto.

6. **Descreva um cenário de controle baseado em host.**  
   Resposta: usuário restrito a arquivos específicos via permissões POSIX.

7. **Diferencie DAC de RBAC.**  
   Resposta: DAC é definido pelo dono do recurso; RBAC por papéis predefinidos.

8. **Como um smart card armazena e processa dados?**  
   Resposta: por circuito integrado, realizando operações criptográficas.

9. **Por que usar OTP em vez de senha estática?**  
   Resposta: reduz risco de replay ou vazamento de credenciais.

10. **Cite um exemplo de autenticação biométrica.**  
    Resposta: leitura de impressão digital.

11. **Quando usar controle centralizado?**  
    Resposta: quando há necessidade de gerenciar autenticações em múltiplos sistemas de forma uniforme.

12. **Explique PAP e CHAP.**  
    Resposta: PAP transmite senha em claro; CHAP usa desafio/resposta criptografado.

13. **Cite um ataque que compromete autenticação por senha.**  
    Resposta: phishing.

14. **Qual a principal limitação do DAC?**  
    Resposta: decisões delegadas ao proprietário podem violar política global.

15. **Benefício do RBAC sobre DAC.**  
    Resposta: gerenciamento simplificado por papéis, evitando decisões dispersas.

16. **Cite um atributo armazenado em LDAP.**  
    Resposta: email do usuário.

17. **Qual a estrutura típica de um diretório LDAP?**  
    Resposta: árvore hierárquica.

18. **Por que registrar logs de acesso?**  
    Resposta: auditoria e responsabilização.

19. **Explique MFA.**  
    Resposta: uso de dois ou mais fatores de autenticação para reforçar segurança.

20. **Dê um exemplo de algo que o usuário possui para autenticação.**  
    Resposta: token físico.

21. **Como biometria garante unicidade?**  
    Resposta: baseia-se em características físicas únicas.

22. **Quais protocolos modernos suportam SSO?**  
    Resposta: SAML, OAuth2, OpenID Connect.

23. **O que é credential stuffing?**  
    Resposta: uso automatizado de credenciais vazadas para invadir contas.

24. **Por que é importante restringir acesso direto a banco de dados?**  
    Resposta: evitar bypass da lógica de aplicação.

25. **Dê um exemplo de redundância para alta disponibilidade.**  
    Resposta: dois servidores web em failover.

26. **Como a criptografia ajuda na confidencialidade?**  
    Resposta: torna dados ilegíveis para não autorizados.

27. **Explique o papel do backup na disponibilidade.**  
    Resposta: permite restaurar dados após falhas.

28. **Como Active Directory atribui permissões?**  
    Resposta: por grupos de segurança e políticas.

29. **Cite um uso de RADIUS.**  
    Resposta: autenticação de usuários em rede corporativa Wi-Fi.

30. **Qual a relação entre controle de acesso e compliance?**  
    Resposta: cumprimento de requisitos legais e normativos (ex.: LGPD, ISO 27001).

---

## 📚 Bibliografia

- UNIVESP. *Controle de Acesso e Mecanismos de Autenticação (LIBRAS)*. Disponível em: [YouTube](https://www.youtube.com/watch?v=69ngnlX29e4&ab_channel=UNIVESP). Acesso em: 14 ago. 2025.  
- STALLINGS, W. *Cryptography and Network Security*. Pearson, 8ª ed., 2023.  
- IETF. RFC 4510 – *Lightweight Directory Access Protocol (LDAP)*. Disponível em: https://datatracker.ietf.org/doc/html/rfc4510. Acesso em: 14 ago. 2025.  
- NEMETH, E.; SNYDER, G.; HEIN, T. R. *Manual Completo do Linux: Guia do Administrador*. Pearson, 2005.  
- OWASP. *Authentication Cheat Sheet*. Disponível