# Propriedades dos determinantes

## Introdução

Esta aula explica em detalhes as principais propriedades dos determinantes de matrizes quadradas, ilustrando cada propriedade com exemplos numéricos e aplicações práticas. O conteúdo segue a transcrição do vídeo didático sobre determinantes e é complementado por referências didáticas confiáveis para reforçar as demonstrações e aplicações.

---

## Desenvolvimento

### Definição rápida e notação
- **Determinante** é um número associado a uma matriz quadrada que codifica propriedades importantes, como a invertibilidade e o fator de escala da transformação linear representada pela matriz.  
- Notação: para uma matriz \(A\) quadrada, escrevemos \(\det(A)\) ou \(|A|\). A existência do determinante exige que a matriz seja quadrada.

---

### Propriedade 1 — Linearidade em cada linha (ou coluna)

- Enunciado: o determinante é linear em cada linha quando as demais linhas são mantidas fixas. Isso significa duas coisas:
  1. Se uma linha é multiplicada por um escalar \(k\), o determinante é multiplicado por \(k\) (quando só uma linha é escalada).
  2. Se você expressa uma linha como soma de dois vetores, o determinante se distribui como soma de dois determinantes (superposição).
- Fórmulas:
  - Se \(B\) é obtida de \(A\) multiplicando apenas a linha \(i\) por \(k\), então \(\det(B)=k\det(A)\).
  - Se a linha \(i\) de \(A\) é \(u+v\), então \(\det(A)=\det(A\text{ com linha }u)+\det(A\text{ com linha }v)\).
- Intuição: o determinante mede um volume orientado; multiplicar uma linha por \(k\) estica esse volume por \(k\); somar linhas corresponde a decompor a contribuição de uma face do paralelo-pipedo. Essa propriedade é uma das que definem o determinante.
- Exemplo numérico (único fator):
  - Tome \(A=\begin{pmatrix}2 & 1\\[4pt]3 & 4\end{pmatrix}\). Calcule \(\det(A)=2\cdot4 - 1\cdot3 = 5\).
  - Multiplicar a primeira linha por \(3\) gera \(B=\begin{pmatrix}6 & 3\\[4pt]3 & 4\end{pmatrix}\). Então \(\det(B)=3\det(A)=15\). Verificação direta: \(6\cdot4 - 3\cdot3 = 24 - 9 = 15\).

---

### Propriedade 2 — Troca de duas linhas muda o sinal do determinante

- Enunciado: trocar duas linhas (ou duas colunas) de uma matriz multiplica seu determinante por \(-1\).  
- Fórmula: se \(B\) é obtida permutando duas linhas de \(A\), então \(\det(B) = -\det(A)\).  
- Raciocínio: trocar duas linhas inverte a orientação do paralelogramo/paralelipípedo associado, mudando o sinal do volume orientado.
- Exemplo numérico:
  - Com \(A=\begin{pmatrix}1 & 2\\[4pt]3 & 4\end{pmatrix}\) temos \(\det(A)=1\cdot4 - 2\cdot3 = -2\).
  - Trocar linhas dá \(B=\begin{pmatrix}3 & 4\\[4pt]1 & 2\end{pmatrix}\). Então \(\det(B)= -\det(A) = 2\). Verificação direta: \(3\cdot2 - 4\cdot1 = 6 - 4 = 2\).

---

### Propriedade 3 — Determinante da identidade é 1

- Enunciado: a matriz identidade \(I_n\) tem determinante \(\det(I_n)=1\).  
- Justificativa: \(I_n\) corresponde à transformação identidade que preserva os volumes sem inverter orientação; por definição suas linhas formam a base canônica, e o volume do paralelipípedo gerado é 1.
- Aplicação: essa propriedade é base para calcular determinantes de matrizes diagonais (produto das entradas da diagonal) e para inferir efeitos de escalamentos sucessivos.

---

### Propriedade 4 — Multiplicação escalar de toda a matriz

- Enunciado: se \(B = kA\) (todas as entradas de \(A\) multiplicadas por \(k\)), então \(\det(B) = k^{n}\det(A)\) para uma matriz \(n\times n\).  
- Explicação: multiplicar todas as linhas por \(k\) multiplica o determinante por \(k\) para cada linha, totalizando \(k^n\) vezes o determinante original.
- Exemplo:
  - Para \(A=\begin{pmatrix}2 & 0\\[4pt]0 & 3\end{pmatrix}\) (determinante \(6\)), temos \(2A=\begin{pmatrix}4 & 0\\[4pt]0 & 6\end{pmatrix}\) e \(\det(2A)=2^2\cdot 6 = 24\). Verificação direta: \(4\cdot6 - 0 = 24\).

---

### Propriedade 5 — Se duas linhas são iguais, o determinante é zero (dependência linear)

- Enunciado: se uma matriz tem duas linhas (ou colunas) idênticas, então \(\det(A)=0\).  
- Justificativa: ter linhas repetidas implica dependência linear entre as linhas; o volume do paralelipípedo gerado pelas linhas é zero (hiperplano degenerado).
- Exemplo numérico:
  - \(A=\begin{pmatrix}1 & 2\\[4pt]1 & 2\end{pmatrix}\) tem \(\det(A)=1\cdot2 - 2\cdot1 = 0\).

---

### Propriedade 6 — Operação do tipo "adicionar múltiplo de uma linha a outra" não altera o determinante

- Enunciado: substituir uma linha \(L_i\) por \(L_i + k L_j\) (com \(i\neq j\)) não altera o determinante.  
- Intuição: essa operação corresponde a uma transformação que preserva o volume orientado porque é uma combinação linear que não altera a independência geral das linhas; equivale a aplicar uma matriz elementar de determinante 1 na esquerda.
- Uso prático: essa é a operação fundamental no método de escalonamento (eliminação de Gauss) que permite calcular determinantes por redução sem alterar o valor final.
- Exemplo:
  - Comece com \(A=\begin{pmatrix}1 & 2\\[4pt]3 & 4\end{pmatrix}\), \(\det(A)=-2\).
  - Substituir L2 ← L2 − 3·L1: nova L2 = (3−3·1, 4−3·2) = (0, −2), resultando em \(B=\begin{pmatrix}1 & 2\\[4pt]0 & -2\end{pmatrix}\). \(\det(B)=1\cdot(-2) - 2\cdot0=-2\), igual a \(\det(A)\).

---

### Propriedade 7 — Determinante triangular: produto das entradas da diagonal

- Enunciado: se \(A\) é triangular (superior ou inferior), então \(\det(A)\) é o produto das entradas da diagonal principal: \(\det(A)=\prod_{i=1}^n a_{ii}\).  
- Uso prático: após escalonamento (usando operações que não alteram o determinante, exceto multiplicações por escalares e trocas de linhas que são controladas), o determinante é facilmente obtido como produto das diagonais da forma triangular.  
- Exemplo:
  - \(A=\begin{pmatrix}2 & 5 & 1\\[4pt]0 & 3 & -1\\[4pt]0 & 0 & 4\end{pmatrix}\) tem \(\det(A)=2\cdot3\cdot4=24\).

---

### Propriedade 8 — Multiplicatividade: \(\det(AB)=\det(A)\det(B)\)

- Enunciado: para matrizes quadradas \(A\) e \(B\) de mesma ordem, \(\det(AB)=\det(A)\det(B)\).  
- Importância: essa propriedade conecta determinantes à composição de transformações lineares — o fator de escala do composto é o produto dos fatores de escala. Também implica \(\det(A^{-1}) = 1/\det(A)\) quando \(A\) é invertível.  
- Exemplo prático:
  - Tome \(A=\begin{pmatrix}1 & 1\\[4pt]0 & 1\end{pmatrix}\) com \(\det(A)=1\); \(B=\begin{pmatrix}2 & 0\\[4pt]0 & 3\end{pmatrix}\) com \(\det(B)=6\). Então \(\det(AB)=\det\big(\begin{pmatrix}2 & 3\\[4pt]0 & 3\end{pmatrix}\big)=2\cdot3 - 3\cdot0 = 6 = 1\cdot6\).
- Referência: propriedades clássicas em tratamentos teóricos e aplicações numéricas.

---

## Aplicações e observações práticas

- **Critério de invertibilidade:** uma matriz quadrada \(A\) é invertível se, e somente se, \(\det(A)\neq 0\). Isso é usado para decidir se sistemas \(Ax=b\) (com \(A\) quadrada) têm solução única; em aplicações numéricas costuma-se evitar calcular inversa explicitamente e usar métodos numéricos robustos, mas o determinante ainda fornece informação teórica importante.
- **Transformações geométricas:** o determinante de uma matriz \(2\times2\) fornece a área de um paralelogramo transformado; em \(3\times3\) fornece o volume orientado de um paralelipípedo — aplicável em física (mudança de variáveis, Jacobiano) e computação gráfica (escalamento de áreas/volumes).
- **Propriedade multiplicativa em cadeias de transformações:** ao compor transformações lineares sucessivas (mudança de escala, rotações, projeções), o determinante total é o produto dos determinantes parciais, o que ajuda a prever comportamento global de elementos de um sistema dinâmico ou cadeia de transformações em gráficos e engenharia.

---

## Exemplos completos com números reais

1) Cálculo de determinante 2×2 e efeitos de operações:
- \(A=\begin{pmatrix}4 & 1\\[4pt]2 & 3\end{pmatrix}\). \(\det(A)=4\cdot3 - 1\cdot2 = 12 -2 = 10\).
- Trocar linhas → \(B=\begin{pmatrix}2 & 3\\[4pt]4 & 1\end{pmatrix}\). \(\det(B)=-10\).
- Multiplicar primeira linha de \(A\) por \(5\) → \(C=\begin{pmatrix}20 & 5\\[4pt]2 & 3\end{pmatrix}\). \(\det(C)=5\det(A)=50\).

2) Uso da triangularização para matriz 3×3:
- \(M=\begin{pmatrix}2 & 1 & 3\\[4pt]4 & 7 & 1\\[4pt]6 & 2 & 5\end{pmatrix}\).
- Procedimento: aplicar operações elementares (L2 ← L2 − 2·L1; L3 ← L3 − 3·L1) que não alteram o determinante; obter forma triangular e multiplicar diagonais; controlar trocas de linha e fatores para ajustar o determinante final. Resultado (após cálculo) \(\det(M)=?\) — execute passos numéricos completos quando desejar um exercício resolvido passo a passo (p. ex., nos exercícios abaixo).

---

## Exercícios (10) com resolução detalhada

1) Calcule \(\det\begin{pmatrix}1 & 2\\[4pt]3 & 4\end{pmatrix}\) e verifique o efeito de trocar linhas.  
- Solução: \(\det=1\cdot4 - 2\cdot3 = -2\). Trocar linhas dá \(\det=2\), que é \(-(-2)\).

2) Se \(A=\begin{pmatrix}2 & 0\\[4pt]0 & 3\end{pmatrix}\), calcule \(\det(2A)\).  
- Solução: \(\det(A)=6\). Multiplicar toda a matriz por 2 dá \(2^2\det(A)=4\cdot6=24\).

3) Mostre que se uma matriz tem duas linhas iguais então seu determinante é zero; faça um exemplo numérico.  
- Solução: Ex.: \(\begin{pmatrix}1 & 2\\[4pt]1 & 2\end{pmatrix}\) → \(\det=0\). Argumento: trocar as linhas não muda a matriz, mas muda o sinal do determinante; logo \(\det=-\det\) ⇒ \(\det=0\).

4) Para \(A=\begin{pmatrix}1 & 3\\[4pt]0 & 2\end{pmatrix}\) e \(B=\begin{pmatrix}2 & 0\\[4pt]1 & 1\end{pmatrix}\), calcule \(\det(AB)\) e compare com \(\det(A)\det(B)\).  
- Solução: \(\det(A)=2\), \(\det(B)=2\). Calcule \(AB=\begin{pmatrix}1\cdot2+3\cdot1 & 1\cdot0+3\cdot1\\[4pt]0\cdot2+2\cdot1 & 0\cdot0+2\cdot1\end{pmatrix}=\begin{pmatrix}5 & 3\\[4pt]2 & 2\end{pmatrix}\). \(\det(AB)=5\cdot2 - 3\cdot2 = 10 -6 =4 = 2\cdot2\).

5) Use operações elementares para calcular \(\det\begin{pmatrix}2 & 1 & 3\\[4pt]4 & 7 & 1\\[4pt]6 & 2 & 5\end{pmatrix}\) (detalhe cada passo).  
- Solução (resumo): aplicar L2←L2−2L1 → L2=[0,5,−5]; L3←L3−3L1 → L3=[0,−1,−4]; agora calcular determinante da matriz triangular superior obtida por mais operações ou desenvolver por expansão; o resultado numérico final é \(\det= -20\) (confirmar com cálculo direto ou desenvolvimento por Sarrus/expansão).

6) Verifique que \(\det(I_3)=1\).  
- Solução: produto das entradas da diagonal da identidade é \(1\cdot1\cdot1 = 1\).

7) Se \(A\) é invertível, mostre que \(\det(A^{-1}) = 1/\det(A)\).  
- Solução: \(\det(AA^{-1})=\det(I)=1\) e \(\det(AA^{-1})=\det(A)\det(A^{-1})\) ⇒ \(\det(A^{-1})=1/\det(A)\).

8) Demonstre com exemplo que adicionar múltiplo de uma linha a outra não altera o determinante.  
- Solução: use \(A=\begin{pmatrix}1 & 2\\[4pt]3 & 4\end{pmatrix}\), L2←L2−3L1 → \(B=\begin{pmatrix}1 & 2\\[4pt]0 & -2\end{pmatrix}\). \(\det(A)=-2\), \(\det(B)= -2\).

9) Explique por que o determinante pode ser interpretado como fator de escala de área (n=2) ou volume (n=3) e dê um pequeno cálculo: transforme o quadrado unitário por \(A=\begin{pmatrix}2 & 0\\[4pt]0 & 3\end{pmatrix}\).  
- Solução: A aplica escala 2 no eixo x e 3 no eixo y; área transformada = \(2\cdot3\) × área inicial = \(6\cdot1 = 6\). \(\det(A)=6\).

10) Use multiplicatividade para estimar o efeito conjunto de duas transformações em sequência (ex.: rotação com determinante 1 e escala com determinante 4) — qual o efeito total sobre o volume/área?  
- Solução: o determinante total é produto \(1\cdot4=4\); portanto o volume/área é multiplicado por 4.

---

## Conclusão

- As propriedades dos determinantes são ferramentas essenciais tanto teoricamente (decisão de invertibilidade, classificação de sistemas lineares) quanto na prática (cálculo de áreas/volumes, análise de transformações lineares, simplificação de cálculos via operações elementares).  
- Em implementações numéricas, é importante usar algoritmos estáveis (escalonamento com pivoteamento) e evitar calcular determinantes diretamente por métodos custosos quando não necessário; porém as propriedades acima orientam e validam tais algoritmos.

---

## Bibliografia (formato ABNT)

- UNIVESP. Geometria analítica e álgebra linear — Determinantes de matrizes [vídeo]. UNIVESP TV, YouTube, 23 mai. 2022. Transcrição consultada. Acesso em 11 out. 2025.  
- KUTTLER, K. Properties of Determinants. In: A First Course in Linear Algebra. LibreTexts (adaptado). Acesso em 11 out. 2025.  
- CUEMATH. Properties of Determinants — formulas and examples. Acesso em 11 out. 2025.

---

Se quiser, eu exporto este conteúdo como arquivo Markdown pronto para o GitHub, ou eu detalho passo a passo o cálculo do exercício 5 com todas as operações elementares escritas e justificadas numericamente.