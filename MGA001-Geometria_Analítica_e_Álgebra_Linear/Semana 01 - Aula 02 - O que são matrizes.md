# O que são matrizes

## Introdução

Este material baseia-se no vídeo “O que são matrizes?” da disciplina Geometria Analítica e Álgebra Linear (UNIVESP). Ele apresenta a definição formal de matriz, tipos básicos (matriz linha, coluna), e aplicações práticas em computação gráfica e processamento de imagem, incluindo um exemplo de reflexo horizontal por reindexação de elementos.  

---

## Desenvolvimento

### Definição formal de matriz
- **Matriz** é uma tabela retangular de números reais organizada em *m* linhas e *n* colunas. Denotamos uma matriz por \(A\) e dizemos que \(A\) é uma matriz \(m \times n\) quando tem \(m\) linhas e \(n\) colunas.  
  - Notação: \(A = (a_{ij})\) onde \(a_{ij}\) representa o elemento na linha \(i\) e coluna \(j\).  
- Exemplo: uma matriz \(2 \times 3\)
  \[
  A = \begin{pmatrix}
  a_{11} & a_{12} & a_{13}\\[4pt]
  a_{21} & a_{22} & a_{23}
  \end{pmatrix}.
  \]
Informação apresentada no vídeo que explica essa estrutura básica e a notação de linhas/colunas.

### Tipos básicos de matrizes (citados no vídeo)
- **Matriz linha**: 1 linha e \(n\) colunas, forma \(1 \times n\).  
- **Matriz coluna**: \(m\) linhas e 1 coluna, forma \(m \times 1\).  
- **Matriz \(m \times n\)**: geral, \(m\) linhas e \(n\) colunas.  
O vídeo exemplifica esses tipos e mostra como identificar dimensões a partir do número de linhas e colunas.

### Aplicações: matrizes como representação de dados e imagens
- Cada linha pode representar um registro (por exemplo, exames de um paciente) e cada coluna uma variável (glicose, cálcio, etc.). Assim, grandes bases de dados podem ser tratadas como matrizes para armazenamento e processamento computacional.
- Em computação gráfica, uma imagem digital pode ser vista como uma matriz de pixels. Cada entrada representa o valor do pixel; em imagens binarias usamos apenas 0 (apagado) e 1 (aceso). Em imagens coloridas, cada pixel pode ter um valor numérico que representa cor ou intensidade em canais (por exemplo, RGB codificados por números).

### Exemplo prático do vídeo: desenho e reflexão de imagens por reindexação
- Situação: dado um array (matriz) que representa uma letra (ex.: letra E) em dimensão \(m \times n\), fazer reflexão horizontal.  
- Ideia mostrada: o elemento \(a_{i,j}\) da matriz original é movido para a posição \(b_{i,\, n+1-j}\) na matriz refletida.  
  - Fórmula de reindexação usada: \(b_{i,k} = a_{i,\, n+1-k}\) ou, visto do ponto de vista do elemento, \(b_{i,\,n+1-j} = a_{i,j}\).  
  - Interpretação: mantém a mesma linha \(i\) e "espelha" a coluna \(j\) em relação ao centro das colunas.  
- Exemplo numérico pequeno (5×7) do vídeo: se \(a_{1,1}=1\) (pixel ligado), ao refletir horizontalmente esse pixel vai para \(b_{1,\,7}\) quando \(n=7\) (porque \(n+1-1=7\)). O vídeo mostra como esse código rearranja os pixels para produzir a imagem refletida.

### Operações elementares (contexto introdutório e limites do conteúdo do vídeo)
- O vídeo avisa que operações com matrizes (adição, multiplicação, transpose, etc.) serão tratadas em seguida; aqui mantemos o foco na definição, tipos e aplicações iniciais, sem introduzir formalmente multiplicação de matrizes porque o vídeo reserva esse tópico para a próxima aula.  
- Complementando com referências didáticas, a manipulação de imagens com matrizes costuma envolver:
  - permutações de índices (como o reflexo descrito acima);  
  - restrição do domínio de valores (quantização) para reduzir a paleta de cores;  
  - operações ponto-a-ponto (aplicadas a cada entrada separadamente) e operações por janelas (filtros), temas que aparecem em materiais introdutórios de álgebra linear aplicada à computação gráfica.

---

## Exemplos resolvidos (passo a passo)

### Exemplo 1 — Identificar dimensão e classificar
Dada \(A = \begin{pmatrix}2 & 1 & 0\\ 5 & -1 & 4\end{pmatrix}\).  
- Fórmula: dimensões \(m \times n\). Aqui há 2 linhas e 3 colunas, logo \(A\) é uma matriz \(2\times3\).  
- Classificação: não é matriz linha (não tem 1 linha) nem matriz coluna (não tem 1 coluna); é uma matriz retangular.

### Exemplo 2 — Reflexão horizontal de matriz 3×4 (aplicando reindexação)
Considere
\[
A = \begin{pmatrix}
1 & 0 & 0 & 0\\[4pt]
0 & 1 & 1 & 0\\[4pt]
0 & 0 & 1 & 0
\end{pmatrix},
\]
\(m=3\), \(n=4\). Aplicamos \(b_{i,j'} = a_{i,\,n+1-j'}\).
- Para \(i=1\), coluna \(j'=1\): \(b_{1,1}=a_{1,4}=0\).  
  \(j'=2:\ b_{1,2}=a_{1,3}=0\).  
  \(j'=3:\ b_{1,3}=a_{1,2}=0\).  
  \(j'=4:\ b_{1,4}=a_{1,1}=1\).
- Repetir para todas as linhas produz:
\[
B=\begin{pmatrix}
0 & 0 & 0 & 1\\[4pt]
0 & 1 & 1 & 0\\[4pt]
0 & 1 & 0 & 0
\end{pmatrix}.
\]
Explicação: cada linha foi mantida; as colunas foram espelhadas.

### Exemplo 3 — Quantização simples (redução de paleta)
- Problema: transformar valores de 0–100 em 0–9 (reduzir paleta).  
- Operação: para cada elemento \(a_{ij}\), compute \(q_{ij} = \lfloor a_{ij}/10 \rfloor\).  
- Interpretação: o operador floor (parte inteira) reduz a granularidade, aproximando tons a uma paleta menor, conceito ilustrado no vídeo para converter imagens coloridas em menor número de cores.

---

## Conclusão

O vídeo introduz a ideia de matriz como uma estrutura organizada em linhas e colunas, apresenta exemplos práticos e mostra aplicações claras em computação gráfica, como representação de pixels e operações de reflexo por reindexação de elementos. Ele prepara o terreno para estudar operações entre matrizes (como multiplicação) que serão tratadas nas próximas aulas.

---

## Análise crítica

- Pontos fortes do vídeo: boa motivação com exemplos concretos (dados de uma clínica, pixels de imagens); demonstra ação prática (reflexo) que torna intuitivo o uso de índices de matrizes.  
- Limitação observada: o vídeo dá a ideia geral de aplicações, mas não formaliza algoritmos nem estimativas de custo computacional (por exemplo, complexidade de manipulação quando \(m,n\) são grandes). Materiais de apoio em álgebra linear e computação gráfica costumam complementar com detalhes sobre complexidade, armazenamento e operações vetorizadas para implementação eficiente.

---

## Sugestões de complementação

- Ler capítulos iniciais sobre matrizes em Nicholson para formalizar notação e propriedades básicas (definição, tipos e manipulações elementares).  
- Estudar exemplos práticos de manipulação de imagens com Python/NumPy (indexação, slicing, operações ponto-a-ponto) para ver como a reindexação é implementada de forma vetorizada e eficiente.  
- Revisar materiais didáticos sobre quantização de imagens e filtros básicos para conectar a teoria das matrizes com operações comuns em processamento de imagem.

---

## Exercícios (30) com resolução detalhada

Observação: todos os exercícios focam nos conceitos apresentados no vídeo: definição, identificação de dimensões, classificação de matrizes, reindexação (reflexão), representação de imagens por matrizes e operações simples por elemento.

1. Exercício 1 — Identificar dimensão  
   Dada \(A=\begin{pmatrix}1&2\\3&4\\5&6\end{pmatrix}\). Qual a dimensão de \(A\)?  
   Resolução: tem 3 linhas e 2 colunas ⇒ dimensão \(3\times2\).

2. Exercício 2 — Classificar tipo  
   \(B=\begin{pmatrix}7&8&9\end{pmatrix}\). É matriz linha, coluna ou retangular?  
   Resolução: possui 1 linha e 3 colunas ⇒ **matriz linha** (\(1\times3\)).

3. Exercício 3 — Classificar tipo  
   \(C=\begin{pmatrix}1\\2\\3\end{pmatrix}\). Tipo?  
   Resolução: 3 linhas e 1 coluna ⇒ **matriz coluna** (\(3\times1\)).

4. Exercício 4 — Reindexação de reflexo (simples)  
   Seja \(A=\begin{pmatrix}1&0&0\\0&1&0\end{pmatrix}\) com \(m=2,n=3\). Obtenha a reflexão horizontal \(B\) usando \(b_{i,j}=a_{i,n+1-j}\).  
   Resolução: \(n+1=4\). Para \(i=1\): \(b_{1,1}=a_{1,3}=0\), \(b_{1,2}=a_{1,2}=0\), \(b_{1,3}=a_{1,1}=1\). Para \(i=2\): \(b_{2,1}=a_{2,3}=0\), \(b_{2,2}=a_{2,2}=1\), \(b_{2,3}=a_{2,1}=0\). Logo \(B=\begin{pmatrix}0&0&1\\0&1&0\end{pmatrix}\).

5. Exercício 5 — Reflexão em matriz quadrada 4×4  
   Aplique o mapeamento \(b_{i,j}=a_{i,5-j}\) sobre  
   \(A=\begin{pmatrix}1&2&3&4\\5&6&7&8\\9&10&11&12\\13&14&15&16\end{pmatrix}\).  
   Resolução: Para cada linha, invertemos a ordem das colunas. Resultado:
   \(B=\begin{pmatrix}4&3&2&1\\8&7&6&5\\12&11&10&9\\16&15&14&13\end{pmatrix}\).

6. Exercício 6 — Verificação de manutenção de linha  
   Mostre que a operação \(b_{i,j}=a_{i,n+1-j}\) não altera o índice de linha.  
   Resolução: A expressão depende de \(i\) apenas na posição do elemento original \(a_{i,\cdot}\). Portanto, linha \(i\) de \(A\) corresponde à linha \(i\) de \(B\); só as colunas mudam por função de \(j\).

7. Exercício 7 — Programação conceitual (índice)  
   Escreva o laço análogo em pseudocódigo para criar \(B\) a partir de \(A\) (índices 1-based).  
   Resolução:
   ```
   para i de 1 até m
     para j de 1 até n
       B[i,j] = A[i, n+1 - j]
   ```
   Cada iteração copia um elemento para sua posição refletida.

8. Exercício 8 — Aplicação a imagem binária 5×7 (interpretação)  
   Explique por que uma matriz binária 5×7 pode representar uma letra em tela pequena.  
   Resolução: cada entrada corresponde a um pixel; 1 = pixel ligado, 0 = apagado. O arranjo de 1s forma o contorno da letra.

9. Exercício 9 — Quantização simples por elemento  
   Dada \(A\) com entradas em 0–100, defina \(q_{ij}=\lfloor a_{ij}/10 \rfloor\). Aplique a um exemplo \(a_{11}=88\).  
   Resolução: \(\lfloor 88/10 \rfloor = \lfloor 8.8 \rfloor = 8\). A entrada quantizada é 8.

10. Exercício 10 — Inversão do reflexo  
    Mostre que aplicar a reindexação \(b_{i,j}=a_{i,n+1-j}\) duas vezes recupera \(A\).  
    Resolução: aplicar de novo: \(c_{i,j}=b_{i,n+1-j} = a_{i,n+1 - (n+1 - j)} = a_{i,j}\). Logo operação é involutiva.

11. Exercício 11 — Contagem de elementos  
    Quantos elementos tem uma matriz \(m\times n\)?  
    Resolução: \(m\cdot n\) elementos.

12. Exercício 12 — Reconhecimento de padrão (linha e coluna)  
    Para \(A\) \(4\times4\), quais são os índices da primeira coluna?  
    Resolução: elementos \(a_{1,1}, a_{2,1}, a_{3,1}, a_{4,1}\).

13. Exercício 13 — Extração de uma submatriz (slicing)  
    Dada \(A\) \(3\times4\), explique como obter a submatriz formada pelas colunas 2 e 3.  
    Resolução: a submatriz \(C\) é \(m\times2\) com \(c_{i,1}=a_{i,2}\), \(c_{i,2}=a_{i,3}\) para \(i=1..m\).

14. Exercício 14 — Verificação numérica de reflexo (pequeno caso)  
    Tome \(A=\begin{pmatrix}1&0\\0&1\end{pmatrix}\). Aplique reflexo horizontal e verifique resultado.  
    Resolução: \(n=2\). \(B=\begin{pmatrix}0&1\\1&0\end{pmatrix}\); cada linha foi invertida.

15. Exercício 15 — Reflexo vertical (adaptação)  
    Proponha fórmula para reflexo vertical (espelhar em relação às linhas) e aplique a \(A\) do exercício 14.  
    Resolução: reflexo vertical: \(b_{i,j} = a_{m+1-i,j}\). Com \(m=2\), \(B=\begin{pmatrix}0&1\\1&0\end{pmatrix}\) (mesmo resultado para matriz identidade 2×2).

16. Exercício 16 — Transformação composta (horizontal + vertical)  
    Mostre que aplicar reflexo horizontal e depois vertical corresponde a rotacionar 180°?  
    Resolução: composição: \(c_{i,j}=a_{m+1-i, n+1-j}\), que é rotação de 180°, porque ambos índices são invertidos.

17. Exercício 17 — Identificação de índice central em colunas ímpares  
    Para \(n\) ímpar, qual coluna permanece fixa no reflexo horizontal?  
    Resolução: coluna \(j_0 = (n+1)/2\). Porque \(n+1 - j_0 = n+1 - (n+1)/2 = (n+1)/2 = j_0\).

18. Exercício 18 — Aplicação em matriz de cores (exemplo conceitual)  
    Se uma matriz contém valores de 0–255 (tons), explique efeito de reduzir para 0–15 por \(\lfloor a_{ij}/16\rfloor\).  
    Resolução: cada valor é mapeado a uma faixa de 16 tons; reduz paleta e diminui carregamento de cor, útil em compressão ou estilização.

19. Exercício 19 — Simetria da matriz (observação)  
    Se \(A\) é simétrica (\(a_{ij}=a_{ji}\)), o reflexo horizontal preserva simetria? Justifique.  
    Resolução: Reflexo horizontal pode quebrar simetria se \(m\neq n\) ou dependendo da posição; em geral, não preserva a condição \(a_{ij}=a_{ji}\) porque troca colunas sem trocar linhas. Ex.: \(A=\begin{pmatrix}0&1\\1&0\end{pmatrix}\) refletida horizontalmente dá \(\begin{pmatrix}1&0\\0&1\end{pmatrix}\) que é simétrica; mas outro exemplo pode alterar.

20. Exercício 20 — Exibição de máscara binária  
    Dada uma matriz binária 4×4 que representa um símbolo, explique como detectar se existe algum pixel ligado na borda esquerda (coluna 1).  
    Resolução: verificar se existe \(i\) tal que \(a_{i,1}=1\). Se sim, há pixel ligado na borda esquerda.

21. Exercício 21 — Permutação de colunas (generalização)  
    Defina mapeamento de permutação de colunas \(\pi\) e escreva a fórmula \(b_{i,j}=a_{i,\pi(j)}\). Explique quando \(\pi(j)=n+1-j\) dá reflexo.  
    Resolução: função \(\pi\) reordena colunas. Para reflexo, \(\pi(j)=n+1-j\). A estrutura de cópia é análoga à apresentada no vídeo.

22. Exercício 22 — Reflexo em imagem não quadrada  
    Apresente cuidado ao refletir matrizes retangulares; aplique em \(2\times5\).  
    Resolução: fórmula \(b_{i,j}=a_{i,n+1-j}\) funciona para qualquer \(n\); mantemos \(i\) e apenas alteramos o mapeamento das colunas.

23. Exercício 23 — Cálculo de armazenamento  
    Quantos bytes são necessários para armazenar uma imagem representada por uma matriz \(1024\times768\) com 1 byte por pixel?  
    Resolução: \(1024\cdot768 = 786432\) bytes ≈ 768 KB.

24. Exercício 24 — Translação por índices (deslocamento de coluna)  
    Defina operação de deslocamento à direita por \(k\) colunas: \(b_{i,j} = a_{i,\,j-k}\) (com preenchimento). Explique como implementar com índice modular ou preenchimento com zero.  
    Resolução: usar caso j-k fora de intervalo: preencher com 0 ou usar módulo \((j-k-1 \bmod n)+1\) para wrap-around.

25. Exercício 25 — Verificação de involução do reflexo geral  
    Prove que reindexação por \(\pi(j)=n+1-j\) é sua própria inversa.  
    Resolução: \(\pi(\pi(j))=n+1-(n+1-j)=j\), logo involutiva.

26. Exercício 26 — Uso de matriz para armazenamento de tabela de exames  
    Defina esquema: cada linha = paciente, colunas = exames. Como representar novos pacientes?  
    Resolução: adicionar nova linha à matriz (aumentar \(m\)). Em implementações reais, geralmente usa-se estrutura dinâmica (arrays/frames) que cresce por linhas.

27. Exercício 27 — Detecção de coluna inteira zero  
    Dada matriz \(A\), como detectar se existe coluna com todos elementos 0?  
    Resolução: verificar se para alguma \(j\): \(\forall i,\ a_{i,j}=0\). Implementação: soma de coluna igual a zero.

28. Exercício 28 — Composição de permutações (abstract)  
    Se \(\pi\) é permutação de colunas e \(\sigma\) outra, qual permutação resulta da aplicação de \(\sigma\) seguida de \(\pi\)?  
    Resolução: composição \(\pi\circ\sigma\) onde \((\pi\circ\sigma)(j)=\pi(\sigma(j))\).

29. Exercício 29 — Exemplo numérico de quantização seguida de reflexo  
    Dada \(A=\begin{pmatrix}88&45\\67&12\end{pmatrix}\), quantize por \(q=\lfloor a/10\rfloor\) e depois reflita horizontalmente. Mostre passos.  
    Resolução: quantização: \(\begin{pmatrix}8&4\\6&1\end{pmatrix}\). Reflexo horizontal (\(n=2\)): troca colunas → \(\begin{pmatrix}4&8\\1&6\end{pmatrix}\).

30. Exercício 30 — Relacione matrizes e vetores (conceito introdutório)  
    Explique como uma **matriz coluna** \(m\times1\) pode representar um vetor em \(\mathbb{R}^m\) e por que isso é útil para representar imagens (cada coluna ou linha como vetor-canal).  
    Resolução: vetor em \(\mathbb{R}^m\) é uma sequência ordenada de \(m\) números; representar como matriz coluna permite aplicar operações matriciais (por exemplo, transformar canais, combinar colunas), facilitando manipulação linear e algoritmos vetorizados em software científico.

---

## Bibliografia (formato ABNT)

- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015. Acesso consultado em 11 out. 2025.  
- UNIVESP. Geometria analítica e álgebra linear — O que são matrizes? [vídeo]. UNIVESP TV, YouTube, maio 2022. Transcrição utilizada para este material. Acesso em 11 out. 2025.  
- Aula “Matrizes — parte 1”, UNIVESP (playlist e materiais de apoio). Acesso em 11 out. 2025.  
- Definição de matrizes numéricas. e-Aulas USP. Acesso em 11 out. 2025.

---

## Materiais complementares (selecionados)

- Nicholson, W. Keith. Álgebra Linear. AMGH Editora, 2. ed., 2015. (Capítulos iniciais sobre definição e manipulação de matrizes).  
- UNIVESP — página de vídeos de apoio e materiais do curso (módulos sobre matrizes e operações). Acesso em 11 out. 2025.  
- e-Aulas USP — “Definição de matrizes numéricas” (aula complementar sobre construção de matrizes a partir de tabelas de informação). Acesso em 11 out. 2025.

---

Observação final: este material segue estritamente o conteúdo do vídeo atual (definição e aplicações iniciais de matrizes, uso para imagens e reindexação para reflexo) e complementa com referências didáticas confiáveis para aprofundamento; tópicos como multiplicação de matrizes e operações algébricas serão estudados na próxima aula, conforme o próprio vídeo indica.