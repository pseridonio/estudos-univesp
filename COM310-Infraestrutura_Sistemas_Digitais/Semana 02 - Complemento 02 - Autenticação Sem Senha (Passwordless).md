# 🔐 Autenticação Sem Senha (Passwordless)

## 1. Conceito

Autenticação sem senha é um método de verificação de identidade que **elimina o uso de senhas tradicionais**, substituindo-as por fatores mais seguros, como:

- **Algo que você é**: biometria (impressão digital, reconhecimento facial, íris, voz).
- **Algo que você tem**: chaves de segurança (FIDO2), smartphones, smart cards.
- **Algo que você recebe**: links mágicos (magic links), códigos OTP temporários.

Em vez de memorizar e digitar uma senha, o usuário confirma sua identidade por meio de um fator físico ou criptográfico, reduzindo riscos de ataques como phishing, força bruta e vazamento de credenciais.

---

## 2. Por que abandonar as senhas?

Segundo a FIDO Alliance, **81% das violações de dados** envolvem senhas fracas ou comprometidas.  
Problemas comuns das senhas:

- Fácil de adivinhar ou quebrar.
- Reutilização em vários serviços.
- Suscetíveis a phishing e vazamentos.
- Custos altos com redefinições e suporte técnico.

---

## 3. Tecnologias e padrões

### 🔹 **FIDO2 + WebAuthn**
- **FIDO2**: conjunto de padrões da FIDO Alliance e W3C que usa criptografia de chave pública para autenticação.
- **WebAuthn**: API que permite navegadores e apps registrarem e autenticarem usuários com chaves públicas, biometria ou dispositivos seguros.
- **CTAP2**: protocolo que conecta autenticadores externos (USB, NFC, Bluetooth) ao cliente.

**Como funciona**:
1. Registro: o dispositivo cria um par de chaves (privada no dispositivo, pública no servidor).
2. Login: o servidor envia um desafio criptográfico.
3. O dispositivo assina o desafio com a chave privada.
4. O servidor valida com a chave pública registrada.

---

## 4. Métodos comuns de autenticação sem senha

| Método | Descrição | Vantagens | Pontos de atenção |
|--------|-----------|-----------|-------------------|
| **Biometria** | Impressão digital, rosto, íris | Conveniente, difícil de falsificar | Privacidade, spoofing avançado |
| **Chaves de segurança (FIDO2)** | Dispositivo físico USB/NFC/BLE | Alta resistência a phishing | Custo e logística de distribuição |
| **Passkeys** | Credenciais criptográficas sincronizadas entre dispositivos | Fácil uso, multiplataforma | Depende de ecossistemas compatíveis |
| **Magic Links** | Link único enviado por e-mail/SMS | Simples para o usuário | Segurança depende do canal de envio |
| **OTP (One-Time Password)** | Código temporário via app ou SMS | Fácil implementação | SMS vulnerável a SIM swap |

---

## 5. Benefícios

- **Segurança reforçada**: elimina senhas armazenadas em servidores.
- **Resistência a phishing**: chaves vinculadas ao domínio legítimo.
- **Experiência do usuário**: login mais rápido e intuitivo.
- **Redução de custos**: menos chamados de redefinição de senha.

---

## 6. Desafios e cuidados

- **Adoção gradual**: usuários e sistemas legados podem exigir transição híbrida.
- **Perda de dispositivo**: é essencial ter métodos de recuperação seguros.
- **Compatibilidade**: nem todos os serviços e navegadores suportam todos os métodos.
- **Treinamento**: conscientizar usuários sobre novos fluxos de login.

---

## 7. Boas práticas de implementação

1. **Começar com grupos piloto** antes de expandir.
2. **Oferecer múltiplas opções** de autenticadores.
3. **Manter MFA** (autenticação multifator) para contas críticas.
4. **Planejar recuperação de conta** (backup keys, suporte verificado).
5. **Monitorar e registrar** tentativas de autenticação para auditoria.

---

## 8. Tendências futuras

- **Passkeys universais** integradas a sistemas operacionais e navegadores.
- **Biometria comportamental** (padrões de digitação, uso do mouse).
- **Identidade descentralizada** (DID) e autenticação baseada em blockchain.
- **Integração com Zero Trust** para autenticação contínua e adaptativa.

---

## 9. Comparativo: Senhas vs Passwordless



| Critério | Senhas Tradicionais | Autenticação Sem Senha |
|----------|--------------------|------------------------|
| **Forma de autenticação** | Algo que o usuário **sabe** (senha alfanumérica). | Algo que o usuário **é** (biometria) ou **tem** (chave de segurança, dispositivo confiável). |
| **Segurança** | Vulnerável a ataques de força bruta, phishing e vazamentos de banco de dados. | Alta resistência a phishing, reutilização e roubo de credenciais, pois não transmite senhas. |
| **Experiência do usuário** | Exige memorização e digitação manual. | Rápida, prática e sem necessidade de lembrar senhas. |
| **Custo de suporte** | Alto — redefinições e bloqueios frequentes. | Reduzido — menos incidentes com perda/esquecimento de credenciais. |
| **Risco em caso de vazamento** | Senhas podem ser usadas em outros serviços (reuso). | Chaves privadas ficam no dispositivo e não são expostas. |
| **Compatibilidade** | Funciona em praticamente qualquer sistema, mesmo legado. | Depende de suporte a padrões como FIDO2/WebAuthn. |
| **Métodos típicos** | Senha única, senha + 2FA (OTP via app/SMS). | Biometria, passkeys, chaves de segurança, magic links. |

---

## 📌 Resumo visual

```
Senha tradicional → vulnerável a ataques
↓
Passwordless → autenticação com biometria, chaves, passkeys
↓
Mais segurança + melhor experiência + menos custos
```

---

## 📚 Referências

- [Microsoft Security – Passwordless Authentication](https://www.microsoft.com/en-us/security/business/solutions/passwordless-authentication)  
- [GeeksforGeeks – What is Passwordless Authentication?](https://www.geeksforgeeks.org/computer-networks/what-is-passwordless-authentication/)  
- [Inteca – Passwordless Authentication Guide](https://inteca.com/blog/identity-access-management/passwordless-authentication-guide/)  
- [FIDO Alliance – Passkeys](https://fidoalliance.org/passkeys/)  
- [Duo Security – WebAuthn, Passwordless and FIDO2 Explained](https://duo.com/blog/webauthn-passwordless-fido2-explained-componens-passwordless-architecture)  

