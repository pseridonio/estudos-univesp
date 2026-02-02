# Acessibilidade em Sistemas Interativos

## Introdução
A aula apresenta conceitos, princípios e práticas de acessibilidade aplicados a interfaces web e móveis, mostrando como identificar e corrigir barreiras para diferentes grupos de usuários e como avaliar conformidade com diretrizes reconhecidas internacionalmente.

---

## Desenvolvimento

### 1. Conceito e importância da acessibilidade
- Definição e objetivo: acessibilidade é um atributo de qualidade que busca tornar produtos, serviços e ambientes utilizáveis pelo maior número possível de pessoas, independentemente de suas capacidades físicas, sensoriais ou cognitivas.  
- Justificativa prática: garantir o direito ao acesso à informação e às funcionalidades, ampliar a base de usuários e reduzir exclusão digital; em aplicações críticas (educação, saúde, serviços públicos) a acessibilidade é requisito ético e legal.

### 2. Barreiras comuns e exemplos
- Tipos de barreiras: perceptivas (p.ex., falta de alternativas textuais para imagens), motoras (elementos com áreas de toque pequenas), auditivas (vídeos sem legendas), cognitivas (linguagem complexa) e de interação (dependência exclusiva de mouse).  
- Exemplo real: sites institucionais que oferecem recursos para pessoas com deficiência visual, como leitores de tela e ícones de acesso, ilustram abordagens práticas de inclusão.

### 3. Princípios e estrutura das WCAG (W3C)
- Princípios fundamentais: percepitível, operável, compreensível e robusto (POUR) — norteiam as recomendações para tornar conteúdo web acessível.  
- Estrutura da WCAG: princípios → diretrizes → critérios de sucesso → técnicas (suficientes e consultivas); critérios são testáveis, permitindo avaliar conformidade.  
- Níveis de conformidade: A (mínimo), AA (intermediário) e AAA (máximo); cada nível agrega requisitos adicionais que aumentam acessibilidade e esforço de implementação.

### 4. Exemplos de diretrizes e técnica aplicáveis
- Alternativas textuais: fornecer texto alternativo para conteúdos não textuais (critério 1.1) para que leitores de tela e Braille possam comunicar a informação.  
- Adaptabilidade: estruturar conteúdo de modo que possa ser apresentado de diferentes formas sem perda de informação (critério 1.3).  
- Distinguibilidade: garantir contraste, dimensionamento e separação entre áudio e visual (critério 1.4).  
- Acessibilidade por teclado: disponibilizar todas as funcionalidades via teclado, sem depender exclusivamente de apontadores (diretriz 2.1).

### 5. Avaliação: humana e automatizada
- Avaliação humana: especialistas treinados em WCAG fazem inspeções detalhadas e geram listas de problemas a corrigir; exige conhecimento das diretrizes e leitura de documentação técnica.  
- Ferramentas automatizadas: ferramentas como scanners e monitores verificam um subconjunto de critérios (p.ex., contraste, presença de atributos alt) e geram relatórios práticos; são úteis para triagem, mas não substituem avaliação humana completa, pois não cobrem todas as necessidades (ex.: questões cognitivas ou nuances de leitura de tela).  
- Limitações das ferramentas: scanners podem focar mais em deficiências visuais e motoras, deixando lacunas para outros tipos de necessidades; interpretar resultados requer contexto e validação humana.

### 6. Processos recomendados para incorporar acessibilidade
- Integrar acessibilidade desde a concepção (design inclusivo), não apenas como etapa final de correção, adotando o “design universal” e validando com usuários reais em contextos diversos.  
- Checklist operacional: mapear requisitos de acessibilidade, aplicar técnicas suficientes da WCAG, usar ferramentas automatizadas para triagem, complementar com auditoria humana e testes com usuários reais (incluindo pessoas com deficiência).  
- Priorizar correções: classificar falhas por severidade e impacto no uso real, corrigir primeiro problemas que bloqueiam acesso a funções essenciais.

---

## Conclusão
A acessibilidade é requisito de qualidade central em IHC: seguir princípios da WCAG, combinar avaliações automática e humana e envolver usuários com necessidades diversas são práticas essenciais para produzir interfaces verdadeiramente inclusivas e universais.

---

## Análise crítica
- Pontos fortes das WCAG: fornecem critérios testáveis e um framework aceito internacionalmente que orienta tanto desenvolvimento quanto conformidade legal e organizacional.  
- Limitações práticas: aplicação completa da WCAG pode demandar esforço significativo; ferramentas automatizadas são necessárias mas insuficientes; avaliações humanas e testes com usuários impactam cronograma e custos, exigindo priorização estratégica.  
- Observação ética: acessibilidade não deve ser tratada apenas como requisito técnico a cumprir, mas como princípio de design que influencia decisões arquiteturais, de conteúdo e de negócio.

---

## Sugestões de complementação
- Inclusão de estudos de caso práticos em sala: auditoria WCAG de uma página do curso, correção das falhas críticas e reteste com ferramenta + usuário real.  
- Fornecer templates: checklist WCAG (A/AA), roteiro de avaliação por especialista e roteiro para testes com usuários com deficiência.  
- Recomendar leituras e recursos: documentação WCAG (W3C), guias de implementação de plataformas (Apple, Google) e tutoriais de uso de ferramentas automatizadas.

---

## Exercícios (com resolução detalhada)

1. Exercício — Identificação de barreiras (prático)  
   - Enunciado: escolha uma página do seu projeto (ou do AVA) e identifique três possíveis barreiras de acessibilidade, indicando a diretriz WCAG correspondente.  
   - Resolução modelo:  
     - Barreira 1: imagens sem atributo alt — Diretriz 1.1 (alternativas textuais).  
     - Barreira 2: botões com área de clique muito pequena — Diretriz 2.1 (teclado e operabilidade; técnica relacionada ao tamanho alvo).  
     - Barreira 3: contraste de texto insuficiente — Diretriz 1.4 (distinguibilidade).  
   - Passos: usar ferramenta automatizada para detectar ocorrências, confirmar manualmente com inspeção de DOM e propor correção (incluir alt, aumentar área de toque, ajustar cores).

2. Exercício — Avaliação com ferramenta e validação humana  
   - Enunciado: rode um scanner automatizado em uma página e receba 12 avisos de acessibilidade; suponha que 7 são problemas de contraste, 3 são imagens sem alt e 2 são problemas de foco de teclado. Classifique e priorize correções.  
   - Resolução: priorizar problemas que impedem acesso funcional (ex.: imagens críticas sem alt que representam conteúdo essencial) e questões de foco de teclado que bloqueiam navegação; problemas de contraste são importantes para legibilidade, priorizar conforme páginas mais visitadas; propor plano: corrigir alt e foco em 1ª iteração, contraste em 2ª, reavaliar com scanner e teste com usuário.

3. Exercício — Níveis de conformidade  
   - Enunciado: explique a diferença entre níveis A, AA e AAA e dê um exemplo de requisito para cada nível.  
   - Resolução:  
     - Nível A (mínimo): requisitos básicos; exemplo: fornecer atributos alt para imagens informativas.  
     - Nível AA (intermediário): requisitos adicionais para melhor acessibilidade; exemplo: contraste mínimo 4.5:1 para texto normal.  
     - Nível AAA (máximo): requisitos que melhoram a experiência mas são difíceis de aplicar universalmente; exemplo: fornecer resumo por cena para vídeos complexos.  

4. Exercício — Teste com usuário com deficiência visual  
   - Enunciado: descreva um protocolo breve (5 passos) para testar navegação de um formulário com um usuário que utiliza leitor de tela.  
   - Resolução:  
     1. Preparação: instruir participante sobre objetivo do teste; garantir ambiente com software leitor de tela comum (NVDA, JAWS, VoiceOver).  
     2. Tarefa: preencher e submeter formulário X representativo.  
     3. Observação: pedir que o participante verbalize percepções e comandos usados; registrar tempos e erros.  
     4. Pós‑tarefa: entrevista semiestruturada sobre dificuldades e sugestões.  
     5. Análise: mapear problemas críticos (ordine por bloqueio de fluxo) e propor correções (roles ARIA, labels, ordem tab).

5. Exercício — Planejamento de integração da acessibilidade ao processo ágil  
   - Enunciado: proponha três práticas para integrar checagens de acessibilidade em sprints curtos.  
   - Resolução:  
     - Prática 1: incluir critérios de aceitação WCAG (A/AA) nas user stories relevantes.  
     - Prática 2: automatizar testes de regressão de acessibilidade no pipeline CI/CD (ex.: axe-core).  
     - Prática 3: reservar uma task por sprint para auditoria rápida por especialista ou teste com usuário quando houver mudanças na área crítica.

---

## Bibliografia (formato ABNT)

- W3C. Web Content Accessibility Guidelines (WCAG) 2.1. World Wide Web Consortium, 2018. Disponível em: https://www.w3.org/TR/WCAG21/. Acesso em: 19 out. 2025.  
- ROCHA, H. V. da; BARANAUSKAS, M. C. C. Design e avaliação de interfaces humano‑computador. Campinas: NIED; UNICAMP, 2003.  
- BENYON, D. Interação humano‑computador. 2. ed. São Paulo: Pearson, 2011.  
- UNIVESP. Interface Humano‑Computador — Acessibilidade (videoaula, Professora Alessandra Alaniz Macedo). YouTube. Acesso em: 19 out. 2025.  
- Material de apoio AVA UNIVESP — Conteúdo do curso Interface Humano‑Computador. Acesso em: 19 out. 2025.

---