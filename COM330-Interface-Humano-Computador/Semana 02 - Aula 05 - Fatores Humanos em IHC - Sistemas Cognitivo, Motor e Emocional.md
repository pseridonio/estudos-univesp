# Fatores Humanos em IHC — Sistemas Cognitivo, Motor e Emocional

## Introdução
A aula explora o processamento humano relevante ao projeto de interfaces: memória sensorial e de trabalho, processamento cognitivo, ações motoras, medidas temporais (como a Lei de Fitts) e o papel das emoções na interação, incluindo aplicações da computação afetiva e modelos preditivos como GOMS e KLM.

---

## Desenvolvimento

### Objetivos da aula
- Descrever os subsistemas do Modelo do Processador de Informação Humana (perceptual, cognitivo, motor) e suas memórias associadas.  
- Apresentar fenômenos perceptuais e princípios cognitivos que orientam decisões de projeto.  
- Explicar modelos analíticos (GOMS/KLM) e a Lei de Fitts para prever performance motor-mecânica.  
- Discutir emoções na IHC e aplicações práticas de computação afetiva, como sensores de condutância da pele (Q‑Sensor) usados em pesquisa e aplicações clínicas/comerciais.

---

### Modelo do Processador de Informação Humana (MPIH / MHP)
- Estrutura básica: subsistemas perceptual, cognitivo e motor; buffers sensoriais (icônico, ecoico, háptico), memória de trabalho (curto prazo) estruturada em chunks e memória de longa duração (procedural/semântica).  
- Temporização: ciclos do processador cognitivo e latências perceptuais são parâmetros úteis para estimativas de tempo de reação e para modelos como KLM/GOMS.  
- Implicação de projeto: externalizar informação (promover reconhecimento sobre lembrança), dividir conteúdo em chunks compreensíveis e reduzir requisitos de memória de trabalho para minimizar erros e tempo de decisão.

Referência prática: sínteses pedagógicas do MHP descrevem constantes típicas e operadores usados em KLM (por exemplo, tempos para tecla, movimento, preparação mental) que ajudam a estimar operações motoras e cognitivas simples na interface.

---

### Processamento perceptual e memória
- Buffers sensoriais: informações visuais, auditivas e táteis passam por buffers de curta duração antes de chegarem à memória de trabalho; a separação temporal é crítica para projetar alertas e feedbacks que o usuário realmente note.  
- Chunking e memória de trabalho: agrupar informações reduz a quantidade de itens ativos na memória de trabalho e facilita a automatização por prática (Power Law of Practice). Interfaces devem favorecer reconhecimento (menus, rótulos, affordances visíveis) para reduzir carga cognitiva.  
- Fenômenos a considerar: competição visual entre elementos, perda de saliência (adaptação), e necessidades de hierarquia visual e contraste para evitar confusão perceptual e aumentar velocidade de identificação.

---

### Processamento motor e Lei de Fitts
- Descrição: ações motoras (apontar, clicar, gestos, toque) são quantificáveis; a Lei de Fitts relaciona tempo de apontamento com distância e tamanho do alvo, orientando dimensionamento e posicionamento de controles na interface.  
- Fórmula da Lei de Fitts (forma discreta comum):  
  \[
  T = a + b \cdot \log_2\left(\frac{D}{W} + 1\right)
  \]  
  - T = tempo de movimento; D = distância até o alvo; W = largura do alvo; a,b = constantes empíricas dependentes do dispositivo.  
  - Uso: estimar o ganho de tornar botões maiores ou posicioná-los mais próximos; justificar a colocação de controles frequentemente usados nas bordas e cantos da tela.  
- Implicação de projeto: aumentar W (tamanho), reduzir D (distância) para ações freuqentes; considerar homing time e transições entre teclado e apontador conforme KLM/GOMS.

Citação prática: materiais de ensino em HCI apresentam constantes e exemplos de aplicação da Lei de Fitts e dos tempos do KLM para comparação de alternativas de design.

---

### Modelos analíticos: GOMS e KLM
- GOMS (Goals, Operators, Methods, Selection rules): decomposição da tarefa em objetivos, operadores elementares, métodos aprendidos e regras de seleção entre métodos; adequado para usuários experientes e tarefas bem definidas para prever e comparar desempenho de designs.  
- KLM (Keystroke-Level Model): versão prática que soma tempos de operadores físicos (teclado, apontar, homing, mental, resposta do sistema) para estimar tempo de realização de tarefa.  
- Procedimento KLM (resumo): identificar sequência de operadores para uma tarefa, aplicar constantes (por exemplo, K, P, H, M) e somar para obter tempo estimado; comparar alternativas de interface.  
- Limitações: aplicam-se melhor a usuários experientes e a tarefas roteirizadas; não capturam emoções, aprendizagem inicial, criatividade ou erros inesperados; complementam — não substituem — testes com usuários e medidas subjetivas.

Exemplo ilustrativo KLM (valores típicos): mover apontador (P/pointing) ≈ 1.1 s; pressionar tecla (K) ≈ 0.2 s; preparação mental (M) ≈ 1.35 s — somar operadores fornece estimativa comparativa de tempo para uma sequência de interação.

---

### Emoção, computação afetiva e aplicações
- Papel da emoção: emoções influenciam retenção, atenção e tomada de decisão; estímulos afetivos facilitam transferência de memória de curto para longo prazo e adaptam comportamento do usuário durante a interação.  
- Perspectivas teóricas em IHC: (1) computação afetiva (Picard) — máquinas que detectam e respondem a estados afetivos; (2) interação afetiva/construtivista — ênfase cultural e contextualização das emoções; (3) experiência tecnológica — emoção como parte da experiência total (ex.: music experience, Norman).  
- Exemplos práticos: sensores de condutância da pele (Q‑Sensor) que detectam alterações autonômicas para inferir excitação/estresse; aplicações incluem apoio a treinamento de reconhecimento emocional em autismo e monitoramento de estresse em trabalhadores de call center.  
- Implicações éticas e de projeto: privacidade e consentimento no uso de dados fisiológicos; transparência sobre limites de inferência emocional; evitar decisões automatizadas sensíveis sem supervisão humana.

---

## Conclusão
Integrar conhecimento sobre percepção, cognição, ação e emoção produz requisitos de projeto mais realistas: reduzir carga cognitiva, oferecer affordances claras, otimizar dimensionamento e posicionamento de controles com base em Fitts, usar GOMS/KLM para decisões iniciais e validar com avaliação empírica. Considerar emoções amplia a qualidade da experiência, mas exige cuidados metodológicos e éticos na coleta e uso de sinais afetivos.

---

## Análise crítica
Modelos como MHP, GOMS e KLM são ferramentas poderosas para quantificar e prever aspectos da interação, mas carregam simplificações (assumem usuários competentes, tarefas bem definidas, pouca variabilidade emocional). A computação afetiva amplia possibilidades, porém enfrenta desafios de validade, generalização cultural e riscos de privacidade; práticas de design devem equilibrar modelagem, testes com usuários diversos e avaliação ética contínua.

---

## Sugestões de complementação
- Aplicar KLM/GOMS em exercícios comparativos entre dois protótipos de baixa fidelidade para justificar decisões de layout.  
- Medir tempos e erros em testes com usuários para validar estimativas analíticas.  
- Realizar estudos pequenos com sensores (ex.: Q‑Sensor) somente com consentimento informado e objetivos claros (ex.: detecção de estresse durante tarefas), agregando medidas subjetivas (questionários) para triangulação.  
- Incluir controle de acessibilidade (tamanhos, atalhos de teclado, foco visível) desde a etapa de prototipagem.

---

## Exercícios (com resolução detalhada)

### Exercício 1 — Interpretação do MHP  
Enunciado: Explique a cadeia informação → buffer → memória de trabalho → ação no MHP e a implicação desta cadeia para o design de feedbacks em formulários online.  
Resolução: a informação sensorial entra em buffers (icônico/ecoico) por curto tempo; relevante é movida para memória de trabalho (chunks) para tomada de decisão; decisões acionam operadores motores. Implicação: feedbacks devem aparecer rapidamente e permanecer tempo suficiente para serem percebidos e processados (por exemplo, mensagem de erro persistente, destaque visual), evitando desaparecer antes que o usuário possa integrar a informação e reagir.

### Exercício 2 — Cálculo com Lei de Fitts  
Enunciado: Suponha D = 400 px e W = 40 px; use a forma T = a + b · log2(D/W + 1) com a = 0,1 s e b = 0,12 s. Calcule T e explique cada termo.  
Resolução passo a passo:  
1. Calcular índice de dificuldade: ID = log2(D/W + 1) = log2(400/40 + 1) = log2(10 + 1) = log2(11) ≈ 3,459.  
2. Aplicar fórmula: T = 0,1 + 0,12 × 3,459 ≈ 0,1 + 0,415 ≈ 0,515 s.  
3. Interpretação: tempo estimado ≈ 0,52 s para mover e clicar; a = intercepto (latência base); b = ganho por unidade de ID; resultado orienta decisões sobre aumentar W ou reduzir D para ações frequentes.

### Exercício 3 — Sequência KLM simples  
Enunciado: Para a tarefa: mover cursor ao botão (pointing P = 1,1 s), clicar (K = 0,2 s), digitar 5 caracteres (5 × 0,2 s), e pressionar Enter (0,2 s). Calcule tempo total.  
Resolução: P = 1,1; clique = 0,2; digitar = 1,0; Enter = 0,2; soma = 1,1 + 0,2 + 1,0 + 0,2 = **2,5 s**. Uso: comparar com alternativa que reducesse um dos passos.

### Exercício 4 — Projeto com emoção e ética  
Enunciado: Proponha um experimento com Q‑Sensor para detectar aumento de estresse durante tarefa de cobrança telefônica; descreva medidas, consentimento e análise.  
Resolução resumida: recrutamento voluntário com consentimento informado; coleta simultânea de condutância da pele (Q‑Sensor), medidas de desempenho (tempo, precisão) e autorrelato (escala de estresse). Análise correlacional entre picos de condutância e eventos de alta carga; considerar anonimização, limite de uso dos dados e possibilidade de feedback em tempo real somente com controle humano.

### Exercício 5 — Crítica de modelos  
Enunciado: Cite duas limitações de usar exclusivamente GOMS para definir interface de um sistema educacional para iniciantes.  
Resolução: (1) GOMS modela usuários experientes, portanto não captura aprendizagem inicial nem erros típicos de iniciantes; (2) não considera motivação, emoções ou variação cultural que afetam aceitação e retenção, elementos fundamentais em educação.

---

## Bibliografia (formato ABNT)

- CARD, S. K.; MORAN, T. P.; NEWELL, A. The Psychology of Human-Computer Interaction. Hillsdale: Lawrence Erlbaum, 1983.  
- UNIVESP. Interface Humano-Computador — Fatores humanos para IHC — Parte 2. Videoaula UNIVESP, 6 out. 2021. Transcrição. Disponível em: https://www.youtube.com/watch?v=uFp2hkiFA-E. Acesso em: 12 out. 2025.  
- HCI 440. Model Human Processor. DePaul University. Disponível em: https://facsrv.cs.depaul.edu/~cmiller/hci440/materials/humanProcessor.html. Acesso em: 12 out. 2025.  
- GOMS. Wikipedia. Disponível em: https://en.wikipedia.org/wiki/GOMS. Acesso em: 12 out. 2025.  
- Models of information processing. Nottingham / Penn State notes. Disponível em: https://acs.ist.psu.edu/misc/nottingham/ihf/notes/extra/models.html. Acesso em: 12 out. 2025.

---

## Materiais complementares (consultados)
- Transcrição da videoaula UNIVESP — Fatores humanos para IHC — Parte 2 (uso direto para estrutura e exemplos).  
- Recursos docentes sobre MHP, GOMS e KLM (DePaul, Penn State) para constantes e exemplos de aplicação prática.  
- Enciclopédia/entradas técnicas sobre GOMS para variações e limitações metodológicas.

--- 