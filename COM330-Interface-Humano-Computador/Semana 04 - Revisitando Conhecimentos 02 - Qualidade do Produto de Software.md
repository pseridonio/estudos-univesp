# Qualidade do Produto de Software — Aula detalhada

## Introdução
Apresenta‑se um mapeamento aprofundado sobre o modelo de qualidade de produto de software (família ISO/IEC 25000), suas categorias (qualidade do produto, qualidade em uso, qualidade de dados), a hierarquia característica → subcaracterística → propriedades mensuráveis e as implicações práticas para projetos de IHC e avaliação de usabilidade.

---

## Desenvolvimento

### 1. Visão geral do modelo ISO/IEC 25000 e utilidade prática
- A família ISO/IEC 25000 define modelos, termos e normas para especificar e avaliar requisitos de qualidade de produto de software; ela substitui e engloba versões anteriores (por exemplo, ISO 9126) e organiza a definição de qualidade em diversas partes e normas específicas para medição e requisitos.  
- Utilidades principais: (1) especificar requisitos de qualidade quantificáveis; (2) orientar seleção de métricas e propriedades mensuráveis; (3) subsidiar avaliações e comparações entre versões ou produtos.

Referência prática: ao definir “qualidade” para um projeto, documente explicitamente quais características e quais propriedades serão priorizadas e medidas durante o desenvolvimento e na aceitação.

### 2. Três níveis do modelo e diferença entre eles
- Qualidade do produto: atributos internos e externos do software que desenvolvedores e engenheiros conseguem medir diretamente (por exemplo, linhas de código, acoplamento, tempos de execução).  
- Qualidade em uso: depende do contexto de execução e do usuário; mede eficácia, eficiência, satisfação, ausência de risco e cobertura de contexto ao usar o produto em situações reais.  
- Qualidade de dados: refere‑se à adequação, completude e precisão dos dados manipulados pelo sistema; normas da família 25xxx tratam também dessa dimensão (relevante em aplicações orientadas a informação).

Implicação: medições de qualidade do produto nem sempre garantem qualidade em uso; é necessário combinar medições internas com testes e avaliações em contexto.

### 3. Hierarquia: característica → subcaracterística → propriedade (métrica)
- Estrutura: cada característica (ex.: usabilidade, confiabilidade) é decomposta em subcaracterísticas que, por sua vez, possuem propriedades observáveis e mensuráveis (ex.: tempo médio de resposta, taxa de erro, número de exceções).  
- Propriedades são os elementos mensuráveis usados para calcular indicadores que expressam graus de conformidade com requisitos de qualidade. Exemplo prático: para medir “previsibilidade” (subcaracterística de usabilidade) podemos usar “tempo médio para aprendizado” e “percentual de tarefas realizadas sem ajuda”.

Regra prática: escolha no máximo 3–5 propriedades por subcaracterística prioritária para manter foco e viabilidade de medição.

### 4. Principais características do modelo de produto (ISO/IEC 25010) — descrição e aplicações
- Adequação funcional (functional suitability): o quanto as funções atendem necessidades especificadas pelos stakeholders; medir por cobertura de requisitos e taxa de conformidade funcional.  
- Eficiência de desempenho (performance efficiency): desempenho relativo ao uso de recursos (CPU, memória, rede); medir latência média, throughput, consumo médio de memória.  
- Compatibilidade (compatibility): capacidade de coexistir e interoperar com outros produtos; medir número de interfaces suportadas, taxa de sucesso em integrações de sistema.  
- Usabilidade (usability): facilidade de uso, aprendizagem, retenção, operabilidade e atratividade; medir tempo de tarefa, taxa de sucesso, satisfação (Likert).  
- Confiabilidade (reliability): execução correta em condições especificadas; medir taxa de falhas por hora, MTTR (Mean Time To Repair), MTBF (Mean Time Between Failures).  
- Segurança (security): proteção da informação e resistência a ataques; medir número de vulnerabilidades críticas encontradas, conformidade com controles de autenticação/autorização.  
- Manutenibilidade (maintainability): facilidade para modificar o produto; medir acoplamento, complexidade ciclomática média, tempo médio para correção de bugs.  
- Portabilidade (portability): facilidade em transferir o produto para diferentes ambientes; medir número de plataformas compatíveis e esforço médio para adaptação.

Exercício aplicado em classe: escolher duas características críticas para um sistema de ensino e propor 2 métricas para cada uma (ver seção exercícios).

### 5. Propriedades internas vs externas e relação com qualidade em uso
- Propriedades internas (visíveis ao desenvolvedor) influenciam propriedades externas (visíveis ao usuário) e, por consequência, a qualidade em uso. Exemplo: alto acoplamento (propriedade interna) aumenta o tempo de correção (propriedade externa relacionada à manutenibilidade), impactando disponibilidade e confiança do usuário.  
- Para garantir qualidade em uso, combine: (a) medições de produto durante desenvolvimento; (b) avaliações em contexto (testes de usabilidade, estudos de campo) que meçam eficácia, eficiência e satisfação reais do usuário.

Processo recomendado: especificar metas mensuráveis de qualidade em uso (por exemplo, 80% de sucesso em tarefa X em ≤ 90 s) e mapear as propriedades do produto que suportam essas metas.

### 6. Priorização e trade‑offs: “necessário e suficiente”
- Nem toda característica pode ser maximizada simultaneamente por custo e viabilidade; priorize usando critérios de impacto no usuário, risco de negócio e custo de implementação.  
- Técnica prática: matriz impacto × esforço para priorizar subcaracterísticas; alinhar prioridades com stakeholders e documentar requisitos de qualidade no backlog/produto.

### 7. Medição: projeção de métricas e exemplos operacionais
- Processo geral: selecionar propriedade → definir métrica formal → instrumento de coleta → rotina de medição (quando e por quem) → meta aceitável → ação quando fora do objetivo.  
- Exemplo 1 — Usabilidade (tempo de tarefa): métrica Tm = média dos tempos de conclusão da tarefa medida em segundos em n usuários; meta: Tm ≤ 90 s; coleta: testes moderados com 5–10 usuários; análise: média, desvio padrão, outliers.  
- Exemplo 2 — Confiabilidade (falhas por uso): métrica F = número de falhas críticas por 1.000 sessões; meta: F ≤ 0.5; coleta: logs do servidor e relatórios de campo; análise: tendência por release.  
- Exemplo 3 — Manutenibilidade (MTTR): métrica MTTR = média do tempo (horas) entre abertura e correção de incidentes críticos; meta: MTTR ≤ 24 h.

Observação: defina fórmulas, unidade, método de coleta e periodicidade antes da medição para evitar ambiguidades.

---

## Conclusão
A aplicação prática do modelo ISO/IEC 25000 em projetos de IHC exige traduzir características de alto nível (usabilidade, confiabilidade, segurança etc.) em propriedades e métricas mensuráveis, priorizadas segundo impacto no usuário e custo. Medições combinadas (produto + uso) e avaliação em contexto asseguram que as decisões de engenharia suportem a experiência real do usuário.

---

## Análise crítica
- Benefícios: modelo padronizado facilita comunicação entre equipes e clientes e suporta seleção de métricas comparáveis entre projetos.  
- Limitações: o modelo é abrangente e pode tornar a medição onerosa; cuidado para não medir “tudo” sem foco. A ligação entre métricas internas e percepção do usuário nem sempre é direta — validação empírica com usuários continua indispensável.  
- Recomendações: usar o modelo como guia estrutural, mas adotar um conjunto enxuto e justificável de métricas alinhadas às prioridades de negócio e aos contextos reais de uso.

---

## Sugestões de complementação
- Adicionar um caso prático guiado durante a aula: do levantamento de requisitos de qualidade até a execução de três medições no protótipo (tempo de tarefa, taxa de sucesso, número de erros).  
- Fornecer templates: (1) planilha de coleta de métricas; (2) checklist de propriedades por subcaracterística; (3) modelo de registro de evidências de usabilidade.  
- Leitura complementar sugerida: textos sobre ISO/IEC 25010 e guias práticos de medição (normas 25022/25023) e capítulos de Rocha & Baranauskas sobre avaliação em IHC.

---

## Exercícios (com resolução detalhada)

1) Seleção de métricas (prático)  
- Enunciado: para um sistema de ensino remoto, escolha 3 características prioritárias do ISO/IEC 25010 e proponha 2 métricas mensuráveis para cada.  
- Resolução exemplo:  
  - Usabilidade: (a) taxa de sucesso na tarefa “enviar atividade” (S%, n participantes); (b) tempo médio para completar essa tarefa (Tm em segundos).  
  - Confiabilidade: (a) número de sessões interrompidas por erro crítico por mês (F); (b) MTTR para incidentes críticos (horas).  
  - Eficiência de desempenho: (a) tempo médio de carregamento da página inicial (s); (b) throughput máximo suportado antes de degradação (requisições/s).  
- Passos: justificar escolha (impacto no aluno), definir método de coleta (testes moderados, logs), estabelecer metas (p.ex., S ≥ 90%, Tm ≤ 60 s).

2) Cálculo de índice de usabilidade composto  
- Enunciado: proponha fórmula que combine taxa de sucesso S (%) e tempo médio de tarefa T (s) em um índice U (maior = melhor) e calcule U para S = 85% e T = 45 s.  
- Resolução: escolha U = S / (1 + T/60) (penaliza tempo elevado). Substituindo: U = 85 / (1 + 45/60) = 85 / (1 + 0,75) = 85 / 1,75 = 48,57. Interpretação: comparar U entre versões; meta relativa a ser definida pelo projeto.

3) Priorização de características por matriz impacto × esforço  
- Enunciado: dado três subcaracterísticas com impactos estimados (A: alto, B: médio, C: baixo) e esforços (A: alto, B: baixo, C: baixo), priorize ações.  
- Resolução: matriz simples coloca A (alto impacto, alto esforço) em segundo plano para quick wins; priorizar B (médio impacto, baixo esforço) e C (baixo impacto, baixo esforço) para ganhos rápidos; planejar A como investimento estratégico com justificativa de ROI.

4) Planejamento de medição de confiabilidade em produção  
- Enunciado: defina como medir “falhas críticas por 1.000 sessões” e como agir caso a métrica ultrapasse o limite.  
- Resolução passo a passo: (1) definir falha crítica; (2) coletar logs de sessão e eventos; (3) calcular F = (n_falhas_criticas / n_sessoes) × 1000; (4) meta F ≤ 0.5; (5) rotina: se F > 0.5 → abrir análise de causa raiz, indicar hotfix e executar correção em < 48 h; (6) monitorar até estabilizar abaixo da meta.

5) Tradução de requisito qualitativo para métrica mensurável  
- Enunciado: transformar “o sistema deve ser fácil de usar” em requisito mensurável.  
- Resolução: definir tarefas representativas; escolher métricas: taxa de sucesso ≥ 85%, tempo médio ≤ 90 s, satisfação média ≥ 4 (escala 1–5); método: teste moderado com 8–10 usuários representativos; aceitação: todos os três critérios atendidos.

---

## Bibliografia (formato ABNT)

- INTERNATIONAL ORGANIZATION FOR STANDARDIZATION. ISO/IEC 25010:2011 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — System and software quality models. ISO, 2011. Acesso em: 19 out. 2025.  
- INTERNATIONAL ORGANIZATION FOR STANDARDIZATION. ISO/IEC 25022 / 25023 — Measurement standards for software quality in use and product quality. ISO, 2016–2018. Acesso em: 19 out. 2025.  
- ROCHA, H. V. da; BARANAUSKAS, M. C. C. Design e avaliação de interfaces humano‑computador. Campinas: NIED; UNICAMP, 2003. Acesso em: 12 out. 2025.  
- BENYON, D. Interação humano‑computador. 2. ed. São Paulo: Pearson, 2011. Acesso em: 19 out. 2025.  
- UNIVESP. Gerência e Qualidade de Software — Aula 02: Qualidade do produto (vídeo). YouTube. Disponível em: conteúdo da transcrição da videoaula UNIVESP. Acesso em: 12 out. 2025.  
- SOBRAL, W. S. Design de interfaces: introdução. Rio de Janeiro: Érica, 2019. Acesso em: 19 out. 2025.

---

Materiais consultados e transcrição da aula base utilizada para estruturar este conteúdo: transcrição do vídeo UNIVESP — "Gerência e Qualidade de Software — Aula 02 — Qualidade de produto" (conteúdo e timestamps); materiais complementares listados no plano de diretivas e no AVA do curso (ambiente de ensino).

--- 

