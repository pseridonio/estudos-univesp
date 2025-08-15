# Middlewares para IaaS

## Objetivos e importância

- **Propósito:** Entender o que é middleware no contexto de infraestrutura como serviço (IaaS), por que ele é essencial e como habilita gestão em escala de nuvens públicas e privadas.   
- **Resultados de aprendizagem:** Identificar funções típicas (autenticação, transações, mensageria, APIs), reconhecer exemplos práticos (OpenStack, Apache CloudStack, Kafka) e relacionar middleware com padronização, integração e multicloud. 

---

## Conceito e papel do middleware em infraestrutura

O middleware é um software posicionado entre o sistema operacional e as aplicações, que padroniza e oculta a complexidade de comunicação, dados e operações em sistemas distribuídos. Ele permite que usuários e aplicações interajam com recursos sem lidar com detalhes de hardware, armazenamento, conectividade ou protocolos, viabilizando escala, resiliência e agilidade operacional. 

- **Ocultação de complexidade:** O usuário não precisa saber em qual servidor ou disco um e-mail ou arquivo está armazenado; o middleware abstrai e orquestra.   
- **Funções nucleares:** comunicação entre serviços, autenticação, gerenciamento de transações, mensageria, servidores de aplicação e servidores web, todos padronizados via bibliotecas e APIs.   
- **Escala e tempo real:** além de “encaminhar dados”, middlewares também suportam processamento distribuído/parallel, inclusive em tempo real. 

---

## Usos típicos e padrões de integração

- **Otimização de aplicações legadas:**  
  - **Objetivo:** padronizar tarefas repetitivas (autenticação, conexão a bancos, formatos de dados), melhorar portabilidade e desempenho ao migrar para nuvem.   
- **Desenvolvimento de novas aplicações:**  
  - **Objetivo:** padronizar ambiente de execução, linguagens e frameworks, expondo serviços via APIs para integrar sistemas internos e externos.   
- **Mensageria e streaming (Apache Kafka):**  
  - **Modelo produtor–consumidor:** múltiplos tópicos/canais para produzir e consumir dados de forma assíncrona, inclusive em tempo real, facilitando integração desacoplada entre aplicações.   
- **Automação e orquestração:**  
  - **Benefício:** reduzir decisões manuais e gerenciar recursos para elevar eficiência do ecossistema (provisionamento, billing, observabilidade).   
- **Multicloud pragmático:**  
  - **Racional:** aproveitar pontos fortes de diferentes nuvens (AWS, Azure, Google Cloud) para escala, gerenciamento ou segurança, conforme a carga de trabalho. 

---

## Middlewares para IaaS em foco

### OpenStack (arquitetura modular)

- **Origem e propósito:** projeto open source iniciado por Rackspace e NASA (2010), camada entre hardware e aplicações para computação, conectividade e armazenamento.   
- **Por que importa:** permite gerenciar de milhares a centenas de milhares de servidores físicos e milhões de instâncias virtuais, servindo tanto provedores (públicas) quanto nuvens privadas corporativas.   
- **Componentes destacados:**  
  - **Ceilometer (telemetria/billing):** ponto de contato para medição e faturamento do uso de recursos.   
  - **Heat (orquestração):** pilha de templates para descrever e implantar infraestruturas e serviços.   
  - **Swift (armazenamento de objetos) e Cinder (armazenamento em blocos):** suporte a diferentes perfis de dados e I/O.   
- **Licenciamento:** ecossistema aberto, favorecendo integração e expansão por terceiros. 

### Apache CloudStack (história e funcionalidades)

- **Linha do tempo:** nascido na Cloud.com; adquirido pela Citrix, que doou o código à Apache Software Foundation — hoje “Apache CloudStack”.   
- **Alvos e camadas:** projetado para operar nuvens públicas/privadas, com camadas que incluem rede (L2), nós de computação e nós de armazenamento.   
- **Compatibilidade e gestão:**  
  - **Hipervisores suportados:** Xen, KVM, Hyper‑V, VMware.   
  - **Operação:** interface web amigável para gerenciar VMs, imagens e snapshots; API nativa e integração com outras nuvens.   
  - **Sinergia com AWS:** tradutor de API para que aplicações escritas para CloudStack possam executar na AWS. 

---

## Comparação prática e cenários

| Aspecto | OpenStack | Apache CloudStack |
|---|---|---|
| **Arquitetura** | Modular, ampla gama de serviços (compute, network, storage, telemetry, orchestration) | Estrutura por camadas com forte foco operacional e UI amigável |
| **Escopo típico** | Grandes nuvens públicas e privadas, alta flexibilidade | Nuvens privadas/públicas com operação simplificada |
| **Ecosistema** | Forte comunidade e projetos adjacentes | Projeto estável na Apache com foco em integração prática |
| **Integrações** | Storage: Swift/Cinder; Telemetria: Ceilometer; Orquestração: Heat | Suporte a múltiplos hipervisores; API nativa; compatibilidade com AWS |

> Sources: 

---

## Análise crítica

- **Termo “middleware” amplo:** No vídeo, “middleware” é usado de forma propositalmente abrangente (incluindo e‑mail/servidores web). Em literatura técnica, e‑mail costuma ser classificado como serviço de aplicação; ainda assim, o ponto didático é válido: software intermediário que mascara complexidade e padroniza acesso.  
- **Ceilometer e faturamento:** O vídeo cita Ceilometer como ponto de medição para billing. Na prática, o ecossistema de telemetria do OpenStack evoluiu (telemetry stack) e costuma ser combinado com outros componentes para faturamento; o conceito de “medir para cobrar” permanece fiel.   
- **Multicloud não é panaceia:** Usar várias nuvens pode otimizar custo/segurança/latência, porém aumenta governança e complexidade operacional (identidades, rede, observabilidade). O vídeo acerta ao tratá‑la como decisão arquitetural consciente, não default. 

---

## Exercícios (30) com resolução detalhada

1. **Defina middleware no contexto de IaaS.**  
   - **Ideia‑chave:** Software entre SO e aplicações que padroniza comunicação e dados.   
   - **Passo 1:** Identifique a posição (entre SO e apps).  
   - **Passo 2:** Liste funções (comunicação, dados, auth).  
   - **Passo 3:** Relacione ao ganho de escala (oculta complexidade).

2. **Explique por que middleware é essencial para nuvem em escala.**  
   - **Passo 1:** Grandes nuvens têm milhares de hosts e milhões de VMs.   
   - **Passo 2:** Operar isso sem abstrações tornaria gestão inviável.  
   - **Passo 3:** Middleware padroniza e automatiza tarefas críticas.

3. **Dê dois exemplos de funções de middleware citadas no vídeo.**  
   - **Passo 1:** Autenticação.   
   - **Passo 2:** Gerenciamento de transações. 

4. **Descreva o papel de mensageria com Kafka.**  
   - **Passo 1:** Modelo produtor–consumidor com múltiplos canais.   
   - **Passo 2:** Integração assíncrona e em tempo real.  
   - **Passo 3:** Desacoplamento entre serviços.

5. **Como middleware ajuda a modernizar legados?**  
   - **Passo 1:** Padroniza tarefas repetitivas (login, DB).   
   - **Passo 2:** Cria APIs para integrar sistemas.  
   - **Passo 3:** Melhora portabilidade e desempenho.

6. **Relacione middleware e APIs.**  
   - **Passo 1:** Middleware expõe serviços via APIs padronizadas.   
   - **Passo 2:** Permite integração entre linguagens/SOs distintos.  
   - **Passo 3:** Acelera conexão entre sistemas.

7. **Quando usar processamento em tempo real via middleware?**  
   - **Passo 1:** Necessidade de eventos imediatos (telemetria, streaming).   
   - **Passo 2:** Alto volume e baixa latência.  
   - **Passo 3:** Topologia produtor–consumidor.

8. **Cite três áreas que OpenStack cobre.**  
   - **Passo 1:** Computação (VMs).   
   - **Passo 2:** Conectividade (rede).   
   - **Passo 3:** Armazenamento (objetos/blocos). 

9. **Qual a origem do OpenStack?**  
   - **Passo 1:** Rackspace + NASA, 2010.   
   - **Passo 2:** Open source, arquitetura modular.  
   - **Passo 3:** Camada entre hardware e apps.

10. **Explique Ceilometer e Heat.**  
    - **Passo 1:** Ceilometer mede uso (telemetria/billing).   
    - **Passo 2:** Heat orquestra pilhas de recursos. 

11. **Diferencie Swift e Cinder.**  
    - **Passo 1:** Swift = objetos (arquivos).   
    - **Passo 2:** Cinder = blocos (volumes). 

12. **Quais públicos o OpenStack atende?**  
    - **Passo 1:** Provedores (nuvens públicas).   
    - **Passo 2:** Empresas (nuvens privadas). 

13. **Resuma a história do CloudStack.**  
    - **Passo 1:** Cloud.com → Citrix.   
    - **Passo 2:** Doação à Apache (ASF).   
    - **Passo 3:** Hoje “Apache CloudStack”.

14. **Liste hipervisores suportados pelo CloudStack.**  
    - **Passo 1:** Xen.   
    - **Passo 2:** KVM.   
    - **Passo 3:** Hyper‑V e VMware. 

15. **Cite três recursos operacionais do CloudStack.**  
    - **Passo 1:** UI web para gerenciar VMs.   
    - **Passo 2:** API nativa.   
    - **Passo 3:** Gestão de snapshots/imagens e storage. 

16. **Como CloudStack se integra com AWS?**  
    - **Passo 1:** Tradutor de API para executar aplicações na AWS.   
    - **Passo 2:** Facilita portabilidade.  
    - **Passo 3:** Habilita cenários híbridos.

17. **Explique “ocultação de complexidade” com exemplo.**  
    - **Passo 1:** Upload no Drive/Dropbox.   
    - **Passo 2:** Middleware provisiona e gerencia storage/rede.  
    - **Passo 3:** Usuário apenas usa a interface web.

18. **Por que telemetria é essencial para IaaS?**  
    - **Passo 1:** Medir uso → faturar (billing).   
    - **Passo 2:** Planejar capacidade.  
    - **Passo 3:** Detectar anomalias.

19. **Dê um exemplo de decisão multicloud citada.**  
    - **Passo 1:** Parte da app em nuvem A (escala).   
    - **Passo 2:** Parte em nuvem B (gestão).   
    - **Passo 3:** Parte em nuvem C (segurança). 

20. **Quais camadas a comparação do vídeo destaca no CloudStack?**  
    - **Passo 1:** Camada 2 (rede L2).   
    - **Passo 2:** Nós de computação.   
    - **Passo 3:** Nós de armazenamento. 

21. **Relacione middleware e padronização de acesso a bancos.**  
    - **Passo 1:** Barramento/biblioteca que abstrai drivers.   
    - **Passo 2:** Suporte a variados modelos (documentos, objetos).  
    - **Passo 3:** Facilita portabilidade da aplicação.

22. **Como middleware melhora eficiência operacional?**  
    - **Passo 1:** Automatiza provisionamento/rotinas.   
    - **Passo 2:** Centraliza políticas (auth, rede).  
    - **Passo 3:** Expõe APIs para integrações rápidas.

23. **Identifique riscos de multicloud.**  
    - **Passo 1:** Aumento de complexidade de gestão.  
    - **Passo 2:** Identidade/segurança heterogênea.  
    - **Passo 3:** Observabilidade e custos de saída.

24. **Quando optar por OpenStack vs CloudStack?**  
    - **Passo 1:** OpenStack para flexibilidade máxima/modularidade.   
    - **Passo 2:** CloudStack para operação simplificada e compatibilidade com hipervisores múltiplos.   
    - **Passo 3:** Avaliar equipe e requisitos.

25. **Exemplifique orquestração com Heat.**  
    - **Passo 1:** Template descreve VMs, redes e volumes.   
    - **Passo 2:** Implantação reproduzível da pilha.  
    - **Passo 3:** Escala/atualiza com versionamento.

26. **Mostre como telemetria alimenta billing.**  
    - **Passo 1:** Coleta métricas de uso (CPU, rede, disco).   
    - **Passo 2:** Agrega por tenant/projeto.  
    - **Passo 3:** Aplica política de tarifação.

27. **Desenhe um fluxo com Kafka para ETL em tempo real.**  
    - **Passo 1:** Serviços produzem eventos em tópicos.   
    - **Passo 2:** Consumidores processam e persistem.  
    - **Passo 3:** Downstream aciona alertas/dashboards.

28. **Como middleware facilita integrações externas?**  
    - **Passo 1:** APIs padronizadas (REST/gRPC).   
    - **Passo 2:** Autenticação centralizada.  
    - **Passo 3:** Transformação/normalização de dados.

29. **Qual relação entre IaaS e servidores web citada?**  
    - **Passo 1:** Servidores web podem operar como parte do middleware (camada de aplicação exposta).   
    - **Passo 2:** Integram com autenticação, mensageria e storage.  
    - **Passo 3:** Orquestrados por componentes IaaS.

30. **Feche: por que middlewares são “fundamentais” no vídeo?**  
    - **Passo 1:** Tornam a nuvem utilizável e escalável ao ocultar protocolos/dispositivos.   
    - **Passo 2:** Fornecem APIs para integrar terceiros.   
    - **Passo 3:** Aceleram criação de soluções com segurança e gestão. 

---

## Bibliografia

- UNIVESP. Infraestrutura para Sistemas de Software – Middlewares para IaaS (LIBRAS). YouTube. Disponível em: https://www.youtube.com/watch?v=NQXQnf-oj6c. Acesso em: 14 ago. 2025.   
- OpenStack Foundation. Documentação do OpenStack (componentes: Compute, Neutron, Cinder, Swift, Telemetry, Heat). Disponível em: https://docs.openstack.org. Acesso em: 14 ago. 2025.  
- Apache Software Foundation. Apache CloudStack – Overview e Admin Guide. Disponível em: https://cloudstack.apache.org. Acesso em: 14 ago. 2025.  
- Apache Software Foundation. Apache Kafka – Documentation. Disponível em: https://kafka.apache.org/documentation. Acesso em: 14 ago. 2025.  
- Wikiversidade. Introdução às Redes de Computadores/Definições das Redes de Computadores. Disponível em: https://pt.wikiversity.org/wiki/Introdu%C3%A7%C3%A3o_%C3%A0s_Redes_de_Computadores/Defini%C3%A7%C3%B5es_das_Redes_de_Computadores. Acesso em: 14 ago. 2025.  