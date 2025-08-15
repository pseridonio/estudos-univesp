# 🛡️ Ataques Comuns Contra Autenticação

## 1. Introdução
A autenticação é a **primeira linha de defesa** contra acessos não autorizados. Quando falha, abre caminho para invasões, roubo de dados e até controle total de sistemas.  
Segundo a StrongDM, **mais de 82% das violações de dados** têm relação com credenciais fracas ou comprometidas.

---

## 2. Principais ataques e vulnerabilidades

| Ataque / Vulnerabilidade | Descrição | Impacto Potencial | Medidas de Mitigação |
|--------------------------|-----------|-------------------|----------------------|
| **Brute Force / Ataque de Dicionário** | Tentativas automáticas de múltiplas combinações de usuário e senha até encontrar a correta. | Comprometimento de contas, especialmente com senhas fracas. | Limitar tentativas, usar CAPTCHA, MFA e senhas fortes. |
| **Credential Stuffing** | Uso de credenciais vazadas de outros serviços para invadir contas. | Acesso não autorizado em massa. | MFA, detecção de padrões anômalos, senhas únicas por serviço. |
| **Phishing** | Enganar usuários para que revelem credenciais. | Roubo de contas, acesso a dados sensíveis. | Treinamento, filtros anti-phishing, autenticação resistente a phishing (FIDO2). |
| **Username Enumeration** | Descoberta de usuários válidos por mensagens de erro ou tempos de resposta. | Facilita ataques direcionados. | Mensagens genéricas de erro, respostas uniformes. |
| **Session Hijacking** | Roubo de identificadores de sessão para assumir contas. | Controle total da conta sem senha. | Cookies seguros, HTTPS, regeneração de sessão após login. |
| **Falhas em MFA** | Implementações incorretas permitem bypass. | Quebra da camada extra de segurança. | Testes de segurança, MFA robusto (hardware keys). |
| **Protocolos Inseguros** | Uso de métodos obsoletos como PAP/CHAP sem criptografia. | Interceptação de credenciais. | TLS, protocolos modernos (OAuth 2.0, OpenID Connect). |
| **Vulnerabilidades em Passkeys/WebAuthn** | Exploração de falhas no protocolo ou implementação. | Comprometimento de autenticação passwordless. | Atualizações, auditorias, implementação correta do padrão. |
| **Bypass em Ambientes Híbridos (AD + Entra ID)** | Escalada de privilégios explorando sincronização e APIs. | Controle administrativo não autorizado. | Auditoria de servidores, rotação de chaves SSO, princípio do menor privilégio. |

---

## 3. Casos recentes e tendências

- **Ataques a Passkeys/WebAuthn**: Pesquisadores demonstraram técnicas para explorar falhas no protocolo, permitindo comprometer autenticação sem senha.  
- **Bypass em Active Directory + Entra ID**: Vulnerabilidade em ambientes híbridos permitiu transformar contas de baixo privilégio em administradores.  
- **Credential Stuffing em larga escala**: Continua sendo um dos ataques mais baratos e eficazes para criminosos, explorando hábitos de reutilização de senhas.

---

## 4. Boas práticas de defesa

1. **Implementar MFA** — preferencialmente com chaves de segurança FIDO2.  
2. **Monitorar tentativas de login** e bloquear padrões suspeitos.  
3. **Educar usuários** sobre phishing e engenharia social.  
4. **Usar protocolos seguros** e manter sistemas atualizados.  
5. **Gerenciar sessões** com expiração e regeneração de tokens.  
6. **Auditar periodicamente** a implementação de autenticação.  

---

## 📌 Resumo visual

```
[Usuário] → [Mecanismo de Autenticação] → [Ameaças: brute force, phishing, hijacking, bypass]
↓
[Impacto: roubo de dados, controle de conta, danos à reputação]
↓
[Defesas: MFA, protocolos seguros, monitoramento, educação]
```
