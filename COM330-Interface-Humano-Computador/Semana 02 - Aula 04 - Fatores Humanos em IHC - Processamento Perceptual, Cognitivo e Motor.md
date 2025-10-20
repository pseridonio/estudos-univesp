# Fatores Humanos em IHC — Processamento Perceptual, Cognitivo e Motor

## Introdução
A aula apresenta os princípios centrais dos fatores humanos aplicados ao projeto de interfaces, descrevendo o Modelo do Processador de Informação Humana (MPIH), os subsistemas **perceptual**, **cognitivo** e **motor**, fenômenos perceptuais relevantes para o design e implicações práticas para reduzir sobrecarga e frustração do usuário.

---

## Desenvolvimento

### Visão geral e objetivos da aula
A disciplina enfatiza que o design de sistemas interativos deve colocar as **pessoas** no centro do processo de projeto, considerando capacidades fisiológicas, perceptuais e cognitivas ao definir requisitos e soluções de interface.

### Modelo do Processador de Informação Humana (MPIH)
- **Descrição do modelo**: o MPIH abstrai o processamento humano em três subsistemas interativos — perceptual, cognitivo e motor — com memórias associadas (buffers sensoriais e memória de trabalho) que permitem reconhecer, raciocinar e agir sobre estímulos apresentados pela interface.  
- **Elementos e parâmetros relevantes**:  
  - **Buffers sensoriais**: memórias visuais e auditivas de curta duração que guardam a saída sensorial enquanto ocorre a codificação simbólica.  
  - **Memória de trabalho**: espaço ativo que integra informação sensorial e trechos da memória de longa duração para tomada de decisão.  
  - **Timing e ciclos**: o ciclo de processamento (variável T) representa o tempo necessário para que percepções se tornem decisões e ações, usado em modelos preditivos como GOMS/KLM.  
- **Implicação de projeto**: reduzir a dependência de lembrança, favorecer reconhecimento com elementos externos (rótulos, histórico, affordances) e minimizar latência entre percepção e resposta para não sobrecarregar o usuário.

### Sistema perceptual e fenômenos úteis ao design
- **Percepção como transformação de sinais**: estímulos físicos chegam aos órgãos sensoriais e são convertidos em representações internas; o sistema visual inclui subcomponentes (visão central, periférica, movimentação ocular) que interagem para formar a cena percebida.  
- **Reconhecimento por casamento de padrões**: o cérebro usa templates e detectores de padrão para reconhecer formas e símbolos; ícones e símbolos familiares exploram esse mecanismo para reduzir carga cognitiva.  
- **Imagens competitivas e ambiguidade**: excesso de elementos ou sinais conflitantes produz competição perceptual (p. ex., figuras ambíguas), reduzindo velocidade e acurácia da interpretação; hierarquia visual e agrupamento atenuam esse problema.  
- **Adaptação sensorial e perda de saliência**: estímulos estáticos ou constantes perdem destaque (ex.: relógio no pulso que deixa de ser notado); micro‑feedbacks e mudanças sutis mantêm a atenção sem causar fadiga.  
- **Efeitos perceptuais relevantes**: pontos fantasma em grades (efeito de interação entre receptores), afterimages (efeito posterior entre cores complementares) e o papel do movimento ocular na manutenção da percepção — todos esses fenômenos informam escolhas de contraste, ritmo de atualização e design visual para evitar ilusões ou cansaço perceptual.

### Memória, chunking e aprendizado
- **Memória de trabalho e chunks**: a capacidade limitada da memória de trabalho favorece designs que externalizam informação em elementos perceptíveis; organizar informação em chunks facilita automação e desempenho com prática (Power Law of Practice).  
- **Reconhecimento sobre lembrança**: interfaces que apresentam opções visíveis (menus, sugestões) permitem decisões por reconhecimento, reduzindo erros e tempo de busca; affordances perceptíveis reforçam essa estratégia.

### Modelos preditivos: GOMS e KLM
- **GOMS**: família de modelos (Goals, Operators, Methods, Selection rules) para decompor tarefas em operadores e estimar desempenho qualitativo e quantitativo; útil para comparar alternativas de projeto quando tarefas são bem definidas.  
- **KLM**: versão focalizada em níveis motoros (keystroke‑level), atribui tempos típicos a operações motoras e perceptivas para calcular tempo estimado de tarefas e comparar protótipos sem testes extensivos.  
- **Limitação prática**: modelos oferecem estimativas e permitem decisões iniciais de projeto, mas não substituem testes com usuários para avaliar fatores afetivos, variabilidade individual e contexto de uso.

### Tradução desses conceitos em requisitos de interface
- **Reduzir carga cognitiva**: apresentar informações relevantes externamente, usar rótulos claros e histórico, oferecer sugestões e preenchimento automático.  
- **Maximizar legibilidade**: tipografia adequada, contraste texto/fundo, evitar caixa alta para grandes blocos de texto, espaçamento e agrupamento coerente.  
- **Suportar reconhecimento**: usar ícones consistentes, metáforas familiares e affordances evidentes.  
- **Feedback e reversibilidade**: fornecer confirmação de ações e meios fáceis para desfazer operações.  
- **Multimodalidade e redundância**: empregar canais visuais, auditivos e táteis quando adequado para aumentar robustez e acessibilidade.

---

## Conclusão
Compreender os subsistemas perceptual, cognitivo e motor e os fenômenos associados permite projetar interfaces que respeitem limitações humanas, melhorem eficiência, reduzam frustração e ampliem a acessibilidade. Modelos como GOMS e KLM fornecem ferramentas quantitativas úteis para comparar designs, mas devem ser complementados por avaliações empíricas com usuários para capturar aspectos não preditos teoricamente.

---

## Análise crítica
Modelagens cognitivas oferecem abstrações poderosas, porém focar exclusivamente em previsões temporais e operações motoras pode negligenciar emoções, contexto social e variabilidade individual. Tecnologias imersivas e multimodais ampliam canais de interação, mas introduzem novos riscos ergonômicos, sobrecarga perceptual e barreiras de acessibilidade que só são identificados por testes com usuários diversos e iterações de design centrado no usuário.

---

## Sugestões de complementação
- Aplicar prototipagem rápida e testes com usuários para validar suposições do MPIH em contextos reais.  
- Medir indicadores objetivos (tempo, taxa de erro) e subjetivos (esforço, satisfação, NASA‑TLX) para diagnosticar sobrecarga perceptual.  
- Integrar verificações heurísticas (recognition over recall, feedback, prevenção de erros) antes de testes com usuários para identificar problemas óbvios.  
- Considerar acessibilidade desde o início (contraste, navegação por teclado, textos alternativos) e testar com pessoas com deficiências sensoriais e motoras.

---

## Exercícios (com resolução detalhada)

### Exercício 1 — Reconhecimento vs. lembrança  
Enunciado: Explique por que projetar um menu que favoreça reconhecimento é preferível a exigir lembrança de comandos.  
Resolução: a memória de trabalho humana tem capacidade limitada; exigir lembrança obriga o usuário a recuperar comandos da memória de longa duração, aumentando carga cognitiva e probabilidade de erro. Menus visíveis externalizam opções, permitindo decisão por reconhecimento, reduzindo tempo de busca e falhas. Conclusão: priorizar reconhecimento melhora eficiência e redução de erros.

### Exercício 2 — Cálculo KLM simplificado  
Enunciado: Estime o tempo para a tarefa: mover o cursor ao menu (M = 1,2 s), clicar (P = 0,2 s), mover ao item (M ≈ 0,8 s), clicar (P = 0,2 s), digitar 8 caracteres (K = 0,2 s por tecla) e Enter (P = 0,2 s).  
Resolução passo a passo:  
1. Mover ao menu = 1,2 s.  
2. Clicar para abrir = 0,2 s.  
3. Mover ao item = 0,8 s.  
4. Clicar seleção = 0,2 s.  
5. Digitar 8 caracteres = 8 × 0,2 = 1,6 s.  
6. Pressionar Enter = 0,2 s.  
Soma total = 1,2 + 0,2 + 0,8 + 0,2 + 1,6 + 0,2 = **4,2 s**. Interpretação: valor aproximado útil para comparação entre alternativas de design, não medida absoluta de campo.

### Exercício 3 — Identificar fenômeno perceptual e implicação de design  
Enunciado: Cite um fenômeno perceptual visto na aula e descreva uma implicação de design.  
Resolução: **Imagens competitivas**: várias imagens ou sinais competindo por atenção reduzem clareza; implicação: reduzir elementos concorrentes, usar hierarquia visual, agrupar informações relevantes para guiar foco e diminuir tempo de interpretação.

### Exercício 4 — Teste de sobrecarga perceptual  
Enunciado: Proponha um protocolo simples para detectar sobrecarga perceptual em um protótipo de formulário online.  
Resolução passo a passo:  
1. Métricas: tempo para completar cada campo, taxa de erro, número de retornos/edições, pontuação subjetiva de esforço (Likert/NASA‑TLX) e comentários verbais.  
2. Participantes: 8–12 usuários representativos.  
3. Procedimento: realizar tarefas típicas (ex.: preencher cadastro), coletar métricas objetivas e aplicar questionário de esforço; gravar tela e observar fixações e regressões de leitura.  
4. Interpretação: tempos elevados, alta taxa de edição e respostas de esforço elevadas indicam sobrecarga perceptual; recomenda‑se reduzir estímulos visuais, aumentar contraste e reorganizar blocos de informação.

### Exercício 5 — Projeto de affordance para reconhecimento  
Enunciado: Dê um exemplo prático em que uma affordance perceptível facilita reconhecimento.  
Resolução: um botão com sombreamento, cor contrastante e rótulo textual “Enviar” comunica pressibilidade e função sem instruções, permitindo ao usuário reconhecer a ação possível e executar com confiança; reduz a necessidade de lembrança de comandos e diminui erros de ação.

---

## Bibliografia (ABNT)

- CARD, S. K.; MORAN, T. P.; NEWELL, A. The Model Human Processor. In: The Psychology of Human-Computer Interaction. Hillsdale: Lawrence Erlbaum, 1983. Acesso em: 12 out. 2025.  
- ROCHA, Maria Cecília; BARANAUSKAS, Maria da Graça. Design e Avaliação de Interfaces Humano-Computador. São Paulo: [s.n.], [s.d.]. Disponível em: https://learn-us-east-1-prod-fleet02-xythos.content.blackboardcdn.com/5f28363662504/2698356. Acesso em: 12 out. 2025.  
- SHARP, Helen; ROGERS, Yvonne; PREECE, Jenny. Design de Interação: Além da Interação Humano-Computador. [Local]: [Editora], [Edição], [Ano]. Acesso em: 12 out. 2025.  
- UNIVESP. Interface Humano-Computador - Fatores humanos para IHC - Parte 1. UNIVESP, vídeo, 32:26. Disponível em: https://www.youtube.com/watch?v=TjHbnkA7_oA. Acesso em: 12 out. 2025. .  
- BARANAUSKAS, M. C. et al. Análise de Tarefas e GOMS. Material de apoio. Portal UNICAMP. Disponível em: https://tnr.nied.unicamp.br/interhad/nied/interhad/miscelanea/MC750_MO825/material-de-apoio/AnalisedeTarefasGOMS.pdf. Acesso em: 12 out. 2025.

---

## Materiais complementares consultados e recomendados
- **Videoaula base**: UNIVESP — Interface Humano-Computador - Fatores humanos para IHC - Parte 1 (transcrição utilizada para revisão e complementação).  
- **Livro didático**: Rocha; Baranauskas — Design e Avaliação de Interfaces Humano-Computador (capítulos sobre fatores humanos e avaliação).  
- **Modelos e guias**: Card, Moran & Newell — MPIH; documentos e apostilas sobre GOMS/KLM (material UNICAMP).  
- **Práticas de projeto**: recomenda‑se revisar normas e diretrizes de acessibilidade e verificações heurísticas aplicáveis ao contexto da disciplina.

--- 