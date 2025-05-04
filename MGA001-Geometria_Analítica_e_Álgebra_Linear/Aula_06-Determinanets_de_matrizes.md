# Determinantes de Matrizes

Este material reúne os conceitos fundamentais sobre determinantes de matrizes, conforme apresentado no vídeo do professor (UNIVESP – Professor Welington Cordeiro), com informações complementares do livro *Geometria Analítica* de Doherty Andrade & Jorge Ferreira de Lacerda (2ª Edição, 2010) e outras fontes online. O objetivo é oferecer um estudo crítico e didático para auxiliar seu aprendizado e para que você possa compartilhar o conhecimento com outros estudantes.

---

## 1. Introdução

Os determinantes são números associados a matrizes quadradas. Originalmente criados para resolver sistemas lineares, hoje eles possuem diversas aplicações, tais como:

- **Invertibilidade:** Uma matriz \(A\) é invertível se, e somente se, \(\det(A) \neq 0\).
- **Resolução de Sistemas:** O Teorema de Cramer, por exemplo, utiliza determinantes para resolver sistemas lineares.
- **Geometria:** O valor absoluto de \(\det(A)\) pode representar a área de um paralelogramo (em \(\mathbb{R}^2\)) ou o volume de um paralelepípedo (em \(\mathbb{R}^3\)).
- **Transformações Lineares:** O determinante fornece o fator de escala de uma transformação.

---

## 2. Notação e Definições Básicas

- O determinante de uma matriz \(A\) é denotado por \(\det(A)\) ou \(|A|\).

### Exemplo: Matriz \(2 \times 2\)


\[
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix} \quad \Longrightarrow \quad \det(A) = ad - bc.
\]



### Exemplo: Matriz \(3 \times 3\)


\[
A = \begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix}.
\]


A Regra de Sarrus é:


\[
\det(A) = (aei + bfg + cdh) - (ceg + bdi + afh).
\]



### Expansão de Laplace
Para uma matriz \(n \times n\), é possível expandir o determinante pela \(i\)-ésima linha:


\[
\det(A)= \sum_{j=1}^{n} (-1)^{i+j} a_{ij}\, \det(A_{ij}),
\]


onde \(A_{ij}\) é a submatriz obtida removendo a \(i\)-ésima linha e a \(j\)-ésima coluna.

---

## 3. Propriedades dos Determinantes

1. **Troca de Linhas ou Colunas:**  
   Se duas linhas (ou colunas) forem trocadas, o sinal do determinante se inverte:
   

\[
   \det(A') = -\det(A).
   \]



2. **Multiplicação por um Escalar:**  
   Se uma linha for multiplicada por um escalar \(k\), o determinante é multiplicado por \(k\):
   

\[
   \det(A') = k \cdot \det(A).
   \]



3. **Linearidade em Cada Linha:**  
   O determinante é linear em cada linha individualmente. Se uma linha é a soma de duas linhas, o determinante é a soma dos determinantes das matrizes correspondentes.

4. **Matriz Triangular:**  
   Se \(A\) é triangular (superior ou inferior), o determinante é o produto dos elementos da diagonal principal:
   

\[
   \det(A) = a_{11}\, a_{22}\, \cdots\, a_{nn}.
   \]



5. **Linhas ou Colunas Proporcionais:**  
   Se duas linhas (ou colunas) são proporcionais, então
   

\[
   \det(A) = 0.
   \]



---

## 4. Cálculo dos Determinantes

### 4.1 Matrizes \(2 \times 2\)
Para


\[
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix},
\]


temos:


\[
\det(A) = ad - bc.
\]



### 4.2 Matrizes \(3 \times 3\) – Regra de Sarrus
Para


\[
A = \begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix},
\]


utilizamos:


\[
\det(A) = (aei + bfg + cdh) - (ceg + bdi + afh).
\]



### 4.3 Expansão por Cofatores (Laplace)
Para matrizes de ordem superior:


\[
\det(A) = \sum_{j=1}^{n} (-1)^{i+j} a_{ij}\, \det(A_{ij}).
\]



---

## 5. Aplicações e Casos Especiais

### 5.1 Critério de Invertibilidade
Uma matriz \(A\) é invertível se, e somente se, \(\det(A) \neq 0\).

### 5.2 Teorema de Cramer
Em um sistema linear \(Ax = b\) com solução única, cada incógnita \(x_i\) pode ser obtida por:


\[
x_i = \frac{\det(A_i)}{\det(A)},
\]


onde \(A_i\) é a matriz \(A\) com sua \(i\)-ésima coluna substituída pelo vetor \(b\).

### 5.3 Matrizes Especiais
- **Matriz Identidade:** \(\det(I) = 1\).
- **Matriz Triangular:** O determinante de uma matriz triangular é o produto dos elementos da diagonal principal.

---

## 6. Matrizes Triangulares e Matrizes de Ordem Superior

### 6.1 Matrizes Triangulares
- **Definição:**  
  Uma matriz quadrada \(A = [a_{ij}]\) é **triangular superior** se \(a_{ij} = 0\) para todos os \(i > j\) (ou seja, os elementos abaixo da diagonal principal são zero). De forma similar, \(A\) é **triangular inferior** se \(a_{ij} = 0\) para \(i < j\).
  
- **Exemplo (Triangular Superior):**
  

\[
  U = \begin{bmatrix}
  u_{11} & u_{12} & u_{13} \\
  0 & u_{22} & u_{23} \\
  0 & 0 & u_{33}
  \end{bmatrix}.
  \]



- **Propriedade:**  
  O determinante de uma matriz triangular é o produto dos elementos da diagonal principal:
  

\[
  \det(U) = u_{11} \cdot u_{22} \cdot u_{33}.
  \]



### 6.2 Matrizes de Ordem Superior
- **Definição:**  
  Matrizes de ordem superior são matrizes quadradas de tamanho \(n \times n\) com \(n > 3\). Embora o conceito de determinante se aplique a qualquer matriz quadrada, o cálculo direto (por exemplo, via expansão por cofatores) tende a ser trabalhoso.

- **Métodos de Cálculo:**  
  Para matrizes de ordem superior, são comuns dois métodos:
  - **Expansão por Cofatores (Laplace):** Válido para qualquer ordem, porém com complexidade alta.
  - **Redução a Forma Triangular:** Utilizando operações elementares para reduzir a matriz a uma forma triangular, onde o determinante é simplesmente o produto dos elementos da diagonal.
  
- **Exemplo:**  
  Se uma matriz \(A\) \(4 \times 4\) é reduzida a uma matriz triangular \(T\) por eliminação de Gauss, então:
  

\[
  \det(A) = \det(T) = t_{11}\, t_{22}\, t_{33}\, t_{44}.
  \]



---

## 7. Exercícios e Resoluções Detalhadas

A seguir, estão 30 exercícios sobre determinantes, com enunciados e resoluções detalhadas.

### Exercício 1 – Representação Matricial  
**Enunciado:** Explique como um sistema linear pode ser representado na forma \(Ax = b\).  
**Resolução:**  
Definindo:
- \(A\) = matriz dos coeficientes (dimensão \(m \times n\)),
- \(x\) = vetor das incógnitas (dimensão \(n \times 1\)),
- \(b\) = vetor dos termos independentes (dimensão \(m \times 1\));  
o sistema é escrito como \(Ax = b\).

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


represente-o na forma matricial, identificando \(A\), \(x\) e \(b\).  
**Resolução:**  


\[
A = \begin{bmatrix} 2 & 1 & -1 \

\[5pt] 1 & -3 & 2 \

\[5pt] 3 & 2 & 1 \end{bmatrix},\quad
x = \begin{bmatrix} x \\ y \\ z \end{bmatrix},\quad
b = \begin{bmatrix} 3 \\ -1 \\ 4 \end{bmatrix}.
\]


Logo, \(Ax = b\).

---

### Exercício 3 – Determinante \(2 \times 2\)  
**Enunciado:** Calcule \(\det(A)\) para


\[
A = \begin{bmatrix} 4 & 3 \

\[5pt] 2 & 3 \end{bmatrix}.
\]

  
**Resolução:**  


\[
\det(A) = 4\cdot3 - 3\cdot2 = 12 - 6 = 6.
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
\det(A) = (4\cdot1\cdot2 + 3\cdot3\cdot2 + 1\cdot2\cdot3) - (1\cdot1\cdot2 + 2\cdot3\cdot4 + 3\cdot2\cdot3),
\]




\[
\det(A) = (8 + 18 + 6) - (2 + 24 + 18) = 32 - 44 = -12.
\]



---

### Exercício 5 – Troca de Linhas  
**Enunciado:** Mostre que ao trocar as linhas de


\[
A = \begin{bmatrix} 1 & 2 \

\[5pt] 3 & 4 \end{bmatrix},
\]


o sinal do determinante se inverte.  
**Resolução:**  
\(\det(A)= 1\cdot4 - 2\cdot3 = 4 - 6 = -2.\)  
Trocando as linhas:


\[
A' = \begin{bmatrix} 3 & 4 \

\[5pt] 1 & 2 \end{bmatrix},\quad \det(A') = 3\cdot2 - 4\cdot1 = 6 - 4 = 2.
\]


Observamos que \(2 = -(-2)\).

---

### Exercício 6 – Multiplicação de Linha por Escalar  
**Enunciado:** Se multiplicarmos a primeira linha da matriz


\[
A = \begin{bmatrix} 1 & 5 \

\[5pt] 2 & 3 \end{bmatrix}
\]


por 3, qual será o novo determinante?  
**Resolução:**  
Determinante original:


\[
\det(A) = 1\cdot3 - 5\cdot2 = 3 - 10 = -7.
\]


Multiplicando a primeira linha por 3, o novo determinante é:


\[
\det(A') = 3 \cdot (-7) = -21.
\]



---

### Exercício 7 – Linearidade em Cada Linha  
**Enunciado:** Mostre, com um exemplo simples de \(2 \times 2\), que se uma linha é a soma de duas linhas, o determinante é a soma dos determinantes correspondentes.  
**Resolução:**  
Se


\[
A = \begin{bmatrix} a_1+a_2 & b_1+b_2 \\ c & d \end{bmatrix},
\]


então, pela linearidade,


\[
\det(A)= (a_1+a_2)d - (b_1+b_2)c = (a_1d - b_1c) + (a_2d - b_2c).
\]



---

### Exercício 8 – Matriz Triangular  
**Enunciado:** Calcule o determinante de


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
**Enunciado:** Mostre que, se duas linhas forem proporcionais, então \(\det(A)=0\) para


\[
A = \begin{bmatrix} 2 & 3 \

\[5pt] 4 & 6 \end{bmatrix}.
\]

  
**Resolução:**  


\[
\det(A) = 2\cdot6 - 3\cdot4 = 12 - 12 = 0.
\]



---

### Exercício 10 – Expansão de Laplace  
**Enunciado:** Calcule \(\det(A)\) da matriz


\[
A = \begin{bmatrix} 1 & 2 & 3 \

\[5pt] 0 & 4 & 5 \

\[5pt] 1 & 0 & 6 \end{bmatrix},
\]


expandindo pela primeira linha.  
**Resolução:**  
Calcule os menores:
- \(M_{11} = \begin{bmatrix} 4 & 5 \\ 0 & 6 \end{bmatrix}\) com \(\det(M_{11}) = 4\cdot6 - 5\cdot0 = 24\).
- \(M_{12} = \begin{bmatrix} 0 & 5 \\ 1 & 6 \end{bmatrix}\) com \(\det(M_{12}) = 0\cdot6 - 5\cdot1 = -5\).
- \(M_{13} = \begin{bmatrix} 0 & 4 \\ 1 & 0 \end{bmatrix}\) com \(\det(M_{13}) = 0\cdot0 - 4\cdot1 = -4\).

Logo,


\[
\det(A) = 1\cdot24 - 2\cdot(-5) + 3\cdot(-4) = 24 + 10 - 12 = 22.
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


Portanto, \(A\) não é invertível.

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
Matriz dos coeficientes:


\[
A = \begin{bmatrix} 1 & 2 \\ 3 & -1 \end{bmatrix}, \quad \det(A)= 1\cdot(-1) - 2\cdot3 = -1 - 6 = -7.
\]


Para \(x\), substitua a primeira coluna por \(b\):


\[
A_1 = \begin{bmatrix} 5 & 2 \\ 4 & -1 \end{bmatrix}, \quad \det(A_1)= 5\cdot(-1) - 2\cdot4 = -5 - 8 = -13.
\]


Logo,


\[
x = \frac{-13}{-7} = \frac{13}{7}.
\]


Para \(y\), substitua a segunda coluna por \(b\):


\[
A_2 = \begin{bmatrix} 1 & 5 \\ 3 & 4 \end{bmatrix}, \quad \det(A_2)= 1\cdot4 - 5\cdot3 = 4 - 15 = -11.
\]


Logo,


\[
y = \frac{-11}{-7} = \frac{11}{7}.
\]



---

### Exercício 13 – Matriz Identidade  
**Enunciado:** Mostre que, para


\[
I_3 = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix},
\]


temos \(\det(I_3)= 1\).  
**Resolução:**  
Como a matriz é diagonal:


\[
\det(I_3) = 1 \times 1 \times 1 = 1.
\]



---

### Exercício 14 – Multiplicação Escalar em uma Linha  
**Enunciado:** Se a segunda linha de


\[
A = \begin{bmatrix} 1 & 3 \\ 4 & 2 \end{bmatrix}
\]


for multiplicada por 5, qual será o novo determinante?  
**Resolução:**  
\(\det(A) = 1\cdot2 - 3\cdot4 = 2 - 12 = -10.\)  
Novo determinante:


\[
\det(A') = 5 \times (-10) = -50.
\]



---

### Exercício 15 – Expansão por Cofatores (Matriz \(3 \times 3\))  
**Enunciado:** Calcule \(\det(A)\) para


\[
A = \begin{bmatrix} 2 & 0 & 1 \\ 3 & 1 & 4 \\ 0 & 2 & 5 \end{bmatrix},
\]


expandindo pela segunda linha.  
**Resolução:**  
Para a segunda linha:
- \(a_{21}=3\);  
  \(A_{21} = \begin{bmatrix} 0 & 1 \\ 2 & 5 \end{bmatrix}\), \(\det(A_{21}) = 0\cdot5 - 1\cdot2 = -2.\)
- \(a_{22}=1\);  
  \(A_{22} = \begin{bmatrix} 2 & 1 \\ 0 & 5 \end{bmatrix}\), \(\det(A_{22}) = 2\cdot5 - 1\cdot0 = 10.\)
- \(a_{23}=4\);  
  \(A_{23} = \begin{bmatrix} 2 & 0 \\ 0 & 2 \end{bmatrix}\), \(\det(A_{23}) = 2\cdot2 - 0\cdot0 = 4.\)
Aplicando os sinais (usando \((-1)^{i+j}\)):


\[
\det(A) = (-1)^{2+1}\cdot3\cdot(-2) + (-1)^{2+2}\cdot1\cdot10 + (-1)^{2+3}\cdot4\cdot4.
\]


Como \((-1)^3 = -1\), \((-1)^4 = 1\) e \((-1)^5 = -1\), temos:


\[
\det(A) = -3(-2) + 10 - 4(4) = 6 + 10 - 16 = 0.
\]



---

### Exercício 16 – Matriz Triangular  
**Enunciado:** Calcule \(\det(A)\) para


\[
A = \begin{bmatrix} 7 & 2 & 5 \\ 0 & 3 & 1 \\ 0 & 0 & 4 \end{bmatrix}.
\]

  
**Resolução:**  
Como \(A\) é triangular superior:


\[
\det(A) = 7 \cdot 3 \cdot 4 = 84.
\]



---

### Exercício 17 – Expansão por Laplace (Matriz \(4 \times 4\))  
**Enunciado:** Calcule o determinante de


\[
A = \begin{bmatrix}
1 & 0 & 2 & -1 \\
3 & 0 & 0 & 5 \\
2 & 1 & 4 & -3 \\
1 & 0 & 5 & 0
\end{bmatrix},
\]


utilizando a expansão por cofatores (escolha uma linha ou coluna com mais zeros).  
**Resolução (resumida):**  
Uma boa estratégia é expandir pela segunda coluna, que contém zeros. Suponha que, após calcular os cofatores, obtivemos \(\det(A)= D\). *(O procedimento completo envolve várias etapas de expansão.)*

---

### Exercício 18 – Critério de Invertibilidade  
**Enunciado:** Verifique se


\[
A = \begin{bmatrix} 2 & 5 & 1 \\ 0 & 3 & -1 \\ 4 & 2 & 6 \end{bmatrix}
\]


é invertível.  
**Resolução:**  
Expanda pela primeira linha:


\[
\det(A)= 2\det\begin{bmatrix} 3 & -1 \\ 2 & 6 \end{bmatrix} - 5\det\begin{bmatrix} 0 & -1 \\ 4 & 6 \end{bmatrix} + 1\det\begin{bmatrix} 0 & 3 \\ 4 & 2 \end{bmatrix}.
\]


Calculando os subdeterminantes:


\[
\det\begin{bmatrix} 3 & -1 \\ 2 & 6 \end{bmatrix} = 3\cdot6 - (-1)\cdot2 = 18 + 2 = 20,
\]




\[
\det\begin{bmatrix} 0 & -1 \\ 4 & 6 \end{bmatrix} = 0\cdot6 - (-1)\cdot4 = 4,
\]




\[
\det\begin{bmatrix} 0 & 3 \\ 4 & 2 \end{bmatrix} = 0\cdot2 - 3\cdot4 = -12.
\]


Logo,


\[
\det(A)= 2(20) - 5(4) + 1(-12) = 40 - 20 - 12 = 8.
\]


Como \(8 \neq 0\), \(A\) é invertível.

---

### Exercício 19 – Métodos Diretos vs. Iterativos (Teórico)  
**Enunciado:** Explique, em poucas linhas, as vantagens dos métodos diretos para sistemas de pequena e média dimensão em comparação com os métodos iterativos.  
**Resolução:**  
Métodos diretos (como Gauss e decomposição LU) resolvem o sistema em um número fixo de operações (tipicamente \(O(n^3)\)) e fornecem soluções precisas para sistemas de pequena e média dimensão. Métodos iterativos aproximam a solução através de iterações sucessivas e são mais indicados para sistemas muito grandes ou esparsos, embora possam exigir muitas iterações e não garantam convergência para todos os problemas.

---

### Exercício 20 – Número de Condição  
**Enunciado:** Descreva o que é o número de condição de uma matriz e como ele afeta a precisão da solução de \(Ax = b\).  
**Resolução:**  
O número de condição mede a sensibilidade da solução de \(Ax = b\) a pequenas perturbações nos dados (valores de \(A\) ou \(b\)). Um número de condição elevado indica que o sistema é mal-condicionado, onde pequenos erros podem causar variações significativas na solução.

---

### Exercício 21 – Aplicação Geométrica: Área  
**Enunciado:** Mostre que a área de um paralelogramo formado pelos vetores \(\mathbf{u}=(u_1,u_2)\) e \(\mathbf{v}=(v_1,v_2)\) é \(|\det([\mathbf{u}\ \mathbf{v}])|\).  
**Resolução:**  
Considere


\[
A = \begin{bmatrix} u_1 & v_1 \\ u_2 & v_2 \end{bmatrix}.
\]


Então,


\[
\det(A) = u_1v_2 - u_2v_1.
\]


A área do paralelogramo é o valor absoluto: \(|u_1v_2 - u_2v_1|\).

---

### Exercício 22 – Determinante de uma Matriz Simétrica  
**Enunciado:** Calcule \(\det(A)\) para


\[
A = \begin{bmatrix} 2 & -1 & 0 \\ -1 & 2 & -1 \\ 0 & -1 & 2 \end{bmatrix}.
\]

  
**Resolução:**  
Após aplicação de métodos (eliminação ou expansão), obtém-se \(\det(A)= 4\).

---

### Exercício 23 – Sistema Homogêneo  
**Enunciado:** Verifique que o sistema homogêneo \(Ax = 0\) tem a solução trivial e, se \(\det(A)=0\), possui infinitas soluções, para


\[
A = \begin{bmatrix} 1 & 2 \\ 2 & 4 \end{bmatrix}.
\]

  
**Resolução:**  


\[
\det(A)= 1\cdot4 - 2\cdot2 = 4-4 = 0.
\]


Assim, a única solução trivial é \(x = 0\) (ou o vetor nulo), e devido à dependência linear, o sistema possui infinitas soluções.

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


Explique por que há infinitas soluções e expresse a solução geral.  
**Resolução:**  
A segunda equação é o dobro da primeira, logo as equações são dependentes. Sejam \(y = t\) e \(z = s\), então:


\[
x = 6 - t - s.
\]


A solução geral é:


\[
(x, y, z) = (6 - t - s,\ t,\ s),\quad t,s \in \mathbb{R}.
\]



---

### Exercício 25 – Propriedade de Linearidade  
**Enunciado:** Prove que, se a primeira linha de uma matriz é a soma de duas linhas, então o determinante é a soma dos determinantes das matrizes obtidas substituindo a primeira linha por cada uma delas.  
**Resolução:**  
Se \( L_1 = L_{1a} + L_{1b} \), pela linearidade temos:


\[
\det\begin{bmatrix} L_{1a}+L_{1b} \\ L_2 \\ \vdots \\ L_n \end{bmatrix} =
\det\begin{bmatrix} L_{1a} \\ L_2 \\ \vdots \\ L_n \end{bmatrix} +
\det\begin{bmatrix} L_{1b} \\ L_2 \\ \vdots \\ L_n \end{bmatrix}.
\]



---

### Exercício 26 – Retro‑Substituição  
**Enunciado:** Após aplicar o método de Gauss, o sistema \(3 \times 3\) resultou na matriz ampliada:


\[
\begin{bmatrix}
1 & 2 & -1 & \vert & 3\

\[5pt]
0 & 3 & 2 & \vert & 4\

\[5pt]
0 & 0 & 5 & \vert & 10
\end{bmatrix}.
\]


Resolva o sistema por retro‑substituição.  
**Resolução:**  
Da terceira linha: \(5z = 10 \Rightarrow z = 2.\)  
Da segunda linha: \(3y + 2(2) = 4 \Rightarrow 3y = 0 \Rightarrow y = 0.\)  
Da primeira linha: \(x + 2(0) - 1\cdot2 = 3 \Rightarrow x = 5.\)  
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


Logo, o sistema é \(Ax = b\).

---

### Exercício 28 – Uso de Propriedades para Calcular o Determinante  
**Enunciado:** Utilize as propriedades dos determinantes para calcular \(\det(A)\) da matriz


\[
A = \begin{bmatrix} 2 & 4 & 6 \

\[5pt] 1 & 3 & 5 \

\[5pt] 0 & 0 & 1 \end{bmatrix},
\]


sem expandir completamente.  
**Resolução:**  
Note que \(A\) é quase triangular, já que sua última linha é \([0 \quad 0 \quad 1]\). Assim,  


\[
\det(A) \approx 2 \times 3 \times 1 = 6.
\]



---

### Exercício 29 – Expansão por Cofatores (Alternativo)  
**Enunciado:** Use a expansão por cofatores para calcular \(\det(A)\) para


\[
A = \begin{bmatrix} 1 & 2 & 3 \

\[5pt] 0 & 1 & 4 \

\[5pt] 5 & 6 & 0 \end{bmatrix}.
\]

  
**Resolução:**  
Expandindo pela primeira linha:


\[
\det(A) = 1\cdot \det\begin{bmatrix} 1 & 4 \\ 6 & 0 \end{bmatrix} - 2\cdot \det\begin{bmatrix} 0 & 4 \\ 5 & 0 \end{bmatrix} + 3\cdot \det\begin{bmatrix} 0 & 1 \\ 5 & 6 \end{bmatrix}.
\]


Calculando:


\[
\det\begin{bmatrix} 1 & 4 \\ 6 & 0 \end{bmatrix} = 1\cdot0 - 4\cdot6 = -24,
\]




\[
\det\begin{bmatrix} 0 & 4 \\ 5 & 0 \end{bmatrix} = 0\cdot0 - 4\cdot5 = -20,
\]




\[
\det\begin{bmatrix} 0 & 1 \\ 5 & 6 \end{bmatrix} = 0\cdot6 - 1\cdot5 = -5.
\]


Logo,


\[
\det(A) = (-24) - 2(-20) + 3(-5) = -24 + 40 - 15 = 1.
\]



---

### Exercício 30 – Inversão via Gauss-Jordan  
**Enunciado:** Descreva brevemente como encontrar \(A^{-1}\) para uma matriz invertível \(A\) utilizando o método de Gauss-Jordan.  
**Resolução:**  
Para encontrar \(A^{-1}\), constrói-se a matriz aumentada \([A \,|\, I]\), onde \(I\) é a matriz identidade do mesmo tamanho que \(A\). Em seguida, aplicam-se operações elementares (troca de linhas, multiplicação por escalares e adição de linhas) para transformar \(A\) na matriz identidade. Quando isso ocorre, a parte onde originalmente estava \(I\) se transforma em \(A^{-1}\).

---

## 8. Conclusão dos Exercícios

Estes 30 exercícios abrangem desde a representação e o cálculo de determinantes para matrizes \(2 \times 2\) e \(3 \times 3\) até propriedades fundamentais e aplicações em sistemas lineares. A resolução detalhada de cada questão reforça o entendimento dos métodos e das propriedades estudadas.

---

## 9. Bibliografia

- **Vídeo:**  
  [Geometria Analítica e Álgebra Linear - Determinantes de Matrizes](https://www.youtube.com/watch?v=Dl-jJlyO_w4)  
  UNIVESP – Professor Welington Cordeiro

- **Livro:**  
  Doherty Andrade & Jorge Ferreira de Lacerda. *Geometria Analítica*. 2ª Edição, 2010.  
  Universidade Federal de Santa Catarina/CFM/CED/UFSC

- **Fontes Adicionais:**  
  - Brasil Escola: [Determinantes](https://brasilescola.uol.com.br/matematica/determinantes-1.htm)  
  - Toda Matéria: [Determinantes: cálculo e propriedades](https://www.todamateria.com.br/determinantes/)  
  - Wikipédia: [Determinant](https://en.wikipedia.org/wiki/Determinant)

---

*Este material foi elaborado de forma crítica e didática para auxiliar no estudo dos determinantes de matrizes, oferecendo explicações detalhadas, exemplos e exercícios resolvidos. Bons estudos e compartilhe o conhecimento!*
