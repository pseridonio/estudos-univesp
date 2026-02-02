# Plataforma de Ingestão e Análise de Dados — Introdução à Computação em Nuvem

---

## Introdução

A **computação em nuvem** transformou a forma como sistemas embarcados e aplicações de Internet das Coisas (IoT) coletam, processam e analisam dados. Em projetos que envolvem sensores, atuadores e dispositivos distribuídos, a nuvem oferece recursos elásticos de armazenamento, processamento e serviços gerenciados que permitem escalar pipelines de ingestão e análise sem a necessidade de infraestrutura local complexa. Este material apresenta os conceitos fundamentais necessários para projetar e avaliar plataformas de ingestão e análise de dados baseadas em nuvem, com foco em arquiteturas, modelos de processamento (batch vs streaming), requisitos não funcionais (latência, throughput, confiabilidade) e exemplos práticos que ilustram decisões de engenharia. 

---

## Desenvolvimento

### Contexto e motivação em sistemas embarcados

Sistemas embarcados modernos frequentemente geram grandes volumes de dados telemetria, logs e eventos. Esses dados podem ser usados para monitoramento, manutenção preditiva, controle em tempo real e análises históricas. A nuvem permite centralizar esses fluxos, aplicar processamento em larga escala e integrar ferramentas analíticas e de visualização. Em cenários industriais, por exemplo, sensores de vibração e temperatura em máquinas enviam leituras contínuas que precisam ser ingeridas com baixa latência para detecção de anomalias, enquanto também são armazenadas para análises históricas.

---

### Arquitetura de uma plataforma de ingestão e análise

**Conceito.** Uma plataforma típica é composta por camadas: dispositivos/edge, gateway/ingestão, transporte de mensagens, armazenamento de longo prazo, processamento (streaming e batch), e camadas de consumo (dashboards, APIs, modelos ML).  

**Funcionamento.**  
- **Edge / Dispositivos:** coletam dados e aplicam pré-processamento leve (filtragem, compressão).  
- **Gateways:** agregam e autenticam dispositivos, aplicam políticas de segurança e encaminham para a nuvem.  
- **Transporte de mensagens:** sistemas como filas e brokers (ex.: MQTT, Apache Kafka) garantem entrega, ordenação e desacoplamento entre produtores e consumidores.  
- **Armazenamento:** combina armazenamento de objetos (para dados brutos), bancos de séries temporais (para métricas) e data lakes/data warehouses para análises históricas.  
- **Processamento:** inclui pipelines de streaming para respostas em tempo real e jobs batch para agregações periódicas.  
- **Camada de consumo:** dashboards, APIs e modelos de ML que consomem os resultados.

**Formalização (modelo lógico).** Uma visão simplificada pode ser representada como um fluxo:  
\[
\text{Dispositivo} \rightarrow \text{Gateway} \rightarrow \text{Broker} \rightarrow
\begin{cases}
\text{Processamento Streaming} \\
\text{Armazenamento Longo Prazo} \rightarrow \text{Processamento Batch}
\end{cases}
\]

**Exemplo explicado.** Um sensor de temperatura envia leituras a cada segundo. O gateway autentica e publica mensagens em um tópico Kafka. Um job de streaming calcula a média móvel em janelas de 1 minuto para alertas em tempo real; paralelamente, todas as leituras são armazenadas em um data lake para análises mensais.

---

### Modelos de ingestão: batch vs streaming

**Contexto.** A escolha entre processamento em lote (batch) e em fluxo (streaming) depende de requisitos de latência, consistência e custo.

**Conceito.**  
- **Batch:** processa grandes volumes de dados acumulados em intervalos; adequado para relatórios e análises históricas.  
- **Streaming:** processa eventos conforme chegam; adequado para detecção de anomalias e controle em tempo real.

**Funcionamento.**  
- **Batch:** dados são coletados, armazenados e processados em jobs agendados. Ex.: executar agregações diárias.  
- **Streaming:** operadores contínuos aplicam transformações em janelas temporais ou por evento; exige mecanismos de estado e tolerância a falhas.

**Formalização (janelas temporais).** Em streaming, uma janela deslizante de tamanho \(w\) com passo \(s\) pode ser definida; a média móvel sobre uma janela \(w\) é:
\[
\overline{x}_{t} = \frac{1}{n}\sum_{i=0}^{n-1} x_{t-i}
\]
onde \(n\) é o número de amostras na janela.

**Exemplo explicado.** Para detectar picos, calcula-se a média móvel de 60 segundos. Se a leitura atual exceder \(\overline{x}_{t} + 3\sigma\) (três desvios-padrão), gera-se um alerta.

---

### Requisitos não funcionais: latência, throughput, durabilidade e custo

**Contexto.** Projetos embarcados têm restrições de rede, energia e custo; a nuvem impõe trade-offs entre desempenho e preço.

**Conceito e funcionamento.**  
- **Latência:** tempo entre geração do evento e resposta. Sistemas de controle em tempo real exigem latências baixas (ms–s).  
- **Throughput:** taxa de eventos por unidade de tempo que a plataforma deve suportar.  
- **Durabilidade:** garantia de que dados não serão perdidos; alcançada por replicação e armazenamento persistente.  
- **Custo:** inclui transferência de dados, armazenamento e processamento; otimizações envolvem compressão, amostragem e políticas de retenção.

**Formalização (throughput e latência).** Se \(N\) eventos são gerados por segundo e cada evento tem tamanho médio \(S\) bytes, a taxa de dados é:
\[
R = N \cdot S \quad (\text{bytes/s})
\]
Para dimensionar a fila/broker, deve-se garantir capacidade \(C\) tal que \(C \ge R\cdot T\), onde \(T\) é o tempo máximo de retenção em buffer.

**Exemplo explicado.** Um conjunto de 1.000 sensores enviando 1 evento/s com 200 bytes/evento gera \(R = 1000 \cdot 200 = 200{,}000\) bytes/s ≈ 200 KB/s. Em uma janela de 1 hora, o volume é \(200\ \text{KB/s} \times 3600 \approx 720\ \text{MB}\).

---

### Garantias de entrega e consistência

**Contexto.** Em pipelines distribuídos, é preciso escolher entre diferentes garantias: *at-most-once*, *at-least-once*, *exactly-once*.

**Conceito.**  
- **At-most-once:** mensagens podem ser perdidas, mas não duplicadas.  
- **At-least-once:** mensagens são entregues pelo menos uma vez; duplicatas possíveis.  
- **Exactly-once:** cada mensagem é processada exatamente uma vez (mais complexo e custoso).

**Funcionamento.** Brokers e frameworks de processamento oferecem mecanismos (acks, commits, checkpoints) para implementar essas garantias. *Exactly-once* geralmente combina idempotência no consumidor com transações ou checkpoints coordenados.

**Exemplo explicado.** Em um sistema de faturamento, *exactly-once* é crítico; em telemetria de sensores, *at-least-once* com deduplicação posterior pode ser aceitável.

---

### Segurança, privacidade e conformidade

**Contexto.** Dados sensíveis exigem criptografia, controle de acesso e políticas de retenção.

**Conceito e funcionamento.**  
- **Criptografia em trânsito e em repouso:** TLS para transporte; chaves gerenciadas para armazenamento.  
- **Autenticação e autorização:** uso de certificados, tokens e políticas de IAM (Identity and Access Management).  
- **Anonimização e minimização de dados:** reduzir exposição de dados pessoais.

**Exemplo explicado.** Sensores que transmitem dados de pacientes devem anonimizar identificadores antes da nuvem e usar canais TLS com autenticação mútua.

---

## Conclusão

Projetar uma plataforma de ingestão e análise de dados em nuvem para sistemas embarcados exige compreender trade-offs entre latência, throughput, durabilidade e custo. Arquiteturas bem-sucedidas combinam processamento em streaming para respostas imediatas e batch para análises históricas, apoiadas por brokers robustos, armazenamento escalável e práticas de segurança. A escolha de garantias de entrega e o dimensionamento correto do pipeline são decisões de engenharia que impactam diretamente a confiabilidade e o custo operacional.

---

## Análise crítica

- **Limitações:** soluções em nuvem introduzem dependência de conectividade; em ambientes com rede intermitente, é necessário projetar tolerância no edge (cache, buffering, sincronização eventual).  
- **Cuidados práticos:** testar cenários de falha (partições de rede, perda de brokers), validar políticas de retenção para evitar custos inesperados e garantir que requisitos de latência sejam medidos em condições reais de produção.  
- **Observações de engenharia:** *exactly-once* é desejável, mas frequentemente caro; avaliar se idempotência e deduplicação resolvem o problema com menor complexidade.

---

## Sugestões de complementação

- **Estudo de caso prático:** implementar um pipeline simples com MQTT no edge, Kafka como broker e um job de streaming (ex.: Apache Flink ou Kafka Streams) para calcular métricas em tempo real. Justificativa: consolida conceitos teóricos com prática. Fonte: Kleppmann (2017).  
- **Laboratório de dimensionamento:** simular cargas variáveis para medir latência e throughput e ajustar parâmetros de retenção e replicação. Justificativa: valida hipóteses de projeto antes da implantação. Fonte: documentação de brokers (Apache Kafka).  
- **Revisão de segurança:** aplicar checklist de criptografia e IAM para ambientes IoT. Justificativa: mitiga riscos de exposição de dados sensíveis.

---

## Exercícios (com resolução detalhada)

### Exercício 1 — Cálculo de taxa de dados e dimensionamento de buffer

**Enunciado.** Uma frota de 2.500 sensores envia leituras a cada 5 segundos. Cada leitura tem 150 bytes. Calcule:  
a) a taxa média de dados em bytes por segundo;  
b) o volume de dados gerado em 24 horas;  
c) se o broker deve manter um buffer de 30 minutos, qual a capacidade mínima em megabytes.

**Resolução.**

- **Passo 1:** determinar eventos por segundo \(N\). Cada sensor envia 1 evento a cada 5 s, então cada sensor gera \(1/5 = 0{,}2\) eventos/s. Para 2.500 sensores:
\[
N = 2500 \times 0{,}2 = 500\ \text{eventos/s}
\]

- **Passo 2:** taxa média \(R\) em bytes/s:
\[
R = N \cdot S = 500 \times 150 = 75{,}000\ \text{bytes/s}
\]
Convertendo para KB/s: \(75{,}000 / 1024 \approx 73{,}24\ \text{KB/s}\).

- **Passo 3:** volume em 24 horas:
\[
V_{24h} = R \times 24 \times 3600 = 75{,}000 \times 86{,}400 = 6{,}480{,}000{,}000\ \text{bytes}
\]
Convertendo para GB: \(6{,}480{,}000{,}000 / (1024^3) \approx 6{,}03\ \text{GB}\).

- **Passo 4:** capacidade do buffer para 30 minutos (\(T = 1800\) s):
\[
C = R \times T = 75{,}000 \times 1800 = 135{,}000{,}000\ \text{bytes}
\]
Convertendo para MB: \(135{,}000{,}000 / (1024^2) \approx 128{,}75\ \text{MB}\).

**Resposta final:**  
a) **75.000 bytes/s** (≈ 73,24 KB/s).  
b) **≈ 6,03 GB** por 24 horas.  
c) **≈ 129 MB** de buffer para 30 minutos.

---

### Exercício 2 — Janela de streaming e média móvel

**Enunciado.** Um pipeline de streaming calcula a média móvel simples de leituras de um sensor com janela de 1 minuto e passo de 10 segundos. Se as leituras a cada 10 segundos são: 20, 22, 21, 23, 24, 22 (6 valores), calcule a média móvel para a janela completa.

**Resolução.**

- **Passo 1:** identificar valores na janela de 1 minuto com passo 10 s. Aqui temos 6 amostras: \(x = [20,22,21,23,24,22]\).

- **Passo 2:** média simples:
\[
\overline{x} = \frac{1}{n}\sum_{i=1}^{n} x_i = \frac{20+22+21+23+24+22}{6} = \frac{132}{6} = 22
\]

**Resposta final:** a média móvel na janela é **22**.

---

### Exercício 3 — Garantia de entrega e duplicatas

**Enunciado.** Um consumidor processa mensagens com garantia *at-least-once*. Explique por que duplicatas podem ocorrer e proponha uma estratégia simples para lidar com duplicatas no consumidor.

**Resolução.**

- **Por que duplicatas ocorrem:** em *at-least-once*, o produtor ou broker pode reenviar mensagens quando não recebe confirmação de processamento; falhas no commit do offset ou reinicialização do consumidor podem levar ao reprocessamento das mesmas mensagens.  
- **Estratégia para lidar com duplicatas:** implementar **idempotência** no consumidor, por exemplo, mantendo um registro (cache) de IDs de eventos processados recentemente e ignorando eventos com ID já visto. Alternativamente, usar transações ou armazenar o último offset processado de forma atômica com o resultado do processamento.

---

## Bibliografia (ABNT)

- KLEPPMANN, Martin. *Designing Data-Intensive Applications: The Big Ideas Behind Reliable, Scalable, and Maintainable Systems*. 1. ed. Sebastopol: O’Reilly Media, 2017.  
- ERL, Thomas; PALLER, Ricardo; et al. *Cloud Computing: Concepts, Technology & Architecture*. 1. ed. Upper Saddle River: Prentice Hall, 2013.  
- APACHE SOFTWARE FOUNDATION. *Apache Kafka Documentation*. 2024.

---

## Materiais complementares (ABNT)

- NIST. *NIST Cloud Computing Reference Architecture*. National Institute of Standards and Technology, 2011.  
- GONZALEZ, J. et al. *Stream Processing Systems: Concepts and Practice*. Revista de Sistemas Distribuídos, 2020.

---
