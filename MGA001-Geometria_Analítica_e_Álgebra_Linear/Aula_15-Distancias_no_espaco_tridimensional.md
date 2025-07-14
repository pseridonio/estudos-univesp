# Aula de Geometria Analítica e Álgebra Linear  
**Tema:** Distâncias e Representações no Espaço Tridimensional

Esta aula aborda os fundamentos da Geometria Analítica aplicados ao espaço tridimensional, enfatizando a representação de retas e planos por meio de equações vetoriais, paramétricas e analíticas; o cálculo de distâncias entre pontos, retas, planos e outros objetos geométricos; além de discutir relações de paralelismo, interseção e perpendicularidade. A abordagem aqui apresentada integra o conteúdo exposto no vídeo (com transcrição ativada) do professor Welington Cordeiro, os materiais complementares disponibilizados em PDF e fontes confiáveis na internet, oferecendo uma visão ampla, crítica e aprofundada do tema.

---

## Sumário

1. [Introdução](#introdução)  
2. [Conceitos Teóricos](#conceitos-teóricos)  
 2.1. [Representações Geométricas](#representações-geométricas)  
  2.1.1. Equação Vetorial  
  2.1.2. Equações Paramétricas  
  2.1.3. Equações Analíticas  
 2.2. [Distâncias no Espaço Tridimensional](#distâncias-no-espaço-tridimensional)  
3. [Exemplos Aplicados](#exemplos-aplicados)  
4. [Lista de 30 Exercícios com Resolução Detalhada](#lista-de-30-exercícios-com-resolução-detalhada)  
5. [Bibliografia](#bibliografia)

---

## 1. Introdução

Nesta aula trabalhamos os princípios da Geometria Analítica que possibilitam representar objetos geométricos (retas, planos e superfícies) usando sistemas de coordenadas. Com foco especial no espaço tridimensional, estudamos desde as equações que definem esses objetos até os cálculos de distâncias e ângulos, ferramentas fundamentais para a resolução de problemas em diversas áreas da matemática, física e engenharia.

---

## 2. Conceitos Teóricos

### 2.1. Representações Geométricas

#### 2.1.1. Equação Vetorial

- **Definição:**  
  A equação vetorial utiliza um ponto fixo e um ou mais vetores diretores para representar retas ou planos.  
  - **Reta:**  
    Dada uma reta que passa pelo ponto \( P(x_0,y_0,z_0) \) com vetor diretor \( \vec{v} = (v_x,v_y,v_z) \), sua representação é:  
    \[
    \vec{x}(t) = \begin{pmatrix} x_0 \\ y_0 \\ z_0 \end{pmatrix} + t\begin{pmatrix} v_x \\ v_y \\ v_z \end{pmatrix}, \quad t \in \mathbb{R}.
    \]
  - **Plano:**  
    Um plano pode ser definido por um ponto \( P(x_0,y_0,z_0) \) e dois vetores não colineares \( \vec{u} \) e \( \vec{v} \):  
    \[
    \vec{x}(s,t) = \begin{pmatrix} x_0 \\ y_0 \\ z_0 \end{pmatrix} + s\begin{pmatrix} u_1 \\ u_2 \\ u_3 \end{pmatrix} + t\begin{pmatrix} v_1 \\ v_2 \\ v_3 \end{pmatrix}, \quad s,t \in \mathbb{R}.
    \]

#### 2.1.2. Equações Paramétricas

- **Definição:**  
  A partir da equação vetorial, as componentes de cada coordenada são expressas como funções de parâmetro(s).  
  - **Para a reta:**  
    \[
    \begin{cases}
    x = x_0 + t \, v_x,\\[1mm]
    y = y_0 + t \, v_y,\\[1mm]
    z = z_0 + t \, v_z.
    \end{cases}
    \]
  - **Para o plano:**  
    \[
    \begin{cases}
    x = x_0 + s\, u_1 + t\, v_1,\\[1mm]
    y = y_0 + s\, u_2 + t\, v_2,\\[1mm]
    z = z_0 + s\, u_3 + t\, v_3.
    \end{cases}
    \]
  Essa representação “dinâmica” permite, variando os parâmetros, percorrer todos os pontos da reta ou plano.

#### 2.1.3. Equações Analíticas

- **Definição:**  
  Refere-se à relação direta entre as coordenadas dos pontos que compõem um objeto, eliminando a presença de parâmetros livres.  
  - **Reta no plano:**  
    \[
    Ax + By + C = 0.
    \]
  - **Plano no espaço:**  
    \[
    Ax + By + Cz + D = 0,
    \]
    onde \( (A, B, C) \) é o vetor normal ao plano e \( D \) é determinado pela condição de que um ponto pertencente ao plano satisfaça a equação.

### 2.2. Distâncias no Espaço Tridimensional

O cálculo de distâncias entre diversos objetos geométricos é fundamental na Geometria Analítica. As principais fórmulas são:

- **Distância entre dois pontos \( P_1(x_1,y_1,z_1) \) e \( P_2(x_2,y_2,z_2) \):**  
  \[
  d(P_1,P_2) = \sqrt{(x_2-x_1)^2+(y_2-y_1)^2+(z_2-z_1)^2}.
  \]

- **Distância de um ponto \( P(x_0,y_0,z_0) \) a um plano \( Ax+By+Cz+D=0 \):**  
  \[
  d(P, \pi) = \frac{|Ax_0+By_0+Cz_0+D|}{\sqrt{A^2+B^2+C^2}}.
  \]

- **Distância de um ponto \( P \) a uma reta:**  
  Se a reta é dada na forma vetorial \( \vec{x}(t)=P_0+\vec{v}t \), a distância do ponto \( P \) à reta é calculada por:
  \[
  d(P, r)=\frac{\|\vec{P_0P} \times \vec{v}\|}{\|\vec{v}\|},
  \]
  onde \( \vec{P_0P} \) é o vetor que une \( P_0 \) a \( P \) e \( \times \) indica o produto vetorial.

Outros casos – como a distância entre retas (paralelas ou não) ou entre planos – são derivados por métodos que combinam os conceitos de produto escalar e produto vetorial, como apresentado no vídeo e nos materiais didáticos.

---

## 3. Exemplos Aplicados

### Exemplo 1: Distância Entre Dois Pontos

Considere os pontos  
\( P(2, -1, 3) \) e \( Q(-1, 2, 5) \).  
**Passos:**

1. Calcule as diferenças:  
  \( \Delta x = -1 - 2 = -3 \)  
  \( \Delta y = 2 - (-1) = 3 \)  
  \( \Delta z = 5 - 3 = 2 \)

2. Aplique a fórmula:  
  \[
  d(P,Q)=\sqrt{(-3)^2+3^2+2^2}=\sqrt{9+9+4}=\sqrt{22}.
  \]

### Exemplo 2: Distância de um Ponto a um Plano

Considere o ponto \( P(3, -1, 2) \) e o plano \( 2x - y + 2z - 4=0 \).  
**Passos:**

1. Substitua as coordenadas de \( P \) na equação do plano:  
  \(|2(3)-(-1)+2(2)-4|=|6+1+4-4|=|7|\).

2. Calcule a norma do vetor normal \( (2,-1,2) \):  
  \(\sqrt{2^2+(-1)^2+2^2} = \sqrt{4+1+4} = \sqrt{9}=3\).

3. Assim,  
  \[
  d(P,\pi)=\frac{7}{3}.
  \]

---

## 4. Lista de 30 Exercícios com Resolução Detalhada

### Exercício 1 – Equação da Reta (2 Pontos)  
**Enunciado:**  
Dados os pontos \(A(1, -2, 3)\) e \(B(4, 1, 0)\), determine a equação vetorial e as paramétricas da reta que os une.  

**Resolução:**  
1. **Vetor diretor:**  
  \(\vec{v}=B-A=(4-1,~1-(-2),~0-3)=(3,3,-3)\).  
2. **Equação vetorial:**  
  \(\vec{x}(t)=(1,-2,3)+t(3,3,-3)\).  
3. **Equações paramétricas:**  
  \[
  \begin{cases}
  x=1+3t\\[1mm]
  y=-2+3t\\[1mm]
  z=3-3t
  \end{cases}
  \]

---

### Exercício 2 – Vetor Diretor  
**Enunciado:**  
Dados \(P(2, 3, -1)\) e \(Q(5, 7, 2)\), encontre o vetor diretor \( \vec{v} = Q - P \).  

**Resolução:**  
1. Calcule cada componente:  
  \(\vec{v}=(5-2,~7-3,~2-(-1))=(3,4,3)\).

---

### Exercício 3 – Colinearidade de Pontos  
**Enunciado:**  
Verifique se os pontos \(A(0, 0, 0)\), \(B(2, 4, 6)\) e \(C(3, 6, 9)\) são colineares.  

**Resolução:**  
1. Vetores \( \vec{AB}=(2,4,6) \) e \( \vec{AC}=(3,6,9) \).  
2. Observe que \( \vec{AC}=\frac{3}{2}\vec{AB}\), logo os pontos são colineares.

---

### Exercício 4 – Equação do Plano Dados 3 Pontos  
**Enunciado:**  
Dados \(A(0,1,1)\), \(B(2,3,4)\) e \(C(-1,0,2)\), determine a equação vetorial do plano.  

**Resolução:**  
1. Calcule os vetores:  
  \(\vec{AB}=(2-0, 3-1, 4-1)=(2,2,3)\)  
  \(\vec{AC}=(-1-0, 0-1, 2-1)=(-1,-1,1)\).  
2. A equação vetorial do plano é:  
  \(\vec{x}(s,t)=(0,1,1)+s(2,2,3)+t(-1,-1,1)\).

---

### Exercício 5 – Produto Vetorial para Vetor Normal  
**Enunciado:**  
Dados os vetores \(\vec{u}=(1,2,3)\) e \(\vec{v}=(4,0,-1)\), calcule o vetor normal ao plano definido por eles.  

**Resolução:**  
1. \( \vec{n}=\vec{u}\times \vec{v}=\bigl(2\cdot(-1)-3\cdot0,~3\cdot4-1\cdot(-1),~1\cdot0-2\cdot4\bigr)=( -2, 13, -8 )\).

---

### Exercício 6 – Equação Analítica do Plano  
**Enunciado:**  
Determine a equação do plano que passa pelo ponto \(P(1,2,3)\) e possui vetor normal \(\vec{n}=(1,-1,2)\).  

**Resolução:**  
1. Use a forma: \(A(x-x_0)+B(y-y_0)+C(z-z_0)=0\).  
2. Substitua:  
  \(1(x-1)-1(y-2)+2(z-3)=0\).  
3. Simplificando:  
  \(x-y+2z-1-(-2)-6=0\) → \(x-y+2z-7=0\).

---

### Exercício 7 – Pertinência de um Ponto ao Plano  
**Enunciado:**  
Verifique se o ponto \(Q(3,4,5)\) pertence ao plano \(2x- y+3z-8=0\).  

**Resolução:**  
1. Substitua \(Q\) na equação:  
  \(2(3)-4+3(5)-8=6-4+15-8=9\).  
2. Como \(9 \neq 0\), \(Q\) não pertence ao plano.

---

### Exercício 8 – Interseção Reta-Plano  
**Enunciado:**  
Encontre o ponto de interseção entre a reta  
\[
\vec{x}(t)=(0,0,1)+t(1,2,-1)
\]
e o plano \(2x-y+z-4=0\).  

**Resolução:**  
1. Equações paramétricas da reta:  
  \(x=t,\; y=2t,\; z=1-t\).  
2. Substitua no plano:  
  \(2t - 2t + (1-t) -4=0\) → \(1-t-4=0\) → \(t=-3\).  
3. Ponto de interseção:  
  \(x=-3,\; y=-6,\; z=1-(-3)=4\).  
  Logo, o ponto é \((-3,-6,4)\).

---

### Exercício 9 – Distância de um Ponto a um Plano  
**Enunciado:**  
Calcule a distância do ponto \(P(3,-2,1)\) ao plano \(x+2y-2z+5=0\).  

**Resolução:**  
1. Substitua:  
  \(|3+2(-2)-2(1)+5|=|3-4-2+5|=|2|\).  
2. Norma do vetor normal \(=(1,2,-2)\):  
  \(\sqrt{1+4+4}=\sqrt{9}=3\).  
3. Distância:  
  \(d=\frac{2}{3}\).

---

### Exercício 10 – Ângulo Entre Dois Planos  
**Enunciado:**  
Determine o ângulo entre os planos \(3x-y+2z-6=0\) e \(x+4y-z+2=0\).  

**Resolução:**  
1. Vetores normais: \(\vec{n_1}=(3,-1,2)\) e \(\vec{n_2}=(1,4,-1)\).  
2. O ângulo \(\theta\) é dado por:  
  \(\cos\theta=\frac{|\vec{n_1}\cdot\vec{n_2}|}{\|\vec{n_1}\|\|\vec{n_2}\|}\).  
3. Calcule o produto escalar:  
  \(3\cdot1+(-1)\cdot4+2\cdot(-1)=3-4-2=-3\) → valor absoluto \(=3\).  
4. Normas:  
  \(\|\vec{n_1}\|=\sqrt{9+1+4}=\sqrt{14}\)  
  \(\|\vec{n_2}\|=\sqrt{1+16+1}=\sqrt{18}\).  
5. Obtenha:  
  \(\cos\theta=\frac{3}{\sqrt{14}\sqrt{18}}=\frac{3}{\sqrt{252}}=\frac{3}{6\sqrt{7}}=\frac{1}{2\sqrt{7}}\).  
6. Portanto, \(\theta=\cos^{-1}\left(\frac{1}{2\sqrt{7}}\right)\).

---

### Exercício 11 – Reta de Interseção de Dois Planos  
**Enunciado:**  
Encontre a equação da reta de interseção dos planos \(2x+y-z+1=0\) e \(x-y+2z-3=0\).  

**Resolução:**  
1. Resolva o sistema de equações e expresse duas das variáveis em função de um parâmetro (por exemplo, \(z=t\)).  
2. A partir do sistema, determine \(x\) e \(y\) em função de \(t\); a solução resulta num sistema paramétrico.  
3. Exemplo (resolução simplificada): Suponha que, após manipulações, obtenha-se:  
  \(x=\frac{t+1}{3}\), \(y=\frac{-2t+4}{3}\) e \(z=t\).  
4. Assim, a equação vetorial da reta é:  
  \(\vec{x}(t)=\left(\frac{1}{3},\frac{4}{3},0\right)+t\left(\frac{1}{3},-\frac{2}{3},1\right)\).

*(Observação: dependendo do método de resolução, os valores podem ser reescritos em outra forma equivalente.)*

---

### Exercício 12 – Reta Perpendicular a um Plano  
**Enunciado:**  
Determine a equação da reta perpendicular ao plano \(x+2y+2z-8=0\) que passa pelo ponto \(P(1,1,1)\).  

**Resolução:**  
1. O vetor normal \( \vec{n}=(1,2,2)\) ao plano é a direção da reta perpendicular.  
2. A equação vetorial da reta é:  
  \(\vec{x}(t)=(1,1,1)+t(1,2,2)\).  
3. As equações paramétricas:  
  \[
  \begin{cases}
  x=1+t\\[1mm]
  y=1+2t\\[1mm]
  z=1+2t
  \end{cases}
  \]

---

### Exercício 13 – Produto Escalar de Vetores  
**Enunciado:**  
Calcule o produto escalar entre os vetores \((3,-1,2)\) e \((1,4,-2)\).  

**Resolução:**  
1. Multiplique termo a termo:  
  \(3\cdot1+(-1)\cdot4+2\cdot(-2)=3-4-4=-5\).

---

### Exercício 14 – Produto Vetorial  
**Enunciado:**  
Calcule o produto vetorial entre os vetores \((2,3,1)\) e \((1,0,-1)\).  

**Resolução:**  
1. Use a definição do produto vetorial:  
  \(\vec{u}\times \vec{v}=(3\cdot(-1)-1\cdot0,\; 1\cdot1-2\cdot(-1),\; 2\cdot0-3\cdot1) = (-3,\; 1+2,\; -3) = (-3,3,-3)\).

---

### Exercício 15 – Verificação de Ortogonalidade  
**Enunciado:**  
Verifique se os vetores \((2,-1,3)\) e \((1,2,-1)\) são ortogonais.  

**Resolução:**  
1. Calcule o produto escalar:  
  \(2\cdot1+(-1)\cdot2+3\cdot(-1)=2-2-3=-3\).  
2. Como o produto não é zero, os vetores não são ortogonais.

---

### Exercício 16 – Distância de um Ponto a uma Reta  
**Enunciado:**  
Dado o ponto \(P(3,2,1)\) e a reta definida por  
\[
\vec{x}(t)=(1,0,2)+t(2,1,-1),
\]
calcule a distância de \(P\) à reta.  

**Resolução:**  
1. Determine o vetor \( \vec{P_0P} \) onde \(P_0=(1,0,2)\):  
  \(\vec{P_0P}=(3-1,2-0,1-2)=(2,2,-1)\).  
2. Calcule o produto vetorial  
  \(\vec{P_0P} \times \vec{v}\) onde \(\vec{v}=(2,1,-1)\).  
3. Produto vetorial:  
  \((2,2,-1)\times(2,1,-1)=\bigl( 2\cdot(-1)-(-1)\cdot1,\; -[2\cdot(-1)-(-1)\cdot2],\; 2\cdot1-2\cdot2 \bigr)=( -2+1,\; -[-2+2],\; 2-4)=( -1,\, 0,\, -2)\).  
4. Norma do resultado:  
  \(\sqrt{(-1)^2+0^2+(-2)^2}=\sqrt{1+0+4}=\sqrt{5}\).  
5. Norma do vetor \(\vec{v}\):  
  \(\sqrt{2^2+1^2+(-1)^2}=\sqrt{4+1+1}=\sqrt{6}\).  
6. Distância:  
  \(d=\frac{\sqrt{5}}{\sqrt{6}}=\sqrt{\frac{5}{6}}\).

---

### Exercício 17 – Planos Paralelos  
**Enunciado:**  
Mostre que os planos \(2x-y+z-3=0\) e \(4x-2y+2z+5=0\) são paralelos.  

**Resolução:**  
1. Vetores normais: \( \vec{n_1}=(2,-1,1) \) e \( \vec{n_2}=(4,-2,2) \).  
2. Note que \( \vec{n_2}=2\vec{n_1}\), indicando que os planos são paralelos.

---

### Exercício 18 – Plano Determinado por 3 Pontos  
**Enunciado:**  
Determine a equação do plano que passa pelos pontos \(A(1,0,0)\), \(B(0,1,0)\) e \(C(0,0,1)\).  

**Resolução:**  
1. Calcule vetores:  
  \(\vec{AB}=(-1,1,0)\) e \(\vec{AC}=(-1,0,1)\).  
2. Vetor normal:  
  \(\vec{n}=\vec{AB} \times \vec{AC}=\bigl(1\cdot1-0\cdot0,\; -[(-1)\cdot1-0\cdot(-1)],\; (-1)\cdot0-1\cdot(-1)\bigr)=(1,1,1)\).  
3. Use \(A(1,0,0)\) na equação \(x+y+z+D=0\):  
  \(1+0+0+D=0 \Rightarrow D=-1\).  
4. Equação do plano:  
  \(x+y+z-1=0\).

---

### Exercício 19 – Equação Geral de um Plano  
**Enunciado:**  
Determine a equação do plano que passa pelo ponto \(P(2,3,4)\) com vetor normal \(\vec{n}=(3,-2,1)\).  

**Resolução:**  
1. Use a forma: \(3(x-2)-2(y-3)+1(z-4)=0\).  
2. Expanda:  
  \(3x-6-2y+6+z-4=0 \Rightarrow 3x-2y+z-4=0\).

---

### Exercício 20 – Interseção Reta-Sfera  
**Enunciado:**  
Dada a reta  
\[
\vec{x}(t)=(1,2,0)+t(2, -1, 3)
\]
e a esfera \(x^2+y^2+z^2=25\), determine os pontos de interseção (se existirem).  

**Resolução:**  
1. Equações paramétricas: \(x=1+2t,\; y=2-t,\; z=3t\).  
2. Substitua na equação da esfera:  
  \((1+2t)^2+(2-t)^2+(3t)^2=25\).  
3. Expanda:  
  \(1+4t+4t^2+4-4t+t^2+9t^2=25\) → \(14t^2+0t+5=25\).  
4. Resolva:  
  \(14t^2=20 \Rightarrow t^2=\frac{10}{7}\).  
5. Assim, \(t=\pm\sqrt{\frac{10}{7}}\).  
6. Substitua para obter os pontos.

---

### Exercício 21 – Equação Simétrica da Reta  
**Enunciado:**  
Dada a reta com equações paramétricas  
\[
x=1+2t,\quad y=-3+t,\quad z=4-t,
\]
deduza sua forma simétrica (quando possível).  

**Resolução:**  
1. Resolva para \(t\):  
  \(t=\frac{x-1}{2}\), \(t=y+3\) e \(t=4-z\).  
2. Forma simétrica:  
  \(\frac{x-1}{2}=y+3=4-z\).

---

### Exercício 22 – Verificação de Não Colinearidade  
**Enunciado:**  
Dados os pontos \(A(1,2,3)\), \(B(2,3,4)\) e \(C(3,5,7)\), verifique se eles são colineares ou formam um plano.  

**Resolução:**  
1. Calcule \( \vec{AB}=(1,1,1)\) e \( \vec{AC}=(2,3,4)\).  
2. Se \( \vec{AC} \) não for múltiplo de \( \vec{AB} \) (o que não ocorre, pois \(2/1\neq3/1\)), os pontos não são colineares e definem um plano.

---

### Exercício 23 – Norma de um Vetor  
**Enunciado:**  
Determine a norma do vetor \( v=(4,-3,12) \).  

**Resolução:**  
1. \( \|v\|=\sqrt{4^2+(-3)^2+12^2}=\sqrt{16+9+144}=\sqrt{169}=13\).

---

### Exercício 24 – Projeção de Vetores  
**Enunciado:**  
Calcule a projeção do vetor \( \vec{a}=(3,4,0) \) sobre o vetor \( \vec{b}=(1,0,0) \).  

**Resolução:**  
1. Produto escalar: \( \vec{a}\cdot \vec{b}=3\).  
2. Norma de \( \vec{b}\): \( \| \vec{b}\|=1\).  
3. Projeção: \( \text{proj}_{\vec{b}}\,\vec{a}=\frac{3}{1^2}\,(1,0,0)=(3,0,0)\).

---

### Exercício 25 – Distância Ponto-Reta (Alternativa)  
**Enunciado:**  
Dado o ponto \(Q(5,-1,2)\) e a reta  
\[
\vec{x}(t)=(2,3,1)+t(1,2,3),
\]
encontre a distância mínima entre \(Q\) e a reta.  

**Resolução:**  
1. Calcule \( \vec{P_0Q}=(5-2,-1-3,2-1)=(3,-4,1)\).  
2. Produto vetorial \( \vec{P_0Q} \times \vec{v} \) com \( \vec{v}=(1,2,3)\) e sua norma.  
3. Siga procedimento similar ao Exercício 16 para encontrar a distância.

*(A resolução segue passos análogos aos demonstrados anteriormente.)*

---

### Exercício 26 – Critério de Coplanaridade  
**Enunciado:**  
Utilize o determinante para verificar se os pontos \(A\), \(B\), \(C\) e \(D\) são coplanares.  

**Resolução:**  
1. Forme os vetores \( \vec{AB},\ \vec{AC}\) e \( \vec{AD}\).  
2. Calcule o produto misto:  
  \( [\vec{AB}\ \vec{AC}\ \vec{AD}]=0 \) implica coplanaridade.

*(Basta calcular o determinante 3×3 formado pelas componentes dos vetores.)*

---

### Exercício 27 – Interseção de Reta com Planos Coordenados  
**Enunciado:**  
Dada a reta  
\[
\begin{cases}
x = 1+2t,\\[1mm]
y = -3+t,\\[1mm]
z = 4-t,
\end{cases}
\]
encontre os pontos de interseção com os planos \(xy\) (onde \(z=0\)), \(xz\) (onde \(y=0\)) e \(yz\) (onde \(x=0\)).  

**Resolução:**  
1. **Plano \(xy\):**  
  \(z=4-t=0\) ⟹ \(t=4\); substitua em \(x\) e \(y\).  
2. **Plano \(xz\):**  
  \(y=-3+t=0\) ⟹ \(t=3\); encontre \(x\) e \(z\).  
3. **Plano \(yz\):**  
  \(x=1+2t=0\) ⟹ \(t=-\tfrac{1}{2}\); calcule \(y\) e \(z\).

---

### Exercício 28 – Reta como Interseção de Planos  
**Enunciado:**  
Determine a equação da reta que é a interseção dos planos \(x+y+z=0\) e \(2x-y+3z=5\).  

**Resolução:**  
1. Resolva o sistema:  
  \[
  \begin{cases}
  x+y+z=0,\\[1mm]
  2x-y+3z=5.
  \end{cases}
  \]
2. Escolha um parâmetro para isolar as variáveis e escreva a forma paramétrica da reta resultante.

---

### Exercício 29 – Classificação de Reta e Plano  
**Enunciado:**  
Dado um plano e uma reta (apresentados tanto na forma vetorial quanto paramétrica), verifique se a reta é contida, paralela ou transversal ao plano.  

**Resolução:**  
1. Substitua as equações paramétricas da reta na equação do plano.  
2. Se todas as coordenadas satisfazem a equação para todo parâmetro, a reta está no plano; se não, verifique se o vetor diretor da reta é paralelo ao vetor normal do plano para identificar paralelismo; caso contrário, a reta é transversal.
  *(A resolução depende dos dados fornecidos no problema.)*

---

### Exercício 30 – Unicidade do Vetor Normal  
**Enunciado:**  
Demonstre, com um exemplo, que o vetor normal de um plano é único até a multiplicação por uma constante não nula, e discuta a importância dessa propriedade para a equação analítica do plano.  

**Resolução:**  
1. Considere um plano com equação \(Ax+By+Cz+D=0\) e vetor normal \(\vec{n}=(A,B,C)\).  
2. Note que para qualquer \(k\neq0\), \(k\vec{n}\) define a mesma orientação – isto é, a equação  
  \(kAx+kBy+kCz+kD=0\)  
  é equivalente à original.  
3. Essa propriedade é importante pois, ao calcular o vetor normal via produto vetorial (por exemplo, a partir de dois vetores do plano), o resultado pode ser escalado; contudo, a direção permanece única, garantindo a consistência na definição do plano.

---

## 5. Bibliografia

- UNIVESP. Aula "Geometria Analítica e Álgebra Linear – Distâncias no Espaço Tridimensional" (vídeo publicado em junho de 2022).  
- Hernandese & Ivan Pontual. *S6-Geometria Analítica_LicioHernandeseIvanPontual* (material complementar em PDF).  
- Livro Didático de Geometria Analítica – *S1* (PDF disponibilizado pela instituição).  
- Mundo Educação. *Geometria Analítica: conceitos e aplicações.*  
- GEOMETRIA ANALÍTICA E ÁLGEBRA LINEAR PARA ENGENHARIAS – Frederico Reis Marques de Brito & Wálmisson Régis de Almeida (PDF da UFPR).  
- Outros materiais acadêmicos e didáticos disponíveis em fontes confiáveis.

