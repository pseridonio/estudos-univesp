# Infraestrutura para sistemas de software — servidores web (conteúdo da videoaula)


## Contexto e objetivos da aula

- **Tema central:** Introdução prática aos servidores web na WWW: surgimento, função, principais características, funcionamento básico e exemplos, conectando com tópicos vistos antes (camadas, endereçamento, DNS, HTTP).   
- **Competências destacadas:** Compreender modelagem de infraestrutura em larga escala, firewalls por filtro de pacotes, proxies (conteúdo e relação com firewalls), mecanismos de autenticação (com menção a OpenLDAP), funcionamento de web servers e complexidade de servir conteúdos variados a partir de data centers.   
- **Motivação:** A EAD e a web moderna dependem de servidores web que atendem requisições de clientes (browsers ou aplicações) para entregar HTML, imagens, áudio/vídeo e APIs, via HTTP/HTTPS. 

---

## História e papel dos servidores web

- **Origens da web:** Tim Berners-Lee (CERN) propôs em 1989 um sistema para compartilhamento de documentos; criou o primeiro browser (WorldWideWeb) e o primeiro servidor HTTP (CERN httpd), inicialmente em um NeXTcube.   
- **Modelo cliente-servidor:** O servidor web é um processo em execução contínua que aceita requisições HTTP e devolve respostas com recursos solicitados, servindo tanto conteúdo estático quanto gerado dinamicamente por aplicações e integrações (ex.: pagamento, e-mail).   
- **WWW por hipermídia:** A navegação por links conecta hosts e recursos, com HTTP no papel de protocolo de aplicação para requisição-resposta de hipermídia. 

---

## HTTP e funcionamento básico

- **Estrutura das mensagens:** Linha inicial, cabeçalhos, linha em branco e corpo; status codes orientam o cliente (famílias 1xx–5xx).   
- **Métodos em destaque:** GET (obter recurso), POST (enviar dados para processamento), PUT (substituir representação), DELETE (remover recurso). A aula enfatiza uso predominante de GET/POST em aplicações comuns e o uso de métodos HTTP em APIs REST.   
- **Ciclo requisição–resposta:** Cliente envia solicitação (método, caminho, cabeçalhos), servidor interpreta e responde com status, cabeçalhos (ex.: Content-Type, Last-Modified) e corpo; pode encaminhar via proxy quando configurado. 

---

## Caminho de uma URL e entrega de conteúdo

- **Desmembrando a URL:** Esquema/protocolo (http/https), nome do servidor (mapeado para endereço IP via DNS), caminho do recurso (ex.: /cursos).   
- **Portas padrão e sessão:** Servidores escutam portas padronizadas (HTTP/80; HTTPS/443) e devolvem HTML e mídia que o navegador renderiza; a conexão ao host identificado pelo IP ocorre após a resolução de nomes.   
- **HTTPS na prática:** Sítios institucionais tendem a usar HTTPS para criptografar todas as transações; o servidor web pode atuar diretamente ou por meio de um proxy (cache/filtragem). 

---

## Conteúdo, proxies e exemplos

- **Conteúdo estático e dinâmico:** Arquivos simples (HTML, imagens, MP3/MP4) versus páginas geradas por motores (PHP, JSP, Python, etc.) integrados a bancos de dados e serviços (e-mail via SMTP, pagamentos, multimídia).   
- **Proxies:** Proxy intermediando o tráfego entre cliente e servidor melhora cache e controle de acesso; em ambientes corporativos, pode também filtrar conteúdo.   
- **Servidores comuns:** Apache é citado como amplamente utilizado, atendendo desde sites e compartilhamento de arquivos até integração com sistemas de e-mail e jogos online. 

---

## Análise crítica e esclarecimentos pontuais

- **HTTP versões atuais:** A aula menciona “versão 2.0” e “2 para cima”. Hoje, HTTP/2 é amplamente usado e HTTP/3 (sobre QUIC/UDP) está em adoção crescente. Em termos práticos, isso impacta performance (multiplexação, cabeçalhos comprimidos, latência reduzida) e transporte (TCP vs. QUIC).   
- **Portas vs. protocolo:** O exemplo de conexão “padrão: porta 80” é correto para HTTP; para HTTPS, a porta padrão é 443. Em sites institucionais, como dito, HTTPS é a norma, logo a porta efetiva usualmente é 443.   
- **Nome do sistema de nomes:** Onde o vídeo se refere a “VMS”, entenda-se DNS (Domain Name System), o serviço que resolve nomes em endereços IP.   
- **Métodos além do quarteto:** Além de GET/POST/PUT/DELETE, métodos como HEAD, OPTIONS e PATCH são comuns em APIs modernas; ainda assim, o foco didático da aula no quarteto é adequado para a introdução.   
- **Proxy: papéis distintos:** A aula aborda o proxy como intermediário/caching. Vale distinguir entre forward proxy (cliente → internet) e reverse proxy (internet → servidores), ambos válidos no contexto mostrado. 

---

## Complementos alinhados aos materiais

- **Transporte sob HTTP:** Na camada de transporte, HTTP historicamente opera sobre TCP (confiável, orientado a conexão); com HTTP/3, opera sobre QUIC (user space, sobre UDP), reduzindo handshake e melhorando multiplexação sob perda. Esse encaixe ilustra a separação entre camadas de aplicação (HTTP) e transporte (TCP/UDP), reforçando a base teórica das aulas de UDP/TCP.  
- **DNS e IP no fluxo da URL:** Antes de o cliente abrir a conexão com o servidor web, ocorre a resolução DNS do nome de host para um endereço IP público roteável; só então a pilha de rede estabelece a conexão na porta de serviço (80/443) para solicitar o caminho (/cursos).  
- **Apache como serviço (Linux):** Em sistemas Linux, o servidor web (ex.: httpd/apache2) roda como daemon, escutando na porta escolhida, com diretórios de documentos e módulos de aplicação; logs e configuração (vhosts) controlam o mapeamento host → conteúdo e política de segurança.

> Observação: Estes complementos conectam diretamente com os materiais de endereçamento IP, TCP/UDP e administração Linux listados pelo professor, sem introduzir tópicos externos à aula (como topologias).

---

## Lista de 30 exercícios com soluções

1. **Exercício 1:** Explique o papel do servidor web no modelo cliente-servidor da WWW.  
   - **Solução:**  
     1) O cliente envia uma requisição HTTP (método + caminho + cabeçalhos). 2) O servidor web, em execução contínua, escuta na porta de serviço (80/443), interpreta a requisição. 3) Ele localiza o recurso (estático ou via aplicação), monta a resposta (status, cabeçalhos, corpo) e devolve ao cliente. 4) Opcionalmente, envolve proxy para cache/filtragem.

2. **Exercício 2:** Diferencie conteúdo estático de dinâmico em servidores web.  
   - **Solução:**  
     1) Estático: arquivos servidos “como estão” (HTML, CSS, imagens). 2) Dinâmico: conteúdo gerado por aplicações (PHP, Python, JSP) com lógica, BD e integrações. 3) Estático é simples e rápido; dinâmico permite personalização e transações.

3. **Exercício 3:** Esboce a estrutura de uma mensagem HTTP de requisição e de resposta.  
   - **Solução:**  
     1) Requisição: linha inicial (ex.: GET /cursos HTTP/1.1), cabeçalhos (Host, Accept), linha em branco, corpo (em POST/PUT). 2) Resposta: status-line (HTTP/1.1 200 OK), cabeçalhos (Content-Type), linha em branco, corpo (HTML/JSON/etc.).

4. **Exercício 4:** Associe os métodos HTTP ao uso típico: GET, POST, PUT, DELETE.  
   - **Solução:**  
     1) GET: obter representação do recurso. 2) POST: enviar dados para processamento (ex.: formulário, criação de recurso). 3) PUT: substituir representação no alvo. 4) DELETE: remover recurso. 5) Em REST, GET é seguro; PUT/DELETE são idempotentes.

5. **Exercício 5:** Qual a diferença prática entre HTTP e HTTPS na entrega de conteúdo?  
   - **Solução:**  
     1) HTTP: sem criptografia; tráfego em texto claro. 2) HTTPS: túnel TLS sobre HTTP, provendo confidencialidade, integridade e autenticação do servidor. 3) Portas padrão: 80 vs 443. 4) HTTPS é a prática recomendada para toda transação.

6. **Exercício 6:** Decomponha a URL https://www.univesp.br/cursos.  
   - **Solução:**  
     1) Esquema: https. 2) Host: www.univesp.br. 3) Caminho: /cursos. 4) Porta implícita: 443 (por ser https). 5) O DNS resolve o host para um IP; a conexão TLS+HTTP é então estabelecida.

7. **Exercício 7:** Descreva o fluxo de resolução de nomes até a obtenção do conteúdo.  
   - **Solução:**  
     1) Cliente consulta cache DNS local; se miss, questiona o resolvedor recursivo. 2) Resolvedor obtém resposta autoritativa e retorna o IP. 3) Cliente conecta ao IP:porta. 4) Envia requisição; recebe resposta; navegador renderiza.

8. **Exercício 8:** Interprete as famílias de códigos de status HTTP.  
   - **Solução:**  
     1) 1xx: informativos. 2) 2xx: sucesso (ex.: 200 OK). 3) 3xx: redirecionamentos (ex.: 301/302). 4) 4xx: erro do cliente (ex.: 400, 404). 5) 5xx: erro do servidor (ex.: 500, 503).

9. **Exercício 9:** Dê um exemplo onde POST é preferível a GET.  
   - **Solução:**  
     1) Envio de credenciais ou dados de checkout. 2) Motivos: sem exposição de parâmetros na URL, payload maior, sem cache automático, sem registro em histórico.

10. **Exercício 10:** Por que PUT e DELETE exigem cautela?  
    - **Solução:**  
      1) São operações que alteram estado no servidor. 2) Devem ser autenticadas/autorizadas. 3) Em proxies/firewalls, podem ser bloqueadas por política. 4) Idempotência não elimina necessidade de validação de permissões.

11. **Exercício 11:** Compare forward proxy e reverse proxy.  
    - **Solução:**  
      1) Forward: entre cliente e internet; foco em cache/filtragem de saída. 2) Reverse: na borda do servidor; foco em balanceamento, TLS offload, cache de entrada. 3) Ambos intermediam HTTP; papéis e políticas diferem.

12. **Exercício 12:** Explique por que sites institucionais adotam HTTPS por padrão.  
    - **Solução:**  
      1) Protege dados do usuário e integridade do conteúdo. 2) Evita ataques de interceptação e injeção. 3) Requisito de conformidade e SEO. 4) Custo/complexidade reduzidos por automação (ex.: ACME).

13. **Exercício 13:** Qual a relação entre HTTP e TCP/UDP?  
    - **Solução:**  
      1) HTTP é protocolo de aplicação. 2) HTTP/1.1 e HTTP/2 usam TCP; HTTP/3 usa QUIC sobre UDP. 3) A camada de transporte impacta latência, multiplexação e resiliência a perdas.

14. **Exercício 14:** Dê um exemplo de integração de servidor web com SMTP.  
    - **Solução:**  
      1) Webmail: interface web (HTTP) integra-se ao servidor de e-mail (SMTP/IMAP). 2) Usuário interage via navegador; servidor web orquestra envio e leitura com serviços de e-mail.

15. **Exercício 15:** Mostre como um proxy melhora desempenho em portais de mídia.  
    - **Solução:**  
      1) Cache de objetos estáticos (imagens, vídeos segmentados). 2) Reduz latência e uso de banda no origin. 3) Políticas de expiração e invalidação controlam frescor.

16. **Exercício 16:** Identifique riscos de usar apenas HTTP em formulários.  
    - **Solução:**  
      1) Exposição de dados sensíveis. 2) Suscetibilidade a MITM e manipulação. 3) Violações de privacidade e compliance. 4) Solução: HTTPS e cabeçalhos de segurança.

17. **Exercício 17:** O que um servidor precisa para “ficar online” servindo HTTP?  
    - **Solução:**  
      1) Processo do servidor (daemon) em execução. 2) Porta aberta e roteável (80/443). 3) DNS apontando para IP público. 4) Regras de firewall liberando tráfego. 5) Conteúdo/mapeamento (vhosts).

18. **Exercício 18:** Relacione métodos HTTP a idempotência e segurança.  
    - **Solução:**  
      1) GET/HEAD: seguros (não alteram estado). 2) PUT/DELETE: idempotentes (efeito repetido é o mesmo). 3) POST: não idempotente. 4) Segurança lógica exige autenticação/autorização conforme operação.

19. **Exercício 19:** Justifique o uso de cabeçalhos Last-Modified/ETag.  
    - **Solução:**  
      1) Permitem validação condicional (If-Modified-Since/If-None-Match). 2) Economizam banda e CPU. 3) Melhora TTFB percebido pelo usuário.

20. **Exercício 20:** Desenhe o caminho de https://www.univesp.br/cursos em alto nível.  
    - **Solução:**  
      1) Navegador consulta DNS. 2) Conecta ao IP:443. 3) Handshake TLS. 4) Envia GET /cursos (Host: www.univesp.br). 5) Recebe 200 e corpo HTML. 6) Baixa recursos referenciados (CSS/JS/imagens).

21. **Exercício 21:** Quando um 404 é preferível a 301/302?  
    - **Solução:**  
      1) Quando o recurso realmente não existe ou foi removido sem substituto. 2) 301/302 indicam redirecionamento; 404 evita confundir indexadores e usuários.

22. **Exercício 22:** Aponte benefícios do HTTP/2 sobre 1.1.  
    - **Solução:**  
      1) Multiplexação em uma conexão. 2) Compressão de cabeçalhos (HPACK). 3) Priorização de streams. 4) Menos “sharding” e hacks como sprites.

23. **Exercício 23:** Por que HTTP/3 pode reduzir latência?  
    - **Solução:**  
      1) QUIC reduz handshakes (0-RTT/1-RTT). 2) Multiplexação sem head-of-line blocking do TCP. 3) Migração de conexão em mudanças de IP.

24. **Exercício 24:** Cite três cabeçalhos de segurança úteis.  
    - **Solução:**  
      1) Strict-Transport-Security (HSTS). 2) Content-Security-Policy (CSP). 3) X-Content-Type-Options (nosniff). 4) Benefícios: downgrade prevention, mitigação XSS, MIME confusion.

25. **Exercício 25:** Explique “renderização” no cliente após resposta HTTP.  
    - **Solução:**  
      1) Browser parseia HTML em DOM. 2) Baixa CSS/JS referenciados. 3) Constrói árvore de renderização e layout. 4) Executa JavaScript, faz novas requisições conforme necessário.

26. **Exercício 26:** Quando usar POST vs. PUT para criação?  
    - **Solução:**  
      1) POST para criação sob coleção (server define URI). 2) PUT quando o cliente define a URI alvo. 3) Consistência com semântica REST facilita cache e idempotência.

27. **Exercício 27:** Como um reverse proxy ajuda na segurança?  
    - **Solução:**  
      1) Termina TLS e aplica WAF. 2) Esconde topologia interna. 3) Limita taxa e bloqueia IPs maliciosos. 4) Aplica políticas de autenticação/autorização centralizadas.

28. **Exercício 28:** Qual o impacto do DNS mal configurado para um site?  
    - **Solução:**  
      1) Nome não resolve → indisponibilidade. 2) TTLs inadequados → propagação lenta. 3) Registros incorretos → roteamento errado / quebra de CDN. 4) Mitigação: validação e monitoramento.

29. **Exercício 29:** Dê um exemplo de erro 400 e outro de 500.  
    - **Solução:**  
      1) 400 Bad Request: sintaxe inválida (ex.: cabeçalho malformado). 2) 500 Internal Server Error: exceção na aplicação no servidor (stack trace). 3) Remediação: validação de input vs. correção de bug/observabilidade.

30. **Exercício 30:** Por que a aula associa proxies a firewalls por filtro de pacotes?  
    - **Solução:**  
      1) Em redes corporativas, políticas de saída/entrada combinam L3/L4 (firewall) com L7 (proxy). 2) O firewall controla portas/endpoints; o proxy inspeciona e decide pelo conteúdo. 3) Juntos, reduzem superfície de ataque e custo de banda.

---

## Bibliografia

- **UNIVESP — Infraestrutura para Sistemas de Software: Servidores Web (LIBRAS).** Professor: Julio Cezar Estrella. YouTube: https://www.youtube.com/watch?v=kYWyX6HalRA (acesso em 14 ago. 2025).  
- **Tim Berners-Lee; CERN.** Primeiros passos da web (história do WorldWideWeb e CERN httpd). CERN & W3C. https://home.cern/science/computing/birth-web e https://www.w3.org/History.html (acesso em 14 ago. 2025).  
- **IETF — HTTP/2 e HTTP/3.** RFC 7540 (HTTP/2, 2015), RFC 9114 (HTTP/3, 2022). https://www.rfc-editor.org/rfc/rfc7540 e https://www.rfc-editor.org/rfc/rfc9114 (acesso em 14 ago. 2025).  
- **MDN Web Docs — HTTP overview e methods.** Mozilla. https://developer.mozilla.org/docs/Web/HTTP e https://developer.mozilla.org/docs/Web/HTTP/Methods (acesso em 14 ago. 2025).  
- **Apache HTTP Server Project — Documentação oficial.** Apache Software Foundation. https://httpd.apache.org/docs/ (acesso em 14 ago. 2025).  
- **Introdução às Redes de Computadores — Definições.** Wikiversidade. https://pt.wikiversity.org/wiki/Introdu%C3%A7%C3%A3o_%C3%A0s_Redes_de_Computadores/Defini%C3%A7%C3%B5es_das_Redes_de_Computadores (acesso em 14 ago. 2025).  
- **Introdução ao Endereçamento IP (PDF).** Blackboard CDN (material do curso). Link conforme fornecido pelo professor (acesso em 14 ago. 2025).  
- **Camada de Transporte UDP (PDF).** Blackboard CDN (material do curso). Link conforme fornecido pelo professor (acesso em 14 ago. 2025).  
- **Camada de Transporte TCP (PDF).** Blackboard CDN (material do curso). Link conforme fornecido pelo professor (acesso em 14 ago. 2025).  
- **Nemeth, E.; Snyder, G.; Hein, T. R.** Manual completo do Linux: guia do administrador. 1. ed. São Paulo: Pearson, 2005. E-book. Disponível em: https://plataforma.bvirtual.com.br (acesso em 14 ago. 2025).  