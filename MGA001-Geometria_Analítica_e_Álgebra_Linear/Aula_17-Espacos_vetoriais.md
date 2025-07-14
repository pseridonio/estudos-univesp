# Geometria Analítica e Álgebra Linear: Espaços Vetoriais

## 1. Introdução

Nesta aula, exploramos os conceitos fundamentais dos espaços vetoriais, estendendo a ideia dos vetores no plano e no espaço para dimensões arbitrárias (ℝ², ℝ³ e ℝⁿ). O vídeo enfatiza a importância de compreender os subespaços (conjuntos que, herdando as operações do espaço maior, possuem estrutura vetorial) e apresenta, de maneira intuitiva, noções relativas aos geradores dos espaços – isto é, os vetores que, por suas combinações lineares, “constroem” o espaço considerado. A aula também toca nos conceitos de kernel (núcleo) e imagem no contexto de transformações lineares, elementos cruciais para analisar a estrutura de funções lineares.

---

## 2. Espaços Vetoriais

Um **espaço vetorial** é um conjunto \(V\) (geralmente composto por vetores) munido de duas operações – adição e multiplicação por escalar – que satisfaz os seguintes axiomas:

- **Fechamento sob adição:** Para quaisquer \(u, v \in V\), temos \(u + v \in V\).
- **Fechamento sob multiplicação por escalar:** Para todo escalar \(c\) e todo \(v \in V\), \(c\,v \in V\).
- **Elemento zero:** Existe um vetor \(0 \in V\) tal que \(v + 0 = v\), para todo \(v \in V\).
- **Inverso aditivo:** Para cada \(v \in V\), existe um vetor \(-v \in V\) de modo que \(v + (-v) = 0\).
- **Associatividade, comutatividade e propriedades distributivas:** Essas operações obedecem às propriedades usuais da aritmética.

Exemplos clássicos incluem:
- \( \mathbb{R}^2 \): o conjunto de todos os pares \((x, y)\);
- \( \mathbb{R}^3 \): o conjunto de todas as trincas \((x, y, z)\);
- \( \mathbb{R}^n \): o conjunto de todos os n-uplas reais.

---

## 3. Subespaços Vetoriais

Um **subespaço** de um espaço vetorial \(V\) é um subconjunto \(W \subseteq V\) que é ele mesmo um espaço vetorial – isto é, as operações de adição e multiplicação por escalar, restritas a \(W\), satisfazem os axiomas de um espaço vetorial. Para que \(W\) seja considerado um subespaço, é necessário que:

1. \(0 \in W\) (o vetor nulo faça parte de \(W\));
2. Se \(u, v \in W\), então \(u + v \in W\);
3. Se \(v \in W\) e \(c\) é um escalar, então \(c\,v \in W\).

*Exemplo:* No plano, a reta definida por  
\[
W = \{(x, y) \in \mathbb{R}^2 : y = 2x\}
\]  
é um subespaço, pois contém o vetor zero, é fechada quanto à adição (a soma de dois pontos na reta resulta em outro ponto na reta) e tem fechamento quanto à multiplicação por escalar.

---

## 4. Geradores de Espaços Vetoriais

Seja \( S = \{v_1, v_2, \ldots, v_k\} \) um conjunto de vetores em um espaço vetorial \(V\). O **span** (ou espaço gerado) por \(S\) é o conjunto de todas as combinações lineares dos vetores de \(S\):
\[
\text{span}(S) = \{ c_1v_1 + c_2v_2 + \cdots + c_kv_k \mid c_1, c_2, \ldots, c_k \in \mathbb{R} \}.
\]
Quando \(\text{span}(S) = V\), dizemos que o conjunto \(S\) gera ou é um sistema gerador de \(V\). Por exemplo, em \(\mathbb{R}^2\) um único vetor não nulo gera uma reta (um subespaço de \(\mathbb{R}^2\)).

---

## 5. Kernel e Imagem de Transformações Lineares

Em uma transformação linear \(T: V \to W\):

- O **kernel** (ou **núcleo**) de \(T\) é o conjunto dos vetores em \(V\) que são mapeados para o vetor nulo de \(W\):
  \[
  \text{ker}(T) = \{ v \in V \mid T(v) = 0 \}.
  \]
- A **imagem** de \(T\) é o conjunto dos vetores em \(W\) que podem ser obtidos pela aplicação de \(T\):
  \[
  \text{im}(T) = \{ w \in W \mid \exists\, v \in V,\, T(v)=w \}.
  \]

Esses conceitos são fundamentais para analisar a estrutura de transformações lineares e compreender como as propriedades do domínio se refletem no contradomínio.

---

## 6. Exemplos Práticos

### Exemplo 1: Subespaço no Plano

Considere o subespaço \(W = \{(x,y) \in \mathbb{R}^2 : y = 2x\}\).  
- O vetor zero \((0,0)\) está em \(W\).  
- Se \((x_1, 2x_1)\) e \((x_2, 2x_2)\) estão em \(W\), sua soma é \((x_1+x_2, 2(x_1+x_2))\), que também pertence a \(W\).  
- Para qualquer escalar \(c\), \(c(x,2x) = (cx, 2cx)\) está em \(W\).

### Exemplo 2: Gerador de Espaço

Em \(\mathbb{R}^3\), os vetores \(v_1=(1,0,0)\) e \(v_2=(0,1,0)\) geram o plano dado por todos os vetores da forma \((x,y,0)\), que é um subespaço de \(\mathbb{R}^3\).

### Exemplo 3: Kernel e Imagem

Seja a transformação linear \(T: \mathbb{R}^3 \to \mathbb{R}\) definida por
\[
T(x,y,z) = x - y + 2z.
\]
- **Kernel:** Conjunto dos vetores \((x,y,z)\) que satisfazem \(x - y + 2z = 0\).  
- **Imagem:** Como \(T\) é linear e não trivial, a imagem é \( \mathbb{R} \).

---

## 7. Conclusão

Nesta aula, foram abordados os conceitos essenciais de espaços vetoriais, enfatizando as características que definem a estrutura vetorial e as condições necessárias para que um subconjunto seja considerado um subespaço. Aprendemos sobre a importância dos geradores — os vetores cujas combinações lineares constroem o espaço — e vimos os conceitos de kernel e imagem dentro do estudo das transformações lineares. Esses fundamentos são indispensáveis para uma compreensão aprofundada da Geometria Analítica e da Álgebra Linear.

---

## 8. Lista de Exercícios

A seguir, são apresentados 30 exercícios, cada um acompanhado de uma resolução detalhada.

### Exercício 1

**Enunciado:**  
Prove que \(\mathbb{R}^2\) é um espaço vetorial com as operações usuais de adição e multiplicação por escalar.

**Solução Detalhada:**
1. **Fechamento:**  
   - Sejam \(u = (x_1,y_1)\) e \(v = (x_2,y_2)\).  
   - A soma \(u+v=(x_1+x_2,\, y_1+y_2)\) também é um par de números reais.
2. **Elemento zero:**  
   - O vetor \(0=(0,0)\) satisfaz \( (x,y)+(0,0)=(x,y) \).
3. **Inversos aditivos:**  
   - Para cada \( (x,y) \), o vetor \((-x,-y)\) é tal que \((x,y)+(-x,-y)=(0,0)\).
4. **Multiplicação por escalar:**  
   - Para \(c\in\mathbb{R}\) e \( (x,y) \), temos \(c(x,y)=(cx, cy)\in\mathbb{R}^2\).
5. **Associatividade, comutatividade e propriedades distributivas:**  
   - Estes são verificados pela aritmética real.
   
Portanto, \(\mathbb{R}^2\) satisfaz todos os axiomas de espaço vetorial.

---

### Exercício 2

**Enunciado:**  
Verifique que o conjunto  
\[
W = \{(x,y) \in \mathbb{R}^2 : y = 2x\}
\]
é um subespaço de \(\mathbb{R}^2\).

**Solução Detalhada:**
1. **Vetor zero:**  
   - Quando \(x=0\), \(y=2(0)=0\) ⇒ \((0,0)\in W\).
2. **Fechamento sob adição:**  
   - Se \((x_1,2x_1)\) e \((x_2,2x_2)\) pertencem a \(W\), então  
     \[
     (x_1+x_2,2x_1+2x_2)=(x_1+x_2,2(x_1+x_2))\in W.
     \]
3. **Fechamento sob multiplicação:**  
   - Para \(c\in\mathbb{R}\) e \((x,2x)\in W\),  
     \[
     c(x,2x)=(cx,2cx)\in W.
     \]
   
Portanto, \(W\) é um subespaço de \(\mathbb{R}^2\).

---

### Exercício 3

**Enunciado:**  
Mostre que o conjunto  
\[
U = \{(x,y) \in \mathbb{R}^2 : y = x + 1\}
\]
não é um subespaço de \(\mathbb{R}^2\).

**Solução Detalhada:**
1. **Vetor zero:**  
   - Check: Para \((x,y)=(0,0)\), a condição \(0=0+1\) não é satisfeita.
2. **Conclusão:**  
   - Como \((0,0)\notin U\), \(U\) não pode ser um subespaço.

---

### Exercício 4

**Enunciado:**  
Determine um conjunto gerador para o subespaço  
\[
W = \{(x,y) \in \mathbb{R}^2 : y = 2x\}.
\]

**Solução Detalhada:**
1. Qualquer vetor de \(W\) pode ser escrito como \((x,2x)=x(1,2)\).
2. Assim, o vetor \((1,2)\) gera \(W\); isto é,  
   \[
   W=\text{span}\{(1,2)\}.
   \]

---

### Exercício 5

**Enunciado:**  
Prove que o conjunto dos polinômios de grau no máximo 2, denotado por \(P_2\), é um espaço vetorial.

**Solução Detalhada:**
1. **Definição:**  
   - Um elemento de \(P_2\) tem a forma \(p(x)=ax^2+bx+c\) com \(a,b,c\in\mathbb{R}\).
2. **Fechamento:**  
   - A soma de dois polinômios de grau ≤2 resulta em um polinômio de grau ≤2.
3. **Multiplicação por escalar:**  
   - Multiplicar \(p(x)\) por um escalar \(k\) resulta em \(kp(x)=kax^2+kbx+kc\), também em \(P_2\).
4. **Demais axiomas:**  
   - As propriedades (zero, inversos, distributividade etc.) derivam da aritmética dos reais.
   
Portanto, \(P_2\) é um espaço vetorial.

---

### Exercício 6

**Enunciado:**  
Mostre que o conjunto das matrizes diagonais de ordem 2,
\[
D = \left\{ \begin{pmatrix} a & 0 \\ 0 & b \end{pmatrix} \mid a,b \in \mathbb{R} \right\},
\]
é um subespaço de \(M_{2 \times 2}(\mathbb{R})\).

**Solução Detalhada:**
1. **Vetor zero:**  
   - A matriz nula \(\begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}\in D\).
2. **Fechamento sob adição:**  
   - Se \(A=\begin{pmatrix} a_1 & 0 \\ 0 & b_1 \end{pmatrix}\) e \(B=\begin{pmatrix} a_2 & 0 \\ 0 & b_2 \end{pmatrix}\), então  
     \[
     A+B=\begin{pmatrix} a_1+a_2 & 0 \\ 0 & b_1+b_2 \end{pmatrix}\in D.
     \]
3. **Fechamento sob multiplicação:**  
   - Para \(c\in\mathbb{R}\), \(cA=\begin{pmatrix} ca_1 & 0 \\ 0 & cb_1 \end{pmatrix}\in D\).

Portanto, \(D\) é um subespaço de \(M_{2 \times 2}(\mathbb{R})\).

---

### Exercício 7

**Enunciado:**  
Considere a transformação linear \(T: \mathbb{R}^3 \to \mathbb{R}^2\) definida por
\[
T(x,y,z) = (x+y,\; y+z).
\]
Determine o kernel e a imagem de \(T\).

**Solução Detalhada:**
1. **Kernel:**  
   - Encontrar \((x,y,z)\) tais que
     \[
     x+y=0 \quad \text{e} \quad y+z=0.
     \]
   - Da primeira equação, \(x=-y\); da segunda, \(z=-y\).  
   - Assim, o kernel é
     \[
     \text{ker}(T)=\{(-y,\,y,\,-y) \mid y\in\mathbb{R}\} = \text{span}\{(-1,1,-1)\}.
     \]
2. **Imagem:**  
   - Seja \(s=x+y\) e \(t=y+z\). Como \(x,y,z\) são arbitrários, quaisquer pares \((s,t)\in\mathbb{R}^2\) podem ser obtidos.  
   - Portanto, \(\text{im}(T)=\mathbb{R}^2\).

---

### Exercício 8

**Enunciado:**  
Prove que a interseção de dois subespaços de um espaço vetorial é também um subespaço.

**Solução Detalhada:**
1. Seja \(W_1\) e \(W_2\) subespaços de \(V\). Defina \(W = W_1 \cap W_2\).
2. **Vetor zero:**  
   - Como \(0\in W_1\) e \(0\in W_2\), \(0\in W\).
3. **Fechamento sob adição:**  
   - Se \(u,v\in W\), então \(u,v\in W_1\) e \(u,v\in W_2\). Assim, \(u+v\in W_1\) e \(u+v\in W_2\), logo \(u+v\in W\).
4. **Fechamento sob multiplicação:**  
   - Se \(u\in W\) e \(c\in\mathbb{R}\), \(cu\in W_1\) e \(cu\in W_2\), então \(cu\in W\).
   
Portanto, \(W_1 \cap W_2\) é um subespaço de \(V\).

---

### Exercício 9

**Enunciado:**  
Determine o span do conjunto \(\{(1,2), (3,6)\}\) em \(\mathbb{R}^2\).

**Solução Detalhada:**
1. Note que \((3,6)=3(1,2)\); ou seja, os vetores são linearmente dependentes.
2. Assim, qualquer combinação linear \(c_1(1,2)+c_2(3,6)\) pode ser escrita como \(d(1,2)\) onde \(d=c_1+3c_2\).
3. Portanto,  
   \[
   \text{span}\{(1,2), (3,6)\}=\{d(1,2)\mid d\in \mathbb{R}\},
   \]
   que é a reta que passa pela origem na direção de \((1,2)\).

---

### Exercício 10

**Enunciado:**  
Determine uma base para o subespaço de \(\mathbb{R}^3\) gerado por \(\{(1,2,3), (2,4,6)\}\).

**Solução Detalhada:**
1. Observe que \((2,4,6)=2(1,2,3)\); portanto, os vetores são linearmente dependentes.
2. Assim, a base pode ser \(\{(1,2,3)\}\).

---

### Exercício 11

**Enunciado:**  
Forneça um exemplo de dois vetores em \(\mathbb{R}^3\) que não geram \(\mathbb{R}^3\) e justifique.

**Solução Detalhada:**
1. Considere \(v_1=(1,0,0)\) e \(v_2=(0,1,0)\).
2. As combinações lineares \(a(1,0,0)+b(0,1,0)=(a,b,0)\) geram o plano \(z=0\), não todo \(\mathbb{R}^3\).
3. Portanto, \(v_1\) e \(v_2\) não geram \(\mathbb{R}^3\).

---

### Exercício 12

**Enunciado:**  
Verifique se os vetores \((1,2)\) e \((2,4)\) são linearmente independentes em \(\mathbb{R}^2\).

**Solução Detalhada:**
1. Verifique se existe \(c_1, c_2\) não ambos nulos tais que  
   \[
   c_1(1,2)+c_2(2,4)=(0,0).
   \]
2. Isso resulta no sistema  
   \[
   c_1+2c_2=0,\quad 2c_1+4c_2=0.
   \]
3. A segunda equação é o dobro da primeira, logo há infinitas soluções (por exemplo, \(c_1=2\), \(c_2=-1\)).
4. Assim, os vetores são linearmente dependentes.

---

### Exercício 13

**Enunciado:**  
Mostre que o conjunto \(\{(0,0)\}\) é um subespaço (trivial) de \(\mathbb{R}^2\).

**Solução Detalhada:**
1. O único elemento é o vetor zero.
2. Ele satisfaz todas as propriedades (a soma de \(0\) com \(0\) é \(0\), e \(c\cdot0=0\) para qualquer escalar \(c\)).
3. Portanto, \(\{(0,0)\}\) é um subespaço trivial de \(\mathbb{R}^2\).

---

### Exercício 14

**Enunciado:**  
Demonstre que a união de dois subespaços de \(\mathbb{R}^2\) não é necessariamente um subespaço.

**Solução Detalhada:**
1. Considere os subespaços \(W_1 = \{(x,0) \mid x\in\mathbb{R}\}\) (eixo \(x\)) e \(W_2 = \{(0,y) \mid y\in\mathbb{R}\}\) (eixo \(y\)).
2. A união \(W_1\cup W_2\) contém, por exemplo, \((1,0)\) e \((0,1)\), mas a soma \((1,0)+(0,1)=(1,1)\) não pertence nem a \(W_1\) nem a \(W_2\).
3. Assim, \(W_1\cup W_2\) não é fechado sob adição e, portanto, não é um subespaço.

---

### Exercício 15

**Enunciado:**  
Em \(\mathbb{R}^3\), determine o conjunto de soluções da equação  
\[
x+y+z=0
\]
e mostre que ele é um subespaço.

**Solução Detalhada:**
1. Seja \(S=\{(x,y,z)\in\mathbb{R}^3 : x+y+z=0\}\).
2. **Vetor zero:**  
   - \(0+0+0=0\) ⇒ \((0,0,0)\in S\).
3. **Soma:**  
   - Se \((x_1,y_1,z_1)\) e \((x_2,y_2,z_2)\) estão em \(S\), então  
     \[
     (x_1+x_2)+(y_1+y_2)+(z_1+z_2)= (x_1+y_1+z_1)+(x_2+y_2+z_2)=0.
     \]
4. **Multiplicação por escalar:**  
   - Para \(c\in\mathbb{R}\), se \(x+y+z=0\) então \(c(x+y+z)=0\).
   
Portanto, \(S\) é um subespaço de \(\mathbb{R}^3\).

---

### Exercício 16

**Enunciado:**  
Encontre o kernel da transformação linear \(T: \mathbb{R}^3 \to \mathbb{R}\) definida por
\[
T(x,y,z)= x - y + 2z.
\]

**Solução Detalhada:**
1. Procure todos os \((x,y,z)\) tais que  
   \[
   x-y+2z=0.
   \]
2. Expressando \(x\) em função de \(y\) e \(z\), obtenha:
   \[
   x=y-2z.
   \]
3. Assim, o kernel é
   \[
   \text{ker}(T)=\{(y-2z,y,z) \mid y,z\in\mathbb{R}\} = \text{span}\{(1,1,0),\,(-2,0,1)\}.
   \]

---

### Exercício 17

**Enunciado:**  
Para a transformação linear \(T: \mathbb{R}^2 \to \mathbb{R}^2\) dada por
\[
T(x,y)=(2x+3y,\; 4x+6y),
\]
determine um conjunto gerador para a imagem de \(T\).

**Solução Detalhada:**
1. Observe que \(4x+6y=2(2x+3y)\).  
2. Assim, todo vetor \(T(x,y)\) tem a forma
   \[
   (s,2s), \quad \text{onde } s=2x+3y.
   \]
3. Portanto, a imagem de \(T\) é a reta
   \[
   \text{im}(T)=\text{span}\{(1,2)\}.
   \]

---

### Exercício 18

**Enunciado:**  
Verifique que o conjunto das matrizes simétricas de ordem 2 é um subespaço de \(M_{2 \times 2}(\mathbb{R})\).

**Solução Detalhada:**
1. Considere \(S=\{A\in M_{2 \times 2}(\mathbb{R}) \mid A = A^T\}\).
2. **Vetor zero:**  
   - A matriz nula é simétrica.
3. **Soma:**  
   - Se \(A=A^T\) e \(B=B^T\), então \((A+B)^T = A^T+B^T = A+B\).
4. **Multiplicação por escalar:**  
   - Para \(c\in\mathbb{R}\), \((cA)^T = cA^T = cA\).
   
Portanto, \(S\) é um subespaço de \(M_{2 \times 2}(\mathbb{R})\).

---

### Exercício 19

**Enunciado:**  
Seja \(V\) o espaço de funções contínuas definidas em \([0,1]\). Mostre que o conjunto
\[
U = \{f \in V \mid f(0)=0\}
\]
é um subespaço de \(V\).

**Solução Detalhada:**
1. **Vetor zero:**  
   - A função zero, \(f(x)=0\) para todo \(x\), satisfaz \(f(0)=0\).
2. **Soma:**  
   - Se \(f(0)=0\) e \(g(0)=0\), então \((f+g)(0)=f(0)+g(0)=0\).
3. **Multiplicação:**  
   - Para \(c\in\mathbb{R}\), \((cf)(0)=c\,f(0)=0\).
   
Logo, \(U\) é um subespaço de \(V\).

---

### Exercício 20

**Enunciado:**  
Dados os subespaços de \(\mathbb{R}^3\)
\[
W_1 = \{(x,y,z) \mid z = 0\} \quad \text{e} \quad W_2 = \{(x,y,z) \mid x = 0\},
\]
determine a soma \(W_1 + W_2\).

**Solução Detalhada:**
1. Qualquer vetor em \(W_1\) tem a forma \((x,y,0)\) e em \(W_2\) tem a forma \((0,y',z)\).
2. A soma é:
   \[
   (x,y,0) + (0,y',z) = (x, y+y', z).
   \]
3. Como \(x\), \(y+y'\) e \(z\) podem assumir quaisquer valores reais, temos:
   \[
   W_1+W_2=\mathbb{R}^3.
   \]

---

### Exercício 21

**Enunciado:**  
Mostre que o span de qualquer conjunto de vetores em um espaço vetorial é um subespaço desse espaço.

**Solução Detalhada:**
1. Seja \(S\) um conjunto de vetores e considere \(W=\text{span}(S)\).
2. Por definição, \(W\) consiste de todas as combinações lineares dos vetores de \(S\).
3. Como combinações lineares são fechadas sob adição e multiplicação por escalar, \(W\) satisfaz os axiomas de subespaço.
4. Portanto, \(\text{span}(S)\) é um subespaço.

---

### Exercício 22

**Enunciado:**  
Se um espaço vetorial \(V\) é gerado pelo conjunto \(\{v_1,v_2,v_3\}\) e os vetores \(v_1\) e \(v_2\) são linearmente independentes, enquanto \(v_3\) pode ser escrito como combinação linear de \(v_1\) e \(v_2\), mostre que \(\{v_1, v_2\}\) é uma base de \(V\).

**Solução Detalhada:**
1. Como \(v_3\) é combinação linear de \(v_1\) e \(v_2\), o span de \(\{v_1,v_2\}\) é o mesmo que o span de \(\{v_1,v_2,v_3\}\).
2. Se \(v_1\) e \(v_2\) são linearmente independentes, então \(\{v_1, v_2\}\) é um conjunto gerador minimal.
3. Portanto, \(\{v_1, v_2\}\) forma uma base para \(V\).

---

### Exercício 23

**Enunciado:**  
Seja \(T: \mathbb{R}^2 \to \mathbb{R}\) dada por
\[
T(x,y) = 3x - 2y.
\]
Encontre uma base para o kernel e determine a imagem de \(T\).

**Solução Detalhada:**
1. **Kernel:**  
   - Procure \((x,y)\) tais que \(3x-2y=0\).  
   - Resolva: \(y=\frac{3}{2}x\).  
   - Assim, \(\text{ker}(T)=\{(x,\frac{3}{2}x) \mid x\in\mathbb{R}\}=\text{span}\{(2,3)\}\) (após ajuste de escala).
2. **Imagem:**  
   - Como \(T(x,y)\) é um número real e existe \((x,y)\) para qualquer valor de \(3x-2y\), temos \(\text{im}(T)=\mathbb{R}\).

---

### Exercício 24

**Enunciado:**  
Mostre que, se \(U\) é um subespaço de um espaço vetorial \(V\), então para todo \(u\in U\) o vetor \(-u\) também pertence a \(U\).

**Solução Detalhada:**
1. Pela propriedade de fechamento de multiplicação por escalar, para qualquer \(c\in\mathbb{R}\) e \(u\in U\), \(c\,u\in U\).
2. Escolhendo \(c=-1\), temos \(-u\in U\).

---

### Exercício 25

**Enunciado:**  
Verifique se o conjunto de soluções da equação  
\[
2x + 3y = 0
\]
em \(\mathbb{R}^2\) é um subespaço.

**Solução Detalhada:**
1. Seja \(S=\{(x,y)\in\mathbb{R}^2 : 2x+3y=0\}\).
2. **Vetor zero:**  
   - \(2(0)+3(0)=0\) ⇒ \((0,0)\in S\).
3. **Fechamento sob adição:**  
   - Se \((x_1,y_1)\) e \((x_2,y_2)\) satisfazem \(2x+3y=0\), então  
     \[
     2(x_1+x_2)+3(y_1+y_2)= (2x_1+3y_1)+(2x_2+3y_2)=0.
     \]
4. **Fechamento sob multiplicação:**  
   - Para \(c\in\mathbb{R}\), se \(2x+3y=0\), então \(2(cx)+3(cy)=c(2x+3y)=0\).
   
Logo, \(S\) é um subespaço de \(\mathbb{R}^2\).

---

### Exercício 26

**Enunciado:**  
Seja \(F=\{f:\mathbb{R}\to\mathbb{R}\}\), o espaço de todas as funções reais. Mostre que o conjunto  
\[
U= \{f\in F \mid f(1)=0\}
\]
é um subespaço de \(F\).

**Solução Detalhada:**
1. **Vetor zero:**  
   - A função \(f(x)=0\) satisfaz \(f(1)=0\).
2. **Fechamento sob adição:**  
   - Se \(f(1)=0\) e \(g(1)=0\), então \((f+g)(1)=f(1)+g(1)=0\).
3. **Fechamento sob multiplicação:**  
   - Para \(c\in\mathbb{R}\), \((cf)(1)=c\cdot f(1)=0\).

Portanto, \(U\) é um subespaço de \(F\).

---

### Exercício 27

**Enunciado:**  
Seja  
\[
S = \{(x,y,z) \in \mathbb{R}^3: 2x - y + 3z = 0\}.
\]
Verifique se \(S\) é um subespaço de \(\mathbb{R}^3\).

**Solução Detalhada:**
1. **Vetor zero:**  
   - \(2(0)-0+3(0)=0\) ⇒ \((0,0,0)\in S\).
2. **Fechamento sob adição:**  
   - Se \((x_1,y_1,z_1)\) e \((x_2,y_2,z_2)\) satisfazem a equação, então  
     \[
     2(x_1+x_2)-(y_1+y_2)+3(z_1+z_2)=0.
     \]
3. **Fechamento sob multiplicação:**  
   - Para \(c\in\mathbb{R}\), se \(2x-y+3z=0\), então \(2(cx)-c y+3(cz)= c(2x-y+3z)=0\).

Logo, \(S\) é um subespaço de \(\mathbb{R}^3\).

---

### Exercício 28

**Enunciado:**  
Para a transformação linear \(T: \mathbb{R}^3 \to \mathbb{R}^3\) definida por
\[
T(x,y,z) = (x,\, 0,\, z),
\]
determine o kernel e a imagem de \(T\).

**Solução Detalhada:**
1. **Kernel:**  
   - Precisamos de \(T(x,y,z)=(0,0,0)\); isto é,  
     \[
     x=0 \quad \text{e} \quad z=0.
     \]
     O valor de \(y\) não influencia, logo:
     \[
     \text{ker}(T)=\{(0,y,0) \mid y\in\mathbb{R}\}.
     \]
2. **Imagem:**  
   - Para qualquer \((x, y, z)\), \(T(x,y,z)=(x,0,z)\).  
   - Assim, \(\text{im}(T)=\{(x,0,z) \mid x,z\in\mathbb{R}\}\), que é um subespaço isomorfo a \(\mathbb{R}^2\).

---

### Exercício 29

**Enunciado:**  
No espaço dos polinômios de grau no máximo 3, identifique um conjunto gerador.

**Solução Detalhada:**
1. Um polinômio \(p(x)\in P_3\) tem a forma:
   \[
   p(x)=a_0+a_1x+a_2x^2+a_3x^3,\quad a_i\in\mathbb{R}.
   \]
2. Assim, o conjunto
   \[
   \{1,\; x,\; x^2,\; x^3\}
   \]
   gera \(P_3\) pois qualquer polinômio de grau ≤3 pode ser escrito como combinação linear desses elementos.

---

### Exercício 30

**Enunciado:**  
Sejam
\[
U = \{(x,0,0): x\in\mathbb{R}\} \quad \text{e} \quad W = \{(0,y,z): y,z\in\mathbb{R}\},
\]
subespaços de \(\mathbb{R}^3\). Mostre que a soma \(U + W\) é um subespaço de \(\mathbb{R}^3\) e determine sua forma.

**Solução Detalhada:**
1. Um elemento de \(U\) é da forma \((x,0,0)\) e de \(W\) é \((0,y,z)\).
2. A soma é:
   \[
   (x,0,0)+(0,y,z)=(x,y,z).
   \]
3. Assim, \(U+W=\{(x,y,z)\mid x,y,z\in\mathbb{R}\}=\mathbb{R}^3\), o que é obviamente um subespaço de \(\mathbb{R}^3\).

---

## 9. Bibliografia

- **Vídeo Aula:**  
  **Título:** _Geometria Analítica e Álgebra Linear – Espaços Vetoriais_  
  **Instituição:** UNIVESP (Universidade Virtual do Estado de São Paulo)  
  **Link:** [https://www.youtube.com/watch?v=NmU4554VkmE&t=1s](https://www.youtube.com/watch?v=NmU4554VkmE&t=1s)  
  **Data de acesso:** 18 de maio de 2025

- **Livro:**  
  **Título:** _Álgebra Linear_  
  **Autor:** W. Keith Nicholson

- **Fontes Complementares na Web:**  
  Recursos de instituições reconhecidas, como Khan Academy, MIT OpenCourseWare e Wolfram MathWorld, podem ser consultados para aprofundamento dos conceitos abordados.

---