# Principais Protocolos de Comunicação

## Objetivos e importância

Nesta aula, apresentamos os protocolos fundamentais do modelo TCP/IP, essenciais para viabilizar a troca de dados entre clientes, servidores e aplicações na Internet e na Web.  

Compreender TCP, UDP, IP e HTTP é imprescindível para projetar sistemas distribuídos, garantir desempenho e confiabilidade em transmissões de arquivos, páginas web, áudio e vídeo em tempo real.

---

## Definição de protocolo

Protocolo é um conjunto de regras que define o formato (sintaxe), o significado (semântica) e as ações necessárias para a troca de mensagens entre duas ou mais entidades comunicantes em rede.  

Cada protocolo é documentado em um RFC (Request for Comments), que padroniza desde codificação de cabeçalhos e temporizações até mecanismos de controle de erros e fluxo.

---

## Modelo em camadas e protocolos

Para reduzir complexidade, o TCP/IP organiza funções em quatro camadas. Cada camada oferece serviços à imediatamente superior e utiliza serviços da imediatamente inferior.

| Camada TCP/IP       | Protocolos principais          |
|---------------------|---------------------------------|
| Aplicação           | HTTP                            |
| Transporte          | TCP, UDP                        |
| Internet            | IP                              |
| Acesso à rede       | Ethernet, Wi-Fi, PPP etc.       |

### Encapsulamento e desencapsulamento

1. A aplicação gera dados e os passa para a camada de Transporte.  
2. A camada de Transporte adiciona seu cabeçalho e produz um segmento (TCP) ou datagrama (UDP).  
3. A camada de Internet encapsula o segmento/datagrama em um datagrama IP.  
4. A camada de Acesso à rede empacota o datagrama IP em um quadro (Ethernet, Wi-Fi).  
5. No receptor, cada camada remove seu cabeçalho em ordem inversa até entregar os dados puros à aplicação.

---

## Protocolos fundamentais

### Internet Protocol (IP)

- Endereçamento lógico de hosts em 32 bits (IPv4).  
- Roteamento de datagramas por algoritmos de estado de enlace ou vetor de distância.  
- Encapsulamento em datagramas com cabeçalho mínimo de 20 bytes.  
- Campos principais: versão, IHL, tipo de serviço, comprimento total, identificação, flags, offset, TTL, protocolo, checksum, endereços de origem e destino, opções.

### Transmission Control Protocol (TCP)

- Orientado a conexão; estabelece comunicação fim a fim com handshake de três vias (SYN, SYN-ACK, ACK).  
- Garante entrega confiável, ordenada, controle de fluxo (janela deslizante) e de congestionamento (slow-start, avoidance).  
- Cabeçalho típico de 20 bytes (sem opções): porta origem, porta destino, número de sequência e confirmação, data offset, flags (SYN, ACK, FIN, etc.), janela, checksum, ponteiro de urgência e opções (quando usadas).

### User Datagram Protocol (UDP)

- Sem conexão, sem garantias de entrega ou ordenação; “best effort”.  
- Muito leve: cabeçalho de 8 bytes contendo porta origem, porta destino, comprimento e checksum.  
- Ideal para aplicações que toleram perda ou exigem baixa latência, como DNS, streaming de áudio/vídeo e VoIP.

### Hypertext Transfer Protocol (HTTP)

- Protocolo de aplicação cliente-servidor sobre TCP.  
- Usa métodos (GET, POST, PUT, DELETE, etc.) para solicitar ou enviar recursos.  
- Mensagem HTTP: linha de requisição/resposta, headers (ex.: Host, Content-Type) e corpo opcional.  
- Códigos de status: 1xx (informação), 2xx (sucesso), 3xx (redirecionamento), 4xx (erro do cliente), 5xx (erro do servidor).

---

## Exercícios

1. Defina protocolo de comunicação e explique sua importância em redes de computadores.  
   Resolução: Protocolo é o conjunto de regras que padroniza formatação, significado e sequência de mensagens trocadas; garante interoperabilidade e confiabilidade.

2. Explique a diferença entre modelo de referência OSI e pilha TCP/IP.  
   Resolução: OSI tem sete camadas; TCP/IP tem quatro. TCP/IP é aplicado na prática, OSI é puramente conceitual.

3. Descreva passo a passo o processo de encapsulamento de dados em redes TCP/IP.  
   Resolução:  
   1) Aplicação → segmento/datagrama de transporte  
   2) Transporte → datagrama IP  
   3) Internet → quadro de enlace  
   4) Enlace → sinal no meio físico  
   5) No receptor, desencapsulamento inverso

4. Quais campos do cabeçalho IPv4 garantem o reenvio de datagramas fragmentados corretamente?  
   Resolução: Identificação, flags de fragmento e offset indicam fragmentos de um mesmo datagrama.

5. Explique o papel do campo TTL no cabeçalho IP.  
   Resolução: TTL (Time to Live) limita saltos permitidos; decrementa a cada roteador; evita loops indefinidos.

6. Compare as funcionalidades de TCP e UDP em termos de confiabilidade e overhead.  
   Resolução: TCP garante confiabilidade, ordenação, controle de fluxo e congestionamento, mas adiciona overhead; UDP é leve, sem garantias.

7. Descreva o handshake de três vias do TCP e a finalidade de cada etapa.  
   Resolução:  
   1) Cliente envia SYN para iniciar conexão.  
   2) Servidor responde SYN+ACK para confirmar.  
   3) Cliente envia ACK final, estabelecendo sessão.

8. Quando é mais adequado usar UDP em vez de TCP? Dê dois exemplos.  
   Resolução: Em aplicações de baixa latência ou tolerantes a perda, como DNS e streaming de vídeo ao vivo.

9. Identifique os componentes principais de uma mensagem HTTP e explique a função de cada um.  
   Resolução:  
   - Linha de requisição/resposta: método ou código  
   - Headers: metadados (Host, Content-Type)  
   - Corpo: payload da requisição ou resposta

10. Descreva como funciona o controle de fluxo no TCP.  
    Resolução: Usa campo de janela no cabeçalho para indicar quantidade máxima de dados não confirmados que podem ser enviados.

11. Explique por que o IPv4 é considerado um protocolo “best effort”.  
    Resolução: Não faz retransmissão automática; entrega ou descarta datagramas sem garantia de integridade.

12. Cite três métodos HTTP e suas aplicações típicas.  
    Resolução: GET para leitura de recurso; POST para envio de dados; DELETE para remoção de recurso.

13. Como roteadores utilizam o protocolo IP para filtrar pacotes?  
    Resolução: Inspeção de campos de endereço origem/destino, protocolo e portas auxiliares para aplicar políticas de firewall.

14. Em que parte do modelo TCP/IP ocorre o controle de congestionamento?  
    Resolução: Na camada de Transporte, especialmente em TCP.

15. Explique o que é MTU e como ele influencia a fragmentação no IP.  
    Resolução: MTU (Maximum Transmission Unit) é o tamanho máximo de quadro no enlace; datagramas maiores são fragmentados.

16. Descreva o formato mínimo do cabeçalho UDP.  
    Resolução: 8 bytes: porta origem (2 B), porta destino (2 B), comprimento (2 B), checksum (2 B).

17. Qual é o campo usado para identificar a aplicação de destino em TCP e UDP?  
    Resolução: O número da porta de destino.

18. Explique o conceito de janela deslizante no TCP.  
    Resolução: Mecanismo que ajusta dinamicamente quantidade de bytes não confirmados em trânsito.

19. Dê um exemplo de status code HTTP da família 4xx e explique seu significado.  
    Resolução: 404 Not Found indica que o recurso requisitado não existe no servidor.

20. Quais mecanismos garantem a integridade dos dados em IP, TCP e UDP?  
    Resolução: IP e UDP usam checksum; TCP usa checksum em cabeçalho e dados.

21. Por que não há handshake no UDP?  
    Resolução: UDP é sem estado e sem conexão, injetando datagramas diretamente na rede.

22. Explique a diferença entre um datagrama IP e um segmento TCP.  
    Resolução: Datagrama IP é unidade de camada de Internet; segmento TCP é unidade de camada de Transporte.

23. Como o protocolo HTTP se relaciona com TCP?  
    Resolução: HTTP usa conexões TCP para transportar requisições e respostas confiáveis.

24. Descreva um cenário em que um datagrama IP chega corrompido e como isso é detectado.  
    Resolução: Checksum de cabeçalho detecta erro; datagrama descartado e retransmissão fica a cargo de TCP.

25. Quais são as vantagens do uso de cabeçalhos menores no UDP?  
    Resolução: Menor overhead, menor latência em transmissões.

26. Explique o papel do campo “Protocolo” no cabeçalho IPv4.  
    Resolução: Indica qual protocolo de camada superior (TCP=6, UDP=17) processará o payload.

27. Como o HTTP/1.1 diferencia múltiplas requisições em uma mesma conexão TCP?  
    Resolução: Cabeçalhos como Host e Connection mantêm sessão; pipelining permite múltiplas requisições antes do fechamento.

28. O que ocorre quando o campo “Checksum” do UDP indica erro?  
    Resolução: Pacote é descartado; não há retransmissão automática.

29. Descreva o processo de retransmissão no TCP após perda de ACK.  
    Resolução: Timeout baseado em estimativa de RTT dispara retransmissão do segmento perdido.

30. Em que situação um servidor web pode responder com status 301?  
    Resolução: Quando um recurso foi movido permanentemente para outra URI; redirecionamento.

---

## Bibliografia

- [Estrella, J. C. _Infraestrutura para Sistemas de Software – Principais Protocolos de Comunicação_. Vídeo-aula UNIVESP, 17 jun. 2025. Acesso em 05 ago. 2025.](https://www.youtube.com/watch?v=dpqu5RP4C-Q&ab_channel=UNIVESP)  
- RFC 791. “Internet Protocol”. IETF, 1981. Disponível em: https://tools.ietf.org/html/rfc791. Acesso em 05 ago. 2025.  
- RFC 793. “Transmission Control Protocol”. IETF, 1981. Disponível em: https://tools.ietf.org/html/rfc793. Acesso em 05 ago. 2025.  
- RFC 768. “User Datagram Protocol”. IETF, 1980. Disponível em: https://tools.ietf.org/html/rfc768. Acesso em 05 ago. 2025.  
- RFC 7231. “Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content”. IETF, 2014. Disponível em: https://tools.ietf.org/html/rfc7231. Acesso em 05 ago. 2025.  
- KUROSE, J. F.; ROSS, K. W. _Computer Networking: A Top-Down Approach_. 7th ed. Pearson, 2017.  

---

Além desses protocolos, vale explorar na sequência protocolos de segurança (TLS), novas versões de HTTP (HTTP/2, HTTP/3) e protocolos de transporte emergentes como QUIC, que trazem redução de latência e multiplexação otimizada para aplicações modernas.