# Endereçamento IP

## Objetivos e importância

Nesta aula, exploramos o endereçamento IPv4, detalhando como 32 bits são divididos em octetos para formar endereços de rede, sub-rede e host, além de entender campos essenciais do cabeçalho IP como TTL, fragmentação, protocolo e checksum. Compreender esses conceitos é crucial para projetar e administrar redes eficientes, segmentar corretamente domínios de broadcast e garantir o roteamento adequado em infraestruturas de software distribuído.

---

## Fundamentos do cabeçalho IPv4

O cabeçalho IPv4 possui campos que controlam o transporte de datagramas entre hosts e roteadores. Veja abaixo os principais:

| Campo             | Tamanho (bits) | Função                                                                             |
|-------------------|----------------|------------------------------------------------------------------------------------|
| Versão            | 4              | Indica a versão do IP (IPv4 = 4)                                                   |
| IHL               | 4              | Comprimento do cabeçalho em palavras de 32 bits                                    |
| Tipo de Serviço   | 8              | Prioridade ou tratamento de tráfego em roteadores                                 |
| Comprimento Total | 16             | Tamanho total do datagrama (cabeçalho + dados)                                    |
| Identificação     | 16             | Número único para reagrupamento de fragmentos                                     |
| Flags             | 3              | Controle de fragmentação (DF, MF)                                                  |
| Offset de Fragmento | 13           | Deslocamento de fragmentação para remontagem                                       |
| TTL               | 8              | Limita o número de saltos; decrementado a cada roteador e descarta ao chegar a 0  |
| Protocolo         | 8              | Identifica o protocolo de camada superior (TCP = 6, UDP = 17, etc.)               |
| Checksum do Cabeçalho | 16         | Verifica integridade do cabeçalho em cada salto                                   |
| Endereço de Origem  | 32           | Identifica o host emissor                                                         |
| Endereço de Destino | 32           | Identifica o host destinatário                                                    |

Cada roteador recalcula o checksum do cabeçalho após alterar o TTL e encaminha ou descarta o datagrama conforme regras de fragmentação e roteamento.

---

## Endereçamento classful e classless

Originalmente o IPv4 adotou classes fixas de redes para otimizar divisão de endereços:

- Classe A (1.0.0.0–127.255.255.255): 8 bits para rede, 24 bits para hosts  
- Classe B (128.0.0.0–191.255.255.255): 16 bits para rede, 16 bits para hosts  
- Classe C (192.0.0.0–223.255.255.255): 24 bits para rede, 8 bits para hosts  
- Classe D (224.0.0.0–239.255.255.255): multicast  
- Classe E (240.0.0.0–255.255.255.255): experimental

Essa divisão rígida levou à escassez de endereços IPv4 e à subutilização de blocos. O Classless Inter-Domain Routing (CIDR) permite máscaras variáveis (“/n”), ajustando dinamicamente quantos bits são usados para rede e hosts, melhorando a eficiência do espaço de endereçamento e habilitando mais sub-redes conforme demanda.

---

## Máscara de rede e operações lógicas

A máscara de rede determina quais bits do endereço IP representam a parte de rede/sub-rede e quais representam o host. As duas operações fundamentais são:

- AND (rede): IP_host AND máscara → endereço de rede  
- OR (broadcast): IP_host OR máscara_invertida → endereço de broadcast  

Por exemplo, com IP 192.168.1.75/28 (máscara 255.255.255.240):

- Rede: 192.168.1.75 AND 255.255.255.240 = 192.168.1.64  
- Broadcast: 192.168.1.75 OR 0.0.0.15 = 192.168.1.79  

Hosts válidos ficam entre .65 e .78, totalizando 14 endereços atribuíveis (2^4 – 2).

---

## Atribuição de endereços e DHCP

Em redes gerenciadas, o DHCP (Dynamic Host Configuration Protocol) automatiza a distribuição de endereços IP, máscara, gateway e DNS. O cliente DHCP envia uma mensagem de descoberta (DHCPDISCOVER) em broadcast, recebe oferta (DHCPOFFER), solicita confirmação (DHCPREQUEST) e obtém confirmação final (DHCPACK) com parâmetros de configuração da sub-rede.

---

## Análise crítica

O uso exclusivo de endereçamento classful, abordado no vídeo, é hoje considerado obsoleto. O CIDR tornou-se padrão desde o RFC 1519, oferecendo flexibilidade e evitando desperdício de blocos IPv4. Além disso, a aula não detalha mecanismos de descoberta de MTU de caminho (PMTUD), que é fundamental para minimizar fragmentação em redes heterogêneas.

---

## Exercícios

1. Descreva a função do campo TTL no cabeçalho IPv4.  
   Resolução: TTL é decrementado a cada roteador; ao chegar a zero, o datagrama é descartado, prevenindo loops de roteamento.  

2. Explique o papel das flags DF e MF na fragmentação.  
   Resolução: DF (Don’t Fragment) bloqueia fragmentação; MF (More Fragments) indica que há mais fragmentos a serem recebidos.  

3. Liste os campos obrigatórios de um cabeçalho IPv4 e seu tamanho total mínimo.  
   Resolução: Versão (4b), IHL (4b), TOS (8b), Total Length (16b), Identification (16b), Flags (3b), Fragment Offset (13b), TTL (8b), Protocolo (8b), Header Checksum (16b), Endereço Origem (32b), Endereço Destino (32b). Total mínimo = 160 bits (20 bytes).  

4. Calcule o endereço de rede e broadcast para IP 10.10.5.123/16.  
   Resolução: Máscara = 255.255.0.0.  
     Rede = 10.10.5.123 AND 255.255.0.0 = 10.10.0.0  
     Broadcast = 10.10.5.123 OR 0.0.255.255 = 10.10.255.255  

5. Quantos hosts válidos existem em uma sub-rede /26?  
   Resolução: 32 – 26 = 6 bits para hosts → 2^6 – 2 = 62 hosts.  

6. Você precisa de pelo menos 500 endereços IP para hosts. Qual prefixo CIDR atende e quantos endereços ele fornece?  
   Resolução: 2^9 = 512 ≥ 500 → prefixo /23 (32 – 9). Hosts válidos = 512 – 2 = 510.  

7. Como o checksum do cabeçalho é recalculado durante o roteamento?  
   Resolução: Ao alterar o TTL, o roteador subtrai o valor anterior do checksum e adiciona o novo TTL, readequando o campo sem recalcular tudo.  

8. Explique a operação AND entre IP e máscara.  
   Resolução: Realiza AND bit a bit; apenas os bits correspondentes a “1” na máscara mantêm seu valor, isolando a parte de rede.  

9. Para o IP 172.16.33.45 e máscara 255.255.248.0, determine rede e broadcast.  
   Resolução: /21  
     Rede = 172.16.32.0  
     Broadcast = 172.16.39.255  

10. Quais são as faixas de endereços privados em IPv4?  
    Resolução:  
      - 10.0.0.0/8  
      - 172.16.0.0/12  
      - 192.168.0.0/16  

11. Explique como o DHCP atribui dinamicamente um endereço IP.  
    Resolução: Cliente envia DHCPDISCOVER → servidor responde DHCPOFFER → cliente envia DHCPREQUEST → servidor confirma com DHCPACK.  

12. Por que o classful addressing levou à rápida exaustão de IPv4?  
    Resolução: Tamanhos fixos desperdiçavam blocos grandes em redes pequenas, criando escassez de endereços.  

13. O que indica o campo “Protocolo” quando contém o valor 6?  
    Resolução: Transporta um segmento TCP.  

14. Defina o CIDR e sua vantagem sobre classes fixas.  
    Resolução: CIDR permite máscaras variáveis, alocando exatamente o número de endereços necessários e reduzindo desperdício.  

15. Calcule quantas sub-redes /28 existem dentro de um bloco /24.  
    Resolução: /24 → 24, /28 → 28 → 4 bits de diferença → 2^4 = 16 sub-redes.  

16. Explique o uso do campo “Identification” na remontagem de fragmentos.  
    Resolução: Todos os fragmentos de um mesmo datagrama carregam o mesmo ID para que o receptor os agrupe corretamente.  

17. Para /30, quantos hosts válidos e para que é comumente usado?  
    Resolução: 32 – 30 = 2 bits → 2^2 – 2 = 2 hosts. Usado em links ponto-a-ponto.  

18. Como um roteador determina a próxima etapa baseado no endereço de destino?  
    Resolução: Faz lookup de prefixo mais longo na tabela de roteamento usando o endereço de rede extraído (IP AND máscara).  

19. Descreva a diferença entre endereço de rede e broadcast.  
    Resolução: Endereço de rede identifica a sub-rede inteira; broadcast atinge todos os hosts dentro dessa sub-rede.  

20. Por que o TTL previne loops de roteamento?  
    Resolução: Garante descarte automático de pacotes que circulam indefinidamente, pois o TTL chega a zero.  

21. Converta a máscara 255.255.240.0 para formato CIDR.  
    Resolução: 16 + 4 = 20 → /20.  

22. Dado um bloco /22, quantas sub-redes /24 podem ser criadas?  
    Resolução: Diferença de 2 bits → 2^2 = 4 sub-redes /24.  

23. Qual é a consequência de descartar datagramas com checksum incorreto?  
    Resolução: Evita entrega de dados corrompidos; a retransmissão fica a cargo de protocolos de camada superior (TCP).  

24. Explique por que a aula aborda apenas IPv4. O que mudou com o IPv6?  
    Resolução: IPv6 usa endereços de 128 bits e elimina fragmentação em roteadores, migrando para PMTUD e autoconfiguração sem classes.  

25. Calcule host, rede e broadcast para 192.0.2.130/25.  
    Resolução: /25 → máscara 255.255.255.128  
      Rede = 192.0.2.128  
      Broadcast = 192.0.2.255  
      Hosts válidos = .129 a .254 (126 endereços).  

26. Quando um datagrama precisa ser fragmentado?  
    Resolução: Quando tamanho do datagrama > MTU do enlace atual e DF = 0.  

27. Descreva a utilidade do campo “Type of Service”.  
    Resolução: Permite roteadores priorizar tráfego (por exemplo, tráfego em tempo real).  

28. Explique o conceito de máscara universal (wildcard mask).  
    Resolução: Bits “0” indicando parte de rede e “1” indicando parte de host; usada em ACLs de roteadores Cisco.  

29. Por que o campo IHL é necessário?  
    Resolução: Indica onde começam os dados, pois opções podem variar o tamanho do cabeçalho.  

30. Como você determinaria o tamanho máximo de dados em um datagrama antes da fragmentação?  
    Resolução: MTU do enlace menos tamanho do cabeçalho IP (IHL × 4 bytes).  

---

## Bibliografia

- [UNIVESP. Infraestrutura para Sistemas de Software – Endereçamento IP (vídeo-aula). YouTube, 17 jun. 2025. Acesso em 05 ago. 2025.](https://www.youtube.com/watch?v=pCcGeBBJcig&ab_channel=UNIVESP)  
- WIKIVERSITY. Introdução às Redes de Computadores/Definições das Redes de Computadores. Disponível em: https://pt.wikiversity.org/wiki/Introdu%C3%A7%C3%A3o_%C3%A0s_Redes_de_Computadores/Defini%C3%B5es_das_Redes_de_Computadores. Acesso em 05 ago. 2025.  
- RFC 791. Internet Protocol. IETF, 1981. Disponível em: https://tools.ietf.org/html/rfc791. Acesso em 05 ago. 2025.  
- RFC 2131. Dynamic Host Configuration Protocol. IETF, 1997. Disponível em: https://tools.ietf.org/html/rfc2131. Acesso em 05 ago. 2025.  
- KUROSE, J. F.; ROSS, K. W. _Computer Networking: A Top-Down Approach_. 7ª ed. Pearson, 2017.