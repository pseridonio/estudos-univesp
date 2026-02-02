# Qualidade de Software e Processos de Desenvolvimento

## Introdução
Apresenta‑se uma visão integrada sobre qualidade de software e modelos de processo de desenvolvimento aplicados a sistemas interativos. A aula aborda definições de qualidade, fatores que a influenciam, visões concorrentes sobre qualidade, modelos de ciclo de vida (incluindo cascata, iterativo, espiral e estrela), o papel da avaliação e da IHC na coleta de requisitos e na validação, e práticas para integrar qualidade e usabilidade ao processo de desenvolvimento.

---

## Desenvolvimento

### 1. O que é qualidade de software
- Definição funcional: qualidade é o grau em que o software atende aos requisitos explícitos e implícitos dos stakeholders; inclui conformidade à especificação e atendimento às metas do usuário.  
- Visões sobre qualidade (síntese):
  - Transcendental: qualidade percebida, difícil de definir formalmente.  
  - Produto: características inerentes (desempenho, capacidade, precisão).  
  - Manufatura: conformidade com especificações e normas.  
  - Usuário: atendimento às metas e tarefas do usuário (usabilidade).  
  - Valor: relação custo‑benefício para o cliente.  
- Implicação para IHC: para sistemas interativos, a visão do usuário e a usabilidade muitas vezes determinam se o sistema é considerado “de qualidade” pelo público, mesmo que outros atributos técnicos (ex.: precisão) estejam corretos.

#### 1.1 Atributos relevantes (exemplos)
- Usabilidade (eficácia, eficiência, satisfação).  
- Confiabilidade (disponibilidade, tolerância a falhas).  
- Manutenibilidade (facilidade de correção e evolução).  
- Segurança (proteção contra acessos indevidos).  
- Portabilidade (rodar em diferentes hardwares/plataformas).  
Escolha de atributo prioritário depende do domínio: para plataformas de ensino a distância, usabilidade e disponibilidade podem ser críticos; para sistemas médicos, precisão e segurança são prioritários.

---

### 2. Fatores que afetam a qualidade do software
- Processo e métodos: uso de processos bem definidos, métodos de engenharia e técnicas de verificação/validação melhora a qualidade.  
- Pessoas: formação, experiência e organização da equipe influenciam diretamente resultados.  
- Tecnologia: linguagens, ferramentas, frameworks e infraestrutura impactam chance de erros e eficiência de desenvolvimento.  
- Gestão (tempo/orçamento): prazos apertados e baixos recursos reduzem margem para prevenção e avaliação, elevando custo de falhas.  
- Avaliação contínua: prevenção (processos), avaliação (testes, inspeções) e correção (falhas) têm custos diferentes; investir em prevenção e avaliação reduz custo de falhas posteriores.

---

### 3. Modelos de ciclo de vida e relação com qualidade e IHC
- Objetivo dos modelos: organizar atividades de especificação, projeto, implementação, testes, implantação e manutenção; cada modelo define como e quando validar com clientes/usuários.

#### 3.1 Modelo Cascata
- Sequência linear: requisitos → projeto → implementação → teste → implantação.  
- Vantagens: previsibilidade, documentação; adequado quando requisitos são estáveis.  
- Desvantagens: baixa adaptabilidade para descobrir problemas de usabilidade tarde, alto custo de correção de falhas encontradas em etapas finais.

#### 3.2 Modelos Iterativos e Espiral
- Iterações curtas com ciclos de refinamento; espiral enfatiza análise de riscos e prototipagem a cada volta.  
- Vantagens: permitem inserir prototipagem e avaliação com usuários cedo, reduzindo risco de construir interfaces inadequadas.

#### 3.3 Modelo Estrela (ondas alternantes)
- Similar ao cascata em atividades, mas com avaliação central e possibilidade de início em qualquer ponto; cada atividade pode ser revisitada conforme resultados de avaliação.  
- Ideal para IHC: avaliação contínua (testes de usabilidade, protótipos) guia as decisões; processo centrado no usuário.

#### 3.4 Desenvolvimento ad hoc ("caótico")
- Início direto da codificação sem processo formal; pode funcionar para experimentos rápidos, mas tende a gerar documentação e qualidade deficientes em projetos maiores.

---

### 4. Integração de IHC e levantamento de requisitos ao processo
- Levantamento de requisitos centrado no usuário: entrevistas, observação, personas, cenários, análise de tarefas e protótipos para eliciar necessidades reais.  
- Modelos centrados no humano promovem: coleta iterativa de requisitos, prototipagem precoce e testes com usuários, o que melhora a validade dos requisitos e reduz retrabalho.  
- Papel do designer: entender usuários, organizar experiências passadas e traduzir em requisitos e critérios de aceitação.

---

### 5. Avaliação, testes e métricas
- Tipos de testes:
  - Testes unitários: verificam cada módulo isoladamente.  
  - Testes de integração: verificam interação entre módulos após testes unitários.  
  - Testes de sistema e aceitação: verificam o sistema como um todo e o alinhamento às necessidades do usuário.  
  - Testes de usabilidade: medem eficácia, eficiência e satisfação em tarefas representativas.  
- Métricas úteis em IHC: taxa de sucesso na tarefa, tempo médio de tarefa, número de erros por tarefa, satisfação (escala Likert), Net Promoter Score para aceitação geral.  
- Interpretação: combine métricas objetivas e subjetivas para priorizar correções (ex.: alto impacto × alta frequência → prioridade).

---

### 6. Práticas recomendadas para garantir qualidade em sistemas interativos
- Inserir prototipagem e testes com usuários desde as fases iniciais.  
- Definir hipóteses de uso e propor métricas antes dos testes (ex.: “80% de sucesso na tarefa X”).  
- Automatizar testes quando possível (unitários, integração) e combinar com avaliações humanas para usabilidade.  
- Adotar revisões de código e inspeções de requisitos/artefatos.  
- Criar um design system e componentes reutilizáveis para consistência e redução de erros.  
- Documentar decisões e evidências de avaliação para rastreabilidade.

---

## Conclusão
Qualidade de software é multifacetada; para sistemas interativos, a usabilidade e a adequação ao contexto do usuário são, frequentemente, atributos centrais. Modelos de processo que incorporam avaliação iterativa e atividades centradas no humano (protótipos, testes com usuários, análise de tarefas) tendem a produzir produtos de maior qualidade percebida e menor custo de correção. Investir em processo, pessoas e avaliação contínua é a estratégia mais eficaz para produzir software confiável, utilizável e valioso.

---

## Análise crítica
- Modelos sequenciais ainda têm espaço em contextos regulados com requisitos estáveis, mas raramente atendem bem a descobertas de usabilidade emergentes.  
- Protótipos de alta fidelidade devem ser usados com cautela: embora ajudem a validar visuais e micro‑interações, usados cedo podem mascarar problemas conceituais e gerar expectativas indevidas.  
- A pressão por prazos curtos é um dos maiores inimigos da qualidade; justificar avaliações com métricas e estimativas de redução de retrabalho facilita alocar tempo para usabilidade.

---

## Sugestões de complementação
- Incluir um caso prático guiado: desde elicitação de requisitos com entrevistas até testes de usabilidade em protótipo (wireframe → protótipo de média fidelidade → métricas e priorização).  
- Acrescentar templates: roteiro de entrevista, checklist de usabilidade e planilha para registro de métricas (tempo, sucesso, comentários).  
- Links para leitura adicional: ISO/IEC 25010 (modelo de qualidade), guias de Nielsen para usabilidade e documentos de Rocha & Baranauskas sobre modelos de IHC.

---

## Exercícios (com resolução detalhada)

1) Exercício — Priorizar requisitos de usabilidade  
   - Enunciado: você coletou 12 problemas de usabilidade em um protótipo. Cada problema tem frequência (número de usuários afetados em 5 testes) e severidade (1 leve, 2 moderada, 3 grave). Calcule o "impacto" definido como Impacto = Frequência × Severidade e classifique os três problemas com maior prioridade.  
   - Resolução passo a passo:  
     1. Para cada problema, multiplique a frequência pela severidade. Ex.: Problema A: frequência 4, severidade 3 → Impacto = 4 × 3 = 12.  
     2. Repita para os 12 problemas.  
     3. Ordene os problemas pelo valor de Impacto decrescente.  
     4. Os três com maior Impacto são as prioridades de correção imediata.  
   - Observação: esse método equilibra frequência e gravidade; ajustes podem incluir custo de correção para priorização prática.

2) Exercício — Escolha de modelo de processo  
   - Enunciado: descreva qual modelo de ciclo de vida você adotaria para um sistema de telemedicina com requisitos parcialmente conhecidos e necessidade de validação de usabilidade, justificando a escolha.  
   - Resolução: optar pelo modelo iterativo/espiral ou estrela; justificativa: requisitos clínicos e de usabilidade precisam ser descobertos e validados com profissionais e pacientes; iterações com prototipagem e análise de risco permitem validar segurança e fluxos críticos antes de implementação completa; avaliação contínua reduz chance de falhas graves em produção.

3) Exercício — Planejar um teste de usabilidade rápido  
   - Enunciado: elabore um protocolo de teste moderado para avaliar o fluxo de agendamento em uma plataforma de ensino. Inclua metas, tarefas, métricas e número de participantes.  
   - Resolução passo a passo:  
     1. Metas: verificar se usuário consegue agendar aula em ≤ 3 minutos e com no máximo 1 erro.  
     2. Tarefas: “localizar disciplina X, selecionar horário Y e confirmar agendamento”.  
     3. Métricas: tempo de tarefa, sucesso/fracasso, número de erros, satisfação (escala 1–5).  
     4. Participantes: 5 usuários representativos para detectar os principais problemas.  
     5. Protocolo: consentimento, tarefa, think‑aloud, registro (cronometragem + notas), entrevista pós‑tarefa.  
     6. Análise: identificar problemas com baixa taxa de sucesso e priorizar correções conforme impacto.  

4) Exercício — Correlação entre teste unitário e usabilidade  
   - Enunciado: explique por que testes unitários não substituem testes de usabilidade em sistemas interativos.  
   - Resolução: testes unitários verificam corretude de componentes isolados (ex.: cálculo correto, API responde), mas não avaliam interação, fluxo, clareza de labels, expectativa do usuário nem erros de navegação que emergem do uso real; testes de usabilidade com usuários reais são necessários para detectar problemas de compreensão, discoverability e satisfação que não aparecem em testes automatizados.

5) Exercício — Métrica composta de qualidade  
   - Enunciado: crie uma métrica simples que combine taxa de sucesso (S, em %) e tempo médio de tarefa (T, em segundos) para gerar um índice de usabilidade U onde valores maiores indicam melhor usabilidade. Proponha fórmula, explique variáveis e dê um exemplo.  
   - Resolução:  
     1. Fórmula proposta: U = S / (1 + T/60).  
        - S = taxa de sucesso em percentagem (0–100).  
        - T = tempo médio de tarefa em segundos.  
        - Lógica: penaliza casos em que o tempo é alto; denominação normaliza pelo fator (1 + T/60) para reduzir o impacto linear do tempo.  
     2. Exemplo: S = 90 (%), T = 30 s → U = 90 / (1 + 30/60) = 90 / (1 + 0,5) = 90 / 1,5 = 60.  
     3. Interpretação: quanto maior U, melhor; comparar U entre versões para decidir melhorias.

---

## Bibliografia (formato ABNT)

- ROCHA, H. V. da; BARANAUSKAS, M. C. C. Design e avaliação de interfaces humano‑computador. Campinas: NIED; UNICAMP, 2003. Acesso em: 12 out. 2025.  
- BENYON, D. Interação humano‑computador. 2. ed. São Paulo: Pearson, 2011. Acesso em: 19 out. 2025.  
- SOBRAL, W. S. Design de interfaces: introdução. Rio de Janeiro: Érica, 2019. Acesso em: 19 out. 2025.  
- PRESSMAN, R. S.; MAXIM, B. R. Engenharia de software. 9. ed. Porto Alegre: AMGH, 2021. Acesso em: 19 out. 2025.  
- ISO/IEC 25010 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE). ISO, 2011. Acesso em: 19 out. 2025.  
- Interaction Design Foundation. Interaction Design — Brief Intro. Acesso em: 19 out. 2025.

---

## Materiais complementares (consultados)
- Videoaula UNIVESP — Gerência e Qualidade de Software (visão geral sobre qualidade e impacto de defeitos). Acesso em: 12 out. 2025.  
- Rocha & Baranauskas — capítulo sobre modelos e avaliação em IHC. Acesso em: 12 out. 2025.  
- Documentos e normas ISO/IEC 25010 para definição de qualidade de produto de software. Acesso em: 19 out. 2025.

--- 
