# Uso de Informações de Usuários em IHC

## Introdução
Esta aula apresenta como coletar, analisar e utilizar informações de usuários para orientar o design de interfaces, os tipos de ferramentas e métricas empregadas, métodos de coleta (logs e tags), aplicações empresariais (CAC, LTV), e as exigências legais e éticas relacionadas ao tratamento de dados pessoais, com foco prático para projetos de IHC.

---

## Desenvolvimento

### Objetivos da aula
- Explicar por que dados de usuário são valiosos para melhorar a experiência digital.  
- Descrever métodos comuns de coleta de dados (logs, tags) e suas vantagens e limitações.  
- Apresentar métricas relevantes para negócios e usabilidade (por exemplo, CAC, LTV, taxa de abandono).  
- Discutir ferramentas comuns de análise e conformidade com a Lei Geral de Proteção de Dados (LGPD).  
- Fornecer práticas de projeto e considerações éticas para coleta e uso de dados em interfaces.

### Por que usar dados de usuários em IHC
Coletar e analisar dados de uso permite identificar problemas de usabilidade em escala, entender comportamentos e preferências, prever padrões e fundamentar decisões de produto e design para reduzir abandono e aumentar satisfação. O uso estratégico desses dados sustenta uma "cultura dirigida a dados" que transforma observações em ações concretas e mensuráveis.

### Métodos de coleta de dados

#### Logs (coleta automática de eventos)
- O que é: registros automáticos de acessos e ações no servidor (páginas visitadas, timestamps, IPs, user agents).  
- Vantagens: coleta contínua e automática em grande volume; bom para auditoria e análise histórica.  
- Desvantagens: excesso de dados irrelevantes; dificuldade para capturar ações parciais (por exemplo, formulários em teste) e necessidade de limpeza e filtragem para obter insights úteis.

#### Tags (instrumentação via JavaScript)
- O que é: snippets ou "tags" inseridos nas páginas que enviam eventos detalhados para ferramentas de analytics (cliques, visualizações de elementos, preenchimento de campos).  
- Vantagens: controle granular do que é coletado; possibilita medir eventos específicos e sessões únicas (visitas únicas, preenchimento individual de formulários).  
- Desvantagens: depende de habilitação de JavaScript no cliente; requer esforço de instalação e manutenção das tags; pode não cobrir páginas sem tags instaladas.

#### Estratégia híbrida
Combinar logs e tags é prática comum para compensar limitações de cada método: logs oferecem cobertura ampla; tags fornecem detalhes granulares e contexto sobre eventos específicos.

### Métricas úteis e como interpretá‑las

- **Taxa de abandono (bounce / abandonment rate):** percentual de sessões que não avançam em fluxos esperados; indica problemas de descoberta, responsividade ou relevância.  
- **CAC (Custo de Aquisição por Cliente):** investimento total em aquisição dividido pelo número de clientes obtidos; ajuda avaliar eficiência de campanhas e custo de aquisição versus retorno.  
- **LTV (Lifetime Value):** estimativa do valor total gerado por um cliente durante seu relacionamento com a empresa; LTV dividido por CAC indica sustentabilidade comercial.  
- **Tempo médio de sessão, páginas por visita, taxa de conversão:** métricas operacionais que ajudam diagnosticar onde otimizar jornadas e pontos de fricção.

Use métricas em conjunto: por exemplo, aumento de visitas com queda no LTV pode indicar aquisição de usuários de baixo valor; alto CAC com LTV baixo sinaliza necessidade de rever canais ou produto.

### Ferramentas e exemplos práticos
- Ferramentas gerais e acessíveis: planilhas (Excel, Google Sheets) para análise e visualização básica; soluções robustas: Google Analytics (tags + relatórios), KNIME, Orange para análise avançada; ferramentas brasileiras para segmentação e automação: Navegg, Aidax (ex.: criação de gatilhos e campanhas com base em comportamento).  
- Exemplo prático de uso: instalar tag de rastreamento, monitorar taxa de abandono em páginas móveis; se 75% dos usuários mobile abandonam (indicador hipotético), priorizar responsividade e otimização de layout para mobile.

### Tomada de decisão orientada a dados
Dados permitem identificar problemas, entender público e gerar insights acionáveis (brainstorms, hipóteses de melhoria), além de suportar decisões estratégicas mensuráveis. Ferramentas analíticas podem ser descritivas (o que aconteceu) ou preditivas/prescritivas (por que acontece e o que fazer) — escolha método conforme objetivo do projeto.

### Privacidade, LGPD e questões éticas
- A LGPD (Lei nº 13.709/2018) regula o tratamento de dados pessoais no Brasil, confere direitos aos titulares e impõe responsabilidades a controladores e operadores; a lei entrou em vigor em 2020, com aplicação progressiva de sanções previstas a partir de 2021, e prevê penalidades que podem alcançar porcentagens do faturamento quando descumprida.  
- Principais implicações práticas: obtenção de consentimento explícito (TCLE) para coleta de cookies e dados pessoais; possibilidade de consentimento granular (aceitar apenas alguns cookies); necessidade de documentar finalidades, período de retenção, bases legais e medidas de segurança; responsabilidade compartilhada ao terceirizar serviços com DPOs/fornecedores.  
- Recomendações éticas e de conformidade: minimizar coleta (data minimization), anonimizar sempre que possível, registrar bases legais e termos de consentimento, prover mecanismos de revogação de consentimento e transparência sobre uso dos dados, realizar avaliações de impacto de privacidade quando aplicável.

---

## Conclusão
O uso responsivo de informações de usuários é uma ferramenta essencial em IHC para identificar problemas, personalizar experiências e embasar decisões de produto. Métodos de coleta devem ser escolhidos considerando cobertura, granularidade e impacto sobre privacidade. Conformidade com a LGPD e práticas éticas são requisitos não negociáveis em projetos atuais.

---

## Análise crítica
- Dados em grande volume não substituem conhecimento qualitativo: analytics apontam onde há problema, mas não explicam completamente o porquê — testes com usuários e entrevistas continuam necessários para validar hipóteses.  
- Risco de viés e conclusões erradas: logs e tags podem registrar artefatos (bots, crawlers) e interpretar mal comportamentos sem contexto. Filtragem e triangulação com dados qualitativos são essenciais.  
- Privacidade e poder: concentração de dados gera vantagem competitiva, mas também riscos de abuso; projetos de IHC devem equilibrar inovação com proteção dos direitos dos usuários e princípios éticos.

---

## Sugestões de complementação prática
- Configure colecta híbrida (logs + tags) e crie dashboards simples em planilhas ou BI para acompanhar métricas essenciais (CAC, LTV, taxa de abandono).  
- Antes de agir, gere hipóteses a partir dos dados e valide com um estudo qualitativo (5–8 usuários) focado nos pontos identificados.  
- Implemente fluxo de consentimento granular para cookies com opção de optar por categorias (estritamente necessários, performance, marketing).  
- Documente um pequeno plano de governança de dados: responsáveis, finalidade, período de retenção, fornecedores e contratos com cláusulas de segurança.

---

## Exercícios (com resolução detalhada)

### Exercício 1 — Escolha de método de coleta  
Enunciado: Seu cliente reclama que não sabe por que formulários de cadastro em teste têm baixa conclusão. Explique qual método (logs, tags ou híbrido) você escolheria primeiro e por quê.  
Resolução: escolheria inicialmente **tags** para instrumentar eventos no formulário (campo preenchido, campo abandonado, foco/blur por campo) porque permitem capturar interações parciais em formulários em teste; complementar com logs para obter sessão e origem de tráfego. Tags dão granularidade; logs dão cobertura; juntos permitem diagnóstico preciso.

### Exercício 2 — Calcular CAC simples  
Enunciado: Uma campanha investiu R$ 20.000 e trouxe 400 novos clientes no período. Calcule o CAC e interprete.  
Resolução: CAC = investimento / novos clientes = R$ 20.000 / 400 = **R$ 50 por cliente**. Interpretação: cada cliente custou R$ 50; compare com LTV médio para avaliar sustentabilidade (se LTV < R$ 50, aquisição é deficitária).

### Exercício 3 — Identificar problema a partir de métricas  
Enunciado: Analytics mostra aumento de visitas vindas de mobile, mas queda na taxa de conversão em mobile. Liste 3 hipóteses de causa e 2 métodos para validar cada hipótese.  
Resolução:  
- Hipótese A: site não responsivo → validar com teste de responsividade e inspeção manual em dispositivos; rodar testes de performance (TTFB, First Contentful Paint).  
- Hipótese B: fluxo de checkout com input difícil no mobile → validar com gravações de sessões (session replay) e testes de usabilidade com participantes mobile.  
- Hipótese C: problemas de compatibilidade com scripts/ads que bloqueiam carregamento → validar com análise de console de erro e remover scripts para teste A/B controlado.

### Exercício 4 — Consentimento e design de interface  
Enunciado: Projete, em linhas, um padrão de consentimento granular para cookies que respeite a LGPD e melhore a taxa de aceitação consciente pelos usuários.  
Resolução: apresentar modal claro com resumo (uso dos cookies), botões: "Necessários" (sempre ativos), toggles para "Performance" e "Marketing", botão primário "Aceitar selecionados" e secundário "Recusar não essenciais"; link "Saiba mais" para política detalhada e opção de alterar preferências a qualquer momento no rodapé; registrar consentimento com timestamp e IP; permitir aceitar apenas categorias específicas em vez de consentimento absoluto.

### Exercício 5 — Triangulação de dados  
Enunciado: Descreva um protocolo rápido para validar um insight extraído de analytics (por exemplo, queda de engajamento em uma seção do site).  
Resolução: 1) Identificar métrica e período; 2) Filtrar dados por segmento (dispositivo, origem, país); 3) Reunir gravações de sessão e heatmaps para observar comportamento; 4) Conduzir 4–6 entrevistas ou testes moderados com usuários focados na seção; 5) Priorizar correções hipóteses e rodar experimento A/B; 6) Medir efeitos e documentar lições. Justificativa: combina análise quantitativa com evidência qualitativa para tomar decisões fundamentadas.

---

## Bibliografia (ABNT)

- UNIVESP. Interface Humano-Computador - Uso de Informações de Usuários. Videoaula UNIVESP, 23:36. Disponível em: https://www.youtube.com/watch?v=EHm_C-zZo_M. Acesso em: 12 out. 2025.  
- ROCHA, Maria Cecília; BARANAUSKAS, Maria da Graça. Design e Avaliação de Interfaces Humano-Computador. São Paulo: [s.n.], [s.d.]. Acesso em: 12 out. 2025.  
- BRASIL. Lei nº 13.709, de 14 de agosto de 2018. Lei Geral de Proteção de Dados Pessoais (LGPD). Diário Oficial da União, 2018. Acesso em: 12 out. 2025.  
- GOOGLE. Google Analytics Documentation. Acesso em: 12 out. 2025.  
- NAVEGG. Plataforma de segmentação de audiência. Acesso em: 12 out. 2025.

--- 

## Materiais complementares (consultados)
- Transcrição e vídeo da UNIVESP — "Interface Humano-Computador - Uso de Informações de Usuários" (fundamento direto para conteúdo e exemplos de ferramentas, métodos e LGPD).  
- Ferramentas e tutoriais de Google Analytics, KNIME, Orange; documentação de boas práticas de consentimento e privacidade; materiais didáticos da disciplina de IHC para procedimentos de validação qualitativa.

--- 