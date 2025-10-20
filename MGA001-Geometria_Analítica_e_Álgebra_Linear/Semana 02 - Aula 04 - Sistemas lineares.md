# Sistemas de equações lineares

### Introdução

Esta aula baseia-se no vídeo "Sistemas e equações lineares" da disciplina Geometria Analítica e Álgebra Linear, cuja transcrição foi usada como fonte principal. Vamos apresentar definição, classificação (solução única, infinitas soluções, sem solução), interpretação geométrica em R², forma matricial \(Ax=b\), e exemplos resolvidos passo a passo. Complementos teóricos e didáticos foram consultados para clarificar conceitos e oferecer exercícios com resoluções detalhadas.

---

## Desenvolvimento

### 1. Definição e notação

- Sistema linear com \(m\) equações e \(n\) incógnitas: conjunto  
```
[a11 a12 ... a1n] [x1] = [b1]]
[a21 a22 ... a2n] [x2] = [b2]
[... ... ... ...] [..] = [...]
[am1 am2 ... amn] [xn] = [bm]
```
  - onde ``` [x1, x2, ..., xn]``` são as incógnitas a serem determinadas, e \(m,n\in\mathbb{N}^*\).

- 
  onde os \(a_{ij}\) são coeficientes e \(b_i\) os termos independentes. Em notação matricial compacta escrevemos
  \[
  A x = b,
  \]
  com \(A\in\mathbb{R}^{m\times n}\), \(x\in\mathbb{R}^n\) e \(b\in\mathbb{R}^m\).

- Representação alternativa em texto (caso LaTeX não seja renderizado):
```
Ax = b  with A = [a_ij] (m x n), x = column vector (n x 1), b = column vector (m x 1)
```

(Citação à definição matricial e notação usada como padrão em álgebra linear.)

---

### 2. Classificação das soluções (interpretação geométrica em R²)

Para sistemas de duas equações e duas incógnitas ```(2 x 2)```, a interpretação geométrica é direta e essencial:

- Solução única: as duas retas que representam as equações se intersectam em um único ponto (retas distintas e não paralelas). Exemplo do vídeo: solução \((x,y)=(2,1)\) obtida pela interseção de duas retas (caso típico).

- Infinitas soluções: as duas equações representam a mesma reta; todos os pontos dessa reta satisfazem ambas as equações (sistemas dependentes). Geometricamente, as retas coincidem e formam uma reta comum de soluções.

- Sem solução: as retas são paralelas (mesma inclinação, termos independentes distintos) e, portanto, não se intersectam; não existe par \((x,y)\) que satisfaça ambas as equações simultaneamente (sistema inconsistente).

A mesma lógica se estende para \(m,n>2\): em \(\mathbb{R}^3\) aparecem planos; soluções podem ser pontos isolados, retas de interseção entre planos, planos coincidentes etc. (intuição geométrica geral).

(Citação: classificação e interpretação geométrica das três possibilidades ilustradas no vídeo e em material didático de álgebra linear.)

---

### 3. Resolução algébrica elementar (exemplo 2×2)

Passos padrão (substituição/eliminção direta) com exemplo completo:

Exemplo: resolver
\[
\begin{cases}
2x - y = 3\\[4pt]
x + 2y = 2
\end{cases}
\]

1. Isolar uma variável (p.ex., da segunda equação): \(x = 2 - 2y\).
2. Substituir na primeira: \(2(2 - 2y) - y = 3\).
3. Desenvolver: \(4 - 4y - y = 3 \Rightarrow 4 - 5y = 3\).
4. Isolar \(y\): \(-5y = -1 \Rightarrow y = \tfrac{1}{5}\).
5. Voltar em \(x = 2 - 2y = 2 - 2\cdot\tfrac{1}{5} = \tfrac{8}{5}\).
6. Solução: \((x,y) = \left(\tfrac{8}{5},\tfrac{1}{5}\right)\).

Observação: a técnica de eliminação por substituição funciona bem em sistemas pequenos; para sistemas maiores, métodos matriciais (escalonamento) são recomendados.

---

### 4. Forma matricial \(Ax=b\) e interpretação

- Construção:
  - Matriz de coeficientes \(A = [a_{ij}]\) (m×n).
  - Vetor incógnita \(x = (x_1,\dots,x_n)^T\).
  - Vetor termos independentes \(b=(b_1,\dots,b_m)^T\).
  - O produto matricial \(Ax\) corresponde à combinação linear das colunas de \(A\) com coeficientes do vetor \(x\); requer definição de produto matricial (ver aula anterior sobre produtos).

- Exemplo para sistema 2×2:
  \[
  \begin{pmatrix}2 & -1\\[4pt]1 & 2\end{pmatrix}
  \begin{pmatrix}x\\[4pt]y\end{pmatrix}
  =
  \begin{pmatrix}3\\[4pt]2\end{pmatrix},
  \]
  que resume as duas equações em uma só expressão matricial. O cálculo de cada linha do produto replica a equação correspondente do sistema (linha i de \(A\) dot produto com \(x\) → \(b_i\)).

(Citação: forma matricial e sua utilidade prática para computação e organização de sistemas.)

---

### 5. Relação entre posto da matriz e tipos de solução (intuição)

- Intuição (sem provas formais completas): o número de graus de liberdade das incógnitas que podem ser fixadas está ligado ao posto (rank) da matriz \(A\) e ao posto da matriz aumentada \([A\;|\;b]\).
  - Se rank\((A)=\)rank\([A\;|\;b]\) = \(n\) (número de incógnitas), solução única.
  - Se rank\((A)=\)rank\([A\;|\;b]\) < \(n\), soluções infinitas (graus de liberdade > 0).
  - Se rank\((A)\) < rank\([A\;|\;b]\), sistema inconsistente (sem solução).
- Observação: no curso estas noções serão formalizadas com conceitos de posto, espaço coluna e núcleo; aqui usamos apenas a intuição geométrica e algébrica.

(Referência introdutória sobre posto e classificação de sistemas em textos didáticos e notas de curso.)

---

## Exemplos resolvidos adicionais

1. Sistema com solução única (resumido):
   \[
   \begin{cases}
   x + y = 4\\[4pt]
   2x - y = 1
   \end{cases}
   \]
   - Eliminação: some as equações (ou isole). Soma: \(3x = 5 \Rightarrow x = \tfrac{5}{3}\). Substituir: \(y = 4 - x = 4 - \tfrac{5}{3} = \tfrac{7}{3}\).

2. Sistema dependente (infinitas soluções):
   \[
   \begin{cases}
   2x + 4y = 6\\[4pt]
   x + 2y = 3
   \end{cases}
   \]
   - Note: primeira linha = 2 × segunda linha → equações equivalentes → solução geral \(x = 3 - 2t,\; y=t,\; t\in\mathbb{R}\).

3. Sistema inconsistente (sem solução):
   \[
   \begin{cases}
   x + y = 1\\[4pt]
   2x + 2y = 5
   \end{cases}
   \]
   - Segunda linha deveria ser \(2(x+y)=2\) se fosse múltiplo; mas tem 5 → contradição → retas paralelas → sem solução.

(Estes casos correspondem às três situações geométricas explicadas no vídeo.)

---

## Conclusão

- Sistemas lineares têm comportamento classificado em três casos: solução única, infinitas soluções ou nenhuma solução; em R² essas situações correspondem a interseção de retas (ponto único), coincidência de retas (reta inteira de soluções) ou retas paralelas (nenhuma interseção).
- A forma matricial \(Ax=b\) organiza o sistema de modo que métodos algorítmicos (eliminação de Gauss, decomposições) possam ser aplicados de forma sistemática e eficiente em computação.

---

## Análise crítica

- O vídeo apresenta a intuição geométrica e ilustra bem as três possibilidades de solução para sistemas em duas incógnitas; contudo, não aprofunda formalmente os conceitos de posto e espaço coluna necessários para uma classificação algébrica completa, nem discute critérios numéricos e estabilidade do método de solução para sistemas grandes — tópicos que serão tratados nas aulas seguintes e em livros-texto como Nicholson.
- Recomenda-se aos alunos verificar sempre os cálculos algébricos (isolamento e operações) e praticar a visualização geométrica (p.ex., com GeoGebra) para consolidar intuição e detectar inconsistências nos sistemas apresentados (casos de dependência e inconsistência).

(Citações de apoio e leitura adicional usadas para estruturar análise e terminologia.)

---

## Exercícios (15) com resolução detalhada

Observação: lista focada no conteúdo da aula atual (classificação, resolução direta e forma matricial). Cada exercício inclui solução passo a passo.

1. Enunciado: Resolva o sistema
   \[
   \begin{cases}
   2x - y = 3\\[4pt]
   x + 2y = 2
   \end{cases}
   \]
   Solução:
   - Isolar \(x\) na segunda: \(x = 2 - 2y\).
   - Substituir na primeira: \(2(2 - 2y) - y = 3 \Rightarrow 4 -4y - y = 3\).
   - Simplificar: \(4 -5y =3 \Rightarrow -5y = -1 \Rightarrow y=\tfrac{1}{5}\).
   - Substituir: \(x = 2 - 2\cdot\tfrac{1}{5} = \tfrac{8}{5}\).
   - Solução: \(\left(\tfrac{8}{5},\tfrac{1}{5}\right)\).

2. Enunciado: Resolva por eliminação
   \[
   \begin{cases}
   x + y = 4\\[4pt]
   2x - y = 1
   \end{cases}
   \]
   Solução:
   - Somar as duas equações: \(3x = 5 \Rightarrow x = \tfrac{5}{3}\).
   - Substituir em \(x+y=4\): \(y = 4 - \tfrac{5}{3} = \tfrac{7}{3}\).
   - Solução: \(\left(\tfrac{5}{3},\tfrac{7}{3}\right)\).

3. Enunciado: Classifique (única, infinita, nenhuma) o sistema
   \[
   \begin{cases}
   2x + 4y = 6\\[4pt]
   x + 2y = 3
   \end{cases}
   \]
   Solução:
   - Observe: primeira = 2 × segunda → equações dependentes.
   - Portanto infinitas soluções; solução geral: \(x = 3 - 2t,\; y=t,\; t\in\mathbb{R}\).

4. Enunciado: Classifique
   \[
   \begin{cases}
   x + y = 1\\[4pt]
   2x + 2y = 5
   \end{cases}
   \]
   Solução:
   - Segunda não é múltiplo da primeira (2×1 ≠ 5) → retas paralelas (mesma inclinação, constantes incompatíveis) → sem solução.

5. Enunciado: Escreva na forma matricial \(Ax=b\) o sistema
   \[
   \begin{cases}
   x - y = 1\\[4pt]
   x + 2y = 4
   \end{cases}
   \]
   Solução:
   - \(A = \begin{pmatrix}1 & -1\\[4pt]1 & 2\end{pmatrix},\; x=\begin{pmatrix}x\\[4pt]y\end{pmatrix},\; b=\begin{pmatrix}1\\[4pt]4\end{pmatrix}\).
   - Portanto \(A x = b\).

6. Enunciado: Resolva via substituição
   \[
   \begin{cases}
   3x + 2y = 7\\[4pt]
   x - y = 1
   \end{cases}
   \]
   Solução:
   - Da segunda: \(x = 1 + y\).
   - Substituir: \(3(1+y) + 2y = 7 \Rightarrow 3 + 3y + 2y = 7 \Rightarrow 5y = 4 \Rightarrow y = \tfrac{4}{5}\).
   - \(x = 1 + \tfrac{4}{5} = \tfrac{9}{5}\).
   - Solução: \(\left(\tfrac{9}{5},\tfrac{4}{5}\right)\).

7. Enunciado: Resolva e interprete geometricamente
   \[
   \begin{cases}
   2x + y = 3\\[4pt]
   4x + 2y = 6
   \end{cases}
   \]
   Solução:
   - Segunda = 2 × primeira → mesmas retas → infinitas soluções; expressar solução geral: \(y = 3 - 2x\), \(x\) livre.

8. Enunciado: Verifique se o sistema tem solução única, infinita ou nenhuma:
   \[
   \begin{cases}
   x - 2y = 0\\[4pt]
   2x - 4y = 1
   \end{cases}
   \]
   Solução:
   - Segunda = 2 × primeira na parte esquerda, mas RHS difere (0 vs 1) → contradição → sem solução.

9. Enunciado: Resolva matricialmente (2×2)
   \[
   A=\begin{pmatrix}2 & -1\\[4pt]1 & 2\end{pmatrix},\quad b=\begin{pmatrix}3\\[4pt]2\end{pmatrix}
   \]
   Solução:
   - Calcule determinante: \(\det(A)=2\cdot2 - (-1)\cdot1 = 4+1 =5\neq0\) → inversa existe.
   - Inversa (2×2): \(A^{-1} = \tfrac{1}{\det(A)}\begin{pmatrix}2 & 1\\[4pt]-1 & 2\end{pmatrix} = \tfrac{1}{5}\begin{pmatrix}2 & 1\\[4pt]-1 & 2\end{pmatrix}\).
   - \(x = A^{-1} b = \tfrac{1}{5}\begin{pmatrix}2 & 1\\[4pt]-1 & 2\end{pmatrix}\begin{pmatrix}3\\[4pt]2\end{pmatrix}
     = \tfrac{1}{5}\begin{pmatrix}2\cdot3 + 1\cdot2\\[4pt]-1\cdot3 + 2\cdot2\end{pmatrix}
     = \tfrac{1}{5}\begin{pmatrix}8\\[4pt]1\end{pmatrix}
     = \begin{pmatrix}8/5\\[4pt]1/5\end{pmatrix}.\)

10. Enunciado: Dado sistema dependente, escreva solução em forma paramétrica:
    \[
    \begin{cases}
    x + 2y - z = 1\\[4pt]
    2x + 4y -2z = 2
    \end{cases}
    \]
    Solução:
    - Segunda = 2 × primeira → redundante.
    - Escrever variáveis livres: escolha \(y = s,\; z = t\).
    - Da primeira: \(x = 1 - 2s + t\).
    - Solução geral: \((x,y,z) = (1 - 2s + t,\; s,\; t)\), \(s,t\in\mathbb{R}\).

11. Enunciado: Resolva por eliminação (caso com frações)
    \[
    \begin{cases}
    \tfrac{1}{2}x + y = 3\\[4pt]
    x - \tfrac{1}{4}y = 1
    \end{cases}
    \]
    Solução:
    - Multiplicar primeira por 2: \(x + 2y = 6\).
    - Subtrair a segunda: \((x + 2y) - (x - \tfrac{1}{4}y) = 6 - 1\) → \(2y + \tfrac{1}{4}y = 5\) → \(\tfrac{9}{4}y = 5\) → \(y = \tfrac{20}{9}\).
    - \(x = 1 + \tfrac{1}{4}y = 1 + \tfrac{1}{4}\cdot\tfrac{20}{9} = 1 + \tfrac{5}{9} = \tfrac{14}{9}\).

12. Enunciado: Dê interpretação geométrica para cada caso estudado e dê um exemplo numérico de cada (já feitos nos exercícios anteriores).  
    Solução:
    - Solução única: retas se cruzam em um ponto (exercício 2).  
    - Infinitas soluções: retas coincidem (exercício 7).  
    - Sem solução: retas paralelas (exercício 8).

13. Enunciado: Usando forma matricial, mostre que quando \(\det(A)\neq0\) (A quadrada) existe solução única \(x=A^{-1}b\) (esquema curto).  
    Solução:
    - Resultado padrão de álgebra linear: se \(A\) é \(n\times n\) e invertível, multiplicando ambos os lados por \(A^{-1}\) obtém-se \(x = A^{-1}b\). Exemplo numérico em exercício 9.

14. Enunciado: Para o sistema
    \[
    \begin{cases}
    x - y = 0\\[4pt]
    2x - 2y = 0
    \end{cases}
    \]
    escreva solução e classe.  
    Solução:
    - Segunda = 2 × primeira → dependente → infinitas soluções. Primeira dá \(x=y\) → solução \(\{(t,t)\;|\;t\in\mathbb{R}\}\).

15. Enunciado: Monte a matriz aumentada \([A\;|\;b]\) e explique como uma linha com zeros à esquerda e RHS não-zero indica inconsistência.  
    Solução:
    - Matriz aumentada ex.: sistema \(x+y=1,\; x+y=2\) → \([A\;|\;b]=\begin{bmatrix}1 & 1 & | & 1\\[4pt]1 & 1 & | & 2\end{bmatrix}\). Subtraindo linha 1 da 2 obtemos \([0\ 0\ | \ 1]\) → equivale a \(0=1\) → inconsistente → sem solução. Interpretação algébrica do caso geométrico de retas paralelas.

---

## Bibliografia (formato ABNT)

- UNIVESP. Geometria analítica e álgebra linear — Sistemas e equações lineares [vídeo]. UNIVESP TV, YouTube, 16 maio 2022. Transcrição consultada para este material. Acesso em 11 out. 2025.  
- IME UNICAMP. Sistemas Lineares. Disponível em: https://www.ime.unicamp.br/~marcia/AlgebraLinear/sistemas_lineares.html. Acesso em 11 out. 2025.  
- BRASIL ESCOLA. Classificação de um sistema linear. Disponível em: https://brasilescola.uol.com.br/matematica/classificacao-um-sistema-linear.htm. Acesso em 11 out. 2025.  
- NEUROCHISPAS. Sistemas de equações sem solução, com infinitas soluções. Disponível em: https://br.neurochispas.com/algebra/sistemas-de-equacoes-sem-solucao-com-infinitas-solucoes/. Acesso em 11 out. 2025.  
- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015. (Recomendado para leitura complementar e fundamentação teórica).

---

## Materiais complementares

- Nicholson, W. Keith. Álgebra Linear. AMGH Editora, 2. ed., 2015 (capítulos sobre sistemas lineares, posto e eliminação de Gauss).  
- Notas e páginas sobre sistemas lineares e classificação: IME Unicamp; Brasil Escola; Neurochispas (consultas indicadas acima).  
- Ferramenta de visualização recomendada: GeoGebra (plotar retas e planos para entender geometricamente soluções).

---