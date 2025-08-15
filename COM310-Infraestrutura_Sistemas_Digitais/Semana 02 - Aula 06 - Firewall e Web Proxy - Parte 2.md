# Firewalls e Web Proxies – Parte 2

## Objetivos

- Explorar o funcionamento de um proxy de aplicação (Squid), desde instalação até configuração avançada de ACLs.  
- Entender como regras de controle de acesso em arquivo texto (ACLs) são interpretadas e aplicadas pelo Squid.  
- Aprender a bloquear domínios, endereços IP, URLs e palavras-chave, assegurando políticas de navegação.  
- Conhecer arquiteturas híbridas de segurança: combinação de filtros de pacotes, proxies, screening routers, bastion hosts e DMZs.  
- Compreender o papel de sistemas de detecção de intrusão (IDS) e honeypots na estratégia de defesa em profundidade.  

---

## Conteúdo

### 1. Proxy de aplicação: Squid

- O Squid é um servidor proxy HTTP/HTTPS que atua na camada de aplicação, intermediando requisições web entre clientes e servidores remotos.  
- Vantagens: cache de conteúdo para otimizar largura de banda e desempenho; controle granular por URL, domínio e palavra-chave.  

### 2. Instalação e arquivo de configuração

| Passo                       | Comando / Descrição                                         |
|-----------------------------|-------------------------------------------------------------|
| Instalação básica           | `sudo apt-get update && sudo apt-get install squid`        |
| Backup de configuração      | `sudo cp /etc/squid/squid.conf /etc/squid/squid.conf.backup`|
| Principal arquivo de regras | `/etc/squid/squid.conf`                                     |

- A cada alteração, reinicie o Squid:  
  ```bash
  sudo systemctl restart squid
  ```

### 3. Sintaxe de ACLs

- Define listas de controle de acesso em arquivo texto, linha a linha.  
- Tipos comuns de ACL:  
  - `acl allowed_sites dstdomain .exemplo.com`  
  - `acl blocked_ips src 192.168.0.0/24`  
  - `acl blocked_words url_regex -i sexo`  
- Uso em sequência:  
  ```conf
  http_access allow allowed_sites
  http_access deny blocked_ips
  http_access deny blocked_words
  http_access deny all
  ```

### 4. Bloqueio por domínio vs. IP

- Bloquear apenas domínio não impede acesso por endereço IP direto.  
- Melhor prática: criar ACLs para ambos, ex.:  
  ```conf
  acl blocked_sites dstdomain .exemplo.com
  acl blocked_ips dst 203.0.113.45
  ```

### 5. Estratégias de negação implícita

- Política “deny all” ao final do arquivo e “allow” apenas para listas específicas.  
- Inverte-se a lógica: somente o que consta em ACLs de permissão é liberado.

### 6. Proxies transparentes e reversos

- **Transparente:** não exige configuração no browser; intercepta requisições na rede.  
- **Reverso:** protege servidores internos, recebe requisições externas e as filtra antes de repassá-las ao backend.

### 7. Arquiteturas de firewall híbrido

- **Screening Router + Bastion Host + DMZ:**  
  1. Roteador externo filtra pacotes básicos.  
  2. Bastion host (servidor fortificado) executa proxy e serviços públicos na DMZ.  
  3. Rede interna isolada, comunicando-se somente com bastion host.  
- Integração com IDS: análise de assinaturas, comportamentos anômalos e protocolos.

### 8. Honeypot e IDS

- **Honeypot:** host que emula vulnerabilidades, coleta informações do atacante sem comprometer o ambiente real.  
- **IDS:** monitora tráfego interno e externo para identificar padrões de ataque e gerar alertas.  

---

## Análise Crítica

- O vídeo detalha bem Squid e ACLs, mas não aborda interceptação HTTPS via TLS proxy (SSL Bump) nem avaliação de certificados.  
- Falta discussão sobre Web Application Firewalls (WAF) para proteção a ataques de camada 7.  
- Poderia incluir práticas de centralização de logs (ELK, Graylog) e orquestração de proxies em escala (Ansible, Puppet).  
- Não menciona suporte ou desafios com IPv6 em ACLs, que vem ganhando adoção crescente.  

---

## Exercícios

1. **Descreva o papel do Squid em uma rede corporativa.**  
   Resolução:  
   - Passo 1: Squid atua como intermediário HTTP/HTTPS, recebendo requisições dos clientes.  
   - Passo 2: Verifica cache local e, se ausente, encaminha ao servidor remoto.  
   - Passo 3: Retorna resposta ao cliente e armazena conteúdo em cache para futuras requisições.

2. **Como criar uma ACL para bloquear todos os IPs da rede 10.0.0.0/8?**  
   Resolução:  
   - Passo 1: Abrir `/etc/squid/squid.conf`.  
   - Passo 2: Adicionar linha `acl blocked_net src 10.0.0.0/8`.  
   - Passo 3: Incluir `http_access deny blocked_net` antes de `http_access deny all`.  
   - Passo 4: Reiniciar o Squid.

3. **Explique a diferença entre `dstdomain` e `dst`.**  
   Resolução:  
   - `dstdomain`: compara nomes de domínio na URL (camada de aplicação).  
   - `dst`: compara endereço IP de destino no pacote (camada de rede).  
   - Escolha depende de necessidade de bloquear por nome ou por IP.

4. **Monte uma ACL que permita apenas `.empresa.com.br` e nada mais.**  
   Resolução:  
   ```
   acl allowed_sites dstdomain .empresa.com.br
   http_access allow allowed_sites
   http_access deny all
   ```

5. **Por que é importante fazer o backup do `squid.conf` antes de modificá-lo?**  
   Resolução:  
   - Permite restaurar configurações originais em caso de erro.  
   - Passo 1: `cp squid.conf squid.conf.bak`  
   - Passo 2: Testar novas regras.  
   - Passo 3: Se falhar, reverter com o backup.

6. **Qual comando Linux reinicia o serviço do Squid?**  
   Resolução:  
   - `sudo systemctl restart squid` (em distribuições systemd).  
   - Alternativa legacy: `sudo service squid restart`.

7. **Explique o que ocorre se `http_access deny all` ficar acima de todas as ACLs de permissão.**  
   Resolução:  
   - Negação implícita bloqueia todo tráfego antes de avaliar ACLs seguintes.  
   - Resultado: nenhum acesso liberado.

8. **Defina um proxy reverso e cite um caso de uso.**  
   Resolução:  
   - Proxy reverso recebe requisições externas e as encaminha a servidores backend.  
   - Caso: balanceamento de carga em múltiplos servidores web.

9. **Como o Squid pode cachear conteúdo estático?**  
   Resolução:  
   - `cache_dir` define local e tamanho do cache.  
   - Squid armazena objetos com base em política de tempo de expiração HTTP (`Expires`, `Cache-Control`).

10. **Demonstre como bloquear URLs contendo a palavra “chat” (case-insensitive).**  
    Resolução:  
    ```
    acl block_chat url_regex -i chat
    http_access deny block_chat
    ```

11. **Por que bloquear domínio e IP simultaneamente?**  
    Resolução:  
    - Domínios podem resolver em múltiplos IPs ou mudar de endereço.  
    - Bloquear IP garante cobertura caso DNS seja contornado.

12. **O que é um bastion host e qual seu papel na DMZ?**  
    Resolução:  
    - Host fortificado exposto à rede externa.  
    - Único ponto que pode ser acessado, isolando demais servidores internos.

13. **Descreva o conceito de screening router.**  
    Resolução:  
    - Roteador posicionado na borda, aplicando filtragem de pacotes básica (ACLs de roteador).

14. **Por que usar `url_regex` em vez de `dstdomain` para certas ACLs?**  
    Resolução:  
    - `url_regex` permite bloquear trechos de URL (paths, parâmetros).  
    - Útil para restringir páginas específicas de um domínio.

15. **Explique como um honeypot auxilia a segurança.**  
    Resolução:  
    - Emula vulnerabilidades para atrair atacantes.  
    - Coleta informações de técnicas e padrões de invasão sem comprometer ativos reais.

16. **Liste três tipos de ACL suportados pelo Squid.**  
    Resolução:  
    1. `src` / `dst` (IP fonte/destino)  
    2. `dstdomain` (domínio de destino)  
    3. `url_regex` (expressões regulares em URL)

17. **Como integrar Squid a um servidor OpenLDAP para autenticação?**  
    Resolução:  
    - Instalar `squid-ldap-auth`.  
    - Configurar `auth_param ldap` em `squid.conf` com URL do servidor, DN e senha de ligação.

18. **Qual o efeito de `cache deny` em uma ACL?**  
    Resolução:  
    - Impede que objetos de determinadas ACLs sejam armazenados em cache.  
    - Exemplo: `cache deny block_chat`.

19. **Explique o que são políticas de permissão implícita.**  
    Resolução:  
    - Tudo negado por padrão; somente o que consta em ACLs de permissão é liberado.

20. **Por que não bloquear apenas palavras-chave gerais em grandes dicionários?**  
    Resolução:  
    - Alto risco de falsos positivos e degradação de desempenho pelo volume de regras.

21. **Mostre como permitir acesso apenas no horário de almoço (12h–14h).**  
    Resolução:  
    ```
    acl lunch_period time MTWHF 12:00-14:00
    http_access allow lunch_period allowed_sites
    http_access deny all
    ```

22. **Descreva um ataque que um IDS deve detectar.**  
    Resolução:  
    - Signature-based: padrão de SQL injection em URL.  
    - Behaviour-based: aumento súbito de tentativas de login.

23. **Como o IDS diferencia tráfego legítimo de anômalo?**  
    Resolução:  
    - Usa perfis de uso normal e compara padrões de volume, frequência e comandos incomuns.

24. **Explique a distinção entre proxy transparente e não-transparente.**  
    Resolução:  
    - Transparente intercepta sem configuração do cliente.  
    - Não-transparente exige apontar explicitamente o proxy no browser.

25. **Por que centralizar logs de Squid e firewall?**  
    Resolução:  
    - Correlacionar eventos, facilitar auditoria e detecção de incidentes.

26. **O que significa “deny all” no contexto de ACLs?**  
    Resolução:  
    - Regra final que bloqueia todo tráfego não explicitamente permitido.

27. **Como ajustar o tamanho do cache do Squid?**  
    Resolução:  
    - Editar `cache_mem` e `cache_dir` em `squid.conf`.

28. **Descreva o fluxo de requisição em ambiente com firewall e proxy.**  
    Resolução:  
    1. Cliente → proxy (Camada aplicação)  
    2. Proxy → firewall (Camada rede)  
    3. Firewall → Internet  
    4. Resposta retorna seguindo caminho inverso

29. **Como prevenir que usuários contornem proxy via SSH tunneling?**  
    Resolução:  
    - Bloquear portas SSH no firewall de borda; permitir somente no bastion host.

30. **Quais cuidados ao manter ACLs de proxy em escala?**  
    Resolução:  
    - Modularizar arquivos de ACL, revisar periodicamente, automatizar deploy e testar em ambiente de homologação.

---

## Bibliografia

- UNIVESP. Infraestrutura para Sistemas de Software – Firewalls e Web Proxies – Parte 2 (LIBRAS). YouTube. Disponível em: https://www.youtube.com/watch?v=l5zx9rT52xU. Acesso em: 17 ago. 2025.  
- WESSELS, D. _Squid: The Definitive Guide_. O’Reilly Media, 2004.  
- Squid-Cache Project. “SQUID Documentation”. Disponível em: http://www.squid-cache.org/Doc/. Acesso em: 17 ago. 2025.  
- RFC 7231. “Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content”. IETF, 2014. Disponível em: https://tools.ietf.org/html/rfc7231. Acesso em: 17 ago. 2025.  
- WIKIVERSITY. Introdução às Redes de Computadores/Definições das Redes de Computadores. Disponível em: https://pt.wikiversity.org/wiki/Introdu%C3%A7%C3%A3o_%C3%A0s_Redes_de_Computadores/Defini%C3%B5es_das_Redes_de_Computadores. Acesso em: 17 ago. 2025.  
- NEMETH, E.; SNYDER, G.; HEIN, T. R. _Manual Completo do Linux: Guia do Administrador_. 1. ed. Pearson, 2005. Acesso em: 17 ago. 2025.