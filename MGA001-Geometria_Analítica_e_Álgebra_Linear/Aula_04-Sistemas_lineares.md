<!--
Para que as expressões LaTeX sejam renderizadas no GitHub Pages, adicione o seguinte código no cabeçalho (por exemplo, no arquivo de layout Jekyll):

<script type="text/javascript">
  window.MathJax = {
    tex: {
      inlineMath: [['$', '$'], ['\\(', '\\)']],
      displayMath: [['$$', '$$'], ['\\[', '\\]']]
    },
    svg: {fontCache: 'global'}
  };
</script>
<script type="text/javascript" async 
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.2/es5/tex-mml-chtml.js">
</script>
-->

# Sistemas de Equações Lineares

Este documento reúne os conteúdos essenciais sobre sistemas de equações lineares, combinando os tópicos apresentados no vídeo “Geometria Analítica e Álgebra Linear – Sistemas e Equações Lineares” da UNIVESP com as informações complementares do Capítulo 2 do livro de Doherty Andrade e Jorge Ferreira de Lacerda, além de pontos adicionais relevantes para uma compreensão completa do assunto.

---

## 1. Introdução

- **Contexto:**  
  Sistemas de equações lineares surgem em diversos problemas envolvendo múltiplas incógnitas e têm aplicações tanto na resolução de problemas práticos quanto na fundamentação teórica da álgebra linear.

- **Objetivos de Estudo:**  
  - Interpretar sistemas de equações de forma algébrica e geométrica.  
  - Representar os sistemas utilizando matrizes, notação de matriz aumentada e conceitos de rank.  
  - Resolver os sistemas por meio de operações elementares (eliminação de Gauss), métodos de retro-substituição e, quando aplicável, via inversão de matrizes.  
  - Utilizar o Teorema de Rouché–Capelli para identificar a consistência dos sistemas e compreender a estrutura das soluções (única, infinitas ou inexistentes).

---

## 2. Representação Geral do Sistema

- **Forma Geral:**  
  Um sistema de equações lineares pode ser expresso como:

  \[
  \begin{cases}
  a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n = b_1 \\
  a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n = b_2 \\
  \quad\vdots \\
  a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n = b_m
  \end{cases}
  \]

- **Classificação dos Sistemas:**  
  - **Sistema Possível e Determinado (SPD):** Solução única; geometricamente, as retas ou planos se interceptam num único ponto.  
  - **Sistema Possível e Indeterminado (SPI):** Infinitas soluções; ocorre quando há equivalência entre as equações (geometricamente, retas ou planos coincidentes).  
  - **Sistema Impossível (SI):** Sem solução; as equações representam retas ou planos paralelos que não se interceptam.

---

## 3. Representação Matricial

- **Forma Matricial:**  
  O sistema pode ser escrito de forma compacta como:

  \[
  A \cdot \mathbf{x} = \mathbf{b}
  \]

  onde:
  - **A** é a matriz dos coeficientes (\(m \times n\));
  - **\(\mathbf{x}\)** é o vetor coluna das incógnitas;
  - **\(\mathbf{b}\)** é o vetor dos termos independentes.

- **Matriz Aumentada:**  
  É comum utilizar a notação \([A \, | \, \mathbf{b}]\) para representar o sistema e facilitar a aplicação de operações elementares.

---

## 4. Abordagem Geométrica

- **Visualizações Gráficas:**  
  Com o auxílio de softwares (como o GeoGebra), pode-se identificar:
  - **Solução Única:** Interseção de retas (ou planos) em um único ponto;
  - **Infinitas Soluções:** Coincidência entre as equações (retas ou planos sobrepostos);
  - **Sem Solução:** Situações em que as retas ou planos são paralelos e não se interceptam.

---

## 5. Operações Elementares e Métodos de Resolução

### 5.1 Operações Elementares de Linha

São três operações fundamentais na matriz aumentada:
1. **Troca de Duas Linhas:** Reordena as equações para facilitar a escolha dos pivôs.
2. **Multiplicação de uma Linha por um Escalar Não-Nulo:** Normaliza o elemento pivô.
3. **Adição de um Múltiplo de uma Linha a Outra:** Zera os elementos abaixo (ou acima) do pivô, levando à forma escalonada.

### 5.2 Forma Escalonada e Forma Reduzida

- **Forma Escalonada:**  
  As linhas não nulas são dispostas de modo que o primeiro elemento não-zero (pivô) de cada linha esteja à direita do pivô da linha anterior.
  
- **Forma Reduzida:**  
  Cada pivô é igual a 1 e é o único elemento não-nulo em sua coluna, facilitando a identificação da solução.

### 5.3 Método de Eliminação de Gauss

- **Procedimento:**
  1. Construir a matriz aumentada \([A \,|\, \mathbf{b}]\).
  2. Aplicar operações elementares para transformá-la na forma escalonada.
  3. Utilizar retro-substituição para encontrar a solução (quando o sistema é possivelmente determinado).

---

## 6. Conceitos Complementares

### 6.1 Teorema de Rouché–Capelli e Rank da Matriz

- **Rank da Matriz:**  
  O rank é o número máximo de linhas (ou colunas) linearmente independentes em \(A\).
  
- **Teorema de Rouché–Capelli:**  
  O sistema é consistente (possui pelo menos uma solução) se, e somente se, o rank da matriz dos coeficientes \(A\) for igual ao rank da matriz aumentada \([A \,|\, \mathbf{b}]\).
  
  - Se \( \text{rank}(A) = \text{rank}([A\,|\,\mathbf{b}]) = n\) (com \(n\) incógnitas), há solução única.
  - Se \( \text{rank}(A) = \text{rank}([A\,|\,\mathbf{b}]) < n\), existem infinitas soluções (parâmetros livres).
  - Se \( \text{rank}(A) \neq \text{rank}([A\,|\,\mathbf{b}])\), o sistema é inconsistente.

### 6.2 Sistemas Homogêneos

- **Definição:**  
  São sistemas da forma:
  
  \[
  A\mathbf{x} = \mathbf{0}
  \]
  
- **Características:**  
  - Possuem sempre a solução trivial \(\mathbf{x} = \mathbf{0}\).
  - Se o número de incógnitas for maior que o rank da matriz \(A\), há infinitas soluções.

### 6.3 Estrutura da Solução Geral

- **Solução Geral (no caso de sistemas indeterminados):**  
  A solução pode ser expressa como:
  
  \[
  \mathbf{x} = \mathbf{x}_p + \mathbf{x}_h
  \]
  
  onde:
  - \(\mathbf{x}_p\) é uma solução particular do sistema não homogêneo \(A\mathbf{x} = \mathbf{b}\);
  - \(\mathbf{x}_h\) é a solução geral do sistema homogêneo associado \(A\mathbf{x} = \mathbf{0}\).

### 6.4 Inversão de Matrizes

- **Conceito:**  
  Se \(A\) é uma matriz quadrada invertível (\(\det(A) \neq 0\)), então a solução única do sistema é dada por:
  
  \[
  \mathbf{x} = A^{-1} \cdot \mathbf{b}
  \]
  
- **Procedimento para Inversão:**  
  Um método clássico é formar a matriz aumentada \([A\, |\, I]\) e, por meio de operações elementares, transformá-la em \([I\, |\, A^{-1}]\).

---

## 7. Conclusão

Os sistemas de equações lineares são ferramentas essenciais em diversas áreas da matemática, engenharia e ciências aplicadas. O estudo detalhado das representações matriciais, operações elementares, análise de consistência (usando o Teorema de Rouché–Capelli) e o método de eliminação de Gauss proporciona uma base sólida para o avanço em temas mais complexos e aplicações computacionais.

---

## 8. Bibliografia

- **Vídeo:**  
  [Geometria Analítica e Álgebra Linear – Sistemas e Equações Lineares](https://www.youtube.com/watch?v=0kquQZdajk8)  
  UNIVESP – Professor Welington Cordeiro.

- **Livro:**  
  Doherty Andrade & Jorge Ferreira de Lacerda. *Geometria Analítica*. 2ª Edição, 2010.  
  Universidade Federal de Santa Catarina/CFM/CED/UFSC.

- **Material Complementar:**  
  Plataforma UNIVESP AVA – [Conteúdo do Curso](https://ava.univesp.br).

---

## 9. Exercícios

A seguir, são apresentados 30 enunciados de exercícios que abordam os temas deste documento:

1. **Exercício 1:**  
   Represente o sistema abaixo em forma matricial e escreva sua matriz aumentada:  
   &nbsp;&nbsp;&nbsp;&nbsp; \( x + 2y = 5 \)  
   &nbsp;&nbsp;&nbsp;&nbsp; \( 3x - y = 4 \)

2. **Exercício 2:**  
   Resolva o sistema do Exercício 1 e determine a solução única.

3. **Exercício 3:**  
   Considere o sistema de três equações:  
   &nbsp;&nbsp;&nbsp;&nbsp; \( x - y + z = 2 \)  
   &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + y - z = 3 \)  
   &nbsp;&nbsp;&nbsp;&nbsp; \( x + y + 2z = 5 \)  
   Escreva a matriz aumentada e resolva o sistema.

4. **Exercício 4:**  
   Utilize o Teorema de Rouché–Capelli para verificar a consistência do seguinte sistema:  
   &nbsp;&nbsp;&nbsp;&nbsp; \( x + y = 2 \)  
   &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + 2y = 5 \)

5. **Exercício 5:**  
   Resolva o sistema homogêneo:  
   &nbsp;&nbsp;&nbsp;&nbsp; \( x - 2y + 3z = 0 \)  
   &nbsp;&nbsp;&nbsp;&nbsp; \( 4x - 8y + 12z = 0 \)

6. **Exercício 6:**  
   Verifique se a matriz \( A = \begin{bmatrix} 1 & 3 \\ 2 & 6 \end{bmatrix} \) é invertível e justifique sua resposta.

7. **Exercício 7:**  
   Determine a solução geral do sistema:  
   &nbsp;&nbsp;&nbsp;&nbsp; \( x + y + z = 6 \)  
   &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + 2y + 2z = 12 \)  
   &nbsp;&nbsp;&nbsp;&nbsp; \( 3x + 3y + 3z = 18 \)

8. **Exercício 8:**  
   Utilize o método da eliminação para resolver o sistema:  
   &nbsp;&nbsp;&nbsp;&nbsp; \( x + y = 4 \)  
   &nbsp;&nbsp;&nbsp;&nbsp; \( x - y = 2 \)

9. **Exercício 9:**  
   Calcule a inversa da matriz \( A = \begin{bmatrix} 2 & 3 \\ 1 & 4 \end{bmatrix} \).

10. **Exercício 10:**  
    Determine o tipo de solução (única, infinitas ou inexistente) para o sistema:  
    &nbsp;&nbsp;&nbsp;&nbsp; \( x + y + z = 3 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( x - 2y + z = 0 \)

11. **Exercício 11:**  
    Resolva o sistema:  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + 3y - z = 5 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 4x + 6y - 2z = 10 \)

12. **Exercício 12:**  
    Expresse em forma paramétrica a solução do sistema:  
    &nbsp;&nbsp;&nbsp;&nbsp; \( x + y - z = 2 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + 2y - 2z = 4 \)

13. **Exercício 13:**  
    Apresente a representação matricial (coeficientes e matriz aumentada) do sistema:  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 3x - y = 7 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( -x + 4y = 3 \)

14. **Exercício 14:**  
    Para o sistema:  
    &nbsp;&nbsp;&nbsp;&nbsp; \( x + 2y + 3z = 1 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + 4y + 6z = 2 \)  
    determine a solução geral.

15. **Exercício 15:**  
    Resolva o sistema utilizando o método de eliminação de Gauss:  
    &nbsp;&nbsp;&nbsp;&nbsp; \( x - y + z = 3 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + y + z = 5 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( -x + 3y - 2z = -1 \)

16. **Exercício 16:**  
    Dada a matriz aumentada já na forma escalonada:

    \[
    \begin{bmatrix}
    1 & 2 & -1 & | & 1 \\
    0 & 3 & 2 & | & 4 \\
    0 & 0 & 5 & | & 10
    \end{bmatrix}
    \]
    
    Utilize a retro-substituição para encontrar \( x \), \( y \) e \( z \).

17. **Exercício 17:**  
    Analise o sistema de 3 equações em 3 incógnitas a seguir e determine se a solução é única:
    &nbsp;&nbsp;&nbsp;&nbsp; \( x + y + z = 6 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + 3y + 4z = 14 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 3x + 5y + 7z = 20 \)

18. **Exercício 18:**  
    Determine o rank da matriz:
    
    \[
    A = \begin{bmatrix}
    1 & 2 & 3 \\
    2 & 4 & 6 \\
    3 & 6 & 9
    \end{bmatrix}
    \]

19. **Exercício 19:**  
    Verifique, utilizando o Teorema de Rouché–Capelli, a consistência do sistema:
    &nbsp;&nbsp;&nbsp;&nbsp; \( x + 2y + 3z = 6 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + 4y + 6z = 12 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 3x + 6y + 9z = 10 \)

20. **Exercício 20:**  
    Resolva o sistema:
    &nbsp;&nbsp;&nbsp;&nbsp; \( x + y + z = 3 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( x + 2y + 3z = 6 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + 3y + 4z = 8 \)

21. **Exercício 21:**  
    Liste as operações elementares necessárias para levar a matriz
    
    \[
    A = \begin{bmatrix}
    0 & 1 & 2 \\
    3 & 4 & 5
    \end{bmatrix}
    \]
    
    à forma escalonada.

22. **Exercício 22:**  
    Resolva o sistema utilizando inversão de matrizes:
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + y = 5 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( x - y = 1 \)

23. **Exercício 23:**  
    Analise o sistema:
    &nbsp;&nbsp;&nbsp;&nbsp; \( 3x + 2y + z = 1 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 6x + 4y + 2z = 2 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( x + y + 2z = 4 \)  
    e determine sua consistência e possíveis soluções.

24. **Exercício 24:**  
    Dado o sistema:
    &nbsp;&nbsp;&nbsp;&nbsp; \( x - y + z = 2 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x - 2y + 2z = 4 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 3x - 3y + 3z = 6 \)  
    encontre a solução geral.

25. **Exercício 25:**  
    Resolva o sistema:
    &nbsp;&nbsp;&nbsp;&nbsp; \( x - y = 1 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + y = 4 \)

26. **Exercício 26:**  
    Demonstre que o sistema a seguir é homogêneo e encontre sua solução:
    &nbsp;&nbsp;&nbsp;&nbsp; \( x + 2y = 0 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 3x + 6y = 0 \)

27. **Exercício 27:**  
    Resolva o sistema homogêneo:
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x - y + 3z = 0 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 4x - 2y + 6z = 0 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( -x + y - z = 0 \)

28. **Exercício 28:**  
    Calcule, se possível, a inversa da matriz:
    
    \[
    A = \begin{bmatrix}
    5 & 2 & 1 \\
    0 & 3 & -1 \\
    2 & 0 & 4
    \end{bmatrix}
    \]

29. **Exercício 29:**  
    Considere o sistema:
    &nbsp;&nbsp;&nbsp;&nbsp; \( x + y + z = 9 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x - y + z = 8 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( -x + 3y - z = -3 \)  
    e resolva-o utilizando o método de eliminação.

30. **Exercício 30:**  
    Para o sistema:
    &nbsp;&nbsp;&nbsp;&nbsp; \( x + 3y - 2z = 4 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 2x + 4y + z = 5 \)  
    &nbsp;&nbsp;&nbsp;&nbsp; \( 3x + 9y - 5z = 9 \)  
    determine o tipo de soluções existentes e resolva-o.

---

## 10. Resolução dos Exercícios Detalhada

### Exercício 1
**Enunciado:**  
Represente o sistema  
  \( x + 2y = 5 \)  
  \( 3x - y = 4 \)  
em forma matricial e escreva sua matriz aumentada.

**Resolução:**  
- A matriz dos coeficientes é  
  \[
  A = \begin{bmatrix} 1 & 2 \\ 3 & -1 \end{bmatrix}
  \]
- O vetor das incógnitas é  
  \[
  \mathbf{x} = \begin{bmatrix} x \\ y \end{bmatrix}
  \]
- O vetor dos termos independentes é  
  \[
  \mathbf{b} = \begin{bmatrix} 5 \\ 4 \end{bmatrix}
  \]
  
Assim, a forma matricial é:  
\[
A \cdot \mathbf{x} = \mathbf{b} \quad \Longrightarrow \quad \begin{bmatrix} 1 & 2 \\ 3 & -1 \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} 5 \\ 4 \end{bmatrix}
\]
E a matriz aumentada é:  
\[
[A \,|\, \mathbf{b}] = \begin{bmatrix} 1 & 2 & | & 5 \\ 3 & -1 & | & 4 \end{bmatrix}
\]

---

### Exercício 2
**Enunciado:**  
Resolva o sistema do Exercício 1.

**Resolução:**  
O sistema é:
\[
\begin{cases}
x + 2y = 5 \quad (1)\\[1mm]
3x - y = 4 \quad (2)
\end{cases}
\]
1. Da (1): \( x = 5 - 2y \).  
2. Substituindo em (2):  
  \( 3(5 - 2y) - y = 4 \)  
  \( 15 - 6y - y = 4 \)  
  \( 15 - 7y = 4 \)  
  \( 7y = 11 \)  
  \( y = \dfrac{11}{7} \).  
3. Então,  
  \( x = 5 - 2\left(\dfrac{11}{7}\right) = \dfrac{35 - 22}{7} = \dfrac{13}{7} \).

**Solução:**  
\[
(x, y) = \left(\frac{13}{7}, \frac{11}{7}\right)
\]

---

### Exercício 3
**Enunciado:**  
Considere o sistema  
  \( x - y + z = 2 \)  
  \( 2x + y - z = 3 \)  
  \( x + y + 2z = 5 \)  
Escreva a matriz aumentada e resolva o sistema.

**Resolução:**  
A matriz aumentada é:
\[
\begin{bmatrix}
1 & -1 & 1  & | & 2 \\
2 & 1  & -1 & | & 3 \\
1 & 1  & 2  & | & 5 
\end{bmatrix}
\]
**Passo 1:** Elimine \( x \) de \( R2 \) e \( R3 \):  
- \( R2 \leftarrow R2 - 2R1 \):  
  \( [0, \; 3, \; -3, \; -1] \).  
- \( R3 \leftarrow R3 - R1 \):  
  \( [0, \; 2, \; 1, \; 3] \).

**Passo 2:** Elimine \( y \) de \( R3 \). Multiplique \( R2 \) por \(\frac{2}{3}\) e subtraia de \( R3 \):  
- \( R2 \times \frac{2}{3} = [0, \; 2, \; -2, \; -\frac{2}{3}] \).  
- \( R3 \leftarrow R3 - [0, \; 2, \; -2, \; -\frac{2}{3}] = [0, \; 0, \; 3, \; \frac{11}{3}] \).

**Passo 3:** Da terceira linha:  
  \( 3z = \frac{11}{3} \) → \( z = \frac{11}{9} \).

**Passo 4:** Na segunda linha:  
  \( 3y - 3z = -1 \) → \( y = \frac{8}{9} \).

**Passo 5:** Na primeira equação:  
  \( x - y + z = 2 \) → \( x = 2 + y - z = \frac{5}{3} \).

**Solução:**  
\[
(x, y, z) = \left(\frac{5}{3}, \frac{8}{9}, \frac{11}{9}\right)
\]

---

### Exercício 4
**Enunciado:**  
Utilize o Teorema de Rouché–Capelli para verificar a consistência do sistema  
  \( x + y = 2 \)  
  \( 2x + 2y = 5 \).

**Resolução:**  
- Matriz dos coeficientes:  
  \( A = \begin{bmatrix} 1 & 1 \\ 2 & 2 \end{bmatrix} \) com \( \text{rank}(A) = 1 \).  
- Matriz aumentada:  
  \( [A \,|\, \mathbf{b}] = \begin{bmatrix} 1 & 1 & | & 2 \\ 2 & 2 & | & 5 \end{bmatrix} \),  
  pois a segunda linha apresenta inconsistência (esperaríamos 4 e não 5).

Portanto, \( \text{rank}(A) = 1 \) e \( \text{rank}([A\,|\,\mathbf{b}]) = 2 \). O sistema é **inconsistente**.

---

### Exercício 5
**Enunciado:**  
Resolva o sistema homogêneo:  
  \( x - 2y + 3z = 0 \)  
  \( 4x - 8y + 12z = 0 \).

**Resolução:**  
A segunda equação é o quádruplo da primeira. Assim, tome:
\[
x - 2y + 3z = 0 \quad \Rightarrow \quad x = 2y - 3z.
\]
Definindo \( y = s \) e \( z = t \), a solução geral é:
\[
(x, y, z) = (2s - 3t,\; s,\; t), \quad s,t \in \mathbb{R}.
\]

---

### Exercício 6
**Enunciado:**  
Verifique se a matriz  
  \( A = \begin{bmatrix} 1 & 3 \\ 2 & 6 \end{bmatrix} \)  
é invertível.

**Resolução:**  
O determinante de \( A \) é
\[
\det(A) = 1\cdot6 - 3\cdot2 = 6 - 6 = 0.
\]
Como o determinante é zero, \( A \) não é invertível.

---

### Exercício 7
**Enunciado:**  
Determine a solução geral do sistema  
  \( x + y + z = 6 \)  
  \( 2x + 2y + 2z = 12 \)  
  \( 3x + 3y + 3z = 18 \).

**Resolução:**  
As equações são múltiplos entre si, reduzindo o sistema a:
\[
x + y + z = 6.
\]
Definindo \( y = s \) e \( z = t \):
\[
x = 6 - s - t.
\]
**Solução:**  
\[
(x, y, z) = (6 - s - t,\; s,\; t), \quad s,t \in \mathbb{R}.
\]

---

### Exercício 8
**Enunciado:**  
Utilize o método da eliminação para resolver:
  \( x + y = 4 \)  
  \( x - y = 2 \).

**Resolução:**  
Somando ambas as equações:
\[
2x = 6 \quad \Rightarrow \quad x = 3.
\]
Substituindo em \( x + y = 4 \):
\[
y = 1.
\]
**Solução:**  
\[
(x, y) = (3, 1)
\]

---

### Exercício 9
**Enunciado:**  
Calcule a inversa da matriz  
  \( A = \begin{bmatrix} 2 & 3 \\ 1 & 4 \end{bmatrix} \).

**Resolução:**  
- Determinante:  
  \(\det(A) = 2\cdot4 - 3\cdot1 = 8 - 3 = 5\).  
- Inversa:
\[
A^{-1} = \frac{1}{5}\begin{bmatrix} 4 & -3 \\ -1 & 2 \end{bmatrix}.
\]

---

### Exercício 10
**Enunciado:**  
Determine o tipo de solução para o sistema:
  \( x + y + z = 3 \)  
  \( x - 2y + z = 0 \).

**Resolução:**  
Subtraindo as equações:
\[
(x+y+z)-(x-2y+z)= 3 \quad \Rightarrow \quad 3y = 3 \quad \Rightarrow \quad y = 1.
\]
Em \( x + y + z = 3 \):
\[
x + z = 2.
\]
Como essa relação envolve 2 incógnitas, temos infinitas soluções. Definindo \( z = t \):
\[
x = 2 - t.
\]
**Solução:**  
\[
(x, y, z) = (2-t,\; 1,\; t), \quad t \in \mathbb{R}.
\]

---

### Exercício 11
**Enunciado:**  
Resolva o sistema:
  \( 2x + 3y - z = 5 \)  
  \( 4x + 6y - 2z = 10 \).

**Resolução:**  
A segunda equação é o dobro da primeira, de modo que resta apenas
\[
2x + 3y - z = 5.
\]
Defina \( x = s \) e \( y = t \):
\[
z = 2s + 3t - 5.
\]
**Solução:**  
\[
(x, y, z) = (s,\; t,\; 2s+3t-5), \quad s,t \in \mathbb{R}.
\]

---

### Exercício 12
**Enunciado:**  
Expresse em forma paramétrica a solução do sistema:
  \( x + y - z = 2 \)  
  \( 2x + 2y - 2z = 4 \).

**Resolução:**  
A segunda equação é múltiplo da primeira, oferecendo:
\[
x + y - z = 2.
\]
Defina \( x = s \) e \( y = t \):
\[
z = s + t - 2.
\]
**Solução:**  
\[
(x, y, z) = (s,\; t,\; s+t-2), \quad s,t \in \mathbb{R}.
\]

---

### Exercício 13
**Enunciado:**  
Apresente a representação matricial (coeficientes e matriz aumentada) do sistema:
  \( 3x - y = 7 \)  
  \( -x + 4y = 3 \).

**Resolução:**  
Matriz dos coeficientes:
\[
A = \begin{bmatrix} 3 & -1 \\ -1 & 4 \end{bmatrix}\,;\quad \mathbf{x} = \begin{bmatrix} x \\ y \end{bmatrix}\,;\quad \mathbf{b} = \begin{bmatrix} 7 \\ 3 \end{bmatrix}.
\]
Forma matricial:
\[
A\mathbf{x} = \mathbf{b} \quad \text{e} \quad [A\,|\,\mathbf{b}] = \begin{bmatrix} 3 & -1 & | & 7 \\ -1 & 4 & | & 3 \end{bmatrix}.
\]

---

### Exercício 14
**Enunciado:**  
Para o sistema:
  \( x + 2y + 3z = 1 \)  
  \( 2x + 4y + 6z = 2 \)  
determine a solução geral.

**Resolução:**  
A segunda equação é o dobro da primeira, reduzindo o sistema a:
\[
x + 2y + 3z = 1.
\]
Defina \( y = s \) e \( z = t \):
\[
x = 1 - 2s - 3t.
\]
**Solução:**  
\[
(x, y, z) = (1-2s-3t,\; s,\; t),\quad s,t \in \mathbb{R}.
\]

---

### Exercício 15
**Enunciado:**  
Resolva o sistema utilizando o método de eliminação de Gauss:
  \( x - y + z = 3 \)  
  \( 2x + y + z = 5 \)  
  \( -x + 3y - 2z = -1 \).

**Resolução:**  
1. Escreva as equações:
   - (1) \( x - y + z = 3 \)  
   - (2) \( 2x + y + z = 5 \)  
   - (3) \( -x + 3y - 2z = -1 \).

2. Da (1), isole: \( x = 3 + y - z \).

3. Substitua em (2):
\[
2(3+y-z)+ y + z = 5 \quad \Rightarrow \quad 6+2y-2z+y+z =5 \quad \Rightarrow \quad 3y - z = -1.
\]
(Chame esta equação de (A).)

4. Substitua em (3):
\[
-[3+y-z] + 3y - 2z = -1 \quad \Rightarrow \quad -3 - y + z + 3y - 2z = -1 \quad \Rightarrow \quad 2y - z = 2.
\]
(Chame esta de (B).)

5. Subtraia (A) de (B):
\[
(2y - z) - (3y - z) = 2 - (-1) \quad \Rightarrow \quad -y = 3 \quad \Rightarrow \quad y = -3.
\]

6. Em (B):  
  \( 2(-3) - z = 2 \) → \( -6 - z =2 \) → \( z = -8 \).

7. Finalmente, \( x = 3 + (-3) - (-8)= 8 \).

**Solução:**  
\[
(x, y, z) = (8, -3, -8).
\]

---

### Exercício 16
**Enunciado:**  
Utilize a retro-substituição na matriz escalonada:
\[
\begin{bmatrix}
1 & 2 & -1 & | & 1 \\
0 & 3 & 2  & | & 4 \\
0 & 0 & 5  & | & 10
\end{bmatrix}
\]
para encontrar \( x \), \( y \) e \( z \).

**Resolução:**  
- Terceira linha: \( 5z = 10 \) → \( z = 2 \).  
- Segunda linha: \( 3y + 2(2) = 4 \) → \( 3y = 0 \) → \( y = 0 \).  
- Primeira linha: \( x + 2(0) - 2 = 1 \) → \( x = 3 \).

**Solução:**  
\[
(x, y, z) = (3, 0, 2).
\]

---

### Exercício 17
**Enunciado:**  
Analise o sistema:
  \( x + y + z = 6 \)  
  \( 2x + 3y + 4z = 14 \)  
  \( 3x + 5y + 7z = 20 \)  
e determine se existe solução única.

**Resolução:**  
Expressar \( x = 6 - y - z \) em (2) e (3) resulta em equações inconsistentes entre si, indicando que o sistema não tem solução única, mas é **inconsistente**.

**Solução:**  
O sistema é inconsistente (não possui solução).

---

### Exercício 18
**Enunciado:**  
Determine o rank da matriz
\[
A = \begin{bmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
3 & 6 & 9
\end{bmatrix}.
\]

**Resolução:**  
Como a segunda linha é o dobro da primeira e a terceira é o triplo, todas as linhas são linearmente dependentes.  
**Rank:** 1.

---

### Exercício 19
**Enunciado:**  
Verifique, com o Teorema de Rouché–Capelli, a consistência do sistema:
  \( x + 2y + 3z = 6 \)  
  \( 2x + 4y + 6z = 12 \)  
  \( 3x + 6y + 9z = 10 \).

**Resolução:**  
As duas primeiras equações são proporcionais, mas a terceira não coincide com a proporcionalidade esperada (deveria ser 18 em vez de 10). Assim, os ranks de \( A \) e \([A\,|\,\mathbf{b}]\) diferem e o sistema é **inconsistente**.

---

### Exercício 20
**Enunciado:**  
Resolva o sistema:
  \( x + y + z = 3 \)  
  \( x + 2y + 3z = 6 \)  
  \( 2x + 3y + 4z = 8 \).

**Resolução:**  
Subtraindo a primeira equação da segunda, obtemos:  
  \( y + 2z = 3 \).  
Subtraindo o dobro da primeira da terceira:  
  \( y + 2z = 2 \).  
Como as duas equações para \( y+2z \) são inconsistentes, o sistema é **inconsistente**.

---

### Exercício 21
**Enunciado:**  
Liste as operações elementares necessárias para levar a matriz
\[
A = \begin{bmatrix}
0 & 1 & 2 \\
3 & 4 & 5
\end{bmatrix}
\]
à forma escalonada.

**Resolução:**  
1. Troque \( R1 \) com \( R2 \) para obter um pivô não-nulo na posição (1,1).  
Após a troca:
\[
\begin{bmatrix}
3 & 4 & 5 \\
0 & 1 & 2
\end{bmatrix}
\]
Esta forma já é escalonada, pois o pivô da primeira linha está à esquerda do da segunda.

---

### Exercício 22
**Enunciado:**  
Resolva o sistema utilizando inversão de matrizes:
  \( 2x + y = 5 \)  
  \( x - y = 1 \).

**Resolução:**  
Matriz dos coeficientes:
\[
A = \begin{bmatrix} 2 & 1 \\ 1 & -1 \end{bmatrix}
\]
Vetor \( \mathbf{b} = \begin{bmatrix} 5 \\ 1 \end{bmatrix} \).  
Determinante: \( \det(A) = 2(-1) - 1(1) = -3 \).

Calculando \( A^{-1} \):
\[
A^{-1} = \frac{1}{-3} \begin{bmatrix} -1 & -1 \\ -1 & 2 \end{bmatrix} = \begin{bmatrix} \frac{1}{3} & \frac{1}{3} \\ \frac{1}{3} & -\frac{2}{3} \end{bmatrix}.
\]
Multiplicando:
\[
\mathbf{x} = A^{-1}\mathbf{b} = \begin{bmatrix} \frac{1}{3} & \frac{1}{3} \\ \frac{1}{3} & -\frac{2}{3} \end{bmatrix}\begin{bmatrix} 5 \\ 1 \end{bmatrix} = \begin{bmatrix} 2 \\ 1 \end{bmatrix}.
\]

**Solução:**  
\[
(x,y) = (2,1).
\]

---

### Exercício 23
**Enunciado:**  
Analise o sistema:
  \( 3x + 2y + z = 1 \)  
  \( 6x + 4y + 2z = 2 \)  
  \( x + y + 2z = 4 \)
para determinar sua consistência.

**Resolução:**  
As duas primeiras equações são proporcionais, restando uma equação independente com a terceira. A substituição resulta em uma equação válida, mas com um grau de liberdade na solução, o que indica **infinitas soluções**.

**Solução (parametrizada):**  
Defina \( x=s \) e \( y=t \); então, de \( 3s + 2t + z=1 \):
\[
z = 1 - 3s - 2t.
\]
Logo,  
\[
(x,y,z) = (s,\; t,\; 1-3s-2t), \quad s,t\in \mathbb{R}.
\]

---

### Exercício 24
**Enunciado:**  
Dado o sistema:
  \( x - y + z = 2 \)  
  \( 2x - 2y + 2z = 4 \)  
  \( 3x - 3y + 3z = 6 \)  
encontre a solução geral.

**Resolução:**  
As equações são proporcionais, reduzindo o sistema a:
\[
x - y + z = 2.
\]
Defina \( y = s \) e \( z = t \); então,  
\[
x = 2 + s - t.
\]
**Solução:**  
\[
(x,y,z) = (2+s-t,\; s,\; t), \quad s,t \in \mathbb{R}.
\]

---

### Exercício 25
**Enunciado:**  
Resolva o sistema:
  \( x - y = 1 \)  
  \( 2x + y = 4 \).

**Resolução:**  
Da primeira equação: \( x = y + 1 \).  
Substituindo em \( 2(y+1) + y = 4 \):
\[
2y+2+y = 4 \quad \Rightarrow \quad 3y = 2 \quad \Rightarrow \quad y = \frac{2}{3}.
\]
Então, \( x = \frac{5}{3} \).

**Solução:**  
\[
(x,y) = \left(\frac{5}{3},\; \frac{2}{3}\right).
\]

---

### Exercício 26
**Enunciado:**  
Demonstre que o sistema  
  \( x + 2y = 0 \)  
  \( 3x + 6y = 0 \)  
é homogêneo e encontre sua solução.

**Resolução:**  
Como o lado direito é 0, o sistema é homogêneo.  
A segunda equação é 3 vezes a primeira, levando a:
\[
x = -2y.
\]
Definindo \( y=t \):
\[
(x,y) = (-2t, \;t),\quad t\in\mathbb{R}.
\]

---

### Exercício 27
**Enunciado:**  
Resolva o sistema homogêneo:
  \( 2x - y + 3z = 0 \)  
  \( 4x - 2y + 6z = 0 \)  
  \( -x + y - z = 0 \).

**Resolução:**  
Note que a segunda é o dobro da primeira. Use a terceira:
\[
-x+y-z=0 \quad \Rightarrow \quad y = x+z.
\]
Substitua em \( 2x - y + 3z = 0 \):
\[
2x - (x+z) + 3z = 0 \quad \Rightarrow \quad x+2z = 0 \quad \Rightarrow \quad x = -2z.
\]
Então \( y = -2z+z = -z \).

**Solução:**  
\[
(x,y,z) = (-2z,\;-z,\;z),\quad z\in\mathbb{R}.
\]

---

### Exercício 28
**Enunciado:**  
Calcule, se possível, a inversa da matriz
\[
A = \begin{bmatrix} 5 & 2 & 1 \\ 0 & 3 & -1 \\ 2 & 0 & 4 \end{bmatrix}.
\]

**Resolução:**  
1. Calcule o determinante:
\[
\det(A) = 5\begin{vmatrix} 3 & -1 \\ 0 & 4 \end{vmatrix} - 2\begin{vmatrix} 0 & -1 \\ 2 & 4 \end{vmatrix} + 1\begin{vmatrix} 0 & 3 \\ 2 & 0 \end{vmatrix} = 5(12)-2(2)-6 = 60-4-6=50.
\]
2. Calcule a matriz de cofatores e, em seguida, a adjunta, obtendo:
\[
\text{adj}(A) = \begin{bmatrix} 12 & -8 & -5 \\ -2 & 18 & 5 \\ -6 & 4 & 15 \end{bmatrix}^T =  
\begin{bmatrix} 12 & -8 & -5 \\ -2 & 18 & 5 \\ -6 & 4 & 15 \end{bmatrix}.
\]
3. Assim,  
\[
A^{-1} = \frac{1}{50}\begin{bmatrix} 12 & -8 & -5 \\ -2 & 18 & 5 \\ -6 & 4 & 15 \end{bmatrix}.
\]

---

### Exercício 29
**Enunciado:**  
Considere o sistema:
  \( x + y + z = 9 \)  
  \( 2x - y + z = 8 \)  
  \( -x + 3y - z = -3 \)  
e resolva-o utilizando o método de eliminação.

**Resolução:**  
1. A partir da primeira equação: \( x = 9-y-z \).  
2. Em (2):
\[
2(9-y-z) - y + z = 8 \quad \Rightarrow \quad 18 - 2y - 2z - y + z = 8 \quad \Rightarrow \quad 18 - 3y - z = 8,
\]
portanto \( 3y+z = 10 \) → \( z = 10 - 3y \).  
3. Em (3), substituindo \( x = 9-y-z \):
\[
-(9-y-z)+3y-z = -3 \quad \Rightarrow \quad -9+y+z+3y-z=-3 \quad \Rightarrow \quad -9+4y = -3,
\]
o que implica \( y = \frac{3}{2} \).  
4. De (2), \( z = 10 - 3\left(\frac{3}{2}\right)= \frac{11}{2} \).  
5. Por fim, \( x = 9-\frac{3}{2}-\frac{11}{2}=2 \).

**Solução:**  
\[
(x,y,z)=\left(2,\; \frac{3}{2},\; \frac{11}{2}\right).
\]

---

### Exercício 30
**Enunciado:**  
Para o sistema:
  \( x + 3y - 2z = 4 \)  
  \( 2x + 4y + z = 5 \)  
  \( 3x + 9y - 5z = 9 \)  
determine o tipo de soluções existentes e resolva-o.

**Resolução:**  
1. Multiplique a primeira equação por 2: \( 2x+6y-4z=8 \).  
2. Subtraia de (2):  
  \( (2x+4y+z) - (2x+6y-4z)= 5-8 \) → \( -2y+5z=-3 \) → \( 2y-5z=3 \). (A)  
3. Multiplique a primeira por 3: \( 3x+9y-6z=12 \).  
4. Subtraia de (3):  
  \( (3x+9y-5z) - (3x+9y-6z)= 9-12 \) → \( z=-3 \).  
5. Em (A), \( 2y-5(-3)=3 \) → \( 2y+15=3 \) → \( y=-6 \).  
6. Substitua em a primeira:  
  \( x+3(-6)-2(-3)=4 \) → \( x-18+6=4 \) → \( x=16 \).

**Solução:**  
O sistema possui solução única:  
\[
(x,y,z)=(16,\;-6,\;-3).
\]

---

*Este conjunto de 30 exercícios e resoluções detalhadas cobre os principais tópicos abordados no documento. Você pode utilizar os delimitadores LaTeX mostrados para incluir expressões matemáticas no estilo GitHub Markdown (usando \( ... \) para inline e \[ ... \] ou $$ ... $$ para blocos).*