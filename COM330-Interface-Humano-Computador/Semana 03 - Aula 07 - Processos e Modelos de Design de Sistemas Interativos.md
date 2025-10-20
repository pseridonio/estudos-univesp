# Processos e Modelos de Design de Sistemas Interativos

## Introdução
Esta aula apresenta processos e modelos para o desenvolvimento de sistemas interativos, enfatizando a distinção entre modelos centrados no produto e modelos centrados no usuário, o papel da prototipagem como técnica de redução de risco e a importância da avaliação iterativa durante o projeto. O conteúdo baseia‑se na videoaula "Processos e Modelos de Design de Sistemas Interativos" e em material institucional sobre a disciplina de IHC.

---

## Desenvolvimento

### 1. O que é processo de software aplicado a sistemas interativos
- Definição: processo de software é um conjunto ordenado de atividades (especificação de requisitos, projeto, implementação, teste e manutenção) que objetiva produzir um produto de software de forma eficiente, previsível e conforme as necessidades do projeto e do negócio.  
- Por que importa em IHC: projetar interfaces exige articular atividades técnicas (implementação, teste) com atividades centradas no humano (pesquisa com usuários, prototipagem, avaliação), portanto o processo de desenvolvimento deve explicitar momentos para descoberta, prototipagem e avaliação com usuários reais.

Fonte do enunciado e transcrição da aula: videoaula UNIVESP, transcrição utilizada como base.

---

### 2. Modelos clássicos de processo e suas características

#### 2.1 Estratégia sem processo (ad hoc)
- Características: desenvolvimento organizado por tentativa e erro; pouca ou nenhuma documentação; alto risco de manutenção e continuidade.  
- Impacto em IHC: pouca garantia de qualidade de interação; difícil replicar decisões de projeto ou portar conhecimento entre ciclos de desenvolvimento.

#### 2.2 Modelo Cascata (waterfall)
- Estrutura: fases sequenciais e bem definidas — requisitos → projeto → implementação → testes → manutenção.  
- Vantagens: previsibilidade, documentação e facilidade de gestão em contextos bem compreendidos.  
- Limitações: difícil acomodar descoberta tardia de requisitos de usabilidade; problemas de interação muitas vezes aparecem apenas em fases finais, o que aumenta custo de correção.

#### 2.3 Modelo Espiral (Boehm)
- Estrutura: iterações em espiral; cada volta contém planejamento, análise de risco, engenharia e avaliação; prototipagem e análise de risco são elementos centrais.  
- Vantagem principal para IHC: permite inserir protótipos e avaliações com clientes a cada volta, reduzindo risco de construir interfaces que não atendem usuários.

#### 2.4 Modelo Iterativo e Modelos Centrados no Usuário
- Características: ciclos repetidos de descoberta, análise, projeto, prototipagem e avaliação; avaliação é atividade central e contínua; o processo pode começar por qualquer uma das atividades (ex.: começar por protótipo) e o fluxo é flexível.  
- Importância: favorece incorporação de descobertas de usuários, adapta-se a mudanças de requisitos e permite refinamento progressivo da interface.

---

### 3. Design centrado no humano (human-centered design)
- Conceito: processo de design orientado às necessidades, desejos e contexto de uso dos usuários; metas do projeto são *informadas* por investigação empírica (entrevistas, observação, testes) e não por suposições do desenvolvedor.  
- Atividades essenciais:
  - Descoberta: identificar necessidades e desejos dos usuários por meio de entrevistas, observação e análise de soluções existentes.  
  - Análise e modelagem: organizar requisitos, priorizar funcionalidades, criar cenários e mapear tarefas.  
  - Projeto e prototipagem: conceber soluções e materializá‑las em artefatos testáveis (wireframes, protótipos de papel, protótipos interativos).  
  - Avaliação: teste com usuários, avaliação heurística e refinamento — atividade central em modelos centrados no usuário.

---

### 4. Prototipagem: objetivos, tipos e cuidados
- Objetivos principais:
  - Reduzir risco (validar hipóteses de uso antes da implementação plena).  
  - Comunicar ideias para stakeholders e usuários.  
  - Permitir testes de usabilidade rápidos e econômicos.  
- Tipos comuns:
  - Baixa fidelidade: esboços e protótipos em papel; rápidos, baratos, ótimos para explorar fluxos iniciais.  
  - Média fidelidade: wireframes digitais ou protótipos com interação limitada; úteis para testar navegação e hierarquia.  
  - Alta fidelidade: protótipos interativos que simulam a interface final; indicados para validar micro‑interações, visuais e performance percebida.  
- Cuidados com protótipos: comunicar claramente ao usuário que o artefato é um protótipo para evitar falsas expectativas; escolher fidelidade adequada ao objetivo do teste; prevenir que stakeholders confundam protótipo com produto final.

---

### 5. Avaliação contínua e integração ao processo
- A avaliação não é um evento final: em modelos centrados no usuário ela é o núcleo do processo, conduzindo iterações e refinamentos.  
- Métodos de avaliação: testes de usabilidade com usuários reais, avaliações heurísticas por especialistas, análises quantitativas de métricas de uso e estudos de campo.  
- Integração prática: definir pontos de verificação no processo (por exemplo, após cada sprint, ou ao final de cada volta da espiral) para realizar testes e priorizar correções com base em evidência empírica.

---

## Conclusão
Modelos de processo para sistemas interativos variam entre abordagens sequenciais (cascata), iterativas (espiral, modelos iterativos) e centradas no usuário. Para IHC, modelos que incorporam prototipagem e avaliação contínua tendem a reduzir risco e produzir interfaces mais adequadas ao uso real, pois permitem validar hipóteses de interação com usuários e ajustar requisitos ao longo do desenvolvimento.

---

## Análise crítica
- Nem sempre modelos sequenciais são inadequados; em projetos com requisitos estáveis e regulamentados o cascata pode ser útil. Entretanto, interfaces exigem descoberta contínua de requisitos humanos; processos que não incluem iteração e avaliação com usuários correm maior risco de produzir soluções inadequadas.  
- Prototipagem generalizada é poderosa, mas mal aplicada pode criar ilusões de entendimento (usuários confundem protótipo com produto final). Comunicar propósito e fidelidade do protótipo é fundamental para obter feedback útil.  
- Custos do design centrado no humano existem, mas a literatura e práticas profissionais mostram que o custo inicial é compensado pela redução de retrabalho e pelo aumento da aceitabilidade do produto no mercado.

---

## Sugestões de complementação
- Implementar um fluxo mínimo prático: descoberta rápida (entrevistas + análise competitiva) → protótipo de baixa fidelidade → teste com 5 usuários (Nielsen) → refinamento → protótipo interativo → teste de usabilidade ampliado.  
- Adotar métricas para justificar investimento em IHC (ex.: redução de erros críticos, tempo de tarefa, Net Promoter Score) para demonstrar retorno sobre o investimento em design centrado no humano.  
- Documentar decisões e evidências de avaliação em um repositório de projeto para apoiar manutenção e evolução.

---

## Exercícios (com resolução detalhada)

1) Explique por que a prototipagem é considerada um mecanismo de redução de risco no modelo espiral.  
Resolução: no modelo espiral cada volta inclui análise de risco e engenharia; protótipos servem para validar suposições (stakeholders irão aceitar o fluxo? usuários conseguem completar tarefas?) antes de avançar para etapas custosas de implementação. Avaliar um protótipo revela problemas de usabilidade e requisitos mal interpretados, permitindo correções antecipadas e reduzindo o risco técnico e de aceitabilidade do produto final.

2) Compare cascata e modelo iterativo em termos de manejo de requisitos de usabilidade.  
Resolução: cascata exige requisitos majoritariamente estáveis no início; mudanças de usabilidade descobertas tardiamente são custosas. O modelo iterativo permite revisitar requisitos a cada iteração, incorporar feedback de testes e ajustar interfaces continuamente, tornando‑o mais adequado para aspectos de IHC, onde descobertas com usuários são frequentes.

3) Descreva um protocolo prático, em 5 passos, para transformar informações de descoberta em um protótipo testável numa semana.  
Resolução passo a passo:  
- Dia 1: entrevistas rápidas (3–5 usuários) e análise de concorrentes para identificar 3 tarefas críticas.  
- Dia 2: mapear fluxos de tarefas e priorizar funcionalidades essenciais.  
- Dia 3: desenhar wireframes em baixa fidelidade (papel ou digital).  
- Dia 4: construir protótipo interativo de média fidelidade (ferramentas como Figma/Adobe XD).  
- Dia 5: testar com 5 usuários focados nas 3 tarefas; registrar métricas (sucesso, tempo, comentários) e extrair 3 prioridades de melhoria para próxima iteração.

4) Que argumentos objetivos você usaria para convencer um gerente que questiona o custo do design centrado no humano?  
Resolução: apresentar evidências de economia: redução de retrabalho (menores custos de correção de problemas detectados tardiamente), aumento da taxa de conversão/uso, diminuição de suporte e churn; propor métricas antes/depois (tempo de tarefa, taxa de erro, satisfação) e estimar retorno econômico comparando custos de design com ganhos operacionais e de retenção. Complementar com estudo de caso ou benchmark setorial aumenta persuasão.

5) Cite três cuidados ao conduzir testes com protótipos e explique a razão de cada um.  
Resolução:  
- Comunicar que é protótipo (evitar falsas expectativas e feedback enviesado).  
- Escolher fidelidade adequada (baixa fidelidade para fluxos e alta para micro‑interações) para responder às perguntas de pesquisa corretamente.  
- Registrar e documentar evidências (vídeo, anotações, métricas) para permitir priorização objetiva das mudanças e rastreabilidade das decisões de projeto.

---

## Bibliografia (formato ABNT)

- UNIVESP. Interface Humano-Computador - Processos e Modelos de Design de Sistemas Interativos. Videoaula UNIVESP, Professora Alessandra Alaniz Macedo. Disponível em: https://www.youtube.com/watch?v=Rzlx9WQ98c8. Acesso em: 19 out. 2025.  
- UNIVERSIDADE VIRTUAL DO ESTADO DE SÃO PAULO. Plano de Ensino — Interfaces Humano-Computador. Disponível em: https://assets.univesp.br/blackboard/plano-de-ensino/disciplinas/EES301.pdf. Acesso em: 19 out. 2025.  
- ROCHA, H. V. da; BARANAUSKAS, M. C. C. Design e avaliação de interfaces humano-computador. Campinas: NIED; Unicamp, 2003. (Material complementar recomendado).  
- SHARP, Helen; ROGERS, Yvonne; PREECE, Jenny. Design de Interação: Além da Interação Humano-Computador. (Material recomendado).  

---

## Materiais complementares (consultados e recomendados)
- Transcrição e vídeo UNIVESP — "Processos e Modelos de Design de Sistemas Interativos" (base desta aula).  
- Plano de ensino Univesp — ementa e conteúdos programáticos da disciplina de IHC.  
- Rocha; Baranauskas — Design e avaliação de interfaces humano‑computador (pdf disponibilizado no ambiente do curso) — para aprofundamento de métodos de avaliação e prototipagem.

---