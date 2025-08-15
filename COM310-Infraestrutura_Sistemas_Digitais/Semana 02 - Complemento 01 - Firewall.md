# Firewall

## Objetivos

Nesta aula, você será apresentado ao conceito de firewall, suas funções, tipos e localização na rede.  
Será explorado como esse recurso atua como uma barreira de segurança, inspecionando e filtrando pacotes antes de permitir ou negar o acesso.  
Ao final, você compreenderá limitações do firewall e sua relação com outras camadas de proteção.  

---

## O que é firewall

Firewall é um dispositivo ou software que atua como “segurança da boate” ao controlar o fluxo de pacotes entre redes (por exemplo, Internet e rede interna).  
Ele inspeciona informações de origem, destino e conteúdo dos pacotes para decidir se permite ou bloqueia sua passagem.  
No contexto de Segurança da Informação, o firewall impede que tráfego não autorizado penetre em ambientes internos, sem, entretanto, remover ou destruir informações legítimas.  

---

## Funções principais do firewall

- Analisar pacotes de dados com base em endereços IP de origem e destino.  
- Filtrar conteúdo de pacotes para identificar trechos suspeitos ou maliciosos.  
- Bloquear acessos não autorizados de vírus, worms, trojans e ataques como ping of death.  
- Registrar eventos de filtragem para auditoria e análise de incidentes.  
- Definir regras de permissão (allow) e negação (deny) de tráfego.  

---

## Tipos de firewall

### Firewall via software

Firewall via software é um programa instalado em servidores ou estações de trabalho.  
Ele filtra o tráfego que chega àquele host específico, permitindo regras granulares por aplicação, porta e protocolo.  

### Firewall via hardware

Firewall via hardware é um equipamento dedicado, posicionado na borda da rede.  
Conecta-se diretamente aos cabos de rede para inspecionar e filtrar todo o tráfego antes que ele atinja a rede interna.  

#### Comparação entre software e hardware

| Característica          | Firewall via Software             | Firewall via Hardware           |
|-------------------------|-----------------------------------|---------------------------------|
| Local de instalação     | Em cada host                      | Em um ponto estratégico da rede |
| Flexibilidade           | Altamente configurável por host   | Configuração centralizada       |
| Desempenho              | Depende dos recursos do host      | Dedicado, geralmente mais rápido|
| Facilidade de manutenção| Atualizações individuais por host | Atualização única no dispositivo|

---

## Posicionamento na rede

O firewall geralmente é inserido entre o roteador/modem (Internet) e a rede local.  
Dessa forma, todo pacote originário da Internet passa primeiro pelo firewall antes de atingir os computadores internos.  
Esse posicionamento garante que apenas pacotes que atendam às políticas de segurança sejam encaminhados à rede interna.  

---

## Cuidados e limitações

Firewall não exclui vírus ou malwares presentes em pacotes; ele apenas impede que pacotes não autorizados entrem na rede.  
Para remoção de códigos maliciosos, utiliza-se antivírus, antimalware e soluções de detecção específicas.  
Nenhum firewall oferece proteção 100%; é imprescindível combinar políticas de filtros, sistemas de detecção de intrusão e boas práticas de segurança para reduzir riscos ao mínimo.  

---

## Exercícios

1. Pergunta: Explique, com suas palavras, o que faz um firewall na rede.  
   Resolução: Firewall inspeciona pacotes de dados, analisando endereços IP e conteúdo, para permitir ou negar acesso conforme políticas definidas.

2. Pergunta: Cite três tipos de ameaças que um firewall pode ajudar a bloquear.  
   Resolução: Firewall pode bloquear vírus, worms, trojans e ataques de ping of death, impedindo tráfego suspeito de chegar à rede interna.

3. Pergunta: Qual a diferença básica entre firewall via software e via hardware?  
   Resolução: Firewall software roda em cada host individualmente, enquanto o hardware é um dispositivo dedicado que protege toda a rede a partir de um ponto central.

4. Pergunta: Por que o firewall não pode ser considerado uma solução completa de segurança?  
   Resolução: Porque ele restringe apenas tráfego não autorizado; não remove malwares internos nem substitui antivírus, nem detecta ataques já dentro da rede.

5. Pergunta: Em que ponto da infraestrutura de rede o firewall deve ser posicionado idealmente?  
   Resolução: Entre o roteador/modem de acesso à Internet e a rede interna, para filtrar todo o tráfego externo antes que alcance os dispositivos internos.

6. Pergunta: Como firewall e antivírus se complementam?  
   Resolução: Enquanto o firewall bloqueia pacotes não autorizados, o antivírus inspeciona e remove malwares presentes em arquivos e processos dentro dos hosts.

7. Pergunta: Defina regra de “allow” e “deny” em um firewall.  
   Resolução: “Allow” permite que pacotes que atendam a critérios passem; “deny” bloqueia pacotes que não correspondam às políticas de segurança.

8. Pergunta: Descreva o que significa “filtragem de pacotes”.  
   Resolução: Processo de inspecionar e decidir o destino de cada pacote baseado em informações do cabeçalho e, às vezes, do conteúdo.

9. Pergunta: Um firewall pode bloquear tráfego de saída indevido? Explique.  
   Resolução: Sim, com regras específicas de saída, porém muitos firewalls padrão só filtram entrada; é boa prática habilitar filtros de saída para evitar vazamento de dados.

10. Pergunta: Explique por que nenhuma solução de firewall garante 100% de bloqueio de ameaças.  
    Resolução: Porque novas vulnerabilidades e técnicas de evasão surgem constantemente, exigindo camadas adicionais de defesa.

11. Pergunta: Dê um exemplo de política simples de filtragem de pacotes.  
    Resolução: Permitir todo tráfego TCP na porta 80 (HTTP) e bloquear todo tráfego com origem fora da rede 192.168.1.0/24.

12. Pergunta: Quais informações do pacote são mais usadas em um filtro de pacotes?  
    Resolução: Endereços IP de origem e destino, números de porta e protocolo de transporte (TCP/UDP).

13. Pergunta: Como o firewall lida com pacotes fragmentados?  
    Resolução: Pode remontar fragmentos para análise completa ou descartar fragmentos suspeitos sem remontagem, dependendo de sua configuração.

14. Pergunta: Por que é importante registrar logs de bloqueio no firewall?  
    Resolução: Logs ajudam na auditoria, identificando tentativas de invasão e permitindo ajustes finos nas regras de filtragem.

15. Pergunta: O que é um falso positivo em firewall? Dê um exemplo.  
    Resolução: Quando o firewall bloqueia tráfego legítimo por engano, como um site confiável que muda de endereço IP sem aviso.

16. Pergunta: Explique o conceito de estado em firewalls stateful.  
    Resolução: Firewall stateful mantém uma tabela de conexões ativas, permitindo retorno automático de pacotes relacionados a conexões previamente abertas.

17. Pergunta: Diferencie packet filter de Stateful Inspection.  
    Resolução: Packet filter analisa apenas cabeçalhos isoladamente; Stateful Inspection monitora o estado de cada sessão para decisões mais precisas.

18. Pergunta: Em uma política de negação implícita (implicit deny), o que acontece com pacotes não especificados nas regras?  
    Resolução: São automaticamente bloqueados por não terem sido explicitamente permitidos.

19. Pergunta: Quais são as vantagens de usar firewall em nuvem (cloud firewall)?  
    Resolução: Elasticidade, escalabilidade e gestão centralizada de políticas sem necessidade de hardware local.

20. Pergunta: Como você testaria se um firewall está bloqueando corretamente uma porta TCP?  
    Resolução: Utilizando ferramentas como nmap para escanear portas de dentro e fora da rede e observar resultados de permissão ou bloqueio.

21. Pergunta: Descreva como um firewall pode mitigar ataques de DDoS.  
    Resolução: Por meio de limites de taxa de conexão e regras que descartam padrões de tráfego típicos de ataques de DDoS massivos.

22. Pergunta: O que significa NAT em firewalls com função de roteador?  
    Resolução: Network Address Translation traduz endereços IP internos para um IP público, ocultando a rede interna e reforçando segurança.

23. Pergunta: Explique brevemente o que é um proxy firewall.  
    Resolução: Um proxy atua como intermediário em aplicações, filtrando requests em nível de aplicação, além de endereço e porta.

24. Pergunta: Quais critérios você consideraria ao definir uma política de firewall para uma rede corporativa?  
    Resolução: Serviços necessários, fluxos de trabalho, minimização de exposição, segregação de redes e requisitos de conformidade.

25. Pergunta: Como manter suas regras de firewall atualizadas?  
    Resolução: Revisões periódicas, análise de logs, auditorias de segurança e alinhamento com mudanças na infraestrutura.

26. Pergunta: Por que é recomendado um firewall em cada estação de trabalho em redes críticas?  
    Resolução: Para proteger hosts isoladamente, impedindo movimentação lateral de atacantes que já estejam dentro da rede.

27. Pergunta: O que é uma “zona desmilitarizada” (DMZ) em conjunto com firewall?  
    Resolução: Segmento de rede isolado onde ficam servidores acessíveis externamente, protegido por regras específicas de entrada e saída.

28. Pergunta: Explique como um firewall colabora com sistemas de detecção de intrusão (IDS).  
    Resolução: Firewall bloqueia tráfego suspeito; IDS monitora padrões de ataque e gera alertas para análise humana ou ações automáticas.

29. Pergunta: Quais cuidados de segurança adicionais são necessários quando o firewall é configurado em roteadores de Internet?  
    Resolução: Garantir atualizações de firmware, senhas seguras, acesso apenas por redes administrativas e backups de configuração.

30. Pergunta: Enumere três boas práticas para gerenciamento de regras de firewall.  
    Resolução:  
    1. Documentar cada regra com propósito e autor.  
    2. Revisar e remover regras obsoletas.  
    3. Testar impacto de alterações em ambiente controlado antes de aplicar em produção.  

---

## Bibliografia

- Washington Luis. Segurança da Informação - Aula 10 (Firewall). YouTube. Disponível em: https://www.youtube.com/watch?v=rIDIF0A0u2c. Acesso em: 17 ago. 2025.  

- NEMETH, E.; SNYDER, G.; HEIN, T. R. Manual completo do Linux: guia do administrador. 1. ed. São Paulo, SP: Pearson, 2005. E-book. Disponível em: https://plataforma.bvirtual.com.br. Acesso em: 17 ago. 2025.  

- “Introdução às Redes de Computadores/Definições das Redes de Computadores.” Wikiversity. Disponível em: https://pt.wikiversity.org/wiki/Introdu%C3%A7%C3%A3o_%C3%A0s_Redes_de_Computadores/Defini%C3%A7%C3%B5es_das_Redes_de_Computadores. Acesso em: 17 ago. 2025.