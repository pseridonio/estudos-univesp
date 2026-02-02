# Aceitabilidade e Usabilidade — Aula detalhada

## Introdução
Esta aula explora os conceitos de aceitabilidade e usabilidade em sistemas interativos, relacionando‑os ao modelo de qualidade ISO/IEC 25010 e às práticas de design centrado no usuário. A videoaula base apresenta definições, exemplos práticos e critérios para medir usabilidade em contexto de uso.

---

## Desenvolvimento

### 1. Aceitabilidade: definição e componentes
- Definição: aceitabilidade geral de um sistema é uma combinação de aceitabilidade social e aceitabilidade prática; aceitabilidade social refere‑se à aceitação cultural e social de uma solução, enquanto aceitabilidade prática refere‑se a parâmetros tradicionais como custo, confiabilidade e compatibilidade com sistemas existentes.  
- Exemplo prático: sistemas de controle físico (ex.: portas de bancos) podem ser eficazes para segurança, mas rejeitados socialmente por gerarem inconveniência ou confusão.

### 2. Usefulness: utilidade versus usabilidade
- Distinção: “usefulness” (utilidade) refere‑se a se o sistema possui as funcionalidades necessárias para atingir um objetivo (requisitos funcionais), já a usabilidade refere‑se à facilidade com que usuários conseguem aprender, lembrar e usar essas funcionalidades; ambos compõem a utilidade prática do sistema.  
- Implicação: projetar apenas funcionalidades não garante aceitabilidade; é necessário que essas funcionalidades sejam descobertas e utilizadas com facilidade pelos usuários.

### 3. Usabilidade: atributos principais segundo Nielsen e ISO
- A usabilidade engloba vários atributos que podem ser avaliados separadamente: facilidade de aprendizado, eficiência no uso, facilidade de lembrar (memorability), baixa taxa de erro e satisfação do usuário.  
- Facilidades:
  - Facilidade de aprendizado: quanto tempo o usuário demora para executar tarefas básicas depois do primeiro contato; avaliada por tempo até atingir proficiência.  
  - Eficiência: produtividade de usuários experientes ao realizar tarefas típicas; avaliada por tempo médio e taxa de sucesso em tarefas repetidas.  
  - Memorability: facilidade com que um usuário volta a usar o sistema após um período sem contato; avaliada por desempenho em tarefas após intervalo de tempo.  
  - Taxa de erro: número e severidade de erros cometidos e capacidade de recuperação sem perda de trabalho.  
  - Satisfação: avaliação subjetiva coletada por questionários (escala Likert) e agregada por média para reduzir variabilidade individual.

### 4. Design centrado no usuário e limites da abordagem
- Princípio: design deve ser centrado no usuário (human‑centered design); conhecer o usuário, as tarefas e o contexto é essencial para priorizar critérios de usabilidade no projeto das interfaces.  
- Nuances: usuários não são designers; eles podem não saber o que precisam, especialmente em sistemas inovadores; portanto, equilibrar insights de usuários com conhecimento de design é necessário para evitar extremos (seguir cegamente preferências ou ignorá‑las).  
- Menos é mais: a sobrecarga de opções e informações aumenta a carga cognitiva; reduzir elementos irrelevantes tende a melhorar usabilidade, sem delegar ao “help” a responsabilidade por um design ruim.

### 5. Trade‑offs entre atributos de usabilidade
- Conflitos típicos: aumentar eficiência via atalhos (teclas de função, abreviações) favorece usuários experientes, mas prejudica memorabilidade e usabilidade de usuários ocasionais; fornecer tutoriais e explicações melhora aprendizado, mas pode reduzir a eficiência para usuários avançados.  
- Estratégia: definir prioridades de usabilidade com usuários prioritários e justificar escolhas por meio de evidências (testes, métricas e contexto de uso).

### 6. Medição prática da usabilidade (passo a passo)
1. Defina tarefas representativas e cenários de uso com base em personas e contextos reais.  
2. Escolha métricas por atributo: taxa de sucesso (S, %), tempo médio de tarefa (T, s), número de erros por tarefa (E), satisfação média (Likert).  
3. Estabeleça metas mensuráveis (ex.: S ≥ 85%, T ≤ 90 s).  
4. Conduza testes moderados com 5–10 participantes representativos; registre vídeo, logs e think‑aloud.  
5. Analise métricas (média, desvio padrão, outliers) e comentários qualitativos; priorize problemas por impacto (Frequência × Severidade) e custo de correção.

### 7. Métricas compostas e exemplos
- Exemplo de métrica composta de usabilidade proposta para comparação entre versões:
  - Fórmula: \(U = \dfrac{S}{1 + T/60}\).  
    - S = taxa de sucesso em porcentagem (0–100).  
    - T = tempo médio de tarefa em segundos.  
    - Lógica: penaliza tempos de tarefa mais longos; valores maiores de U indicam melhor usabilidade.  
  - Exemplo: para S = 88% e T = 40 s, \(U = \dfrac{88}{1 + 40/60} \approx 52{,}8\) (valores maiores indicam melhor desempenho relativo entre versões).

---

## Conclusão
Aceitabilidade e usabilidade são dimensões complementares da qualidade: aceitabilidade engloba fatores sociais e práticos, enquanto usabilidade se concentra na capacidade do usuário de aprender, usar e lembrar o sistema com baixa taxa de erro e satisfação adequada. Medir usabilidade requer traduzir atributos em tarefas, métricas e metas no contexto de uso e priorizar soluções baseadas em evidências coletadas com usuários reais.

---

## Análise crítica
- Benefícios da abordagem apresentada: alinhamento claro entre atributos (ISO), operacionalização em métricas e ênfase na avaliação empírica, o que fortalece justificativas de projeto e decisões de priorização.  
- Limitações: métricas isoladas podem não capturar nuances contextuais; medidas de satisfação são subjetivas e dependem do tamanho e representatividade da amostra; além disso, priorizar um subconjunto de usuários pode deixar outros grupos desassistidos, exigindo cuidado na definição de personas e critérios de priorização.

---

## Sugestões de complementação
- Incluir um exercício prático em aula onde os alunos transformem três requisitos qualitativos de usabilidade em métricas mensuráveis e conduzam um mini‑teste com colegas, coletando S, T e satisfação para calcular U.  
- Fornecer templates: roteiro de teste moderado, planilha para registro de tarefas/tempos/erros e formulário Likert padronizado para satisfação.  
- Ler complementos: capítulos sobre usabilidade em Rocha & Baranauskas e a norma ISO/IEC 25010 para aprofundamento técnico.

---

## Exercícios (com resolução detalhada)

1. Transformar requisitos qualitativos
- Enunciado: a especificação diz “o sistema deve ser fácil de aprender” e “o formulário deve ocasionar poucos erros”. Transforme em métricas e defina metas.  
- Resolução:  
  - Métrica 1 (facilidade de aprendizado): tempo médio para completar tarefa A por novos usuários (T_learning, s); meta: \(T_{learning} \leq 120\) s.  
  - Métrica 2 (taxa de erro no formulário): número médio de erros por submissão (E_sub); meta: \(E_{sub} \leq 0{,}2\) erros/submissão.  
  - Detalhe de coleta: teste moderado com 8 usuários novos, cronometragem e observação direta, registro de cada erro e categorização por severidade.  

2. Calcular índice U e interpretar evolução
- Enunciado: versão A → S = 80%, T = 70 s; versão B → S = 88%, T = 60 s. Calcule U para ambas e indique qual é melhor.  
- Resolução:  
  - Fórmula: \(U = \dfrac{S}{1 + T/60}\).  
  - Versão A: \(U_A = \dfrac{80}{1 + 70/60} = \dfrac{80}{1 + 1{,}1667} = \dfrac{80}{2{,}1667} \approx 36{,}92\).  
  - Versão B: \(U_B = \dfrac{88}{1 + 60/60} = \dfrac{88}{1 + 1} = \dfrac{88}{2} = 44\).  
  - Interpretação: \(U_B > U_A\), portanto a versão B apresenta usabilidade composta melhor segundo essa métrica.  

3. Priorizar correções por impacto
- Enunciado: em um teste com 5 usuários foram registrados três problemas: P1 (freq. 4/5, severidade 3), P2 (freq. 2/5, severidade 2), P3 (freq. 5/5, severidade 1). Calcule Impacto = Frequência × Severidade e ordene prioridades.  
- Resolução:  
  - P1: Impacto = 4 × 3 = 12.  
  - P2: Impacto = 2 × 2 = 4.  
  - P3: Impacto = 5 × 1 = 5.  
  - Ordenação por impacto decrescente: P1 (12), P3 (5), P2 (4). Priorizar correção de P1, depois P3, depois P2.

4. Planejar mini‑teste de memorability
- Enunciado: defina protocolo para avaliar memorability (lembrança) de um fluxo após 7 dias.  
- Resolução:  
  - Passo 1: recrutar 8 participantes que completaram o teste inicial.  
  - Passo 2: após 7 dias sem contato, pedir que realizem a mesma tarefa sem auxílio; cronometrar e registrar erros.  
  - Passo 3: métricas: taxa de sucesso (S_recall), tempo médio (T_recall) e comparação com valores iniciais; meta: \(S_{recall} \geq 0{,}9 \times S_{init}\) e \(T_{recall} \leq 1{,}5 \times T_{init}\).  
  - Passo 4: analisar causas de quedas de desempenho e propor ajustes de interface (prompts, pistas, simplificação).

---

## Bibliografia (formato ABNT)

- ROCHA, H. V. da; BARANAUSKAS, M. C. C. Design e avaliação de interfaces humano‑computador. Campinas: NIED; UNICAMP, 2003. Acesso em: 12 out. 2025.  
- UNIVESP. Interface Humano‑Computador — Aceitabilidade e Usabilidade. Videoaula (YouTube), Professora Alessandra Alaniz Macedo. Disponível em: vídeo da série UNIVESP sobre IHC. Acesso em: 12 out. 2025.  
- INTERNATIONAL ORGANIZATION FOR STANDARDIZATION. ISO/IEC 25010:2011 — Systems and software engineering — System and software quality models. ISO, 2011. Acesso em: 12 out. 2025.

---

Materiais da videoaula usados diretamente como base: transcrição e timestamps do vídeo “Interface Humano‑Computador — Aceitabilidade e Usabilidade”.