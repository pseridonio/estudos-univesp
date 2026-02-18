# Ferramentas para Armazenamento e Recuperação de Dados

## 1. Introdução

Nesta aula, analisamos três bancos NoSQL destacados pelo professor Júlio Estrella: Neo4j, CouchDB e Cassandra.  

Eles representam modelos diferentes de dados (grafos, documentos e colunar) e atendem casos de uso na nuvem, IoT e Big Data.  

Entender essas ferramentas ajuda a escolher a melhor estratégia de persistência e recuperação em sistemas distribuídos.

---

## 2. Neo4j: Banco de Dados em Grafo

Neo4j é um banco de dados transacional orientado a grafos, primariamente usado para modelar relacionamentos entre entidades de forma nativa.  

Ele armazena nós e arestas, cada qual com pares chave-valor, mantendo ACID completo e permitindo consultas por padrões de grafo (linguagem Cypher).  

Neo4j inclui interface web integrada (Fauxton/Grafana), APIs REST, drivers oficiais em Java, JavaScript, Python e suporta exportação em JSON ou CSV para análises externas.  

Uso em nuvem e IoT: identifica conexões complexas (redes sociais, rotas de delivery, monitoramento de dispositivos) e agrupa dados geograficamente próximos para acelerar consultas.

---

## 3. CouchDB: Banco de Dados de Documentos

CouchDB é um banco de dados de documentos baseado em JSON, open source e escrito em Erlang pela Apache Software Foundation.  

Ele adota MVCC (versões imutáveis de documentos) e replicação eventual com resolução automática de conflitos, ideal para ambientes offline e sincronização entre edge e cloud.  

Acesso e inserção ocorrem via API RESTful sobre HTTP, usando métodos GET, POST, PUT e DELETE. A interface web (Fauxton) facilita operações CRUD diretamente do navegador.  

Em arquiteturas IoT, CouchDB pode rodar no dispositivo edge, coletar leituras locais e replicar para uma instância central no cloud, garantindo disponibilidade e sincronização.

---

## 4. Cassandra: Banco Colunar Distribuído

Cassandra é um banco de colunas distribuído, inspirado no Dynamo (Amazon) e Bigtable (Google), projetado para alta escalabilidade e tolerância a falhas.  

Arquitetura peer-to-peer, sem nó mestre, com clusters, datacenters e fatores de réplica configuráveis. Utiliza Memtable (armazenamento em memória), SSTable (arquivos em disco) e filtro de Bloom para leituras rápidas.  

Consistência é tunável por quorum de leitura/gravação, permitindo balanço entre latência e durabilidade. Empresas como Netflix e eBay o usam para milhões de transações por segundo.  

Em nuvem, Cassandra Managed Services fornecem provisionamento elástico de nós, monitoração integrada e backup automático via snapshots.

---

## 5. Comparação Entre Modelos NoSQL

| Banco     | Modelo       | Consistência                | Replicação           | Caso de Uso Típico                       |
|-----------|--------------|-----------------------------|----------------------|------------------------------------------|
| Neo4j     | Grafo        | ACID completo               | Síncrona ou Assíncrona| Social graph, recomendação, roteirização |
| CouchDB   | Documento    | Eventual (MVCC)             | Multimaster eventual | Sincronização offline-online, IoT edge   |
| Cassandra | Colunar      | Tunável por quorum (BASE)   | Peer-to-peer         | Telemetria massiva, logs, métricas       |

---

## 6. Integração com IoT e Cloud

- Edge: CouchDB para captura local de dados, replicando para servidores centrais quando a conexão retorna.  
- Fog: Cassandra para agregação regional e análises em lote de grandes volumes de telemetria.  
- Cloud: Neo4j para análises de grafos em nível global, descobrindo relações entre dispositivos, usuários e eventos.  

Em PaaS de nuvem, esses bancos podem ser consumidos como serviços gerenciados (DBaaS), reduzindo overhead de infraestrutura.

---

## 7. Análise Crítica

- O vídeo afirma que bancos relacionais “dificultam dinamicidade” na nuvem; na prática, soluções híbridas (HTAP, JSONB no PostgreSQL) atenuam esse problema.  
- Em Neo4j e CouchDB, a garantia ACID e o uso de MVCC requerem cuidado na configuração de réplica para evitar degradação de desempenho em clusters geodistribuídos.  
- A menção a Apache Kafka foi fora de escopo para “ferramentas de armazenamento”; Kafka é um sistema de streaming/mensageria que não persiste os dados primários de maneira equivalente a bancos NoSQL.

---

## 8. Conclusão

Escolher entre Neo4j, CouchDB e Cassandra depende do padrão de acesso, do modelo de dados e da topologia de distribuição.  

No ecossistema IoT e nuvem, o ideal é combinar ferramentas: CouchDB no edge, Cassandra em camadas regionais e Neo4j para análise relacional complexa.  

A adoção de DBaaS e arquiteturas PaaS facilita o provisionamento, monitoramento e escalabilidade, mas exige atenção a limites de cota e custos de egressos de dados.

---

## 9. Exercícios

1. **Explique o modelo de dados de Neo4j e escreva uma consulta Cypher para retornar todos os usuários conectados a um dispositivo “SensorA”.**  
   Resolução:  
   a) Modelo de grafo: nós (User, Device) e arestas (“CONNECTED_TO”).  
   b) Cypher:  
   ```cypher
   MATCH (u:User)-[:CONNECTED_TO]->(d:Device {name: 'SensorA'})
   RETURN u;
   ```  
   c) Passo a passo:  
   - `MATCH` define o padrão grafo.  
   - `{name: 'SensorA'}` filtra o nó Device.  
   - `RETURN u` exibe os usuários.

2. **Descreva como CouchDB gerencia conflitos em replicação multimaster.**  
   Resolução:  
   a) Cada documento tem `_rev` e histórico de revisões.  
   b) Ao detectar divergência, CouchDB cria revisões conflitantes armazenadas.  
   c) O cliente ou administrador escolhe a revisão “vencedora” via API REST antes de replicar adiante.

3. **Qual o papel do Bloom filter em Cassandra?**  
   Resolução:  
   a) Bloom filter é um algoritmo probabilístico.  
   b) Ele testa se uma partição pode existir em SSTables específicas.  
   c) Evita leituras desnecessárias de disco, reduzindo latência.

4. **Liste três casos de uso ideais para bancos em grafo.**  
   Resolução:  
   a) Redes sociais (amizades, seguidores).  
   b) Recomendações de produtos (usuário–produto–categoria).  
   c) Otimização de rotas em logística (pontos de entrega interligados).

5. **Implemente uma chamada HTTP para inserir um documento JSON em CouchDB usando cURL.**  
   Resolução:  
   a) Comando:  
   ```bash
   curl -X POST http://localhost:5984/meubanco \
     -H "Content-Type: application/json" \
     -d '{"sensor":"Temp1","value":22.5}'
   ```  
   b) Passo a passo:  
   - `-X POST` indica criação.  
   - URL aponta para o banco alvo.  
   - `-H` define header JSON.  
   - `-d` envia o payload.

6. **Explique como configurar o fator de réplica no Cassandra para 3 cópias em dois data centers.**  
   Resolução:  
   a) Em `cqlsh`, criar keyspace:  
   ```cql
   CREATE KEYSPACE ks_iot WITH 
   REPLICATION = {
     'class':'NetworkTopologyStrategy',
     'DC1':3,
     'DC2':3
   };
   ```  
   b) Explicação:  
   - `NetworkTopologyStrategy` mapeia réplica por DC.  
   - Números indicam cópias em cada DC.

7. **Compare a consistência de leitura em Neo4j (ACID) versus CouchDB (Eventual).**  
   Resolução:  
   a) Neo4j garante leitura sempre atualizada (ACID).  
   b) CouchDB pode retornar versão anterior até a replicação convergir.  
   c) Impacto: aplicações críticas escolhem Neo4j; tolerantes a latência, CouchDB.

8. **Crie um diagrama simples de cluster Cassandra com dois data centers e três nós cada.**  
   Resolução:  
   a) [ASCII-art opcional]  
   b) Descrição: DC1(nó1, nó2, nó3), DC2(nó4, nó5, nó6).  
   c) Anotações de replicação e chave primária.

9. **Por que Neo4j é indicado para transações complexas de relacionamento em tempo real?**  
   Resolução:  
   a) Armazenamento nativo em grafos evita JOINs caros.  
   b) Cypher otimizado analisa padrões de caminho.  
   c) ACID mantém integridade em múltiplas arestas.

10. **Como habilitar views MapReduce em CouchDB para consultas agregadas?**  
    Resolução:  
    a) Definir design document:  
    ```json
    {
      "_id":"_design/v1",
      "views":{
        "countBySensor":{
          "map":"function(doc){ emit(doc.sensor,1); }",
          "reduce":"_sum"
        }
      }
    }
    ```  
    b) Enviar via API e consultar `/meubanco/_design/v1/_view/countBySensor`.

11. **Explique o conceito “peer-to-peer” em Cassandra e seus benefícios.**  
    Resolução:  
    a) Não existe nó mestre; todos aceitam leitura/gravação.  
    b) Evita ponto único de falha.  
    c) Facilita escalonamento horizontal sem reverso de líder.

12. **Descreva como um cliente Java conecta-se ao Cassandra.**  
    Resolução:  
    a) Usar driver DataStax:  
    ```java
    CqlSession session = CqlSession.builder()
      .addContactPoint(new InetSocketAddress("host",9042))
      .withLocalDatacenter("DC1")
      .build();
    ```  
    b) Passos: inicializar cluster, definir datacenter, obter sessão.

13. **Qual impacto das configurações de quorum de leitura em Cassandra?**  
    Resolução:  
    a) Quorum = ⌈(RF+1)/2⌉.  
    b) Leitura QUORUM aguarda maioria de réplicas.  
    c) Maior consistência, mas latência aumenta.

14. **Mostre um exemplo de criação de índice secundário em Cassandra.**  
    Resolução:  
    ```cql
    CREATE INDEX ON ks_iot(reading_time);
    ```  
    a) Permite consultas filtrar por `reading_time`.  
    b) Custo adicional de armazenamento.

15. **Como verificar status de cluster no Cassandra?**  
    Resolução:  
    a) Comando shell: `nodetool status`.  
    b) Exibe nós UP/DOWN, tokens e percentuais.

16. **Explique MVCC em CouchDB e como isso auxilia replicação.**  
    Resolução:  
    a) Cada atualização cria nova revisão `_rev`.  
    b) Históricos paralelos coexistem até merge manual.  
    c) Evita locking pessimista.

17. **Implemente uma consulta Cypher para contar relações “FRIENDS_WITH” por usuário.**  
    Resolução:  
    ```cypher
    MATCH (u:User)-[r:FRIENDS_WITH]->()
    RETURN u.name, count(r) AS totalFriends;
    ```  
    a) `MATCH`: padrão grafo.  
    b) `count(r)`: agregação.

18. **Descreva como adicionar um nó a um cluster Neo4j causal.**  
    Resolução:  
    a) Configurar endereço em `neo4j.conf`:  
    ```properties
    causal_clustering.initial_discovery_members=host1:5000,host2:5000
    ```  
    b) Reiniciar serviço e verificar logs.

19. **Quais métricas monitorar num cluster CouchDB em produção?**  
    Resolução:  
    - Taxa de replicação por DB  
    - Latência de leitura/gravação HTTP  
    - Tamanho de _changes feed  
    - Contagem de revisões e conflitos

20. **Explique a MSCKL (Multi-Site Cassandra) para geo-replicação.**  
    Resolução:  
    a) Uso de datacenters múltiplos em keyspace.  
    b) Política de consistência LOCAL_QUORUM evita tráfego cross-DC.

21. **Como purgar documentos antigos no CouchDB?**  
    Resolução:  
    a) Configurar política de expurgo (`erlang` config).  
    b) Usar `_purge` API para remover revisões não referenciadas.

22. **Mostre como alterar fator de réplica em um keyspace existente.**  
    Resolução:  
    ```cql
    ALTER KEYSPACE ks_iot WITH REPLICATION = {
      'class':'NetworkTopologyStrategy','DC1':2,'DC2':2
    };
    ```  
    a) Cassandra replica dados conforme nova estratégia.

23. **Compare o consumo de disco entre Neo4j e Cassandra em grandes grafos.**  
    Resolução:  
    a) Neo4j armazena metadados de índice de grafo, aumenta overhead em nós/arestas.  
    b) Cassandra otimiza em SSTables mas padroniza colunas esparsas.

24. **Explique a função do Memtable no Cassandra.**  
    Resolução:  
    a) Buffer em memória para escrituras rápidas.  
    b) Periodicamente flush para SSTable em disco.

25. **Como inserir massivamente dados no CouchDB sem sobrecarregar o servidor?**  
    Resolução:  
    a) Usar `_bulk_docs` API:  
    ```json
    { "docs":[{…},{…},…] }
    ```  
    b) Ajustar `max_document_size` e `batch_size`.

26. **Descreva o uso de câmeras de leitura em Neo4j para traversals em tempo real.**  
    Resolução:  
    a) Usar algoritmo `breadthFirst` em Cypher:  
    ```cypher
    MATCH p = (start)-[:REL*1..3]->(end)
    RETURN p;
    ```  
    b) Define profundidade (1..3).

27. **Quais cuidados ao dimensionar um cluster Cassandra para IoT?**  
    Resolução:  
    - Particionamento eficiente por device_id  
    - RF≥3 em DC principais  
    - Monitorar latência de replicação cross-DC

28. **Implemente consulta de view no CouchDB para agrupar sensores por tipo.**  
    Resolução:  
    a) Design doc com map:  
    ```js
    function(doc){
      if(doc.sensorType) emit(doc.sensorType,1);
    }
    ```  
    b) Reduce `_sum`, depois acessar `/db/_design/d1/_view/byType`.

29. **Explique como evitar hotspots em Cassandra.**  
    Resolução:  
    - Use partições balanceadas (hash de device_id+timestamp)  
    - Evitar seqüência de chaves ordenadas que causem carga concentrada

30. **Descreva processo de backup e restauração em Cassandra.**  
    Resolução:  
    a) Backup: usar `nodetool snapshot ks_iot`.  
    b) Copiar snapshots do diretório para local seguro.  
    c) Restauração: parar nó, substituir SSTables, iniciar nó e permitir streaming de dados.

---

## Bibliografia

- Estrella, J. C., “Ferramentas para Armazenamento e Recuperação de Dados”, UNIVESP, YouTube, 24 jun. 2025. Acesso em 19 ago. 2025.  
- Proença, M. H., “Arquitetura IoT para Aplicação em Smart Campus”, TCC, Univ. São Paulo, 2020. Acesso em 19 ago. 2025.  
- Unicamp, “O que é computação em nuvem?”, suporte.nuvem.unicamp.br, 2025. Acesso em 19 ago. 2025.  
- Braga, A., “Cloud Computing”, 2ª ed., Editora Ciência Moderna, 2021. Acesso em 19 ago. 2025.  
- Lakshman, A.; Malik, P., “Cassandra: A Decentralized Structured Storage System”, SOSP, 2010.  
- Ghemawat, S.; Gobioff, H.; Leung, S.-T., “The Google File System”, SOSP, 2003.