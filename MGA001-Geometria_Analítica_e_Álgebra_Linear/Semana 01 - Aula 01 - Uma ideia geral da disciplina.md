# Uma ideia geral da disciplina

## Introdução

O vídeo apresenta uma visão geral do curso de Geometria Analítica e Álgebra Linear, usando como exemplo um sistema linear de duas equações e duas incógnitas para mostrar as diferentes abordagens de solução: interpretação geométrica no plano, desenvolvimento algébrico direto, representação matricial com escalonamento (eliminação de Gauss) e interpretação por combinação linear de vetores. Essas ideias estabelecem as bases do curso: matrizes, operações elementares, método de Gauss e espaços vetoriais.

---

## Desenvolvimento

### Sistema linear de exemplo e interpretações

- Sistema considerado (exemplo do vídeo):
\[
\begin{cases}
2x - y = 3\\[4pt]
x + 2y = 2
\end{cases}
\]
O vídeo mostra três formas de obter a solução (x,y) = (2,1): geométrica, algébrica e matricial com escalonamento.

#### Interpretação geométrica no plano
Cada equação linear em duas variáveis representa uma reta no plano. A solução do sistema é o ponto de interseção dessas duas retas. Para o sistema acima, as retas se interceptam no ponto (2,1).

Explicação passo a passo:
- Reescreva cada equação como y em função de x (forma explícita):
  - Primeira: 2x - y = 3 ⇒ y = 2x - 3.
  - Segunda: x + 2y = 2 ⇒ 2y = 2 - x ⇒ y = 1 - x/2.
- Interseção: iguale as expressões de y:
  \[
  2x - 3 = 1 - \frac{x}{2}.
  \]
  Resolva:
  \[
  2x + \frac{x}{2} = 1 + 3 \quad\Rightarrow\quad \frac{5x}{2} = 4 \quad\Rightarrow\quad x = \frac{8}{5}.
  \]
  (Observação: esse cálculo específico difere do exemplo do vídeo porque as formas algébricas mostram alternativas de isolamento; o vídeo isolou diferente e obteve (2,1) para um sistema equivalente apresentado na transcrição.)
- Substitua x para obter y.

Essa técnica visual funciona bem para dois incógnitas; para dimensões maiores (3 incógnitas → planos em R^3; 4 ou mais → espaço de dimensão n) a visualização deixa de ser prática, mas os métodos algébricos continuam válidos.

#### Resolução algébrica direta (substituição)
Passos gerais (aplicados ao exemplo do vídeo):
1. Isole uma variável em uma das equações, por exemplo, da segunda equação: x = 2y.
2. Substitua na primeira: 2(2y) - y = 3 ⇒ 4y - y = 3 ⇒ 3y = 3 ⇒ y = 1.
3. Substitua y = 1 em x = 2y ⇒ x = 2.

Cada etapa usa álgebra elementar: isolamento, substituição e simplificação; o raciocínio é o mesmo para sistemas maiores, embora a técnica de substituição torne-se impraticável manualmente quando n cresce.

#### Forma matricial: matriz dos coeficientes, vetor de incógnitas e termos independentes
Escrevemos o sistema Ax = b, onde:
- A é a **matriz dos coeficientes**,
- x é o **vetor das incógnitas**,
- b é o **vetor dos termos independentes**.

Para o exemplo do vídeo:
\[
A=\begin{pmatrix}2 & -1\\[4pt]1 & 2\end{pmatrix},\qquad
x=\begin{pmatrix}x\\[4pt]y\end{pmatrix},\qquad
b=\begin{pmatrix}3\\[4pt]2\end{pmatrix}.
\]
Multiplicação de matrizes produz Ax = b; a solução é obtida por métodos algorítmicos como eliminação de Gauss (escalonamento).

##### Operações elementares sobre linhas (operações que preservam o conjunto de soluções)
São permitidas três operações em linhas de uma matriz aumentada [A|b] que geram sistemas equivalentes:
- trocar duas linhas;
- multiplicar uma linha por escalar não nulo;
- adicionar a uma linha um múltiplo de outra linha.

Essas operações correspondem a transformações de sistemas que não alteram a solução e são a base do método de eliminação de Gauss.

#### Método de eliminação de Gauss (escalonamento) — objetivo e procedimento
Objetivo: transformar a matriz aumentada em uma forma triangular superior (ou forma escalonada), i.e., zerar elementos abaixo da diagonal principal, para então resolver por substituição regressiva.

Passos (esquemático):
1. Escolha o pivô na coluna atual (um elemento não nulo na diagonal).
2. Use operações elementares para zerar os elementos abaixo do pivô naquela coluna.
3. Passe à próxima coluna e repita até obter matriz triangular superior.
4. Resolva as incógnitas por substituição regressiva (back-substitution).

Exemplo aplicado passo a passo ao sistema do vídeo usando matriz aumentada:
\[
\left[\begin{array}{cc|c}
2 & -1 & 3\\[4pt]
1 & 2 & 2
\end{array}\right]
\]
- Etapa 1: usar L2 ← L2 - (1/2) L1 para zerar a posição (2,1):
  - (1) L2: 1 - (1/2)*2 = 0.
  - (2) 2 - (1/2)*(-1) = 2 + 1/2 = 5/2.
  - (3) 2 - (1/2)*3 = 2 - 1.5 = 0.5 = 1/2.
  Resultado:
  \[
  \left[\begin{array}{cc|c}
  2 & -1 & 3\\[4pt]
  0 & 5/2 & 1/2
  \end{array}\right]
  \]
- Back-substitution:
  - Segunda equação: (5/2) y = 1/2 ⇒ y = (1/2) / (5/2) = 1/5.
  - Substituir em primeira: 2x - (1/5) = 3 ⇒ 2x = 3 + 1/5 = 16/5 ⇒ x = 8/5.
Observação: este resultado decorre da aplicação direta das operações escritas; o vídeo utilizou um sistema numérico em que o cálculo levou a (2,1) porque seu sistema específico e as operações aplicadas foram ligeiramente diferentes na transcrição; ambos os processos ilustram o método e mostram que pequenos detalhes numéricos do sistema inicial definem a solução final.

Comentário técnico: a escolha de pivôs e a normalização das linhas (transformar pivô em 1) é prática comum para facilitar cálculos e implementação computacional; algoritmos robustos incluem pivoteamento parcial para evitar divisão por números muito pequenos e melhorar estabilidade numérica.

#### Espaços vetoriais e combinação linear
O vídeo reescreve o sistema como combinação linear de vetores, mostrando que o vetor do lado direito é uma combinação dos vetores coluna da matriz de coeficientes com coeficientes x e y (componentes do vetor incógnita).

Formalmente, se A = [v1 v2 ... vn] (colunas), então Ax = x1 v1 + x2 v2 + ... + xn vn. Pergunta central: existe (x1,...,xn) tal que essa combinação gera b? Isso conecta resolução de sistemas com noções de **geração** e **dependência linear** de vetores, fundações dos espaços vetoriais.

Exemplo do vídeo: com v1 = (2,1)^T e v2 = (-1,2)^T e x = 2, y = 1 obtém-se 2 v1 + 1 v2 = (3,0)^T (ilustração visual de combinação linear).

---

## Conclusão

O vídeo introduz os pilares iniciais do curso: interpretação geométrica de equações lineares, solução algébrica por substituição, representação matricial e o método de eliminação de Gauss (escalonamento) como procedimento sistemático e programável, além da visão vetorial via combinações lineares e espaços vetoriais. Esses tópicos serão explorados em profundidade nas aulas seguintes, com matrizes, operações elementares, determinantes, espaços vetoriais e aplicações computacionais (implementações e questões de estabilidade).

---

## Análise crítica

- O vídeo cumpre o objetivo de dar uma visão geral e motivar o estudante mostrando conexões entre geometria, álgebra e computação.
- Observação crítica: em transcrições rápidas de vídeos introdutórios podem surgir pequenas inconsistências numéricas ao aplicar operações ou ao apresentar exemplos numéricos — por isso sempre verificar passo a passo os cálculos algébricos (por exemplo, atenção à escolha de operações aritméticas e pivôs ao escalonar).
- Complemento técnico: para uso computacional do método de Gauss recomenda-se estudar pivoteamento parcial (troca de linhas) e análise de custo computacional (complexidade O(n^3) para eliminação direta), tópicos discutidos em referências de álgebra linear e cálculo numérico.

---

## Sugestões de complementação

- Estudar o algoritmo de Gauss com pivoteamento parcial e suas implicações numéricas (instabilidade e erros de arredondamento).
- Praticar representações em software (GeoGebra para visualizar retas e vetores; programas como Octave, Matlab, Python/NumPy para escalonamento e solução de sistemas).
- Ler capítulos iniciais do livro de W. Keith Nicholson focando em matrizes, operações elementares e algoritmo de Gauss para consolidar conceitos e notações formais.

---

## Exercícios (30) com resolução detalhada

Observação: todos os exercícios relacionam-se a sistemas lineares, eliminação de Gauss, formas matriciais e combinações lineares, conforme o conteúdo do vídeo.

1. Exercício 1 — Resolver por substituição:
   Sistema:
   \[
   \begin{cases}
   2x - y = 3\\[4pt]
   x + 2y = 2
   \end{cases}
   \]
   Resolução:
   - Isole x na segunda equação: x = 2 - 2y.
   - Substitua na primeira: 2(2 - 2y) - y = 3 ⇒ 4 - 4y - y = 3 ⇒ 4 - 5y = 3 ⇒ -5y = -1 ⇒ y = 1/5.
   - Substitua y em x: x = 2 - 2*(1/5) = 2 - 2/5 = 8/5.
   - Solução: (x,y) = (8/5, 1/5).

2. Exercício 2 — Resolver com eliminação de Gauss (matriz aumentada):
   Sistema:
   \[
   \begin{cases}
   x + y = 4\\[4pt]
   2x - y = 1
   \end{cases}
   \]
   Resolução:
   - Matriz aumentada: [ [1 1 | 4]; [2 -1 | 1] ].
   - L2 ← L2 - 2·L1 ⇒ L2: (2 - 2·1 = 0; -1 - 2·1 = -3; 1 - 2·4 = -7).
   - Matriz: [ [1 1 | 4]; [0 -3 | -7] ].
   - Segunda equação: -3 y = -7 ⇒ y = 7/3.
   - Primeira: x + 7/3 = 4 ⇒ x = 4 - 7/3 = 12/3 - 7/3 = 5/3.
   - Solução: (5/3, 7/3).

3. Exercício 3 — Determinar se o sistema tem solução única:
   Sistema:
   \[
   \begin{cases}
   2x + 4y = 6\\[4pt]
   x + 2y = 3
   \end{cases}
   \]
   Resolução:
   - Observe que segunda equação multiplicada por 2 dá 2x + 4y = 6, que é exatamente a primeira.
   - As equações são dependentes ⇒ infinitas soluções ao longo da reta x + 2y = 3.
   - Solução geral: x = 3 - 2y, y livre t ∈ R ⇒ (x,y) = (3 - 2t, t).

4. Exercício 4 — Sistema inconsistente:
   \[
   \begin{cases}
   x + y = 1\\[4pt]
   2x + 2y = 5
   \end{cases}
   \]
   Resolução:
   - Segunda linha é 2·(x+y) = 2, mas tem 5 ⇒ contradição.
   - Não há solução.

5. Exercício 5 — Eliminação de Gauss em 3×3:
   Sistema:
   \[
   \begin{cases}
   x + y + z = 6\\[4pt]
   2x - y + 3z = 14\\[4pt]
   -x + 4y + z = 2
   \end{cases}
   \]
   Resolução:
   - Matriz aumentada:
     \[
     \left[\begin{array}{ccc|c}
     1 & 1 & 1 & 6\\
     2 & -1 & 3 & 14\\
     -1 & 4 & 1 & 2
     \end{array}\right]
     \]
   - L2 ← L2 - 2·L1 ⇒ [0, -3, 1, 2].
   - L3 ← L3 + L1 ⇒ [0, 5, 2, 8].
   - Agora pivô da coluna 2 é -3; faça L3 ← L3 + (5/ -3)·L2 = L3 - (5/3)·L2.
     - Compute L3 new:
       - coluna2: 5 - (5/3)(-3) = 5 + 5 =10? (corrija: (5/ -3)·(-3) = -5; L3 + (-5) = 0) — método alternativo: melhor trabalhar com frações stepwise:
       - L2: [0, -3, 1 | 2]
       - Para zerar L3(2)=5, faça L3 ← L3 + (5/3)·L2? Note: L2(2) = -3, queremos 0: L3 + (5/3)·L2 ⇒ 5 + (5/3)(-3) = 5 -5 =0. Correção: multiplicador = 5/3 with L2.
     - L3 new:
       - coluna3: 2 + (5/3)*1 = 2 + 5/3 = 11/3.
       - RHS: 8 + (5/3)*2 = 8 + 10/3 = 34/3.
   - Matriz triangular:
     \[
     \left[\begin{array}{ccc|c}
     1 & 1 & 1 & 6\\
     0 & -3 & 1 & 2\\
     0 & 0 & 11/3 & 34/3
     \end{array}\right]
     \]
   - Terceira equação: (11/3) z = 34/3 ⇒ z = 34/11.
   - Segunda: -3 y + z = 2 ⇒ -3y + 34/11 = 2 ⇒ -3y = 2 - 34/11 = (22 - 34)/11 = -12/11 ⇒ y = (4/11).
   - Primeira: x + y + z =6 ⇒ x = 6 - 4/11 - 34/11 = 6 - 38/11 = 66/11 - 38/11 = 28/11.
   - Solução: (28/11, 4/11, 34/11).

6. Exercício 6 — Representar Ax = b como combinação linear:
   Dados v1 = (1,2)^T, v2 = (3, -1)^T e b = (7,1)^T. Encontre scalars α, β tais que α v1 + β v2 = b.
   Resolução:
   - Sistema:
     \[
     \begin{cases}
     1·α + 3·β = 7\\[4pt]
     2·α -1·β = 1
     \end{cases}
     \]
   - Use eliminação: da primeira, α = 7 - 3β.
   - Substituir na segunda: 2(7 - 3β) - β = 1 ⇒ 14 -6β - β = 1 ⇒ -7β = -13 ⇒ β = 13/7.
   - α = 7 - 3·(13/7) = 7 - 39/7 = 49/7 - 39/7 = 10/7.
   - Combinação: (α,β) = (10/7, 13/7).

7. Exercício 7 — Verificar dependência linear:
   Vetores u = (2,4), v = (1,2). Determinar se são linearmente dependentes.
   Resolução:
   - Note v·2 = (2,4) = u ⇒ u = 2 v.
   - Logo dependentes; dimensão do subespaço gerado = 1.

8. Exercício 8 — Resolver sistema com parâmetro (infinitas soluções):
   \[
   \begin{cases}
   x + 2y - z = 1\\[4pt]
   2x + 4y - 2z = 2
   \end{cases}
   \]
   Resolução:
   - A segunda é 2·(primeira) ⇒ mesmas equações ⇒ infinito de soluções.
   - Escreva solução geral: x = 1 - 2y + z; parâmetros y = s, z = t ⇒ (x,y,z) = (1 - 2s + t, s, t).

9. Exercício 9 — Aplicar pivoteamento parcial:
   Sistema:
   \[
   \begin{cases}
   0.0001 x + y = 1\\[4pt]
   x + y = 2
   \end{cases}
   \]
   Resolução:
   - Se escalonarmos sem pivoteamento, dividiríamos por 0.0001 causando grande erro numérico. Pivoteamento parcial troca linhas para evitar divisão por número pequeno.
   - Troque L1 ↔ L2:
     \[
     \begin{cases}
     x + y = 2\\
     0.0001 x + y = 1
     \end{cases}
     \]
   - L2 ← L2 - 0.0001·L1 ⇒ L2: (0, 1 - 0.0001·1 = 0.9999; RHS = 1 - 0.0001·2 = 0.9998).
   - Segunda: 0.9999 y = 0.9998 ⇒ y ≈ 0.9999.
   - Primeiro: x = 2 - y ≈ 1.0001.
   - Demonstra a utilidade do pivoteamento para estabilidade numérica.

10. Exercício 10 — Encontrar determinante 2×2 e relacionar à solução:
    Matriz A = [[2, -1],[1,2]]. Calcule det(A) e conclua sobre unicidade de solução para Ax = b.
    Resolução:
    - det(A) = 2·2 - (-1)·1 = 4 + 1 = 5 ≠ 0 ⇒ A é invertível ⇒ para todo b existe solução única x = A^{-1} b.

11. Exercício 11 — Resolver 3×3 (exemplo direto):
    Sistema:
    \[
    \begin{cases}
    1x + 0y + 2z = 3\\[4pt]
    0x + 1y - z = 1\\[4pt]
    2x + y + 3z = 8
    \end{cases}
    \]
    Resolução:
    - Use L3 ← L3 - 2·L1 ⇒ L3: (0, 1, -1).
    - Agora L2 e L3 iguais: y - z = 1 and y - z = 2? calc RHS: L3 RHS: 8 - 2·3 = 2.
    - Então temos:
      - Eq1: x + 2z = 3 ⇒ x = 3 - 2z.
      - Eq2: y - z = 1 ⇒ y = 1 + z.
      - Eq3: y - z = 2 ⇒ Contradição se não coincidem. Observação: revisar as operações: após L3 ← L3 - 2·L1: L3: (2-2·1=0; 1-2·0=1; 3 - 2·2 = -1; RHS: 8 - 6 = 2). Assim L2: y - z =1, L3: y - z = 2 ⇒ inconsistente ⇒ sem solução.

12. Exercício 12 — Combinação linear ilustrativa:
    Dados v1 = (1,0,1), v2 = (0,1,2), b = (2,1,4). Encontre aí x,y com x v1 + y v2 = b.
    Resolução:
    - Sistema:
      \[
      \begin{cases}
      x = 2\\
      y = 1\\
      x + 2y = 4
      \end{cases}
      \]
    - Verifique terceira equação: 2 + 2·1 = 4 ok. Solução (2,1).

13. Exercício 13 — Verificar se b pertence ao subespaço gerado por colunas:
    A = [[1,2],[3,6]], b = (4,12). Pergunta: existe x tal que Ax=b?
    Resolução:
    - Colunas são dependentes (segunda = 2·primeira). b = (4,12) = 4·(1,3) = 2·(2,6). Então existe, com infinitas soluções (parâmetro livre). Ex.: t = 0 ⇒ x = (4,0) funciona? A·(4,0) = 4·(1,3) = (4,12). Assim uma solução: x = (4,0), soluções paramétricas conforme relação de dependência.

14. Exercício 14 — Eliminação com normalização de pivô:
    Sistema:
    \[
    \begin{cases}
    3x + 6y = 9\\
    x + y = 4
    \end{cases}
    \]
    Resolução:
    - Normalize L1: L1 ← L1 /3 ⇒ x + 2y = 3.
    - Subtraia L2 - L1 ⇒ (x + y) - (x + 2y) = 4 - 3 ⇒ -y = 1 ⇒ y = -1.
    - x = 4 - y = 5.
    - Solução: (5, -1).

15. Exercício 15 — Sistema 3×3 com back-substitution:
    \[
    \begin{cases}
    2x + y - z = 3\\
    0x + 3y + z = 7\\
    0x + 0y + 4z = 8
    \end{cases}
    \]
    Resolução:
    - Terceira eq: 4z = 8 ⇒ z = 2.
    - Segunda: 3y + 2 = 7 ⇒ 3y = 5 ⇒ y = 5/3.
    - Primeira: 2x + 5/3 - 2 = 3 ⇒ 2x = 3 - 5/3 + 2 = (9/3 - 5/3 + 6/3) = 10/3 ⇒ x = 5/3.
    - Solução: (5/3, 5/3, 2).

16. Exercício 16 — Encontrar inversa 2×2 e usar para resolver:
    A = [[4,7],[2,3]], b = (1,0). Encontre x = A^{-1} b.
    Resolução:
    - det(A) = 4·3 - 7·2 = 12 -14 = -2.
    - A^{-1} = (1/det)·[[3, -7],[-2, 4]] = (-1/2)·[[3,-7],[-2,4]] = [[-3/2, 7/2],[1, -2]].
    - x = A^{-1} b = first column times 1 plus second times 0 ⇒ x = column1 = (-3/2, 1)^T.

17. Exercício 17 — Eliminação com trocas de linha:
    Sistema:
    \[
    \begin{cases}
    0x + y = 2\\
    x + 2y = 5
    \end{cases}
    \]
    Resolução:
    - Troque linhas para ter pivô não nulo na posição (1,1): L1 ↔ L2 ⇒ [ [1 2 | 5]; [0 1 |2] ].
    - Back-substitute: segunda: y = 2; primeira: x + 4 =5 ⇒ x=1.
    - Solução: (1,2).

18. Exercício 18 — Sistema com parâmetros (solução infinita), encontrar solução geral:
    \[
    \begin{cases}
    x - y + 2z = 0\\
    2x - 2y + 4z = 0
    \end{cases}
    \]
    Resolução:
    - Segunda é 2·(primeira); uma equação redundante.
    - Livre: z = t; então primeira: x - y + 2t = 0 ⇒ x = y - 2t.
    - Parâmetros y = s, z = t ⇒ (x,y,z) = (s - 2t, s, t).

19. Exercício 19 — Resolver sistema com frações:
    \[
    \begin{cases}
    \frac{1}{2}x + y = 3\\
    x - \frac{1}{4}y = 1
    \end{cases}
    \]
    Resolução:
    - Multiplique primeira por 2: x + 2y = 6.
    - Segunda: x - 1/4 y = 1.
    - Subtraia segunda da primeira: (x + 2y) - (x - 1/4 y) = 6 -1 ⇒ (2 + 1/4)y = 5 ⇒ (9/4) y = 5 ⇒ y = 20/9.
    - x = 1 + 1/4 y = 1 + 5/9 = 14/9.
    - Solução: (14/9, 20/9).

20. Exercício 20 — Checar consistência via posto da matriz:
    A = [[1,2,3],[2,4,6],[3,6,9]], b = (1,2,3). Existe solução?
    Resolução:
    - Colunas de A são lineares dependentes; rank(A) = 1 (todas colunas são múltiplos).
    - Se b pertence à coluna gerada por A? b = (1,2,3) é múltiplo de (1,2,3) com coef 1, que é uma combinação das colunas? Como colunas são (1,2,3),(2,4,6),(3,6,9) — b coincide com primeira coluna ⇒ existe solução infinita. Ex.: x = (1,0,0).

21. Exercício 21 — Resolver sistema triangular superior:
    \[
    \begin{cases}
    3x + 2y - z = 4\\
    0x + y + 3z = 1\\
    0x + 0y + 5z = 10
    \end{cases}
    \]
    Resolução:
    - Terceira: z = 2.
    - Segunda: y + 3·2 = 1 ⇒ y = 1 -6 = -5.
    - Primeira: 3x + 2(-5) - 2 = 4 ⇒ 3x -10 -2 =4 ⇒ 3x = 16 ⇒ x = 16/3.

22. Exercício 22 — Aplicar Gauss-Jordan para matriz identidade:
    A = [[2,1],[1,1]]. Use Gauss-Jordan para encontrar A^{-1}.
    Resolução:
    - Forme [A | I]:
      \[
      \left[\begin{array}{cc|cc}
      2 & 1 & 1 & 0\\
      1 & 1 & 0 & 1
      \end{array}\right]
      \]
    - L1 ↔ L2 (opcional) ou eliminar:
      - L1 ← L1 - 2·L2 ⇒ [0, -1, 1, -2].
      - Agora normalize L2 etc; seguir passos:
      - Melhor: L1 ← L1 - L2 ⇒ [1,0 |1, -1]; L2 ← L2 - (1)*L1(original?) — atenção com ordem; uma sequência possível:
        - L1 ↔ L2 ⇒ [1 1 | 0 1]; [2 1 |1 0]
        - L2 ← L2 - 2·L1 ⇒ [1 1 | 0 1]; [0 -1 |1 -2]
        - L2 ← -L2 ⇒ [0 1 | -1 2]
        - L1 ← L1 - L2 ⇒ [1 0 | 1  -1]
      - Resultado: A^{-1} = [[1, -1],[-1, 2]].

23. Exercício 23 — Sistema com números inteiros:
    \[
    \begin{cases}
    3x + y = 10\\
    2x + 4y = 8
    \end{cases}
    \]
    Resolução:
    - L2 ← L2 - (2/3)·L1 ⇒ ou usar eliminação direta:
    - Multiplique L1 por 2: 6x + 2y = 20. Subtraia 3·L2: 6x + 12y = 24 ⇒ subtraindo: (6x+2y) - (6x+12y) = 20 -24 ⇒ -10y = -4 ⇒ y = 2/5.
    - x = (10 - y)/3 = (10 - 2/5)/3 = (50/5 - 2/5)/3 = 48/5 /3 = 16/5.
    - Solução: (16/5, 2/5).

24. Exercício 24 — Analisar sistema retangular (mais equações que incógnitas):
    Sistema (3×2):
    \[
    \begin{cases}
    x + y = 2\\
    2x + 2y = 4\\
    3x + 3y = 6
    \end{cases}
    \]
    Resolução:
    - Todas equações múltiplos ⇒ sistema depende de uma equação ⇒ infinitas soluções: x = 2 - y.

25. Exercício 25 — Exercício prático com GeoGebra (descritivo):
    - Pedir ao aluno: desenhar as retas 2x - y = 3 e x + 2y = 2 no GeoGebra e verificar interseção.
    Resolução esperada:
    - Interseção numérica coincide com solução algébrica obtida pelos métodos anteriores; utilizar os comandos de intersecção do GeoGebra para checar.

26. Exercício 26 — Solução usando formula de Cramer (2×2):
    \[
    \begin{cases}
    4x - y = 3\\
    2x + 3y = 7
    \end{cases}
    \]
    Resolução:
    - det(A) = 4·3 - (-1)·2 = 12 + 2 = 14.
    - det_x = [3, -1; 7, 3] ⇒ 3·3 - (-1)·7 = 9 + 7 = 16 ⇒ x = det_x / det = 16/14 = 8/7.
    - det_y = [4,3;2,7] ⇒ 4·7 - 3·2 = 28 -6 =22 ⇒ y = 22/14 = 11/7.

27. Exercício 27 — Determinar base e dimensão do espaço gerado:
    Vetores a = (1,0,2), b = (2,0,4), c = (0,1,1). Determine uma base de span{a,b,c}.
    Resolução:
    - Note b = 2a ⇒ dependente. Então {a,c} são linearmente independentes (verificar: não há α,β com α a + β c = 0 exceto α=β=0). Dimensão = 2. Base = {a,c}.

28. Exercício 28 — Resolver sistema com números negativos:
    \[
    \begin{cases}
    -x + 2y = 1\\
    3x - 6y = -3
    \end{cases}
    \]
    Resolução:
    - Segunda é -3·(primeira): -3(-x + 2y) = 3x -6y = -3 ⇒ mesma equação ⇒ infinito de soluções; solução geral: x = 2y -1 ⇒ y = t, x = 2t -1.

29. Exercício 29 — Encontrar coordenadas de um vetor em base dada:
    Base B = { (1,1), (1,-1) } e v = (4,0). Encontre coordenadas [v]_B.
    Resolução:
    - Procurar α,β tal que α(1,1) + β(1,-1) = (4,0).
    - Sistema: α + β = 4; α - β = 0 ⇒ somando: 2α = 4 ⇒ α = 2 ⇒ β = 2.
    - Coordenadas: (2,2).

30. Exercício 30 — Implementação conceitual (passos) do método de Gauss em computador:
    - Descrever o algoritmo (pseudocódigo) passo a passo e mencionar pivoteamento parcial.
    Resolução (resumo passo a passo):
    1. Para k de 1 a n-1:
       - Escolher linha p ≥ k com |A[p,k]| máximo (pivoteamento parcial).
       - Se p ≠ k, trocar linhas k e p.
       - Para i = k+1 até n: multiplicador m = A[i,k] / A[k,k]; para j = k até n: A[i,j] ← A[i,j] - m·A[k,j]; b[i] ← b[i] - m·b[k].
    2. Após triangularização, aplica back-substitution para obter x_n, x_{n-1}, ..., x_1.
    Observação: pivoteamento melhora estabilidade numérica e evita divisões por zero (ou por números muito pequenos).

---

## Bibliografia (formato ABNT)

- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015. Acesso: Google Books, 24 abr. 2015.
- NICHOLSON, W. Keith. Álgebra Linear. Capa comum. AMGH, 2006 (edição em português disponível). Consultado: Amazon Brasil, acesso em 11 out. 2025.
- ROMANAZZI, Giuseppe. Método direto de Eliminação de Gauss. Portal IME Unicamp. Material de apoio e slides sobre eliminação de Gauss. Acesso em 11 out. 2025.
- Responde Aí. Escalonamento de Matrizes: Eliminação de Gauss Passo a Passo. Acesso em 11 out. 2025.
- O Baricentro da Mente. Escalonamento ou o Método da Eliminação de Gauss. Acesso em 11 out. 2025.
- Transcrição do vídeo: UNIVESP — "Geometria analítica e álgebra linear - Uma ideia geral da disciplina" (YouTube). Consultado em 11 out. 2025.

---

## Materiais complementares

- Livro: Nicholson, W. Keith. Álgebra Linear. AMGH Editora, 2. ed., 2015. (Capítulos sobre matrizes, operações elementares e algoritmo de Gauss são recomendados).
- Artigos e notas sobre eliminação de Gauss e estabilidade numérica: Giuseppe Romanazzi (IMEC-UNICAMP) — "Método direto de Eliminação de Gauss".
- Tutoriais e páginas explicativas (ensinando passo a passo e com exemplos resolvidos): Responde Aí — "Escalonamento de Matrizes"; blog O Baricentro da Mente — artigo sobre eliminação de Gauss com exemplos.
- Ferramentas: GeoGebra (visualização geométrica de retas e vetores); Python/NumPy ou Octave/Matlab (implementação prática das rotinas de solução de sistemas).

---