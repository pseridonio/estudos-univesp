# Expansão de Shannon, SoP canônica e Mapas de Karnaugh — Aula detalhada

## Introdução

Esta aula explica em detalhes a transformação de uma tabela-verdade em uma expressão na forma Soma de Produtos (SoP) canônica, o teorema da expansão de Shannon e a síntese e simplificação de funções booleanas com mapas de Karnaugh (K-map). Usaremos exemplos numéricos concretos, passo a passo, e mostraremos como implementar funções com multiplexadores a partir da expansão de Shannon, conforme apresentado na videoaula base e em referências técnicas.

---

## Desenvolvimento

### 1. SoP (Soma de Produtos) e sua forma canônica

#### 1.1 Definição e motivação
- SoP (Sum of Products) é uma forma de representar funções booleanas como a soma lógica (OR) de termos produto (AND) de literais.  
- A SoP canônica é aquela em que cada produto contém todas as variáveis da função, cada produto é um *mintermo* e corresponde exatamente a uma linha da tabela-verdade cujo resultado é 1. Essa representação é útil para mapear diretamente tabela-verdade ↔ expressão e para aplicar técnicas gráficas de simplificação como o K-map.

#### 1.2 Como obter a SoP canônica a partir de uma tabela-verdade — procedimento passo a passo
1. Identifique todas as linhas da tabela-verdade onde a saída F = 1. Anote os índices dos mintermos (em decimal) ou os vetores binários.  
2. Para cada linha com F = 1, construa o mintermo: escreva cada variável em forma direta (ex.: A) se o bit for 1, ou negada (ex.: A') se o bit for 0. Cada mintermo deve conter todas as variáveis na ordem estabelecida (por exemplo, A B C).  
3. Some logicamente (OR) todos os mintermos identificados: F = m_i + m_j + ... . Uma notação compacta é F = Σ(m_i, m_j, ...).  
4. Verifique: expandir cada mintermo e avaliar a função para as entradas correspondentes deve produzir 1 somente nas linhas originais.

Exemplo concreto (3 variáveis A,B,C):
- Tabela-verdade com F = 1 em linhas 1 (001), 3 (011) e 5 (101).  
- Mintermos: m1 = A' B' C; m3 = A' B C; m5 = A B' C.  
- SoP canônica: F = A'B'C + A'BC + AB'C.  

Explique cada passo: por que A' no mintermo m1? Porque na linha 1 o bit A = 0, logo aparece negado; por que C aparece não-negado? porque C = 1 naquela linha.

#### 1.3 Converter SoP não-canônica para canônica (quando termos não têm todas as variáveis)
- Se um termo da SoP não contém todas as variáveis (por exemplo AB), para convertê-lo em mintermos aplique a identidade distributiva com X + X' = 1:  
  AB = AB·(C + C') = ABC + ABC' → agora são dois mintermos completos.  
- Proceda repetidamente até que todos os produtos contenham todas as variáveis.

---

### 2. Teorema da Expansão de Shannon — definição e aplicação prática

#### 2.1 Enunciado do teorema (forma básica)
Para qualquer função booleana F(x1, x2, ..., xn) e para qualquer variável xi, a expansão de Shannon em relação a xi é:

F = xi·F_\{xi=1\} + xi'·F_\{xi=0\}

onde:
- F_\{xi=1\} é o cofator positivo: a função F com xi substituído por 1 (ou seja, simplificar a função assumindo xi=1).  
- F_\{xi=0\} é o cofator negativo: a função F com xi substituído por 0.  
- xi' é a negação de xi.  

Essa identidade permite decompor sistematicamente a função em dois subproblemas e é a base para implementar funções com multiplexadores e para obter expressões canônicas e simplificações.

Citação técnica: a expansão de Shannon é usada explicitamente para síntese via multiplexadores e para decomposição recursiva de funções booleanas.

#### 2.2 Interpretação prática e ligação ao multiplexador
- Interpretando xi como uma chave seletora de um multiplexador, a expansão diz que F é igual a: quando xi = 0, a saída é F_{xi=0}; quando xi = 1, a saída é F_{xi=1}.  
- Logo, com um multiplexador 2:1 com seletor xi, conectamos F_{xi=0} na entrada 0 do MUX e F_{xi=1} na entrada 1; a saída do MUX implementa F. Essa técnica permite implementar funções de n variáveis usando um MUX e subfunções com menos variáveis, ou diretamente usar um MUX com entradas constantes (0/1) e outras variáveis para implementar qualquer função (método prático apresentado na videoaula).

#### 2.3 Exemplo numérico detalhado com Shannon (3 variáveis)
Considere F(A,B,C) definida pelos mintermos {1,3,5,6} (índices decimais).

1. Escreva F por SoP canônica:  
   m1 (001) → A'B'C  
   m3 (011) → A'BC  
   m5 (101) → AB'C  
   m6 (110) → ABC'  
   F = A'B'C + A'BC + AB'C + ABC'.

2. Aplique a expansão em A (escolha A como xi):
   - Cofator A=0: F_\{A=0\} = (substituir A=0 nos mintermos) → m1 e m3 permanecem, m5 e m6 desaparecem → F_{A=0}(B,C) = B' C + B C = C (pois B' C + B C = C·(B' + B) = C).  
   - Cofator A=1: F_\{A=1\} = m5 + m6 = B' C + B C' (função de B e C). Não simplifica diretamente.  
3. Pela expansão: F = A'·F_\{A=0\} + A·F_\{A=1\} = A'·C + A·(B' C + B C').  
4. Observação: A'·C = C·A'; o termo A·(B' C + B C') pode às vezes ser implementado por um MUX quando se escolhe outra variável como seletora ou por simplificação adicional.  
5. Implementação com MUX 2:1 selecionado por A:  
   entrada 0 = F_\{A=0\} = C;  
   entrada1 = F_\{A=1\} = B' C + B C';  
   saída = F.  
   Assim um MUX 2:1 mais lógica para entrada1 implementa a função global.

Comentário: essa decomposição facilita a implementação física via MUXs e também ajuda a visualizar a função em blocos menores, o que é vantajoso para síntese modular e otimização de hardware.

#### 2.4 Expansão recursiva e impacto no custo
- Pode-se expandir por várias variáveis recursivamente até reduzir as subfunções a constantes 0/1; isso é a base da expressão canônica (cada caminho da decomposição produz um mintermo).  
- Trade-off: expansão completa gera SoP canônica (potencialmente grande). Expansões estratégicas (escolher variáveis com cofatores simples) permitem implementações com menos lógica e menos entradas de MUX.

---

### 3. Mapas de Karnaugh — construção, leitura e dicas práticas

#### 3.1 O que é um K-map e por que ele funciona
- O K-map é uma grade que representa a tabela-verdade de forma geométrica onde células adjacentes diferem em exatamente um bit (ordem Gray). Agrupando células com 1s obtemos termos simplificados pela eliminação das variáveis que mudam dentro do grupo. O K-map é uma ferramenta gráfica para encontrar uma SoP simplificada (mínima ou quase mínima) com menos esforço que manipulação algébrica manual.

Referência da videoaula e justificativa do uso de K-map na simplificação de funções combinacionais.

#### 3.2 Estrutura e rotulagem (2, 3 e 4 variáveis)
- 2 variáveis: 2×2. Células: 00, 01, 11, 10 (ordem Gray).  
- 3 variáveis: 2×4 (linhas: A, colunas: BC em Gray = 00,01,11,10). Cada célula corresponde a um mintermo 0..7.  
- 4 variáveis: 4×4 (linhas: AB em Gray, colunas: CD em Gray). A ordem Gray nas duas dimensões garante que células vizinhas diferem em 1 bit. Lembre-se do wrap-around: bordas opostas são adjacentes.

#### 3.3 Passo a passo para montar o K-map
1. Determine o número de variáveis n.  
2. Desenhe a grade apropriada (ex.: 4×4 para n=4).  
3. Rotule linhas e colunas em ordem Gray.  
4. Preencha as células com 1, 0 ou X (don’t care) conforme a tabela-verdade.  
5. Busque formar grupos retangulares com formatos 2^k (1,2,4,8...) só contendo 1s (pode incluir Xs para ampliar).  
6. Para cada grupo, deduza o termo: mantenha as variáveis que não mudam no grupo; se a variável é 1 em todas as células aparece direta; se 0 aparece negada; se varia, elimina-se.  
7. OR entre os termos de todos os grupos → expressão simplificada.

#### 3.4 Regras de agrupamento — por que e como agrupar
- Sempre use grupos com 2^k células (0,1,2,4,8...).  
- Prefira grupos maiores: maiores grupos produzem termos com menos literais.  
- Permita sobreposição quando isso reduzir o número total de termos ou literais.  
- Use Xs (don’t care) para ampliar grupos quando vantajoso; X pode ser tratado como 1 ou 0 conforme convier.  
- Cobertura: todos os 1s devem ser cobertos por pelo menos um grupo; tente cobrir cada 1 usando o maior grupo possível.

Dica prática: marque os 1s e tente “envolvê-los” em blocos grandes; sempre verifique adjacências horizontais, verticais e por wrap-around.

#### 3.5 Exemplo detalhado (3 variáveis com valores concretos)
Função F(A,B,C) = 1 para minterms {1,3,5,7}. Vamos construir e simplificar.

1. SoP canônica inicial:  
   m1 = A'B' C  
   m3 = A' B C  
   m5 = A B' C  
   m7 = A B C  
   F = A'B'C + A'BC + AB'C + ABC.

2. K-map 2×4 (linhas A=0 / A=1; colunas BC = 00,01,11,10):
   - A=0 row: cells correspondem a m0,m1,m3,m2 (colunas 00,01,11,10) → preencha 1 em m1 e m3.  
   - A=1 row: cells m4,m5,m7,m6 → preencha 1 em m5 e m7.

   Visualização (linha A=0): [m0=0, m1=1, m3=1, m2=0]  
   Visualização (linha A=1): [m4=0, m5=1, m7=1, m6=0]

3. Agrupamento: observe que as quatro células com 1 formam um bloco 2×2 que cobre colunas 01 e 11 em ambas linhas → esse bloco de 4 células tem C = 1 constante (nas colunas 01 e 11 C = 1), enquanto A e B variam → termo simplificado = C.  
4. Resultado: F = C. Verificação: todas as minterms indicadas têm C = 1; logo F = C é equivalente e muito mais simples.

Explique cada passo: por que o termo final é C? Porque dentro do grupo todas as células têm C=1, logo as demais variáveis podem variar sem afetar a saída, permitindo eliminar A e B.

#### 3.6 Exemplo com don’t care e 4 variáveis (numérico)
Considere F(W,X,Y,Z) = 1 em {1,3,7,11} e Xs em {10,14} (don’t care). Procedimento:

1. Desenhe o K-map 4×4 rotulando linhas AB (W,X) e colunas CD (Y,Z) em Gray.  
2. Preencha 1s e Xs nas células correspondentes.  
3. Busque grupos grandes: X em 10 (binário 1010) pode ser usado como 1 para formar um grupo maior com m11 (1011), criando um bloco de 2 que reduz literais; X em 14 (1110) pode permitir formar um grupo de 4 se houver vizinhos adequados.  
4. Extraia termos por grupo; incluir Xs estrategicamente reduz o número de termos finais.  
5. Verifique a expressão final comparando com a tabela-verdade original para entradas válidas.

Comentário: don’t cares são ferramentas poderosas para reduzir lógica sem alterar comportamento em entradas válidas.

#### 3.7 Estratégias e heurísticas (sequência de montagem)
- Sempre priorize formar grupos grandes (8 → 4 → 2 → 1).  
- Para cada 1 não coberto, tente expandi-lo ao máximo com vizinhos 1 ou X.  
- Se houver múltiplas opções iguais, prefira a que gera menos termos depois (às vezes exige experimentar).  
- Use sobreposição quando reduz termos; não tema cobrir uma célula mais de uma vez.  
- Para aprendizagem: pratique com mapas de 2 e 3 variáveis, depois 4; visualize o K-map como uma superfície toroidal para entender wrap-around.

---

## Conectando Shannon, SoP e K-map na prática de projeto

- A SoP canônica é a forma direta obtida por expansão completa (cada mintermo); o K-map é a ferramenta gráfica para reduzir a SoP canônica sem expandir algebricamente cada termo.  
- A expansão de Shannon fornece decomposição dirigida para implementação com multiplexadores: escolha uma variável de expansão que simplifique cofatores; implemente a função com um MUX cujo seletor é a variável escolhida e entradas são cofatores (ou constantes quando aplicável).  
- Exemplo prático: se uma expansão por A produz F = A'·C + A·G(B,C), implementa-se MUX com A como seletor, entrada0 = C, entrada1 = G(B,C).

Referências indicam explicitamente o uso da expansão de Shannon para síntese via multiplexadores e métodos pedagógicos semelhantes ao mostrado na aula.

---

## Conclusão

- A SoP canônica é um ponto de partida sistemático (fácil de obter a partir da tabela-verdade), mas geralmente precisa ser simplificada para implementação prática.  
- O teorema de Shannon é uma ferramenta poderosa para decomposição e implementação por multiplexadores; escolher variáveis de expansão adequadas reduz custo de hardware.  
- Mapas de Karnaugh são uma técnica gráfica eficiente para simplificar SoP, especialmente para até 4 variáveis; don’t cares e agrupamentos estratégicos são cruciais para obter expressões mais compactas.

---

## Análise crítica

- O método canônico é conceitualmente claro, porém pouco eficiente se usado sem passos de simplificação: expansão completa gera expressões longas que aumentam custo e atraso. O uso combinado de Shannon com K-map e seleção cuidadosa de variáveis de expansão equilibra clareza e eficiência e é recomendado em síntese manual e ensino.  
- Em projetos industriais, síntese automática via ferramentas CAD e técnicas como Quine–McCluskey ou heurísticas espresso complementam os métodos manuais para funções maiores; para aprendizado, K-map + Shannon oferecem intuição sólida.

(Citações sobre aplicação prática e multiplicadores e síntese via Shannon aparecem em publicações técnicas e trabalhos acadêmicos sobre implementação com multiplexadores.)

---

## Exercícios (com resolução detalhada e valores numéricos)

### Exercício 1 — SoP canônica e simplificação via K-map (3 variáveis)
Função F(A,B,C) = 1 para minterms {0,2,3,6}.  
a) Escreva a SoP canônica.  
b) Construa o K-map 2×4 e simplifique.

Resolução:
a) Mintermos:
- m0 (000) → A' B' C'  
- m2 (010) → A' B C'  
- m3 (011) → A' B C  
- m6 (110) → A B C'  
SoP canônica: F = A'B'C' + A'BC' + A'BC + AB C'.

b) K-map (linhas A=0/1, colunas BC = 00,01,11,10):
- A=0 row: m0=1 (00), m1=0, m3=1 (11), m2=1 (10) → preencha conforme índices.  
  Observação: certifique-se da ordem Gray: colunas 00,01,11,10 correspondem a m0,m1,m3,m2 na linha A=0.
- A=1 row: m4,m5,m7,m6 → preencha m6=1 (col 10).

Mapa preenchido:
- Linha A=0: [m0=1, m1=0, m3=1, m2=1]
- Linha A=1: [m4=0, m5=0, m7=0, m6=1]

Agrupamentos:
- Grupo 1: m2 (A=0, col10) e m6 (A=1, col10) → vertical de 2 células: coluna 10 tem BC = 10 (B=1,C=0) com A variando → termo = B C' (mantém B=1 e C=0).  
- Grupo 2: m0 (A=0,col00) e m3 (A=0,col11) não são adjacentes diretas; mas m0 (col00) é adjacente por wrap-around a m2 (col10) e m3 (col11) é adjacente a m2. Melhor abordagem: formar grupo de 2 entre m0 e m2? m0 (col00) e m2 (col10) não são adjacentes (diferença em 2 bits). Então formar grupo de 2 entre m0 (col00) e m4 se m4 fosse 1 — não é. Outra alternativa: formar dois grupos: (m0) isolado e (m3) isolado; entretanto observe que m0 e m3 estão ambos na linha A=0; m0 (00) e m3 (11) diferem em 2 bits e não podem ser agrupados.

Portanto grupos finais:
- Grupo A: (m2,m6) → termo: B C'  
- Grupo B: m3 isolado → termo: A' B C  
- Grupo C: m0 isolado → termo: A' B' C'

Expressão simplificada: F = B C' + A' B C + A' B' C'.

Verificação: substitua combinações correspondentes e compare à tabela-verdade inicial. Observação: talvez seja possível reorganizar agrupamentos com don’t care se existissem; sem don’t care, solução final é essa.  

Comentário didático: quando não há grupos maiores possíveis, mintermos isolados permanecem como termos com todas as variáveis.

---

### Exercício 2 — Shannon + MUX (3 variáveis com valores numéricos)
Dada F(A,B,C) com minterms {1,4,5} (decimal).  
a) Expresse F com SoP canônica.  
b) Aplique a expansão de Shannon em A e mostre como implementar F com um MUX 2:1 selecionado por A, indicando as entradas do MUX como funções de B,C.

Resolução:
a) Mintermos:
- m1 (001) → A' B' C  
- m4 (100) → A B' C'  
- m5 (101) → A B' C  
SoP: F = A'B' C + A B' C' + A B' C.

b) Expansão em A:
- F_{A=0} = substitua A=0 → minterms com A=0: m1 → F_{A=0}(B,C) = B' C.  
- F_{A=1} = substitua A=1 → minterms com A=1: m4 and m5 → F_{A=1}(B,C) = B' C' + B' C = B' (C' + C) = B'.  
Logo Shannon: F = A'·(B' C) + A·(B').

Implementação com MUX 2:1 (selector = A):
- MUX input 0 (A=0) = F_{A=0} = B' C (é uma expressão de B,C; implemente com uma porta AND entre B' e C).  
- MUX input 1 (A=1) = F_{A=1} = B' (inverter B e conectar) .  
- Saída do MUX = F.

Observação prática: usando Shannon conseguimos reduzir as duas subfunções: uma é um produto simples B' C, a outra é B' (simplíssima). O MUX seleciona entre essas subfunções com base em A, resultando numa implementação compacta. Isso ilustra o poder da expansão de Shannon para síntese via MUX.

---

### Exercício 3 — K-map com don’t care e simplificação (4 variáveis)
F(W,X,Y,Z) = 1 para minterms {0,2,5,7,8,10} e don’t cares em {3,11,14}. Simplifique via K-map.

Resolução (resumida com passos claros):
1. Desenhe K-map 4×4 (linhas WX em Gray: 00,01,11,10; colunas YZ em Gray: 00,01,11,10).  
2. Preencha 1s nas células 0,2,5,7,8,10; X nas células 3,11,14.  
3. Procure formar grupos grandes usando Xs quando útil:
   - X em 3 (0011) junto com 2 (0010) e 7 (0111) pode ajudar a formar um bloco de 4; verifique adjacências.  
   - X em 11 (1011) pode ajudar a agrupar 10 e 11 formando par vertical.  
   - X em 14 (1110) pode ajudar a agrupar com 10 (1010) e 8 (1000) via wrap-around, formando um bloco de 4 se possível.  
4. Extraia os termos (determinar, para cada bloco, quais variáveis são constantes).  
5. Forma final: combinação de poucos termos com poucas literais (detalhe das extrações depende do agrupamento escolhido).

Observação: a solução final depende das escolhas de agrupamento; a regra prática é maximizar o tamanho de cada grupo e usar Xs para aumentar blocos, reduzindo literais.

---

## Sugestões de aprofundamento e complementação

- Treinar com uma coleção de K-maps variados (2 a 4 variáveis) até que a identificação visual de blocos grandes seja automática.  
- Experimentar implementação por multiplexadores usando a expansão de Shannon, comparando custo (número de portas, MUX) para diferentes escolhas de variável de expansão.  
- Estudar algoritmos de minimização (Quine–McCluskey, Espresso) quando a função tem muitas variáveis, mas manter K-map e Shannon para intuição e projeto manuais.

---

## Bibliografia (formato ABNT)

- UNIVESP. Circuitos Digitais - Circuitos Combinacionais. Professor André Ricardo Fioravanti. YouTube, 25 out. 2021. Disponível em: https://www.youtube.com/watch?v=HFXlJJsAWWI. Acesso em: 10 out. 2025.  
- ROUT, Kumaresh; BASU, Srilata; MISRA, Sarita. Design and Implementation of Boolean Functions using Multiplexer and also using Shannon Expansion Theorem. International Research Journal of Engineering and Technology (IRJET), v.03, n.02, 2016. Disponível em: https://www.irjet.net/archives/V3/i2/IRJET-V3I2208.pdf. Acesso em: 10 out. 2025.  
- Research Article. Implementation of Boolean Functions through Multiplexers with the Help of Shannon Expansion Theorem. International Journal of Computer Applications, volume 62, number 6. Disponível em: https://research.ijcaonline.org/volume62/number6/pxc3884708.pdf. Acesso em: 10 out. 2025.  
- GUNTZEL, J. Circuitos de Armazenamento. Universidade Federal de Santa Catarina. Disponível em: https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf. Acesso em: 10 out. 2025.

---

## Materiais complementares (indicados)
- TOCCI, Ronald J.; WIDMER, Neal S.; MOSS, Gregory L. Sistemas digitais: princípios e aplicações. 11. ed. São Paulo: Pearson, 2011.  
- GUNTZEL, J. Circuitos de Armazenamento. UFSC. Disponível em: https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf. Acesso em: 10 out. 2025.  
- Documentos e slides sobre Shannon expansion e implementação por multiplexadores (IRJET, IJCA) que demonstram formalmente a identidade e múltiplas aplicações práticas.

---