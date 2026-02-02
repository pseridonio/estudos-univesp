# Qualidade em Uso e ISO/IEC 25010

## Introdução
Apresenta‑se uma aula detalhada sobre qualidade em uso aplicada a sistemas interativos, com base na videoaula “Qualidade e desenvolvimento de sistemas interativos” e no modelo ISO/IEC 25010. A aula explica características, métricas operacionais, relação com usabilidade e procedimentos práticos para medir e priorizar qualidade em projetos de IHC.

---

## Desenvolvimento

### Modelo de qualidade e foco em IHC
A família ISO/IEC 25000 define modelos de qualidade do produto e de qualidade em uso; para IHC o foco principal é a qualidade em uso, que avalia o quanto um sistema permite que usuários atinjam objetivos em contextos reais. 

#### Características centrais da qualidade em uso
- **Eficácia**: grau com que usuários alcançam metas com precisão e integridade.  
- **Eficiência**: relação entre recursos gastos (tempo, esforço) e o nível de eficácia alcançado.  
- **Satisfação (User Experience)**: avaliação subjetiva do usuário sobre emoções e aceitação do sistema.  
- **Liberdade de risco**: capacidade do sistema de mitigar riscos potenciais (segurança, danos) durante o uso.  
- **Cobertura de contexto**: grau em que o produto mantém as características anteriores em contextos especificados e além daqueles inicialmente identificados. 

### Como transformar características em métricas mensuráveis
1. Escolher propriedades observáveis por característica (ex.: para eficácia → taxa de sucesso; para eficiência → tempo médio de tarefa).  
2. Definir fórmula, unidade e método de coleta (ex.: tempo em segundos via cronometragem, taxa em % via testes moderados).  
3. Estabelecer meta aceitável e periodicidade de medição (ex.: S ≥ 85%, Tm ≤ 90 s).  
4. Instrumentar coleta (logs, gravações, questionários Likert) e analisar distribuições, médias e outliers. 

#### Exemplo operacional — métrica de frequência de erros
- Definição: X = A / T, onde A = número de erros observados em uma sessão/atividade e T = tempo gasto ou número de tarefas executadas; valores próximos a zero indicam melhor eficácia. 

#### Exemplo operacional — satisfação
- Coleta: questionário com escala Likert aplicado após tarefas representativas; agrega‑se média e distribuição por item para identificar pontos críticos de experiência. 

### Relacionando qualidade do produto (interno/externo) à qualidade em uso
- Propriedades internas (acoplamento, complexidade) e externas (tempo de resposta, taxa de falhas) suportam ou prejudicam a qualidade em uso; medições internas devem ser combinadas com avaliações em contexto para garantir que metas de uso (eficácia/eficiência/satisfação) sejam atingidas. 

### Processo prático para especificar requisitos de qualidade em um projeto IHC
1. Mapear objetivos do usuário e cenários de uso.  
2. Selecionar 2–4 características ISO 25010 críticas para o domínio (ex.: usabilidade, confiabilidade, segurança, cobertura de contexto).  
3. Para cada característica, definir 2 métricas mensuráveis com fórmulas, métodos de coleta e metas.  
4. Planejar ciclos de medição: protótipo → teste com usuários (5–10) → análise → priorização → iteração.  
5. Documentar evidências e evoluir metas conforme dados empíricos e custo/benefício. 

### Priorização de problemas e trade‑offs
- Use matriz impacto × esforço e métricas compostas (ex.: Impacto = Frequência × Severidade) para priorizar correções que melhoram qualidade em uso com menor custo. Metas conservadoras e validação iterativa reduzem risco e retrabalho. 

---

## Conclusão
Aplicar a ISO/IEC 25010 ao design de interfaces implica traduzir características de alto nível em métricas mensuráveis e testáveis em contexto. Combinar medições de produto com avaliações de uso (testes de usabilidade, questionários, logs) é essencial para garantir eficácia, eficiência, satisfação, mitigação de riscos e cobertura de contexto nos sistemas interativos.

---

## Exercícios (com resolução detalhada)

1. Escolher métricas
- Enunciado: para um ambiente de ensino remoto, selecione 3 características críticas e proponha 2 métricas para cada.  
- Resolução:  
  - Usabilidade: taxa de sucesso na submissão de atividade (S% via teste moderado); tempo médio para submissão (Tm em s via cronometragem).  
  - Confiabilidade: número de sessões interrompidas por erro crítico por mês (F = falhas/mês via logs); MTTR (horas) para incidentes críticos via ticketing system.  
  - Cobertura de contexto: taxa de sucesso em ambientes móveis vs desktop (comparação % entre contextos) e percentual de funcionalidade disponível offline (%) em cenários com conectividade limitada. 

2. Calcular frequência de erros
- Enunciado: em um teste, um usuário cometeu 6 erros em 3 tarefas que levaram 180 s. Calcule X = A/T (erros por tarefa) e X' = A/time (erros por segundo).  
- Resolução passo a passo:  
  - A = 6; T_tarefas = 3 → X = 6 / 3 = 2 erros por tarefa.  
  - Tempo T_seg = 180 s → X' = 6 / 180 = 0,033 erros por segundo. Interpretação: X menor é melhor; comparar com benchmark para priorizar correções. 

3. Índice composto de usabilidade
- Enunciado: use U = S / (1 + T/60); calcule U para S = 88% e T = 40 s.  
- Resolução: substituir na fórmula: U = 88 / (1 + 40/60) = 88 / (1 + 0,6667) = 88 / 1,6667 ≈ 52,8. Valores maiores indicam melhor usabilidade; comparar entre versões para medir evolução. 

4. Planejar um teste de usabilidade rápido
- Enunciado: protocolo de 5 etapas para avaliar eficácia de fluxo de login.  
- Resolução: (1) definir tarefa (login com credenciais válidas); (2) recrutar 5 participantes representativos; (3) conduzir teste moderado com think‑aloud, cronometragem e registro de erros; (4) calcular taxa de sucesso e tempo médio; (5) priorizar correções se sucesso < 80% ou tempo médio > objetivo (p.ex., 45 s). 

---

## Bibliografia

- UNIVESP. Interface Humano-Computador — Qualidade e desenvolvimento de sistemas interativos. Videoaula (YouTube). Transcrição utilizada como base para esta aula.   
- INTERNATIONAL ORGANIZATION FOR STANDARDIZATION. ISO/IEC 25010:2011 — Systems and software engineering — System and software quality models. ISO, 2011.  
- ROCHA, H. V. da; BARANAUSKAS, M. C. C. Design e avaliação de interfaces humano‑computador. Campinas: NIED; UNICAMP, 2003.

--- 