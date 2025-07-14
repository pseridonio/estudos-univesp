# Geometria Analítica e Álgebra Linear: Matrizes e Transformações Lineares

## 1. Introdução

Nesta aula, exploramos os conceitos fundamentais que interligam **transformações lineares** e **transformações matriciais**. Vimos como uma função que preserva a aditividade e a multiplicação por escalar pode ser representada por uma matriz em dimensões finitas. A partir dos exemplos apresentados, compreendemos que calcular a imagem de um vetor por uma transformação linear equivale a multiplicá-lo por uma matriz associada. Abordamos ainda a importância da ordem na composição de transformações, por exemplo, ao combinar escalas e rotações, e como pequenas alterações em uma matriz podem modificar significativamente a imagem de um objeto geométrico.

## 2. Conceitos Fundamentais

### 2.1. Transformação Linear

Uma **transformação linear** \(T: V \to W\) entre espaços vetoriais satisfaz as seguintes propriedades para quaisquer vetores \(u, v \in V\) e escalar \(c\):
- **Aditividade:** \(T(u+v)=T(u)+T(v)\)
- **Homogeneidade:** \(T(c\,u)= c\,T(u)\)

Essas propriedades garantem que estruturas essenciais dos espaços vetoriais são preservadas.

### 2.2. Matrizes e Representação de Transformações

Em espaços de dimensão finita toda transformação linear pode ser representada por uma matriz. Por exemplo, considere a função  
\[
T(x,y) = (2x+y,\;2y,\;0)
\]  
de \( \mathbb{R}^2 \) para \( \mathbb{R}^3 \). A matriz associada, com 3 linhas e 2 colunas, é  
\[
A = \begin{pmatrix} 2 & 1 \\ 0 & 2 \\ 0 & 0 \end{pmatrix},
\]  
de forma que para qualquer vetor \((x,y)\) temos  
\[
T(x,y) = A \begin{pmatrix} x \\ y \end{pmatrix}.
\]

### 2.3. Composição de Transformações

A composição de transformações lineares corresponde à multiplicação de suas matrizes representativas. Se \(S : \mathbb{R}^n \to \mathbb{R}^m\) é representada por uma matriz \(A\) e \(T : \mathbb{R}^m \to \mathbb{R}^p\) por uma matriz \(B\), a transformação composta \(T \circ S\) é dada por  
\[
T(S(x)) = B (A x)
\]  
cuja matriz resultante é \(BA\). Ressalta-se que a ordem da composição é essencial, pois geralmente a multiplicação de matrizes não é comutativa.

---

## 3. Exemplos Práticos

### 3.1. Exemplo 1: Transformação de \( \mathbb{R}^2 \) para \( \mathbb{R}^3 \)

Considere \(T(x,y) = (2x+y,\;2y,\;0)\).  
- **Matriz associada:**  
  \[
  A=\begin{pmatrix} 2 & 1 \\ 0 & 2 \\ 0 & 0 \end{pmatrix}
  \]
- **Aplicação:** Para o vetor \((3,-2)\), temos  
  \[
  T(3,-2) = A\begin{pmatrix} 3 \\ -2 \end{pmatrix} =
  \begin{pmatrix} 2\cdot3 + 1\cdot(-2) \\ 0\cdot3 + 2\cdot(-2) \\ 0\cdot3+0\cdot(-2) \end{pmatrix} = \begin{pmatrix} 4 \\ -4 \\ 0 \end{pmatrix}.
  \]

### 3.2. Exemplo 2: Transformações no Plano com Matrizes 2×2

- **Identidade:** \( I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \)  
  Aplicar \( I \) a qualquer vetor \( (x,y) \) retorna \( (x,y) \).

- **Escala:** \( S = \begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix} \)  
  Transforma \( (x,y) \) em \( (2x,2y) \), aumentando uniformemente todas as dimensões (o círculo unitário se torna um círculo de raio 2).

- **Modificação Direcional:**  
  Exemplo: \( A = \begin{pmatrix} \tfrac{1}{2} & 0 \\ 0 & 2 \end{pmatrix} \)  
  Nesse caso, o vetor \( (x,y) \) é transformado em \( (\tfrac{1}{2}x,\, 2y) \), comprimindo horizontalmente e esticando verticalmente.

### 3.3. Exemplo 3: Composição de Escala e Rotação

Considere:
- Uma transformação de escala: \( S = \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} \)
- Uma rotação de 45° anticlockwise: \( R_{45} = \begin{pmatrix} \cos45^\circ & -\sin45^\circ \\ \sin45^\circ & \cos45^\circ \end{pmatrix} = \begin{pmatrix} \tfrac{\sqrt{2}}{2} & -\tfrac{\sqrt{2}}{2} \\ \tfrac{\sqrt{2}}{2} & \tfrac{\sqrt{2}}{2} \end{pmatrix} \)

A transformação composta \( T = R_{45} \circ S \) é dada por  
\[
T = R_{45} \cdot S = \begin{pmatrix} \tfrac{\sqrt{2}}{2}\cdot3 & -\tfrac{\sqrt{2}}{2}\cdot1 \\ \tfrac{\sqrt{2}}{2}\cdot3 & \tfrac{\sqrt{2}}{2}\cdot1 \end{pmatrix} 
= \begin{pmatrix} \tfrac{3\sqrt{2}}{2} & -\tfrac{\sqrt{2}}{2} \\ \tfrac{3\sqrt{2}}{2} & \tfrac{\sqrt{2}}{2} \end{pmatrix}.
\]
Esta matriz define uma transformação que primeiro estica (afetando preferencialmente a componente \(x\)) e depois rotaciona o vetor.

---

## 4. Propriedades das Transformações Lineares

- **Preservação da Soma e do Escalar:**  
  Para \( T: \mathbb{R}^n \to \mathbb{R}^m \), \( T(u+v) = T(u)+T(v) \) e \( T(c\,u)= c\,T(u) \). Isto garante que a estrutura linear do espaço é mantida.

- **Composição e Multiplicação de Matrizes:**  
  A composição de duas transformações lineares é também linear e, em termos matriciais, corresponde à multiplicação das matrizes associadas. É fundamental atentar para a ordem dos fatores.

- **Representação Única:**  
  Em espaços finitos, os efeitos que vemos na geometria (como rotações, escalas e reflexões) são integralmente descritos por matrizes e suas propriedades (como determinante e traço) possuem interpretações geométricas, por exemplo, o determinante representa o fator de escala de área (ou volume).

---

## 5. Análise Crítica

Apesar de o conteúdo apresentado no vídeo ser formal e claro, é essencial que o estudante adote uma postura crítica ao analisar os exemplos e demonstrações. Verifique sempre os cálculos (como a multiplicação de matrizes e a verificação das propriedades de linearidade) utilizando referências confiáveis, seja na literatura clássica de Álgebra Linear ou em fontes digitais de instituições conceituadas. Além disso, observe a importância da ordem na composição de transformações – uma sutileza que, se ignorada, pode levar a erros na interpretação dos resultados.

---

## 6. Conclusão

Nesta aula, reforçamos que qualquer transformação linear em um espaço finito pode ser representada por uma matriz e que as operações com essas matrizes correspondem à composição das transformações envolvidas. A compreensão dessa equivalência é fundamental para o estudo de geometria analítica e álgebra linear, principalmente ao manipular objetos geométricos e transformar espaços. Na próxima aula, aprofundaremos o estudo dos espaços vetoriais.

---

## 7. Lista de Exercícios

A seguir, 30 exercícios com resolução detalhada para fixação dos conceitos abordados:

---

### Exercício 1

**Enunciado:**  
Seja \( T: \mathbb{R}^2 \to \mathbb{R}^3 \) definida por  
\[
T(x,y) = (2x+y,\;2y,\;0)
\]  
com matriz associada  
\[
A = \begin{pmatrix} 2 & 1 \\ 0 & 2 \\ 0 & 0 \end{pmatrix}.
\]  
Calcule \( T(3,-2) \).

**Solução Detalhada:**  
1. Calcule o primeiro componente: \( 2 \cdot 3 + 1 \cdot (-2) = 6 - 2 = 4 \).  
2. Calcule o segundo componente: \( 0 \cdot 3 + 2 \cdot (-2) = -4 \).  
3. O terceiro componente é \( 0 \cdot 3 + 0 \cdot (-2) = 0 \).  
4. Portanto, \( T(3,-2) = (4, -4, 0) \).

---

### Exercício 2

**Enunciado:**  
Demonstre que a função \( T: \mathbb{R}^2 \to \mathbb{R}^3 \) dada por  
\[
T(x,y) = (2x+y,\;2y,\;0)
\]  
é uma transformação linear.

**Solução Detalhada:**  
1. **Verificação da aditividade:**  
   - Sejam \( u=(x_1,y_1) \) e \( v=(x_2,y_2) \).  
   - Então, \( T(u+v) = T(x_1+x_2,\, y_1+y_2) = (2(x_1+x_2)+(y_1+y_2),\, 2(y_1+y_2),\,0) \).  
   - Isto é igual a  
     \[
     (2x_1+2x_2+y_1+y_2,\, 2y_1+2y_2,\, 0).
     \]
   - Por outro lado,  
     \[
     T(u)+T(v) = (2x_1+y_1,\,2y_1,\,0) + (2x_2+y_2,\,2y_2,\,0) = (2x_1+2x_2+y_1+y_2,\, 2y_1+2y_2,\, 0).
     \]
   - Como os resultados são iguais, a propriedade de aditividade é verificada.

2. **Verificação da homogeneidade:**  
   - Seja \( c \) um escalar e \( u = (x,y) \).  
   - Então, \( T(c\,u) = T(cx,cy) = (2(cx)+cy,\;2(cy),\;0) = (c(2x+y),\, c(2y),\,0) \).  
   - Por outro lado, \( c\,T(u) = c\,(2x+y,\,2y,\,0) = (c(2x+y),\, c(2y),\, 0) \).  
   - Assim, \( T(c\,u)= c\,T(u) \).

Portanto, \( T \) é linear.

---

### Exercício 3

**Enunciado:**  
Sejam  
\[
A = \begin{pmatrix} 1 & 0 \\ 0 & 2 \end{pmatrix} \quad \text{e} \quad B = \begin{pmatrix} 2 & 3 \\ 0 & 1 \end{pmatrix}.
\]  
Calcule a composição \( C = A \cdot B \).

**Solução Detalhada:**  
1. \( C_{11} = 1\cdot2 + 0\cdot0 = 2 \).  
2. \( C_{12} = 1\cdot3 + 0\cdot1 = 3 \).  
3. \( C_{21} = 0\cdot2 + 2\cdot0 = 0 \).  
4. \( C_{22} = 0\cdot3 + 2\cdot1 = 2 \).  
5. Assim, \( C = \begin{pmatrix} 2 & 3 \\ 0 & 2 \end{pmatrix} \).

---

### Exercício 4

**Enunciado:**  
Determine a matriz de rotação para 90° (sentido anti-horário).

**Solução Detalhada:**  
1. A matriz de rotação padrão para um ângulo \(\theta\) é  
   \[
   R(\theta)=\begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}.
   \]
2. Para \(\theta=90°\):  
   \(\cos90° = 0\) e \(\sin90° = 1\).
3. Substituindo, temos  
   \[
   R(90°)=\begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}.
   \]
4. Verifique: Aplicando a \( (1,0) \), obtemos \( (0,1) \).

---

### Exercício 5

**Enunciado:**  
Verifique a propriedade de linearidade \( T(u+v)=T(u)+T(v) \) para  
\[
T(x,y)= (3x-y,\,2x+4y),
\]  
usando \( u=(1,2) \) e \( v=(-2,3) \).

**Solução Detalhada:**  
1. Calcule \( u+v = (1+(-2),\, 2+3) = (-1,5) \).  
2. Então, \( T(u+v) = T(-1,5) = (3(-1)-5,\, 2(-1)+4\cdot5) = (-3-5,\,-2+20) = (-8,18) \).  
3. Agora,  
   - \( T(1,2) = (3\cdot1-2,\, 2\cdot1+4\cdot2) = (3-2,\, 2+8) = (1,10) \).  
   - \( T(-2,3) = (3(-2)-3,\, 2(-2)+4\cdot3)= (-6-3,\,-4+12)= (-9,8) \).  
4. Então, \( T(u)+T(v)= (1+(-9),\; 10+8)= (-8,18) \).  
5. Como \( T(u+v)= T(u)+T(v) \), a propriedade está verificada.

---

### Exercício 6

**Enunciado:**  
Verifique se a matriz  
\[
A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}
\]  
é invertível e, em caso afirmativo, determine \(A^{-1}\).

**Solução Detalhada:**  
1. Calcule o determinante:  
   \(\det(A)=1\cdot4-2\cdot3=4-6=-2\).  
2. Como \(\det(A) \neq 0\), a matriz é invertível.  
3. A fórmula para a inversa de uma matriz 2×2 é  
   \[
   A^{-1} = \frac{1}{\det(A)} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}.
   \]
4. Assim,  
   \[
   A^{-1} = \frac{1}{-2} \begin{pmatrix} 4 & -2 \\ -3 & 1 \end{pmatrix} = \begin{pmatrix} -2 & 1 \\ \tfrac{3}{2} & -\tfrac{1}{2} \end{pmatrix}.
   \]

---

### Exercício 7

**Enunciado:**  
Considere a matriz de escala  
\[
S = \begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix}.
\]  
Descreva o efeito desta transformação sobre o círculo unitário \(x^2+y^2=1\).

**Solução Detalhada:**  
1. A transformação \( (x,y) \to (2x,\,2y) \) dobra as coordenadas de todos os pontos.  
2. Assim, o ponto \((x,y)\) do círculo unitário será mapeado para \((2x,2y)\).  
3. Como as distâncias aumentam por um fator 2, o círculo unitário torna-se um círculo de raio 2.  
4. A área, que depende do quadrado do raio, aumenta por fator \(2^2=4\).

---

### Exercício 8

**Enunciado:**  
Encontre a matriz que representa a transformação que primeiro escala o eixo \(x\) por 3 (mantendo \(y\) inalterado) e, em seguida, rotaciona o vetor 45° no sentido anti-horário.

**Solução Detalhada:**  
1. Matriz de escala:  
   \[
   S = \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix}.
   \]
2. Matriz de rotação por 45°:  
   \[
   R_{45}=\begin{pmatrix} \frac{\sqrt{2}}{2} & -\frac{\sqrt{2}}{2} \\[4mm] \frac{\sqrt{2}}{2} & \frac{\sqrt{2}}{2} \end{pmatrix}.
   \]
3. A transformação composta é dada por  
   \[
   T = R_{45} \cdot S = \begin{pmatrix} \frac{\sqrt{2}}{2} & -\frac{\sqrt{2}}{2} \\[2mm] \frac{\sqrt{2}}{2} & \frac{\sqrt{2}}{2} \end{pmatrix} \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix}.
   \]
4. Multiplicando:  
   - Primeiro elemento: \(\frac{\sqrt{2}}{2}\cdot3 + -\frac{\sqrt{2}}{2}\cdot0 = \frac{3\sqrt{2}}{2}\).  
   - Segundo elemento: \(\frac{\sqrt{2}}{2}\cdot0 + -\frac{\sqrt{2}}{2}\cdot1 = -\frac{\sqrt{2}}{2}\).  
   - Terceiro elemento: \(\frac{\sqrt{2}}{2}\cdot3 + \frac{\sqrt{2}}{2}\cdot0 = \frac{3\sqrt{2}}{2}\).  
   - Quarto elemento: \(\frac{\sqrt{2}}{2}\cdot0 + \frac{\sqrt{2}}{2}\cdot1 = \frac{\sqrt{2}}{2}\).  
5. Assim, a matriz resultante é  
   \[
   T = \begin{pmatrix} \frac{3\sqrt{2}}{2} & -\frac{\sqrt{2}}{2} \\[2mm] \frac{3\sqrt{2}}{2} & \frac{\sqrt{2}}{2} \end{pmatrix}.
   \]

---

### Exercício 9

**Enunciado:**  
Determine os autovalores da matriz  
\[
A = \begin{pmatrix} 4 & 2 \\ 1 & 3 \end{pmatrix}.
\]

**Solução Detalhada:**  
1. Calcule o polinômio característico:  
   \[
   \det\left(A-\lambda I\right)=
   \begin{vmatrix} 4-\lambda & 2 \\ 1 & 3-\lambda \end{vmatrix} = (4-\lambda)(3-\lambda)-2.
   \]
2. Expanda:  
   \((4-\lambda)(3-\lambda)= 12-7\lambda+\lambda^2\).  
   Subtraindo 2, obtemos  
   \[
   \lambda^2 - 7\lambda + 10 = 0.
   \]
3. Fatorando:  
   \((\lambda-5)(\lambda-2)=0\).  
4. Assim, os autovalores são \(\lambda = 5\) e \(\lambda = 2\).

---

### Exercício 10

**Enunciado:**  
Encontre a matriz resultante da composição de uma reflexão sobre o eixo \(x\) com uma rotação de 90°.

**Solução Detalhada:**  
1. Matriz de reflexão sobre o eixo \(x\):  
   \[
   R_x = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}.
   \]
2. Matriz de rotação de 90°:  
   \[
   R_{90} = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}.
   \]
3. Composição (aplicando \(R_x\) primeiro e depois a rotação):  
   \[
   R = R_{90} \cdot R_x = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}.
   \]
4. Multiplicando:  
   - \(R_{11}=0\cdot1+(-1)\cdot0=0\).  
   - \(R_{12}=0\cdot0+(-1)\cdot(-1)=1\).  
   - \(R_{21}= 1\cdot1+0\cdot0=1\).  
   - \(R_{22}=1\cdot0+0\cdot(-1)=0\).  
5. Assim, a matriz resultante é  
   \[
   R = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix},
   \]  
   que corresponde à reflexão em relação à reta \(y=x\).

---

### Exercício 11

**Enunciado:**  
Determine os valores de \(a\) e \(b\) para que a matriz  
\[
A = \begin{pmatrix} a & b \\ b & -a \end{pmatrix}
\]  
represente uma reflexão em \( \mathbb{R}^2 \).

**Solução Detalhada:**  
1. Uma matriz de reflexão deve ser ortogonal (ou seja, \(A^T A = I\)) e ter determinante \(-1\).  
2. Primeiro, calcule o determinante:  
   \[
   \det(A)= a\cdot(-a)-b\cdot b = -a^2 - b^2.
   \]
3. Para que \(\det(A)=-1\), é necessário que  
   \[
   a^2+b^2=1.
   \]
4. Ademais, a simetria \(A=A^T\) já ocorre se os elementos fora da diagonal forem iguais (o que ocorre).  
5. Portanto, quaisquer \(a\) e \(b\) tais que \(a^2+b^2=1\) fornecerão uma matriz de reflexão.

---

### Exercício 12

**Enunciado:**  
Demonstre que o conjunto de todas as matrizes \(2\times2\) forma um espaço vetorial sob a adição de matrizes e multiplicação por escalar.

**Solução Detalhada:**  
1. **Fechamento sob adição:** A soma de duas matrizes \(2\times2\) é outra matriz \(2\times2\).  
2. **Associatividade e comutatividade:** A adição de matrizes é associativa e comutativa.  
3. **Elemento neutro:** Existe a matriz nula \(O = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}\).  
4. **Inverso aditivo:** Para cada matriz \(A\), existe \(-A\) tal que \(A+(-A)=O\).  
5. **Fechamento sob multiplicação por escalar:** Se \(c \in \mathbb{R}\) e \(A\) é \(2\times2\), então \(cA\) é \(2\times2\).  
6. **Propriedades distributivas e associativas:** Todas as propriedades dos espaços vetoriais são satisfeitas.

Portanto, o conjunto das matrizes \(2\times2\) é um espaço vetorial.

---

### Exercício 13

**Enunciado:**  
Defina \( T: \mathbb{R}^2 \to \mathbb{R}^2 \) por  
\[
T(x,y)= (2x-y,\; x+3y).
\]  
Verifique que os vetores \(T(e_1)\) e \(T(e_2)\), onde \( e_1=(1,0) \) e \( e_2=(0,1) \), determinam totalmente \(T\).

**Solução Detalhada:**  
1. Calcule:  
   - \(T(e_1) = T(1,0)= (2\cdot1-0,\; 1+3\cdot0)= (2,1)\).  
   - \(T(e_2) = T(0,1)= (2\cdot0-1,\; 0+3\cdot1)= (-1,3)\).
2. Qualquer vetor \( (x,y) \) pode ser escrito como \( x\,(1,0) + y\,(0,1) \).  
3. Pela linearidade,  
   \[
   T(x,y)= x\,(2,1) + y\,(-1,3).
   \]
4. Portanto, \(T\) está completamente determinada por \(T(e_1)\) e \(T(e_2)\).

---

### Exercício 14

**Enunciado:**  
Considere a transformação \( T: \mathbb{R}^2 \to \mathbb{R}^2 \) definida por  
\[
T(x,y)= (4x,\;5y).
\]  
Calcule \( T(2(x,y)) \) e compare com \(2T(x,y)\).

**Solução Detalhada:**  
1. \( T(2x,2y)= (4\cdot2x,\; 5\cdot2y)= (8x,10y) \).  
2. \( 2\,T(x,y)= 2\,(4x,5y)= (8x,10y) \).  
3. Portanto, \( T(2(x,y))= 2T(x,y) \), confirmando a homogeneidade.

---

### Exercício 15

**Enunciado:**  
Calcule o produto da matriz  
\[
A = \begin{pmatrix} 3 & -1 \\ 2 & 4 \end{pmatrix}
\]  
com o vetor \( v=(1,3) \).

**Solução Detalhada:**  
1. Primeiro componente: \(3\cdot1 + (-1)\cdot3= 3-3=0\).  
2. Segundo componente: \(2\cdot1 + 4\cdot3= 2+12=14\).  
3. Assim, \(Av = (0,14)\).

---

### Exercício 16

**Enunciado:**  
Sejam as matrizes  
\[
S = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix} \quad \text{e} \quad T = \begin{pmatrix} 1 & 4 \\ 2 & -1 \end{pmatrix}.
\]  
Determine a matriz que representa a composição \( T \circ S \).

**Solução Detalhada:**  
1. Calcule \( T \cdot S \):  
   - \( (1,1):\; 1\cdot2+4\cdot0=2 \).  
   - \( (1,2):\; 1\cdot0+4\cdot3=12 \).  
   - \( (2,1):\; 2\cdot2+(-1)\cdot0=4 \).  
   - \( (2,2):\; 2\cdot0+(-1)\cdot3=-3 \).  
2. Assim, a matriz resultante é  
   \[
   \begin{pmatrix} 2 & 12 \\ 4 & -3 \end{pmatrix}.
   \]

---

### Exercício 17

**Enunciado:**  
Para a transformação \( T: \mathbb{R}^2 \to \mathbb{R}^2 \) definida por  
\[
T(x,y)= (x+2y,\; 3x+6y),
\]  
determine o núcleo (kernel) e a imagem (range) de \(T\).

**Solução Detalhada:**  
1. **Núcleo:**  
   - Resolva \(T(x,y)=(0,0)\), ou seja,  
     \[
     x+2y=0 \quad \text{e} \quad 3x+6y=0.
     \]
   - Note que a segunda equação é \(3\) vezes a primeira. Assim,  
     \[
     x=-2y.
     \]
   - Logo, o núcleo é  
     \[
     \{(x,y) \in \mathbb{R}^2 : x=-2y\}.
     \]
2. **Imagem:**  
   - Como \(T(x,y) = (x+2y,\; 3x+6y) = (x+2y,\; 3(x+2y))\), todo vetor imagem é da forma  
     \[
     (s, 3s) \quad \text{com } s\in\mathbb{R}.
     \]
   - Assim, a imagem é a reta gerada por \( (1,3) \).

---

### Exercício 18

**Enunciado:**  
Encontre a matriz que transforma o vetor \( (x,y) \) no vetor \( (3x-y, \;2x+y) \).

**Solução Detalhada:**  
1. Calcule a ação sobre os vetores da base:  
   - \( T(1,0)= (3\cdot1-0,\; 2\cdot1+0)= (3,2) \).  
   - \( T(0,1)= (3\cdot0-1,\; 2\cdot0+1)= (-1,1) \).
2. A matriz padrão é montada colocando estes resultados como colunas:  
   \[
   A=\begin{pmatrix} 3 & -1 \\ 2 & 1 \end{pmatrix}.
   \]

---

### Exercício 19

**Enunciado:**  
Considere a transformação \( T: \mathbb{R}^2 \to \mathbb{R}^2 \) definida por  
\[
T(x,y)= (ax+by,\; cx+dy).
\]  
Quais condições devem ser impostas aos números \(a\), \(b\), \(c\) e \(d\) para que \(T\) seja invertível?

**Solução Detalhada:**  
1. A transformação é invertível se a matriz  
   \[
   A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}
   \]  
   tiver determinante diferente de zero.  
2. Assim, deve ser satisfeito que  
   \[
   ad-bc\neq0.
   \]

---

### Exercício 20

**Enunciado:**  
Calcule o determinante da matriz  
\[
A=\begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix}
\]  
e interprete o seu valor em termos do fator de escala de área.

**Solução Detalhada:**  
1. O determinante é  
   \[
   \det(A)= 3\cdot4-1\cdot2=12-2=10.
   \]
2. Isto indica que qualquer área no domínio é multiplicada por 10 (em valor absoluto) pela transformação associada a \(A\).

---

### Exercício 21

**Enunciado:**  
Dada a transformação \( T: \mathbb{R}^2 \to \mathbb{R}^2 \) definida por  
\[
T(x,y)= (5x-2y,\;3x+4y),
\]  
determine a matriz inversa de \(T\), se existir.

**Solução Detalhada:**  
1. Considere a matriz associada:  
   \[
   A = \begin{pmatrix} 5 & -2 \\ 3 & 4 \end{pmatrix}.
   \]
2. Calcule o determinante:  
   \(\det(A)=5\cdot4 - (-2\cdot3)=20+6=26\).
3. Como \(\det(A)\neq0\), a inversa existe e é dada por  
   \[
   A^{-1} = \frac{1}{26}\begin{pmatrix} 4 & 2 \\ -3 & 5 \end{pmatrix}.
   \]

---

### Exercício 22

**Enunciado:**  
Calcule o quadrado da matriz  
\[
A=\begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix}
\]  
e interprete o resultado.

**Solução Detalhada:**  
1. \(A^2 = A\cdot A = \begin{pmatrix} 2^2 & 0 \\ 0 & 3^2 \end{pmatrix}= \begin{pmatrix} 4 & 0 \\ 0 & 9 \end{pmatrix}\).  
2. Aplicar \(A\) duas vezes equivale a escalar a componente \(x\) por 4 e a componente \(y\) por 9.

---

### Exercício 23

**Enunciado:**  
Considere a matriz de rotação  
\[
R_\theta = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}.
\]  
Se  
\[
R = \begin{pmatrix} 0.6 & -0.8 \\ 0.8 & 0.6 \end{pmatrix},
\]  
determine o ângulo de rotação \(\theta\).

**Solução Detalhada:**  
1. Identifique que \(\cos\theta=0.6\) e \(\sin\theta=0.8\).  
2. Calcule \(\theta = \arccos(0.6)\), que resulta aproximadamente em \(53.13°\).  
3. Alternativamente,  
   \(\theta = \arctan\left(\frac{0.8}{0.6}\right)\approx \arctan(1.333)\approx 53.13°\).

---

### Exercício 24

**Enunciado:**  
Demonstre que a composição de duas rotações, \( R_\alpha \) e \( R_\beta \), é igual a uma rotação de ângulo \( \alpha+\beta \).

**Solução Detalhada:**  
1. Escreva:  
   \[
   R_\alpha = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix},\quad
   R_\beta = \begin{pmatrix} \cos\beta & -\sin\beta \\ \sin\beta & \cos\beta \end{pmatrix}.
   \]
2. Multiplicando \(R_\alpha R_\beta\), obtemos:  
   \[
   \begin{pmatrix} \cos\alpha\cos\beta-\sin\alpha\sin\beta & -(\cos\alpha\sin\beta+\sin\alpha\cos\beta) \\[4mm] \sin\alpha\cos\beta+\cos\alpha\sin\beta & \cos\alpha\cos\beta-\sin\alpha\sin\beta \end{pmatrix},
   \]
3. Utilizando as identidades trigonométricas, isto é equivalente a  
   \[
   \begin{pmatrix} \cos(\alpha+\beta) & -\sin(\alpha+\beta) \\ \sin(\alpha+\beta) & \cos(\alpha+\beta) \end{pmatrix}.
   \]
4. Portanto, \(R_\alpha R_\beta= R_{\alpha+\beta}\).

---

### Exercício 25

**Enunciado:**  
Determine a matriz que representa a reflexão no eixo \(x\) e aplique-a ao ponto \((3,4)\).

**Solução Detalhada:**  
1. A matriz de reflexão sobre o eixo \(x\) é  
   \[
   R_x = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}.
   \]
2. Aplicando:  
   \[
   R_x(3,4)= (1\cdot3+0\cdot4,\; 0\cdot3+(-1)\cdot4) = (3,-4).
   \]

---

### Exercício 26

**Enunciado:**  
Considere a função \( F:\mathbb{R}^2\to\mathbb{R}^2 \) definida por  
\[
F(x,y) = (x^2,\; y).
\]  
Mostre por que \(F\) não é uma transformação linear.

**Solução Detalhada:**  
1. Uma transformação linear precisa satisfazer \( F(c\,u)=c\,F(u) \) para qualquer escalar \(c\).  
2. Tome \( u=(x,y) \); então, \( F(c\,x,c\,y)= ((cx)^2,\,cy)=(c^2x^2,\, c y) \).  
3. Em geral, \( c^2x^2 \neq c(x^2) \) (exceto quando \( c=0 \) ou \(1 \)).  
4. Portanto, \(F\) falha na propriedade de homogeneidade e, consequentemente, não é linear.

---

### Exercício 27

**Enunciado:**  
Determine a matriz padrão que representa a projeção de \( \mathbb{R}^2 \) sobre a reta \( y=x \).

**Solução Detalhada:**  
1. A projeção de um vetor \((x,y)\) sobre a reta \( y=x \) é  
   \[
   \left(\frac{x+y}{2},\, \frac{x+y}{2}\right).
   \]
2. Isso pode ser escrito em forma matricial:  
   \[
   T(x,y)= \left(\frac{1}{2}x+\frac{1}{2}y,\; \frac{1}{2}x+\frac{1}{2}y\right).
   \]
3. Assim, a matriz padrão é  
   \[
   P = \begin{pmatrix} \tfrac{1}{2} & \tfrac{1}{2} \\[4mm] \tfrac{1}{2} & \tfrac{1}{2} \end{pmatrix}.
   \]

---

### Exercício 28

**Enunciado:**  
Seja \( T: \mathbb{R}^2\to\mathbb{R}^2 \) representada por  
\[
A=\begin{pmatrix} 2 & 1 \\ 0 & 3 \end{pmatrix}.
\]  
Determine a imagem do polígono com vértices \((0,0)\), \((1,0)\), \((1,1)\) e \((0,1)\).

**Solução Detalhada:**  
1. Aplique \(T\) a cada vértice:  
   - \( T(0,0)= (0,0) \).  
   - \( T(1,0)= (2\cdot1+1\cdot0,\; 0\cdot1+3\cdot0)= (2,0) \).  
   - \( T(1,1)= (2\cdot1+1\cdot1,\; 0\cdot1+3\cdot1)= (3,3) \).  
   - \( T(0,1)= (2\cdot0+1\cdot1,\; 0\cdot0+3\cdot1)= (1,3) \).
2. O polígono transformado tem vértices \((0,0)\), \((2,0)\), \((3,3)\) e \((1,3)\).

---

### Exercício 29

**Enunciado:**  
Considere a função \( F: \mathbb{R}^2\to\mathbb{R}^2 \) dada por  
\[
F(x,y)= (2x+3,\; 4y-1).
\]  
Explique por que \(F\) não é uma transformação linear e identifique sua parte linear.

**Solução Detalhada:**  
1. Uma transformação linear deve enviar o zero para o zero.  
   - Note que \( F(0,0)= (3,\;-1) \neq (0,0) \).  
2. Portanto, \(F\) não é linear, pois há um termo de translação.  
3. A parte linear \(L\) associada é obtida ao desconsiderar as constantes constantes:  
   \[
   L(x,y)= (2x,\; 4y).
   \]

---

### Exercício 30

**Enunciado:**  
Se a matriz identidade \( I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \) é modificada no elemento \( (1,1) \) para formar  
\[
A=\begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix},
\]  
descreva o efeito desta transformação sobre um vetor \((x,y)\).

**Solução Detalhada:**  
1. A transformação dada por \(A\) atua via  
   \[
   A(x,y)= (2x,\; y).
   \]
2. Assim, a componente \(x\) é escalada por 2 enquanto a \(y\) permanece inalterada.  
3. Geometricamente, isso implica um estiramento horizontal: objetos terão seu comprimento horizontal duplicado, enquanto a dimensão vertical não é alterada.

---

## 8. Bibliografia

- **Vídeo Aula:**  
  **Título:** _Geometria analítica e álgebra linear – Matrizes x Transformações Lineares_  
  **Instituição:** UNIVESP (Universidade Virtual do Estado de São Paulo)  
  **Link:** [https://www.youtube.com/watch?v=R0mZBNJNOHc&t=1s](https://www.youtube.com/watch?v=R0mZBNJNOHc&t=1s)  
  **Data de acesso:** 18 de maio de 2025

- **Livro:**  
  **Título:** _Álgebra Linear_  
  **Autor:** W. Keith Nicholson  
  **Observação:** Utilize a edição disponível de acordo com sua biblioteca (os detalhes completos de edição, editora e ano podem ser consultados na cópia local ou fonte digital).

- **Fontes Complementares na Web:**  
  Fontes e recursos de instituições confiáveis como Khan Academy, MIT OpenCourseWare e Wolfram MathWorld podem ser consultados para complementação dos conceitos abordados.

---