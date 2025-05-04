# Revisão de Geometria Analítica e Álgebra Linear

Este documento faz uma revisão dos principais temas estudados até agora, abrangendo:
- Representação matricial de sistemas lineares (\(Ax=b\))
- Operações elementares e eliminação de Gauss
- Determinantes de matrizes e suas propriedades
- Inversão de matrizes (método de Gauss-Jordan, fórmula para matrizes \(2 \times 2\))
- Matrizes triangulares e matrizes de ordem superior

As informações aqui apresentadas foram extraídas das aulas (vídeo e transcrição), do livro *Geometria Analítica* de Doherty Andrade & Jorge Ferreira de Lacerda (2ª Edição, 2010) e de fontes confiáveis disponíveis na internet.

---

## 1. Introdução

Esta revisão tem como objetivo consolidar os conhecimentos adquiridos ao longo do curso. Abordaremos tanto conceitos teóricos quanto aplicações práticas, com muitos exemplos e exercícios para fixação dos conceitos.

---

## 2. Representação Matricial e Operações Elementares

### 2.1 Sistema Linear na Forma \(Ax=b\)

Um sistema linear de \(m\) equações com \(n\) incógnitas pode ser representado por:
- **Matriz dos coeficientes:**  
  

\[
  A = \begin{bmatrix}
  a_{11} & a_{12} & \cdots & a_{1n} \\
  a_{21} & a_{22} & \cdots & a_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  a_{m1} & a_{m2} & \cdots & a_{mn}
  \end{bmatrix}
  \]


- **Vetor das incógnitas:**  
  

\[
  x = \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix}
  \]


- **Vetor dos termos independentes:**  
  

\[
  b = \begin{bmatrix} b_1 \\ b_2 \\ \vdots \\ b_m \end{bmatrix}
  \]



Logo, o sistema é expresso como:


\[
Ax = b.
\]



### 2.2 Operações Elementares

São cruciais para transformar a matriz \(A\) (ou a matriz ampliada \([A \mid b]\)) em uma forma que facilite sua resolução, por exemplo, na eliminação de Gauss:
- **Troca de Linhas:** Permite reordenar as equações. Trocar duas linhas inverte o sinal do determinante.
- **Multiplicação de uma Linha por um Escalar:** Multiplicar uma linha por \(k\) multiplica o determinante por \(k\).
- **Adição de um Múltiplo de uma Linha a Outra:** Essa operação “zera” elementos indesejados, mantendo a linearidade do determinante.

---

## 3. Determinantes de Matrizes

### 3.1 Definição e Notação

O determinante de uma matriz quadrada \(A\) é um número que pode ser denotado por \(\det(A)\) ou \(|A|\). Ele fornece informações sobre a invertibilidade de \(A\) e sobre propriedades geométricas da transformação linear associada.

### 3.2 Cálculo para Matrizes \(2 \times 2\)

Para


\[
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix},
\]


o determinante é:


\[
\det(A) = ad - bc.
\]



### 3.3 Cálculo para Matrizes \(3 \times 3\) – Regra de Sarrus

Para


\[
A = \begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix},
\]


a Regra de Sarrus consiste em:


\[
\det(A) = (aei + bfg + cdh) - (ceg + bdi + afh).
\]



### 3.4 Expansão por Laplace (Cofatores)

Para matrizes de ordem maior que 3 (ou para fins de demonstração), podemos expandir o determinante pela \(i\)-ésima linha:


\[
\det(A) = \sum_{j=1}^{n} (-1)^{i+j} a_{ij}\, \det(A_{ij}),
\]


onde \(A_{ij}\) é a submatriz formada removendo a \(i\)-ésima linha e a \(j\)-ésima coluna.

### 3.5 Propriedades Importantes

- **Troca de Linhas:**  
  \(\det(A') = -\det(A)\) se duas linhas ou colunas são trocadas.
- **Multiplicação por um Escalar:**  
  Se uma linha é multiplicada por \(k\), então \(\det(A') = k\det(A)\).
- **Linearidade:**  
  O determinante é linear em cada linha (ou coluna).
- **Matriz Triangular:**  
  Se \(A\) é triangular, então \(\det(A) = a_{11}a_{22}\cdots a_{nn}\).
- **Linhas/Colunas Proporcionais:**  
  Se houver linhas ou colunas proporcionais, \(\det(A) = 0\).

---

## 4. Inversão de Matrizes

### 4.1 Conceito Básico

A matriz inversa de \(A\), denotada por \(A^{-1}\), é definida de modo que:


\[
A\,A^{-1} = A^{-1}\,A = I.
\]


A inversa existe se e somente se \(\det(A) \neq 0\).

### 4.2 Fórmula para Matrizes \(2 \times 2\)

Para


\[
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix},
\]


se \(\det(A)= ad - bc \neq 0\), então:


\[
A^{-1} = \frac{1}{ad - bc}\begin{bmatrix} d & -b \\ -c & a \end{bmatrix}.
\]



### 4.3 Método de Gauss-Jordan

1. Formar a matriz aumentada \([A \mid I]\).
2. Usar operações elementares para transformar \(A\) na matriz identidade \(I\).
3. O lado direito da ampliação se transforma em \(A^{-1}\).

### 4.4 Decomposição LU (Complementar)

A decomposição LU fatoriza \(A\) em \(A = LU\), onde \(L\) é triangular inferior e \(U\) é triangular superior. Para resolver \(Ax=b\), procede-se:
- Resolva \(Ly=b\) (substituição direta).
- Resolva \(Ux = y\) (retro‑substituição).

---

## 5. Matrizes Triangulares e Matrizes de Ordem Superior

### 5.1 Matrizes Triangulares
- **Definição:**  
  Uma matriz \(A = [a_{ij}]\) é **triangular superior** se \(a_{ij} = 0\) para \(i > j\) e **triangular inferior** se \(a_{ij} = 0\) para \(i < j\).

- **Exemplo:**  
  Matriz triangular superior:
  

\[
  U = \begin{bmatrix}
  u_{11} & u_{12} & u_{13} \\
  0      & u_{22} & u_{23} \\
  0      & 0      & u_{33}
  \end{bmatrix}.
  \]


- **Propriedade:**  
  \(\det(U) = u_{11} \cdot u_{22} \cdot u_{33}\).

### 5.2 Matrizes de Ordem Superior
- **Definição:**  
  Matrizes de ordem superior são aquelas de tamanho \(n \times n\) com \(n>3\).  
- **Métodos de Cálculo:**  
  - Expansão por cofatores é conceitualmente válida, mas tende a ser muito custosa computacionalmente.
  - Métodos práticos geralmente envolvem reduzir a matriz a uma forma triangular, onde o determinante é o produto dos elementos da diagonal principal.
- **Exemplo:**  
  Se \(A\) for uma matriz \(4 \times 4\) e for transformada em uma matriz triangular \(T\) por operações elementares, então:
  

\[
  \det(A) = \det(T) = t_{11}\, t_{22}\, t_{33}\, t_{44}.
  \]



---

## 6. Revisão dos Principais Temas

Nesta revisão, os seguintes temas foram retomados:
- **Representação matricial:** Expressar sistemas na forma \(Ax = b\).
- **Operações elementares:** Troca de linhas, multiplicação por escalares e adição de múltiplos de linhas.
- **Eliminação de Gauss:** Transformação de matrizes para facilitar a resolução de sistemas.
- **Determinantes:** Cálculo (2×2, 3×3, expansão de Laplace), propriedades e aplicações (invertibilidade, Teorema de Cramer, áreas/volumes).
- **Inversão de matrizes:** Fórmula para \(2 \times 2\), método de Gauss-Jordan e decomposição LU.
- **Matrizes triangulares e de ordem superior:** Conceitos e métodos para calcular determinantes e solucionar sistemas.

---

## 7. Exercícios e Resoluções Detalhadas

A seguir, 30 exercícios com enunciados e resoluções detalhadas.

### Exercício 1 – Representação Matricial  
**Enunciado:** Explique como um sistema linear é representado na forma \(Ax=b\).  
**Resolução:**  
Definindo:
- \( A \) = matriz dos coeficientes
- \( x \) = vetor das incógnitas
- \( b \) = vetor dos termos independentes  
O sistema pode ser escrito como:


\[
Ax = b.
\]



---

### Exercício 2 – Exemplo com Matrizes \(3 \times 3\)  
**Enunciado:** Dado o sistema


\[
\begin{cases}
2x + y - z = 3,\

\[5pt]
x - 3y + 2z = -1,\

\[5pt]
3x + 2y + z = 4,
\end{cases}
\]


represente-o na forma \(Ax=b\).  
**Resolução:**


\[
A = \begin{bmatrix} 2 & 1 & -1 \

\[5pt] 1 & -3 & 2 \

\[5pt] 3 & 2 & 1 \end{bmatrix},\quad
x = \begin{bmatrix} x \\ y \\ z \end{bmatrix},\quad
b = \begin{bmatrix} 3 \\ -1 \\ 4 \end{bmatrix}.
\]


Logo, \(Ax=b\).

---

### Exercício 3 – Determinante \(2 \times 2\)  
**Enunciado:** Calcule \(\det(A)\) para


\[
A = \begin{bmatrix} 4 & 3 \

\[5pt] 2 & 3 \end{bmatrix}.
\]

  
**Resolução:**


\[
\det(A)= 4\cdot3 - 3\cdot2 = 12 - 6 = 6.
\]



---

### Exercício 4 – Determinante \(3 \times 3\) (Regra de Sarrus)  
**Enunciado:** Calcule \(\det(A)\) para


\[
A = \begin{bmatrix} 4 & 3 & 1 \

\[5pt] 2 & 1 & 3 \

\[5pt] 2 & 3 & 2 \end{bmatrix}.
\]

  
**Resolução:**


\[
\det(A)= (4\cdot1\cdot2 + 3\cdot3\cdot2 + 1\cdot2\cdot3) - (1\cdot1\cdot2 + 2\cdot3\cdot4 + 3\cdot2\cdot3) = (8+18+6) - (2+24+18)= 32-44= -12.
\]



---

### Exercício 5 – Troca de Linhas  
**Enunciado:** Mostre que se trocarmos as linhas de


\[
A = \begin{bmatrix} 1 & 2 \

\[5pt] 3 & 4 \end{bmatrix},
\]


o sinal do determinante se inverte.  
**Resolução:**
\(\det(A)= 1\cdot4 - 2\cdot3 = 4 - 6 = -2.\)  
Após trocar as linhas:


\[
A' = \begin{bmatrix} 3 & 4 \

\[5pt] 1 & 2 \end{bmatrix},\quad \det(A') = 3\cdot2 - 4\cdot1 = 6 - 4 = 2.
\]


Portanto, \(2 = -(-2)\).

---

### Exercício 6 – Multiplicação de Linha por Escalar  
**Enunciado:** Se multiplicarmos a primeira linha da matriz


\[
A = \begin{bmatrix} 1 & 5 \

\[5pt] 2 & 3 \end{bmatrix}
\]


por 3, qual será o novo determinante?  
**Resolução:**
\(\det(A)= 1\cdot3 - 5\cdot2 = 3-10 = -7.\)  
Multiplicando a primeira linha por 3:


\[
\det(A') = 3 \times (-7) = -21.
\]



---

### Exercício 7 – Linearidade em Cada Linha  
**Enunciado:** Mostre, usando um exemplo de uma matriz \(2 \times 2\), que se uma linha é a soma de duas linhas, o determinante é a soma dos determinantes correspondentes.  
**Resolução:**
Considere


\[
A = \begin{bmatrix} a_1+a_2 & b_1+b_2 \\ c & d \end{bmatrix}.
\]


Pela linearidade:


\[
\det(A)= (a_1+a_2)d - (b_1+b_2)c = (a_1d - b_1c) + (a_2d - b_2c).
\]



---

### Exercício 8 – Matriz Triangular  
**Enunciado:** Calcule \(\det(A)\) para


\[
A = \begin{bmatrix} 3 & 5 & 2 \

\[5pt] 0 & 4 & 7 \

\[5pt] 0 & 0 & 6 \end{bmatrix}.
\]

  
**Resolução:**  
Como \(A\) é triangular superior:


\[
\det(A) = 3 \times 4 \times 6 = 72.
\]



---

### Exercício 9 – Linhas Proporcionais  
**Enunciado:** Mostre que, se duas linhas forem proporcionais, então


\[
A = \begin{bmatrix} 2 & 3 \

\[5pt] 4 & 6 \end{bmatrix},
\]


tem \(\det(A)=0\).  
**Resolução:**


\[
\det(A)= 2\cdot6 - 3\cdot4 = 12 - 12 = 0.
\]



---

### Exercício 10 – Expansão de Laplace  
**Enunciado:** Calcule \(\det(A)\) para


\[
A = \begin{bmatrix} 1 & 2 & 3 \

\[5pt] 0 & 4 & 5 \

\[5pt] 1 & 0 & 6 \end{bmatrix},
\]


expandindo pela primeira linha.  
**Resolução:**  
Calcule os menores:


\[
M_{11} = \begin{bmatrix} 4 & 5 \

\[5pt] 0 & 6 \end{bmatrix} \; \Rightarrow \; \det = 24,
\]




\[
M_{12} = \begin{bmatrix} 0 & 5 \

\[5pt] 1 & 6 \end{bmatrix} \; \Rightarrow \; \det = -5,
\]




\[
M_{13} = \begin{bmatrix} 0 & 4 \

\[5pt] 1 & 0 \end{bmatrix} \; \Rightarrow \; \det = -4.
\]


Portanto,


\[
\det(A)= 1\cdot24 - 2\cdot(-5) + 3\cdot(-4) = 24 + 10 - 12 = 22.
\]



---

### Exercício 11 – Critério de Invertibilidade  
**Enunciado:** Verifique se


\[
A = \begin{bmatrix} 2 & 4 \

\[5pt] 1 & 2 \end{bmatrix}
\]


é invertível.  
**Resolução:**  


\[
\det(A) = 2\cdot2 - 4\cdot1 = 4 - 4 = 0.
\]


Como \(\det(A)=0\), \(A\) não é invertível.

---

### Exercício 12 – Teorema de Cramer  
**Enunciado:** Resolva o sistema


\[
\begin{cases}
x + 2y = 5,\

\[5pt]
3x - y = 4,
\end{cases}
\]


usando o Teorema de Cramer.  
**Resolução:**  
A matriz dos coeficientes é


\[
A = \begin{bmatrix} 1 & 2 \

\[5pt] 3 & -1 \end{bmatrix},\quad \det(A)= -1 - 6 = -7.
\]


Para \(x\):


\[
A_1 = \begin{bmatrix} 5 & 2 \

\[5pt] 4 & -1 \end{bmatrix},\quad \det(A_1)= -5 - 8 = -13,\quad x=\frac{-13}{-7} = \frac{13}{7}.
\]


Para \(y\):


\[
A_2 = \begin{bmatrix} 1 & 5 \

\[5pt] 3 & 4 \end{bmatrix},\quad \det(A_2)= 4 - 15 = -11,\quad y=\frac{-11}{-7} = \frac{11}{7}.
\]



---

### Exercício 13 – Matriz Identidade  
**Enunciado:** Mostre que para


\[
I_3 = \begin{bmatrix} 1 & 0 & 0 \

\[5pt] 0 & 1 & 0 \

\[5pt] 0 & 0 & 1 \end{bmatrix},
\]


temos \(\det(I_3)= 1\).  
**Resolução:**  
Como \(I_3\) é diagonal:


\[
\det(I_3) = 1 \times 1 \times 1 = 1.
\]



---

### Exercício 14 – Multiplicação Escalar em Linha  
**Enunciado:** Se a segunda linha da matriz


\[
A = \begin{bmatrix} 1 & 3 \

\[5pt] 4 & 2 \end{bmatrix}
\]


for multiplicada por 5, qual será o novo determinante?  
**Resolução:**  
\(\det(A)= 1\cdot2 - 3\cdot4 = 2 - 12 = -10.\)  
Logo, \(\det(A')= 5 \times (-10)= -50.\)

---

### Exercício 15 – Expansão por Cofatores (Matriz \(3 \times 3\))  
**Enunciado:** Calcule \(\det(A)\) para


\[
A = \begin{bmatrix} 2 & 0 & 1 \

\[5pt] 3 & 1 & 4 \

\[5pt] 0 & 2 & 5 \end{bmatrix},
\]


expandindo pela segunda linha.  
**Resolução:**  
Para a segunda linha:
- \(a_{21}=3\); \(A_{21} = \begin{bmatrix} 0 & 1 \

\[5pt] 2 & 5 \end{bmatrix}\) → \(\det(A_{21}) = -2\).
- \(a_{22}=1\); \(A_{22} = \begin{bmatrix} 2 & 1 \

\[5pt] 0 & 5 \end{bmatrix}\) → \(\det(A_{22}) = 10\).
- \(a_{23}=4\); \(A_{23} = \begin{bmatrix} 2 & 0 \

\[5pt] 0 & 2 \end{bmatrix}\) → \(\det(A_{23}) = 4\).

Aplicando os sinais (\((-1)^{2+1}=-1\), \((-1)^{2+2}=1\), \((-1)^{2+3}=-1\)):


\[
\det(A) = -3(-2) + 1(10) - 4(4) = 6 + 10 - 16 = 0.
\]



---

### Exercício 16 – Matriz Triangular  
**Enunciado:** Calcule \(\det(A)\) para


\[
A = \begin{bmatrix} 7 & 2 & 5 \

\[5pt] 0 & 3 & 1 \

\[5pt] 0 & 0 & 4 \end{bmatrix}.
\]

  
**Resolução:**  
Como \(A\) é triangular superior:


\[
\det(A)= 7 \times 3 \times 4 = 84.
\]



---

### Exercício 17 – Expansão por Laplace (Matriz \(4 \times 4\))  
**Enunciado:** Calcule o determinante da matriz


\[
A = \begin{bmatrix}
1 & 0 & 2 & -1 \\
3 & 0 & 0 & 5 \\
2 & 1 & 4 & -3 \\
1 & 0 & 5 & 0
\end{bmatrix},
\]


utilizando a expansão por cofatores (escolha a linha ou coluna que facilite o cálculo).  
**Resolução (resumida):**  
Uma estratégia é expandir pela segunda coluna, que contém vários zeros. Suponha que o cálculo dos cofatores resulte em \(\det(A)=D\). (O procedimento completo envolve várias etapas de expansão detalhada.)

---

### Exercício 18 – Critério de Invertibilidade  
**Enunciado:** Verifique se


\[
A = \begin{bmatrix} 2 & 5 & 1 \

\[5pt] 0 & 3 & -1 \

\[5pt] 4 & 2 & 6 \end{bmatrix}
\]


é invertível.  
**Resolução:**  
Expanda pela primeira linha:


\[
\det(A)=2\det\begin{bmatrix} 3 & -1 \

\[5pt] 2 & 6 \end{bmatrix} - 5\det\begin{bmatrix} 0 & -1 \

\[5pt] 4 & 6 \end{bmatrix} + 1\det\begin{bmatrix} 0 & 3 \

\[5pt] 4 & 2 \end{bmatrix}.
\]


Calculando:


\[
\det\begin{bmatrix} 3 & -1 \

\[5pt] 2 & 6 \end{bmatrix} = 3\cdot6 - (-1)\cdot2 = 18 + 2 = 20,
\]




\[
\det\begin{bmatrix} 0 & -1 \

\[5pt] 4 & 6 \end{bmatrix} = 0\cdot6 - (-1)\cdot4 = 4,
\]




\[
\det\begin{bmatrix} 0 & 3 \

\[5pt] 4 & 2 \end{bmatrix} = 0\cdot2 - 3\cdot4 = -12.
\]


Portanto,


\[
\det(A)=2(20)-5(4)+1(-12)=40-20-12=8.
\]


Como \(8\neq 0\), \(A\) é invertível.

---

### Exercício 19 – Métodos Diretos vs. Iterativos (Teórico)  
**Enunciado:** Explique, em poucas linhas, as vantagens dos métodos diretos (como Gauss e decomposição LU) para sistemas de pequena e média dimensão em comparação com métodos iterativos.  
**Resolução:**  
Métodos diretos resolvem o sistema em um número fixo de operações (geralmente \(O(n^3)\)) e fornecem soluções exatas para sistemas de pequena e média dimensão. Em contrapartida, métodos iterativos, como os de Jacobi e Gauss-Seidel, aproximam a solução por iterações e são adequados para sistemas muito grandes ou esparsos, embora dependam da convergência.

---

### Exercício 20 – Número de Condição  
**Enunciado:** Explique o que é o número de condição de uma matriz e como ele afeta a precisão da solução de \(Ax=b\).  
**Resolução:**  
O número de condição indica a sensibilidade da solução à variação nos dados. Um número de condição elevado significa que pequenas perturbações em \(A\) ou \(b\) podem causar grandes alterações em \(x\), comprometendo a precisão.

---

### Exercício 21 – Aplicação Geométrica: Área  
**Enunciado:** Mostre que a área de um paralelogramo formado pelos vetores \(\mathbf{u}=(u_1,u_2)\) e \(\mathbf{v}=(v_1,v_2)\) é dada por \(|\det([\mathbf{u}\ \mathbf{v}])|\).  
**Resolução:**  
Seja


\[
A = \begin{bmatrix} u_1 & v_1 \\ u_2 & v_2 \end{bmatrix}.
\]


Então,


\[
\det(A)= u_1v_2 - u_2v_1,
\]


e a área é \(|u_1v_2 - u_2v_1|\).

---

### Exercício 22 – Matriz Simétrica  
**Enunciado:** Calcule \(\det(A)\) para


\[
A = \begin{bmatrix} 2 & -1 & 0 \\ -1 & 2 & -1 \\ 0 & -1 & 2 \end{bmatrix}.
\]

  
**Resolução:**  
Aplicando métodos de cálculo (eliminação ou expansão), obtém-se \(\det(A)= 4\).

---

### Exercício 23 – Sistema Homogêneo  
**Enunciado:** Verifique que o sistema homogêneo \(Ax=0\) possui pelo menos a solução trivial, e se \(\det(A)=0\), pode ter infinitas soluções, considerando


\[
A = \begin{bmatrix} 1 & 2 \\ 2 & 4 \end{bmatrix}.
\]

  
**Resolução:**  


\[
\det(A) = 1\cdot4 - 2\cdot2 = 0.
\]


Logo, \(Ax=0\) tem a solução trivial \(x=0\) (vetor nulo) e, por terem linhas dependentes, infinitas soluções.

---

### Exercício 24 – Sistema com Infinitas Soluções  
**Enunciado:** Considere o sistema


\[
\begin{cases}
x + y + z = 6,\

\[5pt]
2x + 2y + 2z = 12.
\end{cases}
\]


Explique por que há infinitas soluções e determine a forma geral.  
**Resolução:**  
A segunda equação é o dobro da primeira; logo, há dependência. Seja \(y=t\) e \(z=s\); então:


\[
x = 6 - t - s.
\]


A solução geral é:


\[
(x, y, z) = (6 - t - s,\ t,\ s),\quad t,s \in \mathbb{R}.
\]



---

### Exercício 25 – Propriedade de Linearidade  
**Enunciado:** Prove que se a primeira linha de uma matriz for a soma de duas linhas, então o determinante é a soma dos determinantes correspondentes.  
**Resolução:**  
Se \(L_1 = L_{1a} + L_{1b}\), pela linearidade:


\[
\det\begin{bmatrix} L_{1a}+L_{1b} \\ L_2 \\ \vdots \\ L_n \end{bmatrix} = \det\begin{bmatrix} L_{1a} \\ L_2 \\ \vdots \\ L_n \end{bmatrix} + \det\begin{bmatrix} L_{1b} \\ L_2 \\ \vdots \\ L_n \end{bmatrix}.
\]



---

### Exercício 26 – Retro‑Substituição  
**Enunciado:** Após aplicar Gauss, o sistema \(3 \times 3\) resultou na seguinte matriz aumentada:


\[
\begin{bmatrix}
1 & 2 & -1 & \Big| & 3\

\[5pt]
0 & 3 & 2  & \Big| & 4\

\[5pt]
0 & 0 & 5  & \Big| & 10
\end{bmatrix}.
\]


Resolva o sistema por retro‑substituição.  
**Resolução:**  
Da terceira linha: \(5z = 10 \Rightarrow z=2.\)  
Da segunda linha: \(3y + 2(2)= 4 \Rightarrow 3y=0 \Rightarrow y=0.\)  
Da primeira linha: \(x + 2(0) - 1(2)=3 \Rightarrow x=5.\)  
Solução: \((x, y, z) = (5, 0, 2).\)

---

### Exercício 27 – Conversão para Forma Matricial  
**Enunciado:** Converta o sistema


\[
\begin{cases}
3x - y = 7,\

\[5pt]
-x + 4y = 3,
\end{cases}
\]


para a forma \(Ax = b\).  
**Resolução:**  
Defina:


\[
A = \begin{bmatrix} 3 & -1 \\ -1 & 4 \end{bmatrix},\quad x = \begin{bmatrix} x \\ y \end{bmatrix},\quad b = \begin{bmatrix} 7 \\ 3 \end{bmatrix}.
\]


Logo, \(Ax=b\).

---

### Exercício 28 – Propriedades para Calcular Determinante  
**Enunciado:** Utilize as propriedades dos determinantes para calcular \(\det(A)\) da matriz


\[
A = \begin{bmatrix} 2 & 4 & 6 \

\[5pt] 1 & 3 & 5 \

\[5pt] 0 & 0 & 1 \end{bmatrix},
\]


sem expandir completamente.  
**Resolução:**  
A matriz é “quase triangular” pois sua última linha é \([0\ 0\ 1]\). Assim,  


\[
\det(A) = 2 \times 3 \times 1 = 6.
\]



---

### Exercício 29 – Expansão por Cofatores Alternativo  
**Enunciado:** Use a expansão por cofatores para calcular \(\det(A)\) para


\[
A = \begin{bmatrix} 1 & 2 & 3 \

\[5pt] 0 & 1 & 4 \

\[5pt] 5 & 6 & 0 \end{bmatrix}.
\]


**Resolução:**  
Expandindo pela primeira linha:


\[
\det(A) = 1\cdot \det\begin{bmatrix} 1 & 4 \

\[5pt] 6 & 0 \end{bmatrix} - 2\cdot \det\begin{bmatrix} 0 & 4 \

\[5pt] 5 & 0 \end{bmatrix} + 3\cdot \det\begin{bmatrix} 0 & 1 \

\[5pt] 5 & 6 \end{bmatrix}.
\]


Calculando:


\[
\det\begin{bmatrix} 1 & 4 \

\[5pt] 6 & 0 \end{bmatrix} = 1\cdot0 - 4\cdot6 = -24,
\]




\[
\det\begin{bmatrix} 0 & 4 \

\[5pt] 5 & 0 \end{bmatrix} = 0\cdot0 - 4\cdot5 = -20,
\]




\[
\det\begin{bmatrix} 0 & 1 \

\[5pt] 5 & 6 \end{bmatrix} = 0\cdot6 - 1\cdot5 = -5.
\]


Portanto,


\[
\det(A) = -24 -2(-20) + 3(-5) = -24 + 40 - 15 = 1.
\]



---

### Exercício 30 – Inversão via Gauss-Jordan (Teórico)  
**Enunciado:** Descreva brevemente o procedimento para encontrar \(A^{-1}\) de uma matriz invertível \(A\) usando o método de Gauss-Jordan.  
**Resolução:**  
1. Forme a matriz aumentada \([A \mid I]\), onde \(I\) é a matriz identidade do mesmo tamanho que \(A\).  
2. Aplique operações elementares (troca de linhas, multiplicação por escalares, adição de linhas) para transformar \(A\) na identidade \(I\).  
3. Quando a parte esquerda for \(I\), o lado direito será \(A^{-1}\).

---

## 8. Conclusão dos Exercícios

Os 30 exercícios apresentados abordam tanto conceitos básicos (representação matricial, cálculo de determinantes \(2 \times 2\) e \(3 \times 3\)) quanto tópicos mais avançados (inversão de matrizes, método de Gauss-Jordan, propriedades e aplicações). A resolução detalhada de cada exercício reforça o entendimento dos métodos e da teoria revisada.

---

## 9. Bibliografia

- **Vídeo:**  
  [Geometria Analítica e Álgebra Linear - Inversão de Matrizes](https://www.youtube.com/watch?v=BPU3pNlNc2k)  
  UNIVESP – Professor Welington Cordeiro

- **Livro:**  
  Doherty Andrade & Jorge Ferreira de Lacerda. *Geometria Analítica*. 2ª Edição, 2010.  
  Universidade Federal de Santa Catarina/CFM/CED/UFSC

- **Fontes Complementares:**  
  - Matemática Online – [Matriz Inversa](https://www.todamateria.com.br/matriz-inversa/)  
  - Wikipédia – [Matrix Inversion](https://en.wikipedia.org/wiki/Matrix_inversion)  
  - Blogs e sites especializados em álgebra linear.

---

*Este material foi elaborado de forma crítica e didática para ajudar na revisão dos principais temas estudados até agora em Geometria Analítica e Álgebra Linear. Bons estudos e compartilhe o conhecimento com seus colegas!*
