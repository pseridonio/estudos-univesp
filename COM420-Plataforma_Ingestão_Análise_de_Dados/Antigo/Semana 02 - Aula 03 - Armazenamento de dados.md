# Armazenamento de Dados

## 1. Introdução

Nesta aula exploramos a complexidade de armazenar e recuperar dados gerados por sistemas heterogêneos, distribuídos geograficamente e em ambientes de nuvem.

Discutimos como o modelo de armazenamento (tabelar, chave-valor, colunar, hierárquico) impacta na velocidade de recuperação, na escalabilidade e na consistência.

Abordamos ainda as principais preocupações de segurança, conectividade, custos e processamento remoto em bancos de dados implantados como serviço na nuvem.

---

## 2. Arquitetura de Armazenamento em Nuvem

- O armazenamento é oferecido frequentemente como serviço (“Database as a Service – DBaaS”), com provisionamento elástico de CPU, memória, disco e rede.  

- O acesso remoto a esses dados ocorre via conexões seguras (por exemplo SSH com tunelamento TCP ou VPN) e linguagens de consulta padrão, como SQL para bancos relacionais.  

- A infraestrutura de nuvem oculta a complexidade de instalação, configuração e patching dos SGBDs, deixando ao usuário apenas a gestão de esquemas, índices e consultas.  

- Apesar da percepção de “capacidade infinita”, todo provedor possui limites físicos e regionais. Além disso, custos de armazenamento, transferência e IOPS crescem conforme o volume de dados e nível de replicação configurado.

---

## 3. Modelos de Armazenamento de Dados

### 3.1 Relacional (Tabela)

- Organiza dados em linhas e colunas, suporta transações ACID e SQL.  
- Ideal quando há relacionamentos complexos, requisitos de integridade referencial e consultas ad hoc envolvendo várias tabelas.

### 3.2 Não Relacional (NoSQL)

- Chave-valor: hash distribuída para acesso rápido por chave (ex.: DynamoDB).  
- Documento: armazena JSON/BSON sem esquema fixo, permitindo flexibilidade no formato de cada documento (ex.: MongoDB, CouchDB).  
- Colunar: otimizado para leitura e agregação de grandes volumes por coluna (ex.: Apache Cassandra).  
- Grafo: gerencia relacionamentos dinâmicos e complexos de forma nativa (ex.: Neo4j).  

---

## 4. Sistemas de Arquivo Distribuídos

- Google File System (GFS): fragmenta arquivos em blocos replicados automaticamente, com detecção de falhas pelo master.  
- Hadoop Distributed File System (HDFS): inspirado no GFS, de código aberto e integrado a MapReduce para processamento de Big Data.  

Esses sistemas priorizam tolerância a falhas e throughput em lote, mas não são indicados para pequenas transações de bancos relacionais.

---

## 5. Transações, Consistência e CAP

- Transações ACID garantem Atomicidade, Consistência, Isolamento e Durabilidade em sistemas centralizados ou distribuídos.  
- Em sistemas distribuídos, o teorema CAP afirma que só é possível priorizar duas entre Consistência, Disponibilidade e Tolerância a Partições.  
- Soluções modernas permitem **tunabilidade** dessas propriedades via configuração de quorum de leitura/escrita, ajustando dinamicamente latência versus durabilidade conforme o caso de uso.  
- Modelos BASE (Basicamente Disponível, Estado Soft, Eventualmente Consistente) são adotados por muitos bancos NoSQL para maximizar disponibilidade e elasticidade.

---

## 6. Escalabilidade: Vertical × Horizontal

- Vertical (scale-up): aumentar recursos (CPU, RAM, disco) de um único servidor.  
- Horizontal (scale-out): replicar instâncias idênticas, distribuindo carga via balanceadores ou sharding.  
- Em nuvem, a elasticidade e clonagem rápida de máquinas virtuais tornam o scale-out a estratégia mais comum para atender picos e reduzir custos com overprovisioning.

---

## 7. Tolerância a Falhas e Replicação

- Sharding (fragmentação): particionamento de dados em nós diferentes para distribuir carga e armazenar subconjuntos do dataset.  
- Réplicas síncronas garantem consistência forte, mas aumentam latência de escrita; réplicas assíncronas reduzem latência, mas permitem divergência temporária.  
- Estratégias de failover automático e monitoramento de latência são fundamentais para manter SLAs de disponibilidade e RTO/RPO.

---

## 8. Serviços de Banco de Dados em Nuvem

- Relacionais nativos: Azure SQL Database e Amazon Aurora — projetados para nuvem com armazenamento distribuído e replicação multi-zona.  
- Relacionais adaptados: Amazon RDS para MySQL/PostgreSQL — portados de ambientes on-premises, com menor flexibilidade de escala horizontal.  
- NoSQL gerenciados: DynamoDB (chave-valor), Cosmos DB (multi-modelo), MongoDB Atlas e CouchDB na nuvem (documento), Cassandra Managed Services (colunar), Neo4j Aura (grafo).  

Esses serviços oferecem monitoramento integrado, backups automáticos e ajuste de IOPS/throughput conforme demanda.

---

## 9. Limitações e Custos de Armazenamento em Nuvem

- Todo provedor de nuvem impõe cotas e limites regionais de capacidade e throughput.  
- Custos de armazenamento escalam conforme volume, replicação e requisições de leitura/gravação; a previsibilidade exige planejamento de growth tiers.  
- Transferências de dados entre zonas ou regiões geram cobranças adicionais (egresso de dados), impactando projetos geo-distribuídos.

---

## Lista de Exercícios

1. **Defina scale-up e scale-out e dê um exemplo prático de cada um.**  
   Solução:  
   - Scale-up: migrar um servidor de 8 GB para 32 GB de RAM.  
   - Scale-out: criar três réplicas de um cluster MongoDB e usar balanceador.

2. **Explique o teorema CAP e dê um cenário AP (Disponibilidade + Partição).**  
   Solução:  
   - Em chat em larga escala, aceita eventual consistency para garantir mensagens sempre acessíveis, mesmo com falha de datacenter.

3. **Quais vantagens e desvantagens de usar HDFS em vez de sistema de arquivos local?**  
   Solução:  
   - Vantagens: alta tolerância a falhas, paralelismo MapReduce.  
   - Desvantagens: alta latência em leituras pequenas, dependência de JVM.

4. **Como o modelo BASE difere do ACID?**  
   Solução:  
   - ACID foca em integridade imediata.  
   - BASE prioriza disponibilidade e performance, aceitando estados intermediários.

5. **Cite três bancos NoSQL e identifique seu modelo.**  
   Solução:  
   - DynamoDB: chave-valor.  
   - MongoDB: documento.  
   - Cassandra: colunar.

6. **Descreva o sharding e seu principal benefício.**  
   Solução:  
   - Sharding é particionamento lógico do dataset; distribui carga de leitura/escrita e suporta escala horizontal.

7. **Por que réplicas síncronas aumentam a latência de escrita?**  
   Solução:  
   - Cada gravação aguarda confirmação em todas as réplicas antes de retornar sucesso.

8. **Como o GFS detecta e recupera falhas em blocos?**  
   Solução:  
   - Master monitora heartbeats dos chunkservers e recria réplicas quando detecta falhas.

9. **Quando recomendar MongoDB em vez de banco relacional?**  
   Solução:  
   - Em esquemas flexíveis ou documentos com atributos variáveis, como perfis de usuário dinâmicos.

10. **Como Amazon RDS difere de Aurora?**  
    Solução:  
    - RDS usa motores legados; Aurora possui armazenamento distribuído otimizado, maior throughput e replicação integrada.

11. **Desenhe o fluxo de consulta SQL em DBaaS.**  
    Solução:  
    - Cliente → TLS → endpoint DBaaS → proxy interno → instância primária/replica → resultado.

12. **Quais desafios de consistência em cluster no mesmo datacenter?**  
    Solução:  
    - Latência de rede, ordenação de commits, controle de locks e potencial deadlock.

13. **Fragmentação vs. replicação de dados.**  
    Solução:  
    - Fragmentação divide dados sem redundância; replicação cria cópias completas para disponibilidade.

14. **Três características necessárias para arquivos em Big Data.**  
    Solução:  
    - Escalabilidade horizontal, tolerância a falhas via réplica de blocos, alto throughput em lote.

15. **Estratégia híbrida de replicação síncrona e assíncrona.**  
    Solução:  
    - Síncrona dentro da mesma AZ e assíncrona entre AZs para balancear latência e recuperação de desastre.

16. **Como DBaaS reduz custos operacionais?**  
    Solução:  
    - Padroniza backups e atualizações, elimina DBAs de infraestrutura e cobra por uso efetivo.

17. **Diferença IaaS, PaaS e SaaS no contexto de dados.**  
    Solução:  
    - IaaS: VMs e disco; PaaS: DBaaS; SaaS: aplicação completa com persistência interna.

18. **Como funciona balanceamento em réplicas de leitura?**  
    Solução:  
    - Proxy/DNS distribui consultas de leitura para secundárias, gravações vão à primária.

19. **Fatores para escolher entre relacional e NoSQL colunar.**  
    Solução:  
    - Volume de dados analíticos, flexibilidade de esquema, consistência transacional.

20. **O que é eventual consistency e quando é aceitável?**  
    Solução:  
    - Leitores podem ver versões antigas até convergência; ideal para dashboards e feeds de redes sociais.

21. **Como virtualização auxilia scale-out em nuvem?**  
    Solução:  
    - Clonagem rápida de VMs com configurações idênticas sem depender de hardware físico.

22. **Quais KPIs monitorar em cluster distribuído?**  
    Solução:  
    - Latência de leitura/escrita, throughput, uso de CPU/memória, estado de replicação, heartbeat.

23. **Caso de uso ideal para banco de dados em grafo.**  
    Solução:  
    - Análise de redes sociais e recomendações baseadas em conexões complexas.

24. **Como Cassandra equilibra replicação?**  
    Solução:  
    - Usa anel de nós e fator de réplica configurável; cada partição é armazenada em N nós consecutivos.

25. **Impactos de fragmentação de rede na consistência.**  
    Solução:  
    - Pode gerar “split-brain” e conflitos de escrita em diferentes segmentos.

26. **Snapshot vs. log-structured storage.**  
    Solução:  
    - Snapshot captura imagem pontual; log-structured grava operações sequenciais para replay.

27. **Onde colocar pré-processamento em arquitetura IoT?**  
    Solução:  
    - Edge para filtrar e reduzir tráfego; fog para agregação regional; cloud para análises complexas.

28. **Banco nativo-cloud vs. adaptado.**  
    Solução:  
    - Nativo-cloud tem APIs e elasticidade embutidas; adaptado é portado de sistemas legados com limitações.

29. **Backup incremental vs. full copy.**  
    Solução:  
    - Full copy copia tudo; incremental copia apenas alterações desde o último backup, otimizando tempo e espaço.

30. **Projete um mini-SLA para DBaaS.**  
    Solução:  
    - Disponibilidade 99,95%; RTO ≤ 5 min; RPO ≤ 1 min; réplicas em múltiplas zonas, backups automáticos.

---

## Bibliografia

- Plataforma de Ingestão e Análise de Dados – “Armazenamento de Dados”, UNIVESP, YouTube, 24 jun 2025. Acesso em 19 ago 2025.  
- Proença, M. H., “Arquitetura IoT para Aplicação em Smart Campus”, TCC Soro Proença, BlackBoard, 2020. Acesso em 19 ago 2025.  
- Unicamp, “O que é computação em nuvem?”, suporte.nuvem.unicamp.br, 2025. Acesso em 19 ago 2025.  
- Braga, A., “Cloud Computing”, PDF Blackboard, 2021. Acesso em 19 ago 2025.  
- Lakshman, A.; Malik, P., “Cassandra: A Decentralized Structured Storage System”, SOSP, 2010. Acesso em 19 ago 2025.  
- Ghemawat, S.; Gobioff, H.; Leung, S.-T., “The Google File System”, SOSP, 2003. Acesso em 19 ago 2025.