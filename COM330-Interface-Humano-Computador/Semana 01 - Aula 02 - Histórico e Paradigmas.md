### Interface Humano-Computador - Histórico e Paradigmas

### Introdução
A aula apresenta a evolução histórica dos sistemas interativos, relaciona mudanças tecnológicas com paradigmas de interação e aponta impactos sobre usabilidade, acessibilidade e experiência do usuário. A videoaula base desta atividade foi usada como referência principal para estruturar o conteúdo e guiar as complementações bibliográficas.

---

### Desenvolvimento

#### Linha do tempo das gerações de sistemas interativos
A evolução das interfaces pode ser organizada em gerações que acompanham o avanço do hardware e do paradigma de interação, desde máquinas eletromecânicas até interfaces multimodais atuais. Na era pioneira até 1945 os computadores eram mecânicos ou eletromecânicos, usados para cálculos e programados por alterações físicas em cabos e chaves com saída via luzes e cartões perfurados.  
Na segunda fase, entre 1955 e 1965, a substituição de válvulas por transistores tornou os sistemas mais confiáveis; surgiram linguagens de baixo nível como assembly e sistemas de time sharing, além de terminais remotos e menus hierárquicos primários.  
A terceira geração, ligada ao paradigma WIMP que agrupa Windows, Icons, Menus e Pointing devices, caracterizou-se pelo uso doméstico e pessoal dos computadores, displays gráficos coloridos e interação direta com apontadores como o mouse, consolidando a metafórica “mesa de trabalho” (desktop) como ambiente de interação.  
A quarta geração, a partir de meados dos anos 1990 até os dias atuais, concentra a multiplicidade de dispositivos, redes sempre‑conectadas, interfaces sensíveis ao toque, realidade virtual, computação vestível e interação multimodal com gestos e fala.

#### Paradigmas de interação e suas características
- Batch e linha de comando: processamento em lotes e interfaces textuais exigindo conhecimento técnico e suscetíveis a erros de sintaxe; eram predominantes nas primeiras fases.  
- Menus hierárquicos e formulários: introduziram organização deixaram tarefas mais estruturadas e acessíveis a usuários não especialistas.  
- WIMP: introduziu metáforas visuais como janelas e ícones e dispositivos apontadores possibilitando manipulação direta de objetos digitais e aumento da produtividade para tarefas gráficas e documentais.  
- Interação multimodal e imersiva: inclui toque ("touch"), gestos, fala, realidade virtual ("virtual reality") e haptics; essas modalidades ampliam os canais sensoriais e exigem avaliação de fatores humanos, latência e responsividade para preservar usabilidade e senso de presença.  

#### Tecnologias de suporte e dispositivos relevantes
- Dispositivos de entrada e saída evoluíram para suportar vários canais sensoriais, incluindo telas capacitivas, sensores de movimento, sensores táteis e óculos de realidade virtual; o desenvolvimento desses dispositivos requer integração hardware‑software e considerações de ergonomia e *responsiveness* para manter a experiência fluida.  
- Realidade virtual e ambientes virtuais imersivos demandam sistemas de rastreamento, renderização em tempo real e, em aplicações com feedback tátil, tecnologia haptics; aplicações vão de treinamento e visualização a entretenimento e reabilitação médica.  

#### Impactos sobre usabilidade e acessibilidade
A democratização do computador, impulsionada por redução de custo e melhor suporte gráfico, ampliou a base de usuários e trouxe exigências de usabilidade que vão além da eficiência de especialistas, incluindo facilidade de aprendizado, prevenção de erros e satisfação. A conformidade com diretrizes de acessibilidade e a provisão de múltiplas modalidades de interação reduzem exclusões e ampliam o alcance das interfaces.

---

### Conclusão
A compreensão histórica dos paradigmas de IHC ajuda a entender por que certas soluções surgiram e como elas influenciam o projeto atual de interfaces. A trajetória das gerações demonstra que avanços tecnológicos provocam novos modelos de interação e novos requisitos de usabilidade e acessibilidade.

---

### Análise crítica
A mudança de paradigmas nem sempre leva automaticamente a melhor usabilidade para todos os usuários. Tecnologias emergentes como VR e interfaces gestuais trazem promessas de imersão, mas também criam novos problemas: curvas de aprendizado, exigências de hardware, riscos ergonômicos e desafios de acessibilidade que demandam avaliações empíricas e multidisciplinares. A literatura e práticas de IHC indicam que o sucesso depende de processos iterativos de design centrado no usuário e de avaliação combinando métodos qualitativos e quantitativos.

---

### Sugestões de complementação
- Estudar casos práticos de avaliação de interfaces WIMP e gestuais para comparar métricas de desempenho e satisfação.  
- Investigar diretrizes de acessibilidade aplicáveis a interfaces móveis e imersivas.  
- Realizar prototipagem rápida e testes com usuários para validar hipóteses sobre interação multimodal.

---

### Exercícios com resolução detalhada

1. Descrever as quatro gerações de sistemas interativos e exemplificar um dispositivo ou paradigma representativo para cada geração.  
   Resolução passo a passo:  
   - Primeira geração: máquinas eletromecânicas e cartões perfurados; exemplo: computadores de válvulas com entrada por cartões perfurados.  
   - Segunda geração: transistores e terminais; exemplo: sistemas com time sharing e terminais alfanuméricos.  
   - Terceira geração: paradigma WIMP; exemplo: desktops com janelas, ícones e mouse.  
   - Quarta geração: interfaces multimodais e dispositivos móveis; exemplo: smartphones com tela sensível ao toque e sensores inerciais.

2. Comparar linha de comando e interfaces WIMP apontando vantagens e desvantagens em termos de usabilidade.  
   Resolução passo a passo:  
   - Linha de comando: vantagem velocidade para especialistas; desvantagem alta curva de aprendizado e propensão a erros de sintaxe; exige memória de comandos.  
   - WIMP: vantagem descoberta visual, manipulação direta e maior acessibilidade a usuários não especialistas; desvantagem em eficiência para tarefas repetitivas altamente especializadas. Conclusão: escolha depende de contexto de uso e perfil do usuário.

3. Um sistema VR tem latência de sistema perceptível que causa desconforto. Explique por que a latência prejudica a presença e apresente duas estratégias de mitigação.  
   Resolução passo a passo:  
   - Por que prejudica: latência entre ação do usuário e resposta visual/tátil quebra a consistência temporal necessária para gerar sensação de presença; isso pode causar enjoo e reduzir desempenho.  
   - Estratégias: reduzir tempo de renderização com otimizações gráficas e pré‑processamento; usar predição de movimento para compensar atrasos no rastreamento. Implementação: medir latência end‑to‑end; priorizar pipeline gráfico; validar com testes com usuários.

4. Projetar uma alternativa acessível a um semáforo que use apenas cores para sinais. Forneça justificativa e elementos concretos de design.  
   Resolução passo a passo:  
   - Problema: daltonismo e baixa visão impedem distinção apenas por cor.  
   - Solução: manter posição padronizada das lâmpadas, adicionar formas internas (círculo, triângulo, quadrado) ou ícones, incorporar sinal sonoro e vibração em semáforos com botão para pedestres; justificar redundância sensorial para garantir percepções múltiplas e reduzir dependência de um único canal sensorial.

5. Liste três métodos de avaliação de usabilidade e explique quando cada um é mais adequado.  
   Resolução passo a passo:  
   - Teste com usuários: observação de tarefas reais; adequado para validar cenários de uso e medir métricas de desempenho.  
   - Avaliação heurística: especialistas analisam conformidade com heurísticas; adequado nas fases iniciais para identificar problemas óbvios rapidamente.  
   - Inspeção cognitiva: foco em tarefas críticas e processos de pensamento do usuário; adequado para verificar se novos usuários conseguem atingir objetivos sem instrução.

---

### Bibliografia
- ROCHA, Maria Cecília; BARANAUSKAS, Maria da Graça. Design e Avaliação de Interfaces Humano-Computador. São Paulo: [s.n.], [s.d.]. Disponível em: https://learn-us-east-1-prod-fleet02-xythos.content.blackboardcdn.com/5f28363662504/2698356. Acesso em: 12 out. 2025.  
- SHARP, Helen; ROGERS, Yvonne; PREECE, Jenny. Design de Interação Além da Interação Humano-Computador. [Local de publicação]: [Editora], [Edição], [Ano].  
- BARRETO, Jeanine dos S.; JR., Paulo A. P.; BARBOZA, Fabrício F. M.; et al. Interface humano-computador. Porto Alegre: SAGAH, 2018. E-book. ISBN 9788595027374. Acesso em: 12 out. 2025.  
- KELNER, Judith; TEICHRIEB, Veronica. Interface Interação Navegação Realidade Virtual. Recife: CIN UFPE, [s.d.]. Disponível em: https://www.cin.ufpe.br/~if687/frame/if687/interface-interacao-navegacao.pdf. Acesso em: 12 out. 2025.  
- UNIVESP. Interface Humano-Computador Histório de IHC Videoaula Professora Alessandra Alaniz Macedo. YouTube, 6 out. 2021. Disponível em: https://www.youtube.com/watch?v=FQymNVFnx6w. Acesso em: 12 out. 2025.  
- SCC-560 HCI Paradigmas de IHC Material de curso ICMC USP. Disponível em: http://java.icmc.usp.br/moodle/mod/forum/discuss.php?d=999&lang=pt_br. Acesso em: 12 out. 2025.  
- IHC 101 Evolução Princípios e Usabilidade Studocu. Disponível em: https://www.studocu.com/pt-br/document/universidade-virtual-do-estado-de-sao-paulo/interface-humano-computador/interface-humano-computador/115553793. Acesso em: 12 out. 2025.

---

### Materiais complementares
- Rocha Baranauskas Design e Avaliação de Interfaces Humano-Computador PDF disponível no ambiente digital da disciplina.  
- Tutorial Realidade Virtual UFPE sobre visualização e interação em 3D com discussão de haptics e imersão.  
- Artigos e notas de curso sobre paradigmas de IHC e engenharia de usabilidade ICMC USP.  

---