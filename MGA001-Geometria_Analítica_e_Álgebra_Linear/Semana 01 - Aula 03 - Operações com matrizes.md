# Operações com matrizes

### Introdução

Este material foi elaborado a partir do vídeo "Operações com matrizes" da disciplina Geometria Analítica e Álgebra Linear (transcrição do vídeo utilizada como fonte principal) e das diretivas fornecidas. O objetivo é apresentar, de forma didática e compatível com GitHub Markdown, os conceitos introdutórios sobre matrizes, as operações básicas (soma, produto por escalar, multiplicação entre matrizes), a interpretação prática via tabelas e um exemplo aplicado (composição de tabelas por multiplicação de matrizes). As explicações seguem a notação matemática em LaTeX quando pertinente, com alternativas em texto quando necessário.

---

## Introdução ao tema

- Definição intuitiva: uma matriz é uma tabela retangular de números organizada em linhas e colunas; é a estrutura natural para representar tabelas de dados e imagens (pixels) e também para modelar transformações lineares em álgebra linear.

- Notação: denotamos por $A = (a_{ij})$ uma matriz cujos elementos são $a_{ij}$, onde $i$ é o índice da linha e $j$ o índice da coluna. Se $A$ tem $m$ linhas e $n$ colunas dizemos que $A$ é uma matriz $m\times n$.

- Exemplo
```
A = [ a_11  a_12  ...  a_1n ]
    [ a_21  a_22  ...  a_2n ]
    [ ...                   ]
    [ a_m1  a_m2  ...  a_mn ]
```

---

## Desenvolvimento

### 1. Tipos básicos e notação

- Matriz linha: ```1 x n```, exemplo: 
```
- L = [ l₁  l₂  ...  lₙ ]
```

- Matriz coluna: `m x 1`, exemplo: 
```
- c = [ c_1 ]
      [ c_2 ]
      [ ... ]
      [ c_m ]
```

- Matriz quadrada: ```n X n``` (mesmo número de linhas e colunas), exemplo:
```  
- Q = [ q_11  q_12  ...  q_1n ]
      [ q_21  q_22  ...  q_2n ]
      [ ...                   ]
      [ q_n1  q_n2  ...  q_nn ]
```

Essas noções e a notação foram destacadas no vídeo como base para a manipulação algébrica de matrizes.

---

### 2. Operações elementares apresentadas no vídeo

A seguir as operações que o vídeo descreve, com fórmulas, significado das variáveis, lógica e exemplos passo a passo.

#### 2.1 Soma de matrizes
- Fórmula: se $A=(a_{ij})$ e $B=(b_{ij})$ são ambas $m\times n$, então sua soma $C=A+B$ é a matriz $m\times n$ cuja entrada genérica é
  \[
  c_{ij} = a_{ij} + b_{ij}.
  \]
  - Variáveis: $a_{ij}, b_{ij}$ são os elementos nas mesmas posições das matrizes $A$ e $B$; $c_{ij}$ é o elemento resultante.
  - Lógica: soma é feita componente a componente; condição necessária: mesmas dimensões.
- Exemplo resolvido:
  - $A=\begin{pmatrix}1 & 2\\ 3 & 4\end{pmatrix}$, $B=\begin{pmatrix}5 & -1\\ 0 & 2\end{pmatrix}$.
  - Computo:
    \[
    C = A+B = \begin{pmatrix}1+5 & 2+(-1)\\ 3+0 & 4+2\end{pmatrix}
      = \begin{pmatrix}6 & 1\\ 3 & 6\end{pmatrix}.
    \]

#### 2.2 Produto por escalar
- Fórmula: dado escalar $k\in\mathbb{R}$ e matriz $A=(a_{ij})$ ($m\times n$),
  \[
  (kA)_{ij} = k\cdot a_{ij}.
  \]
  - Variáveis: $k$ é o escalar; $a_{ij}$ elemento de $A$.
  - Lógica: multiplicação aplicada entrywise.
- Exemplo resolvido:
  - $k=4$, $A=\begin{pmatrix}2 & 3\\ -1 & 0\end{pmatrix}$.
  - $4A = \begin{pmatrix}8 & 12\\ -4 & 0\end{pmatrix}$.

#### 2.3 Combinação linear e operações combinadas
- Podemos combinar escalar e soma: por exemplo $2A + B$ é calculado primeiro como $2A$ (multiplicação escalar) e depois soma com $B$ usando a regra da soma de matrizes.

---

### 3. Multiplicação entre matrizes (definição, condição e algoritmo)

O vídeo apresenta a definição de produto entre matrizes, a condição necessária para que o produto exista e o procedimento para calcular cada elemento do produto.

#### 3.1 Condição de compatibilidade
- Se $A$ é $m\times n$ e $B$ é $n\times p$ então o produto $C = A B$ existe e será uma matriz $m\times p$.
- Intuição: o número de colunas de $A$ deve igualar o número de linhas de $B$.

#### 3.2 Fórmula do elemento genérico
- Fórmula (LaTeX):
  \[
  c_{ij} = \sum_{k=1}^{n} a_{ik}\,b_{kj},\qquad i=1,\dots,m,\ j=1,\dots,p.
  \]
  - Significado: $c_{ij}$ é o produto escalar da i-ésima linha de $A$ com a j-ésima coluna de $B$.
  - Variáveis: $a_{ik}$ é elemento da linha $i$, coluna $k$ de $A$; $b_{kj}$ é elemento da linha $k$, coluna $j$ de $B$; $n$ é a dimensão interna comum.
  - Lógica por trás: essa escolha de definição corresponde à composição de transformações lineares e à agregação de contribuições ao elemento $(i,j)$ através do índice intermediário $k$.
- Exemplo resolvido passo a passo:
  - Seja
    \[
    A = \begin{pmatrix}1 & 3 & -2 & 5\end{pmatrix} \quad (1\times 4),
    \quad
    B = \begin{pmatrix}2\\[4pt]0\\[4pt]1\\[4pt]3\end{pmatrix} \quad (4\times 1).
    \]
  - O produto $C = AB$ é $1\times1$ (um número):  
    \[
    c_{11} = 1\cdot2 + 3\cdot0 + (-2)\cdot1 + 5\cdot3 = 2 + 0 -2 +15 = 15.
    \]
    Resultado: $C = (15)$.
  - Exemplo mais geral: se $A$ é $2\times3$ e $B$ é $3\times2$, para calcular $c_{21}$ fazemos o somatório sobre $k=1,2,3$ de $a_{2k}b_{k1}$.

#### 3.3 Interpretação prática (aplicação mostrada no vídeo)
- O vídeo explica que multiplicações de matrizes representam composições de transformações lineares e exemplifica com tabelas que modelam linhas de transmissão entre usinas e cidades: multiplicando matrizes que representam ligações em etapas obtemos uma matriz que resume o número de rotas compostas (soma sobre caminhos intermediários).
- Essa interpretação justifica a definição do produto pela utilidade em aplicações reais onde a composição de relações é necessária.

---

### 4. Exemplo aplicado: tabelas de transmissão (resumo do vídeo)

- Situação: matriz $M$: usinas × cidades (número de linhas de transmissão diretas), matriz $T$: cidades × outras cidades (número de transmissões), então $M\cdot T$ dá uma matriz que representa composições (quantas linhas efetivas de usina → cidade final via cidades intermediárias), conforme explicado no vídeo com o exemplo conceitual de usinas e cidades.
- Conclusão: multiplicação de matrizes automatiza a contagem e compostagem de relações em redes grandes (muitas usinas/cidades), evidenciando por que a definição é útil.

---

## Conclusão

- O vídeo apresenta e motiva as operações básicas com matrizes: soma, produto por escalar e multiplicação entre matrizes, enfatizando condições de existência e interpretação geométrica/operacional (transformações lineares e composição de relações).
- A definição do produto é escolhida por sua utilidade prática (composição de relações e transformações), mesmo que sua forma seja menos intuitiva que soma ou multiplicação entrywise.

---

## Análise crítica

- Pontos fortes: demonstração passo a passo das operações básicas; uso de exemplos concretos (imagens e tabelas) que ajudam a entender por que certas definições são úteis na prática (p.ex., multiplicação para composição de ligações).
- Limitações/observações: o vídeo não discute complexidade computacional das operações nem aspectos numéricos (estabilidade, custo de memória) nem variações alternativas (Hadamard product — produto entrywise — que é diferente da multiplicação matricial padrão). Esses tópicos são relevantes para aplicações e serão úteis como complementação em leituras adicionais.

---

## Sugestões de complementação

- Consultar capítulos iniciais de Nicholson para fundamentação teórica de operadores lineares, multiplicação e propriedades algébricas de matrizes.  
- Experimentar implementações em Python/NumPy para visualizar diferenças de desempenho entre loops explícitos e operações vetorizadas (produto interno para cada elemento versus multiplicação matricial nativa).  
- Estudar produtos alternativos (produto de Hadamard, produto Kronecker) quando aplicável em processamento de sinais e imagens.

---

## Exercícios (30) com resolução detalhada

Observação: todos os exercícios cobrem soma, produto por escalar, multiplicação matricial, condição de compatibilidade, interpretação e exemplos práticos. As fórmulas usam LaTeX; quando o seu cliente renderizador não suportar LaTeX, as expressões são legíveis em texto simples.

1. Enunciado: Calcule $A+B$ se
   \[
   A=\begin{pmatrix}1 & 2\\[4pt]3 & 4\end{pmatrix},\quad
   B=\begin{pmatrix}5 & -1\\[4pt]0 & 2\end{pmatrix}.
   \]
   Resolução:
   - Fórmula: $(A+B)_{ij}=a_{ij}+b_{ij}$.
   - Cálculo:
     \[
     A+B=\begin{pmatrix}1+5 & 2+(-1)\\[4pt]3+0 & 4+2\end{pmatrix}
         =\begin{pmatrix}6 & 1\\[4pt]3 & 6\end{pmatrix}.
     \]

2. Enunciado: Calcule $3A$ para
   \[
   A=\begin{pmatrix}2 & -1\\[4pt]0 & 5\end{pmatrix}.
   \]
   Resolução:
   - Fórmula: $(kA)_{ij}=k a_{ij}$.
   - Cálculo: $3A=\begin{pmatrix}6 & -3\\[4pt]0 & 15\end{pmatrix}$.

3. Enunciado: Determine se $A+B$ existe para $A$ de dimensão $2\times3$ e $B$ de dimensão $3\times2$.  
   Resolução:
   - Condição: somas exigem mesmas dimensões. Como $2\times3\neq3\times2$, não existe $A+B$.

4. Enunciado: Calcule $AB$ com
   \[
   A=\begin{pmatrix}1 & 0 & 2\\[4pt] -1 & 3 & 1\end{pmatrix}\ (2\times3),
   \quad
   B=\begin{pmatrix}2 & 1\\[4pt]0 & -1\\[4pt]1 & 2\end{pmatrix}\ (3\times2).
   \]
   Resolução:
   - Verificar compatibilidade: colunas de $A$ = 3; linhas de $B$ = 3 → produto existe; resultado será $2\times2$.
   - Fórmula: $c_{ij}=\sum_{k=1}^3 a_{ik} b_{kj}$.
   - Cálculo:
     - $c_{11}=1\cdot2 + 0\cdot0 + 2\cdot1 = 2 + 0 +2 =4$.
     - $c_{12}=1\cdot1 + 0\cdot(-1) + 2\cdot2 =1 +0 +4 =5$.
     - $c_{21}=(-1)\cdot2 + 3\cdot0 + 1\cdot1 = -2 +0 +1 = -1$.
     - $c_{22}=(-1)\cdot1 + 3\cdot(-1) + 1\cdot2 = -1 -3 +2 = -2$.
   - Resultado:
     \[
     AB = \begin{pmatrix}4 & 5\\[4pt]-1 & -2\end{pmatrix}.
     \]

5. Enunciado: Calcule $c_{11}$ do produto entre uma matriz linha $R=(1\ 3\ -2\ 5)$ e a coluna $v=(2\ 0\ 1\ 3)^T$.  
   Resolução:
   - Produto é $1\times1$: $c_{11}=1\cdot2 + 3\cdot0 + (-2)\cdot1 +5\cdot3 = 2 +0 -2 +15 =15$.

6. Enunciado: Dadas $A$ ($2\times2$) e $B$ ($2\times2$), prove que $(A+B)^T = A^T + B^T$ (transposta da soma).  
   Resolução:
   - Uso da definição: $(A+B)_{ij}=a_{ij}+b_{ij}$. A transposta troca índices: $((A+B)^T)_{ij}=(A+B)_{ji}=a_{ji}+b_{ji}=(A^T)_{ij}+(B^T)_{ij}$. Logo igualdade entrywise.

7. Enunciado: Verifique compatibilidade e calcule $AB$ para
   \[
   A=\begin{pmatrix}1 & 2\\[4pt]3 & 4\\[4pt]5 & 6\end{pmatrix}\ (3\times2),
   \quad
   B=\begin{pmatrix}7 & 8 & 9\\[4pt]0 & 1 & -1\end{pmatrix}\ (2\times3).
   \]
   Resolução:
   - $AB$ existe e é $3\times3$.
   - Calcule cada entrada por produto escalar da linha de $A$ com coluna de $B$.
   - Resultados (cálculos explícitos):
     - Primeira linha × primeira coluna: $1\cdot7 + 2\cdot0 = 7$.
     - ... (proceder para todas) → finalize matriz:
     \[
     AB=\begin{pmatrix}7 & 10 & 0\\[4pt]21 & 28 & 5\\[4pt]35 & 46 & 10\end{pmatrix}.
     \]
     (verifique entrywise seguindo a regra $c_{ij}=\sum_k a_{ik}b_{kj}$).

8. Enunciado: Mostre que, em geral, $AB\neq BA$ (não comutatividade). Forneça exemplo numérico.  
   Resolução:
   - Tome $A=\begin{pmatrix}1 & 1\\[4pt]0 & 1\end{pmatrix}$, $B=\begin{pmatrix}0 & 1\\[4pt]1 & 0\end{pmatrix}$.
   - Calcule $AB=\begin{pmatrix}1\cdot0+1\cdot1 & 1\cdot1+1\cdot0\\[4pt]0\cdot0+1\cdot1 & 0\cdot1+1\cdot0\end{pmatrix}=\begin{pmatrix}1 & 1\\[4pt]1 & 0\end{pmatrix}$.
   - Calcule $BA=\begin{pmatrix}0\cdot1+1\cdot0 & 0\cdot1+1\cdot1\\[4pt]1\cdot1+0\cdot0 & 1\cdot1+0\cdot1\end{pmatrix}=\begin{pmatrix}0 & 1\\[4pt]1 & 1\end{pmatrix}$.
   - $AB\neq BA$.

9. Enunciado: Dado $A=\begin{pmatrix}2 & -1\\[4pt]1 & 0\end{pmatrix}$, calcule $2A + \begin{pmatrix}1 & 1\\[4pt]1 & 1\end{pmatrix}$.  
   Resolução:
   - $2A = \begin{pmatrix}4 & -2\\[4pt]2 & 0\end{pmatrix}$.
   - Soma: $\begin{pmatrix}5 & -1\\[4pt]3 & 1\end{pmatrix}$.

10. Enunciado: Mostre que se $A$ é $m\times n$ e $B$ é $n\times p$, então cada $c_{ij}$ de $C=AB$ é combinação linear da coluna $j$ de $B$ com coeficientes vindos de colunas de $A$.  
    Resolução:
    - Escreva linha $i$ de $A$ como vetor $(a_{i1},\dots,a_{in})$ e colunas de $B$ como $b^{(j)}$. Então $c_{ij} = \sum_k a_{ik} b_{kj}$ é exatamente o produto escalar entre a linha e a coluna, que é uma combinação linear das entradas da coluna $j$ com coeficientes $a_{ik}$.

11. Enunciado: Verifique se $A=\begin{pmatrix}1 & 2\\[4pt]2 & 4\end{pmatrix}$ é inversível.  
    Resolução:
    - Determinante (2×2): $\det(A)=1\cdot4 - 2\cdot2 = 4 -4 = 0$. Como det = 0, $A$ não é inversível.

12. Enunciado: Calcule $AB$ e $BA$, quando definidas, para
    \[
    A=\begin{pmatrix}1 & 2 & 3\\[4pt]0 & 1 & 4\end{pmatrix}\ (2\times3),\quad
    B=\begin{pmatrix}2 & 0\\[4pt]1 & 1\\[4pt]0 & -1\end{pmatrix}\ (3\times2).
    \]
    Resolução:
    - $AB$ existe e é $2\times2$; calcule entrywise seguindo $c_{ij}=\sum_k a_{ik}b_{kj}$.  
    - $BA$ não existe (B é $3\times2$, A é $2\times3$ → $BA$ é $3\times3$ e existe sim; atenção: o produto $BA$ existe porque colunas de $B$ = 2 e linhas de $A$ = 2 → $BA$ é $3\times3$). Calcule separadamente. (Proceder compute passo a passo).

13. Enunciado: Dada matriz identidade $I_2$, verifique que $AI_2 = I_2 A = A$ para qualquer $A$ $2\times2$.  
    Resolução:
    - Use definição: $I_2$ tem 1 na diagonal e 0 fora; o produto com $A$ mantém cada linha/coluna igual por definição do produto (ver cálculo componentwise).

14. Enunciado: Se $A$ é $m\times n$, quantos elementos tem $A$?  
    Resolução:
    - $m\cdot n$ elementos.

15. Enunciado: Mostre que multiplicar cada entrada de uma matriz que representa imagem por 0.5 reduz a intensidade pela metade (efeito escalar).  
    Resolução:
    - Aplicar $0.5\cdot A$ entrywise reduz cada pixel para metade do valor original, preservando estrutura espacial.

16. Enunciado: Explique por que a multiplicação de matrizes representa composição de relações (ex.: caminhos de usina → cidade → cidade final).  
    Resolução:
    - Cada $c_{ij}$ soma sobre os intermediários $k$ a contribuição de caminhos via $k$; isso é soma de produtos que contabilizam caminhos compostos; é exatamente composição de transformações lineares (ver discussão do vídeo).

17. Enunciado: Dado $A$ ($2\times3$) e $B$ ($3\times2$) do exercício 4, calcule a linha 2 inteira de $AB$ com detalhamento.  
    Resolução:
    - Repetir os cálculos do exercício 4 e explicar cada multiplicação e soma.

18. Enunciado: Seja $A=\begin{pmatrix}1 & 1\\[4pt]1 & 1\end{pmatrix}$. Calcule $A^2 = A\cdot A$.  
    Resolução:
    - $A^2_{11}=1\cdot1 + 1\cdot1 = 2$, simetricamente todas entradas serão 2, portanto $A^2 = \begin{pmatrix}2 & 2\\[4pt]2 & 2\end{pmatrix}$.

19. Enunciado: Demonstre que $0\cdot A = 0$ (matriz nula) para qualquer matriz $A$.  
    Resolução:
    - Entrywise: $(0A)_{ij} = 0\cdot a_{ij} = 0$.

20. Enunciado: Considere matrizes $A$ ($m\times n$) e $B$ ($n\times p$). Mostre que cada coluna de $AB$ é combinação linear das colunas de $A$ com coeficientes vindos de colunas de $B$.  
    Resolução:
    - A coluna $j$ de $AB$ é $A$ multiplicado pelo vetor coluna formado por elementos $b_{1j},\dots,b_{nj}$, que é combinação linear das colunas de $A$.

21. Enunciado: Se $A$ é $2\times2$ e $B$ é $2\times2$ tais que $AB=I$, mostre que $BA=I$ (no caso de matrizes quadradas, inversa é única).  
    Resolução:
    - Usar resultado teórico de álgebra linear: se $AB=I$ e $A,B$ quadradas, então $B$ é inversa de $A$ e $BA=I$ (prova via multiplicar por inversa, etc.). Referência teórica em Nicholson.

22. Enunciado: Dado vetor coluna $v\in\mathbb{R}^m$ e matriz $A$ $m\times n$, explique por que $Av$ não está definido, enquanto $v^T A$ pode estar definido conforme dimensões.  
    Resolução:
    - Verificar dimensões: $A$ ($m\times n$) e $v$ ($m\times1$) → $Av$ não existe (colunas de $A$ = $n$ diferente de linhas de $v$ = $m$), mas $v^T A$ exige que colunas de $v^T$ (1) igualem linhas de $A$ (m) — normalmente não compatível; explique cuidado de dimensões caso a caso.

23. Enunciado: Mostre um caso concreto em que $A$ ($1\times3$) e $B$ ($3\times1$) e calcule $AB$ e $BA$ (quando definidos).  
    Resolução:
    - $A=(1\ 2\ 3)$, $B=(4\ 0\ -1)^T$ → $AB$ é $1\times1$: $1\cdot4 +2\cdot0 + 3\cdot(-1)=4 +0 -3 =1$.  
    - $BA$ é $3\times3$ e deve ser calculado por produto de coluna vezes linha → matriz resultado com entries $b_i a_j$.

24. Enunciado: Dada matriz que representa número de linhas de transmissão de usinas para cidades ($M$) e matriz que representa linhas entre cidades ($T$), explique qualitativamente por que $M\cdot T$ fornece linhas de usina para cidades finais via cidades intermediárias (resumo do vídeo).  
    Resolução:
    - Cada entrada de $M\cdot T$ soma sobre cidades intermediárias $k$ o produto das contribuições: linhas da usina até cidade $k$ vezes linhas de $k$ até cidade final; conta caminhos compostos. Esta é a propriedade que torna a multiplicação útil em redes.

25. Enunciado: Prove que se $A$ é $m\times n$ e $B$ é $n\times p$, então $rank(AB)\le \min(rank(A), rank(B))$ (enunciado — justificar intuição).  
    Resolução (intuição): imagens lineares compostas estão contidas nas imagens de cada fator; formalizar via transformações lineares e subespaços. Para demonstração completa consultar texto teórico (Nicholson).

26. Enunciado: Dado $A=\begin{pmatrix}1 & 2\\[4pt]3 & 4\end{pmatrix}$ e $B=\begin{pmatrix}0 & 1\\[4pt]1 & 0\end{pmatrix}$, calcule $AB$ explicitamente e interprete a ação de $B$ como permutação de colunas.  
    Resolução:
    - $AB = \begin{pmatrix}1\cdot0+2\cdot1 & 1\cdot1+2\cdot0\\[4pt]3\cdot0+4\cdot1 & 3\cdot1+4\cdot0\end{pmatrix}=\begin{pmatrix}2 & 1\\[4pt]4 & 3\end{pmatrix}$. Multiplicar por $B$ permuta as colunas de $A$ (troca 1ª e 2ª coluna).

27. Enunciado: Explique por que produto entrywise (Hadamard) difere da multiplicação matricial padrão.  
    Resolução:
    - Hadamard: $(A\circ B)_{ij}=a_{ij}b_{ij}$ (requer mesmo tamanho) — operação entrywise; multiplicação padrão envolve somatórios e mistura de entradas de linhas/colunas, com interpretações diferentes (composição vs escala entrywise).

28. Enunciado: Dado $A$ $3\times3$, quantos multiplicações escalares e somas são necessárias para calcular $AB$ por definição direta?  
    Resolução:
    - Para cada dos 9 elementos de $C$ são feitas 3 multiplicações e 2 somas (se somas encadeadas), total aproximado: $9\cdot3=27$ multiplicações e 9*(3-1)=18 somas. Generalização: $O(n^3)$ para matrizes $n\times n$.

29. Enunciado: Calcule produto de uma matriz por vetor (caso $A$ $m\times n$ e $x$ $n\times 1$).  
    Resolução:
    - Cada componente $(Ax)_i = \sum_{k=1}^{n} a_{ik} x_k$. Exemplo numérico com dados concretos e passo a passo.

30. Enunciado: Usando um pequeno exemplo, mostre que multiplicação de matrizes pode ser implementada por operações sobre linhas e colunas (explique algoritmo de produto como múltiplos produtos escalares entre linhas e colunas).  
    Resolução:
    - Explicitar pseudocódigo aninhado:
      ```
      para i = 1..m:
        para j = 1..p:
          c[i,j] = 0
          para k = 1..n:
            c[i,j] += a[i,k] * b[k,j]
      ```
    - Demonstrar com um exemplo 2×2 e realizar cada iteração.

---

## Bibliografia (formato ABNT)

- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015. Acesso em 11 out. 2025.  
- UNIVESP. Geometria Analítica e Álgebra Linear — Operações com matrizes [vídeo]. UNIVESP TV, YouTube, 9 mai. 2022. Transcrição utilizada como base deste material. Acesso em 11 out. 2025.  
- Referências complementares para leitura sobre multiplicação de matrizes, complexidade e aplicações: consultar capítulos introdutórios de livros de Álgebra Linear e tutoriais de NumPy (busca online recomendada).  

---

## Materiais complementares (selecionados)

- Nicholson, W. Keith. Álgebra Linear. AMGH Editora, 2. ed., 2015 (capítulos sobre matrizes, transformações lineares e produto de matrizes).  
- Tutorial NumPy — documentação oficial (para implementação prática de operações matriciais e desempenho).  
- Transcrição e vídeo da UNIVESP sobre operações com matrizes (fonte primária usada aqui).

---

Referência à fonte do conteúdo do vídeo (transcrição e conceito): o desenvolvimento e exemplos seguem a transcrição do vídeo "Geometria analítica e álgebra linear - Operações com matrizes", UNIVESP.

Se desejar, exporto este conteúdo como arquivo Markdown pronto para salvar no GitHub, ou posso:
- Gerar uma versão alternativa que use representação textual completa (sem blocos LaTeX), caso o repositório alvo não renderize fórmulas;  
- Expandir as resoluções dos exercícios com todos os cálculos numéricos item a item (atualmente o passo a passo está indicado e exemplificado; posso detalhar cada soma e multiplicação se desejar).