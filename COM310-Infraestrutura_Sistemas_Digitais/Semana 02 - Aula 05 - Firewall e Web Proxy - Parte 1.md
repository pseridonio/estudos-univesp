# Firewalls e Web Proxies – Parte 1

## Objetivos

Nesta aula você vai aprender o que são firewalls e web proxies, por que são críticos numa infraestrutura de software e como eles se complementam para controlar, registrar e proteger o tráfego de dados.

Você conhecerá as principais funções de um firewall de filtro de pacotes, as características de um servidor proxy de aplicação e as estratégias de políticas de negação e permissão.

Ao fim, entenderá limitações, casos de uso e diferenças de desempenho e granularidade entre filtros de pacotes e proxies.

---

## Definição de Firewall

Firewall é um componente de segurança que regula o tráfego entre redes distintas, funcionando como uma “parede corta-fogo” que permite ou bloqueia datagramas IP baseado em regras.

Ele fica na fronteira entre Internet e rede interna, inspecionando cabeçalhos de pacotes (endereço de origem, destino, porta e protocolo) para assegurar que apenas tráfego autorizado passe adiante.

Em geral, adota política de negação implícita: tudo é bloqueado por padrão e somente o estritamente necessário é liberado.

---

## Principais funções do Firewall

- Filtrar pacotes ou datagramas IP conforme regras de origem, destino, protocolo e porta.  
- Fazer tradução de endereços de rede (NAT), ocultando sub-redes internas e compartilhando um IP público.  
- Manter estado de conexões (stateful inspection), permitindo pacotes de retorno em TCP/UDP automaticamente.  
- Registrar logs de todo tráfego permitido ou negado, auxiliando auditoria e análise de incidentes.  

---

## Tipos de Firewall

### Filtro de Pacotes (Packet Filter)

Opera na camada de rede, inspecionando apenas cabeçalhos de datagramas IP.  
É transparente ao usuário, de baixo custo de processamento, mas não analisa conteúdo de aplicação.

### Proxy de Aplicação (Application Proxy)

Age como intermediário entre cliente e servidor, inspecionando conteúdo da aplicação (HTTP, FTP etc.), fazendo cache e autenticação.  
Fornece logs detalhados e controle por URL ou tipo de conteúdo, porém tem maior latência.

#### Comparativo Packet Filter × Application Proxy

| Característica         | Packet Filter                       | Application Proxy            |
|------------------------|-------------------------------------|------------------------------|
| Camada                 | Rede (IP)                           | Aplicação (HTTP, FTP etc.)   |
| Análise                | Cabeçalho de pacote                 | Conteúdo da transação        |
| Transparência          | Total ao cliente                    | Cliente configurado ou transparente |
| Desempenho             | Alto                                | Médio a baixo                |
| Granularidade de logs  | Baixa (IP, porta, protocolo)        | Alta (URL, usuário, conteúdo)|

---

## Políticas de Controle

1. Negar tudo e permitir apenas o necessário  
2. Permitir tudo e bloquear exceções – raramente adotada sozinha  
3. Misturar negação implícita com exceções explícitas para serviços críticos  

Em organizações maduras, o firewall faz parte da política de segurança global, integrando-se a sistemas de detecção de intrusão (IDS) e segmentação de redes (DMZ).

---

## Web Proxy

Web proxy é um servidor que recebe requisições HTTP/HTTPS em nome dos clientes, cacheia conteúdo e aplica regras de filtragem por URL, tipo de arquivo ou autenticação.

Permite reduzir largura de banda consumida, melhorar performance de acesso repetitivo e manter auditoria detalhada.

Tipos comuns de proxy:

- Proxy direto: browser configurado aponta para o proxy  
- Proxy transparente: interceptação automática, sem configuração no cliente  
- Proxy reverso: protege servidores, filtrando requisições externas  

---

## Integração Firewall × Proxy

Firewall de pacote bloqueia tráfego indesejado em nível IP e porta, mas não entende conteúdo.  
Proxy de aplicação analisa dados embarcados em protocolos web e pode autenticar usuários via LDAP ou OpenLDAP.

Em conjunto, fornecem defesa em profundidade: o pacote filtrado elimina tráfego bruto, o proxy filtra a camada de aplicação.

---

## Cuidados e Limitações

- Firewall não remove malware contido em conteúdo permitido; antivírus e análise de conteúdo são complementares.  
- Proxy não cobre protocolos não web; filtragem de UDP, SSH e outros depende do firewall de pacotes ou proxies específicos.  
- IP spoofing e fragmentação de pacotes podem burlar filtros simples; stateful inspection e IDS ajudam a mitigar.  
- Ambos introduzem latência adicional ao tráfego; dimensionamento e hardware dedicado podem aliviar gargalos.  

---

## Exercícios

1. Explique a função de um firewall em uma rede corporativa.  
   Resolução: Firewall regula tráfego entre redes, inspecionando cabeçalhos de pacotes e decidindo entrada/saída conforme regras.

2. Qual a diferença essencial entre filtro de pacotes e proxy de aplicação?  
   Resolução: Filtro age na camada de rede (IP e portas), proxy age na camada de aplicação (HTTP, cache, autenticação).

3. Descreva o que é política de negação implícita.  
   Resolução: Padrão de segurança que bloqueia todo tráfego não explicitamente permitido.

4. Como o firewall stateful melhora a filtragem de pacotes?  
   Resolução: Mantém tabela de conexões, permitindo pacotes de retorno de sessões válidas sem regras adicionais.

5. Dê um exemplo de regra de NAT em um firewall.  
   Resolução: Traduz IP interno 192.168.0.10 para IP público 200.100.50.5 em saída, permitindo acesso externo.

6. Por que é recomendável usar proxy reverso em datacenters?  
   Resolução: Protege servidores web internos, faz cache e equilibra carga sem expor IP reais.

7. Como um proxy transparente difere de um proxy direto?  
   Resolução: Transparente intercepta tráfego sem configuração no cliente, direto exige apontar o browser ao proxy.

8. Quais logs você analisaria para investigar um acesso HTTP suspeito?  
   Resolução: Logs do proxy (URL, usuário, horário) e logs do firewall (IP origem, porta destino, ação).

9. Explique como firewall e IDS se complementam.  
   Resolução: Firewall bloqueia tráfego indesejado, IDS detecta tentativas de ataque e alerta administradores.

10. O que é IP spoofing e como mitigá-lo?  
    Resolução: Falsificação de IP de origem; mitigado por filtros de saída, stateful inspection e listas brancas.

11. Cite três protocolos que não são filtrados por proxy web genérico.  
    Resolução: SSH, DNS, SNMP.

12. Como o proxy contribui para economia de banda?  
    Resolução: Cacheia conteúdo popular, atendendo novas requisições sem buscar novamente na Internet.

13. Defina DMZ e seu relacionamento com firewall.  
    Resolução: Zona semidmilitarizada onde servidores públicos ficam isolados entre dois firewalls.

14. Um filtro de pacotes pode bloquear ping (ICMP)? Como?  
    Resolução: Criando regra para descartar datagramas ICMP echo-request e echo-reply.

15. Explique desvantagens de usar apenas proxy de aplicação como única defesa.  
    Resolução: Não cobre protocolos não suportados, pode introduzir maior latência e complexidade de configuração.

16. Como autenticação LDAP pode ser integrada ao proxy?  
    Resolução: Proxy solicita credenciais que são validadas em servidor OpenLDAP antes de liberar acesso.

17. Quais métricas de desempenho avaliar antes de dimensionar um firewall?  
    Resolução: Throughput máximo, conexões simultâneas, latência de inspeção e uso de CPU/memória.

18. Descreva um cenário de uso de proxy reverso para balanceamento de carga.  
    Resolução: Proxy recebe requisições externas e distribui para múltiplos servidores web internos conforme algoritmo round-robin.

19. O que acontece se uma regra de firewall for aplicada após tráfego já filtrado por proxy?  
    Resolução: Firewall não afetará tráfego já estabelecido pelo proxy, pois a sessão já existe.

20. Explique porque o filtro de pacotes não enxerga o conteúdo de downloads HTTPS.  
    Resolução: HTTPS é criptografado na aplicação, camada de rede só vê pacotes SSL/TLS, não conteúdo.

21. Dê um exemplo de política que bloqueie vídeo em HTTP mas permita textos.  
    Resolução: Proxy inspeciona URL ou Content-Type e nega arquivos com extensão .mp4 ou Content-Type video/*.

22. Por que vale a pena filtrar MAC address em firewall?  
    Resolução: Bloqueia dispositivos não autorizados, mesmo que mudem IP dinâmico em redes Wi-Fi.

23. Como fragmentação de pacotes pode burlar filtros simples?  
    Resolução: Dividir cabeçalho crítico em múltiplos fragmentos faz o filtro não reconhecer padrões.

24. Explique o trade-off entre granularidade de logs e desempenho.  
    Resolução: Mais detalhes em logs (proxy) geram maior uso de disco e CPU, potencialmente reduzindo throughput.

25. Como você testaria regras de firewall para porta TCP 22?  
    Resolução: Usar nmap ou telnet de um host externo e verificar resposta ou falta de conexão.

26. Quais estratégias contra DDoS podem ser aplicadas no firewall?  
    Resolução: Limitar taxa de novas conexões, listas negras, quotas por IP e cloud scrubbing.

27. O que é “falso positivo” em filtragem de proxy?  
    Resolução: Quando conteúdo legítimo é indevidamente bloqueado por regras de URL ou palavras-chave.

28. Descreva fluxo de requisição em proxy reverso.  
    Resolução: Cliente → proxy reverso → servidor backend → proxy → cliente, com cache possível.

29. Como manter as regras de firewall alinhadas a mudanças de infraestrutura?  
    Resolução: Documentação viva, revisão periódica, testes em ambiente controlado e uso de automation (Ansible, Terraform).

30. Explique como implementar logs centralizados para firewall e proxy.  
    Resolução: Enviar logs via syslog a servidor de log (Graylog, ELK), padronizar formatos e criar dashboards de análise.  

---

## Bibliografia

- UNIVESP. Infraestrutura para Sistemas de Software – Firewalls e Web Proxies – Parte 1 (LIBRAS). YouTube. Disponível em: https://www.youtube.com/watch?v=GcKC_O9zovc. Acesso em: 17 ago. 2025.

- NEMETH, E.; SNYDER, G.; HEIN, T. R. Manual completo do Linux: guia do administrador. 1. ed. São Paulo: Pearson, 2005. E-book. Disponível em: https://plataforma.bvirtual.com.br. Acesso em: 17 ago. 2025.

- “Introdução às Redes de Computadores/Definições das Redes de Computadores.” Wikiversity. Disponível em: https://pt.wikiversity.org/wiki/Introdu%C3%A7%C3%A3o_%C3%A0s_Redes_de_Computadores/Defini%C3%B5es_das_Redes_de_Computadores. Acesso em: 17 ago. 2025.

- “IPtables Tutorial.” Netfilter. Disponível em: https://www.netfilter.org/documentation/HOWTO//packet-filtering-HOWTO.html. Acesso em: 17 ago. 2025.

- “What Is a Reverse Proxy?” Cloudflare. Disponível em: https://www.cloudflare.com/learning/cdn/glossary/reverse-proxy/. Acesso em: 17 ago. 2025.