# Introdução às Redes de Computadores

## Objetivos e importância

A rede de computadores surgiu para permitir que elementos computacionais troquem dados e compartilhem recursos, como áudio, vídeo e aplicações hospedadas em hosts remotos.  

No contexto de infraestrutura para sistemas de software, compreender redes é fundamental para projetar, implementar e manter aplicações distribuídas na nuvem, Internet das Coisas e demais soluções que dependem de comunicação confiável entre clientes, servidores e dispositivos inteligentes.

---

## Definições e conceitos principais

As redes de computadores são formadas por:

- Usuários e aplicações  
- Elementos de comutação: roteadores e switches  
- Servidores (web, proxy, de aplicação etc.)  
- Meio físico (cabeado ou sem fio)  
- Dispositivos finais: desktops, notebooks, tablets e celulares  

Cada um desses componentes processa, encaminha ou gera dados em pacotes (datagramas) que trafegam por links de comunicação. Protocolos padronizados definem como esses pacotes são formatados, endereçados, transmitidos e reenviados em caso de perda.

---

## Arquitetura em camadas

Para lidar com a complexidade da comunicação, adota-se um modelo em camadas. Cada camada oferece serviços para a camada acima e utiliza serviços da camada abaixo.

| Camada OSI (7)           | Camadas didáticas TCP/IP (5)   | Camadas práticas TCP/IP (4)    |
|--------------------------|--------------------------------|---------------------------------|
| 7. Aplicação             | 5. Aplicação                   | Aplicação                       |
| 6. Apresentação          | 4. Transporte                  | Transporte                      |
| 5. Sessão                | 3. Internet                    | Internet                        |
| 4. Transporte            | 2. Acesso à rede (Enlace)      | Acesso à rede                   |
| 3. Rede                  | 1. Física                      |                                 |
| 2. Enlace                |                                |                                 |
| 1. Física                |                                |                                 |

### Encapsulamento e desencapsulamento

Para exemplificar:

1. O emissor coloca a informação (palito de fósforo) dentro de uma série de “caixas” (protocol headers).  
2. Cada camada adiciona seu cabeçalho, formando segmentos, datagramas e quadros.  
3. O meio físico transporta o sinal resultante.  
4. No receptor, o processo é invertido: cada camada retira seu cabeçalho até recuperar a informação original.

---

## Camadas do modelo TCP/IP

### Camada de Aplicação

Responsável pela interface com software de usuário e formatação das mensagens. Exemplos:

- HTTP em comércio eletrônico  
- SMTP/IMAP para e-mail  
- DNS para resolução de nomes  

### Camada de Transporte

Fornece comunicação lógica fim a fim entre aplicações em hosts distintos. Os principais protocolos são:

- UDP (User Datagram Protocol)  
  - Sem conexão; não garante entrega nem ordem  
  - Cabeçalho simples (porta origem, porta destino, comprimento, checksum)  
  - Uso em DNS, streaming de áudio/vídeo e VoIP  

- TCP (Transmission Control Protocol)  
  - Orientado a conexão; garante confiabilidade, controle de fluxo e congestionamento  
  - Estabelece handshake em três vias  
  - Cabeçalho mais complexo (seqüência, ACK, janela, flags)  
  - Uso em HTTP, FTP, e-mail e transferência de arquivos  

### Camada Internet (Rede)

Responsável pelo endereçamento lógico e roteamento de pacotes. O protocolo mais comum é o IPv4 (e, em expansão, o IPv6).

### Camada de Acesso à Rede (Enlace e Física)

Cuida da codificação de bits, transmissão binária e acesso ao meio físico:

- Tipos de meio: par trançado, fibra óptica, cabo coaxial ou rádio  
- Codificação, detecção de erro e controle de acesso  

---

## A Internet e a Web

A Internet é a interconexão de milhões de redes regionais, corporativas e domésticas, composta por roteadores, enlaces cabeados e sem fio, provedores de serviços e hosts finais. Em cima dessa infraestrutura, a WWW (World Wide Web) surge como uma aplicação distribuída de documentos interligados por hipermídia, acessados via HTTP.

---

## Exercícios

1. **Defina rede de computadores e explique seus dois principais objetivos.**  
   Resolução:  
   - Troca de dados entre elementos computacionais.  
   - Compartilhamento de recursos (aplicações, áudio, vídeo).  

2. **Liste cinco componentes que formam uma rede de computadores.**  
   Resolução:  
   1. Roteador  
   2. Switch  
   3. Servidor web  
   4. Placa de rede (NIC)  
   5. Meio físico (cabo ou rádio)  

3. **Compare roteador e switch, indicando em qual camada cada um opera.**  
   Resolução:  
   - Switch: camada de enlace; encaminha quadros com base em endereços MAC.  
   - Roteador: camada de rede; encaminha pacotes usando endereços IP.  

4. **Explique o conceito de encapsulamento em redes.**  
   Resolução:  
   - Processo de adicionar cabeçalhos em cada camada do emissor e retirar no receptor.  

5. **Represente em cinco passos a sequência de encapsulamento no modelo didático de 5 camadas.**  
   Resolução:  
   1. Aplicação gera dados  
   2. Transporte encapsula em segmento  
   3. Internet encapsula em datagrama  
   4. Enlace encapsula em quadro  
   5. Física transforma em bits e envia  

6. **Descreva como funciona o handshake de três vias do TCP.**  
   Resolução:  
   1. SYN do cliente ao servidor.  
   2. SYN+ACK do servidor ao cliente.  
   3. ACK final do cliente ao servidor.  

7. **Cite dois casos de uso típicos para o UDP.**  
   Resolução:  
   - Transmissão de vídeo ao vivo.  
   - Consultas DNS.  

8. **Por que o modelo OSI não foi adotado na prática?**  
   Resolução:  
   - Modelo de referência; era complexo e fragmentado em sete camadas independentes.  

9. **Quais camadas do OSI foram unificadas no TCP/IP?**  
   Resolução:  
   - Aplicação, Apresentação e Sessão → Camada de Aplicação  
   - Enlace e Física → Camada de Acesso à Rede  

10. **Explique o papel do endereço lógico na camada de Internet.**  
    Resolução:  
    - Identificação única de host para roteamento de pacotes.  

11. **Descreva três formas de meio físico e suas características de transmissão.**  
    Resolução:  
    1. Par trançado: cobre, suscetível a EMI, até 1 Gbps.  
    2. Fibra óptica: alta largura de banda, imune a ruído.  
    3. Rádio: sem fio, variável conforme frequência e ambiente.  

12. **O que é largura de banda e como ela se relaciona ao meio de comunicação?**  
    Resolução:  
    - Capacidade máxima de transmissão de dados em bps; depende da tecnologia do meio.  

13. **Defina o que é a WWW e diferencie-a da Internet.**  
    Resolução:  
    - WWW: aplicação distribuída de documentos interligados.  
    - Internet: rede de redes que oferece infraestrutura.  

14. **Descreva um exemplo de como um sensor IoT utiliza redes de computadores.**  
    Resolução:  
    - Sensor envia datagramas UDP para servidor na nuvem, sem garantia de entrega, ideal para leituras periódicas.  

15. **Explique o que acontece quando um quadro se perde na rede.**  
    Resolução:  
    - Protocolo de transporte TCP reenvia segmento após timeout; UDP ignora.  

16. **Por que a comunicação sem fio pode exigir antenas e placas específicas?**  
    Resolução:  
    - Necessidade de captar/transmitir sinais de rádio e converter em dados.  

17. **Como o controle de congestionamento do TCP protege a rede?**  
    Resolução:  
    - Ajusta dinamicamente a janela de transmissão conforme feedback de ACKs e detecção de perdas.  

18. **Explique o processo inverso de desencapsulamento no receptor.**  
    Resolução:  
    - Cada camada remove seu cabeçalho e processa informação, até recuperar dados da aplicação.  

19. **Cite cinco protocolos de camada de aplicação e suas funções.**  
    Resolução:  
    1. HTTP – transferência de hipertextos.  
    2. FTP – transferência de arquivos.  
    3. SMTP – envio de e-mail.  
    4. DNS – resolução de nomes.  
    5. DHCP – atribuição dinâmica de endereços IP.  

20. **Descreva a diferença entre comunicação lógica e física fim a fim.**  
    Resolução:  
    - Lógica: conexão estabelecida em camada de transporte;  
    - Física: percurso real dos sinais.  

21. **O que garante a entrega ordenada de pacotes no TCP?**  
    Resolução:  
    - Numeração de sequência e ACKs cumulativos.  

22. **Identifique dois fabricantes distintos de equipamentos de rede e por que a padronização é importante.**  
    Resolução:  
    - Cisco, Juniper; padronização em protocolos permite interoperabilidade.  

23. **Explique o que é um datagrama e como ele difere de um segmento.**  
    Resolução:  
    - Datagrama: unidade de IP (camada de rede);  
    - Segmento: unidade de TCP/UDP (camada de transporte).  

24. **Quais são as vantagens e desvantagens do modelo em camadas?**  
    Resolução:  
    - Vantagens: modularidade, padronização;  
    - Desvantagens: overhead de cabeçalhos, possível complexidade.  

25. **Descreva como um switch aprende endereços MAC.**  
    Resolução:  
    - Analisa origem dos quadros e atualiza tabela de endereçamento.  

26. **Por que o TCP/IP é o modelo predominante na Internet?**  
    Resolução:  
    - Simplicidade, robustez, ampla adoção histórica e padronização IETF.  

27. **O que difere IPv4 de IPv6?**  
    Resolução:  
    - IPv6: cabeçalho simplificado, espaço de endereçamento de 128 bits vs 32 bits do IPv4.  

28. **Explique quando usar UDP em vez de TCP.**  
    Resolução:  
    - Cenários que toleram perda: streaming em tempo real, gaming online.  

29. **Como a camada de aplicação sabe que porta usar?**  
    Resolução:  
    - Através de convenções e registros oficiais (IANA) ou configuração de serviço.  

30. **Descreva um cenário onde múltiplos roteadores formam a Internet.**  
    Resolução:  
    1. Provedor A conecta região Norte.  
    2. Provedor B conecta região Sul.  
    3. Roteadores trocam rotas via BGP.  
    4. Hosts em redes distintas comunicam-se através desses roteadores.  

---

## Bibliografia

- [UNIVESP. Infraestrutura para Sistemas de Software – Introdução às Redes de Computadores. Vídeo-aula. Acesso em 05 ago. 2025.](https://www.youtube.com/watch?v=Sea42wIzMOY&ab_channel=UNIVESP)  
- KUROSE, J. F.; ROSS, K. W. _Computer Networking: A Top-Down Approach_. 7th ed. Pearson, 2017.  
- WIKIVERSITY. Introdução às Redes de Computadores/Definições das Redes de Computadores. Disponível em: https://pt.wikiversity.org/wiki/Introdu%C3%A7%C3%A3o_%C3%A0s_Redes_de_Computadores/Defini%C3%A7%C3%B5es_das_Redes_de_Computadores. Acesso em 05 ago. 2025.  
- RFC 768. User Datagram Protocol. IETF, 1980. Acesso em 05 ago. 2025.  
- RFC 793. Transmission Control Protocol. IETF, 1981. Acesso em 05 ago. 2025.