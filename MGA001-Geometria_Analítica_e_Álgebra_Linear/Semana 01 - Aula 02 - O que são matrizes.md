# O que são matrizes

### Introdução

Este material foi produzido a partir do vídeo "O que são matrizes?" da disciplina Geometria Analítica e Álgebra Linear (transcrição do vídeo usada como base) e revisado para garantir compatibilidade com GitHub Markdown e navegadores comuns. Apresenta definição, tipos básicos, aplicações em processamento de dados e imagens, a operação de reflexão por reindexação mostrada no vídeo, exemplos resolvidos, análise crítica e exercícios com soluções passo a passo.

---

## Desenvolvimento

### Definição formal de matriz

- Definição (texto): uma **matriz** é uma tabela retangular de números reais com m linhas e n colunas. Denotamos uma matriz por A e dizemos que A é uma matriz m × n quando tem m linhas e n colunas. Essa definição e notação são apresentadas no vídeo como base da aula.

- Notação compatível com Markdown (bloco monoespaçado):
```
A = [ a_11  a_12  ...  a_1n
      a_21  a_22  ...  a_2n
      ...
      a_m1  a_m2  ...  a_mn ]
```
Aqui `a_ij` representa o elemento na i-ésima linha e j-ésima coluna.

(Referência ao conteúdo expositivo do vídeo sobre a definição formal).

---

### Tipos básicos de matrizes

- **Matriz linha**: 1 × n, exemplo:
```
L = [ b_11  b_12  ...  b_1n ]
```
- **Matriz coluna**: m × 1, exemplo:
```
C = [ c_11
      c_21
      ...
      c_m1 ]
```
- **Matriz retangular**: m × n com m ≠ n (ou igual) — representação geral acima. O vídeo mostra exemplos simples de matriz linha, coluna e matrizes 2×3 para ilustrar os conceitos básicos.

---

### Matrizes como representação de dados e de imagens

- Estruturas tabulares: cada linha pode representar um registro (por exemplo, um paciente), cada coluna uma variável (ex.: glicose, cálcio). Matrizes facilitam armazenamento, indexação e processamento em sistemas computacionais; o vídeo utiliza a analogia de uma clínica com muitos exames para justificar o uso de matrizes em computação de dados.

- Imagens como matrizes de pixels:
  - Matriz binária: valores 0/1 onde 1 = pixel ligado e 0 = pixel apagado. Exemplo mostrado no vídeo: uma matriz 5 × 7 com zeros e uns que desenha uma letra (p.ex., letra E) na tela cuando interpretada como pixels.
  - Imagens com tons: cada entrada corresponde a um valor numérico (ex.: 0–255) ou a canais (R, G, B) representados por três matrizes paralelas.
  - Observação prática do vídeo: com o aumento do número de pixels e paleta de cores, a dimensão das matrizes e a variedade de valores crescem, mas o princípio de representar imagens por matrizes permanece.

---

### Reflexão horizontal por reindexação (exemplo prático do vídeo)

- Objetivo: espelhar (refletir) uma imagem horizontalmente usando apenas operação de reindexação dos elementos da matriz.

- Regra de reindexação (texto sem LaTeX):
  - Se A é m × n, definir B por:
    ```
    B[i, j] = A[i, n + 1 - j]
    ```
  - Interpretação: mantemos a mesma linha `i` e colocamos na coluna `j` de B o elemento que estava na coluna `n+1-j` de A. O vídeo explicita precisamente essa fórmula e a aplica a exemplos (p.ex., A[1,1] → B[1,n]).

- Observações:
  - A operação preserva o índice de linha; apenas as colunas são permutadas.
  - Aplicável tanto para matrizes pequenas (5×7 no exemplo do vídeo) quanto para imagens grandes (n pode ser 1000, 1.000.000 etc.), a fórmula continua válida e é implementada por um algoritmo simples que percorre todos os índices.

---

### Quantização simples (redução da paleta de cores)

- Idéia apresentada no vídeo (explicada): para reduzir o número de cores (por exemplo, transformar tons 0–100 em 0–10), aplica-se uma operação por elemento que elimina ordens de grandeza (por exemplo, manter apenas as dezenas). Um procedimento simples:
  - Para cada elemento `a_ij` em 0..100, definir:
    ```
    q_ij = floor(a_ij / 10)
    ```
  - Exemplo: `a_11 = 88` → `q_11 = floor(88/10) = 8`.
- O vídeo descreve essa abordagem como ideia geral para converter imagens coloridas em um número menor de tons, sem detalhar algoritmos avançados de processamento de imagem.

---

## Exemplos resolvidos (detalhados e compatíveis)

### Exemplo 1 — Identificar dimensão e classificar
Dada a matriz:
```
A = [ 2  1  0
      5 -1  4 ]
```
- Contagem: 2 linhas, 3 colunas → A é 2 × 3 (matriz retangular).

### Exemplo 2 — Reflexão horizontal em 3 × 4 (passo a passo)
Dada:
```
A = [1 0 0 0
     0 1 1 0
     0 0 1 0]
```
- m = 3, n = 4. Usamos B[i,j] = A[i, 4 + 1 - j] = A[i, 5 - j].
- Linha 1:
  - j=1: B[1,1] = A[1,5-1] = A[1,4] = 0
  - j=2: B[1,2] = A[1,5-2] = A[1,3] = 0
  - j=3: B[1,3] = A[1,5-3] = A[1,2] = 0
  - j=4: B[1,4] = A[1,5-4] = A[1,1] = 1
- Linha 2:
  - j=1: B[2,1] = A[2,4] = 0
  - j=2: B[2,2] = A[2,3] = 1
  - j=3: B[2,3] = A[2,2] = 1
  - j=4: B[2,4] = A[2,1] = 0
- Linha 3:
  - j=1: B[3,1] = A[3,4] = 0
  - j=2: B[3,2] = A[3,3] = 1
  - j=3: B[3,3] = A[3,2] = 0
  - j=4: B[3,4] = A[3,1] = 0
- Resultado:
```
B = [0 0 0 1
     0 1 1 0
     0 1 0 0]
```
(Procedimento idêntico ao mostrado no vídeo para exemplos de reflexão).

### Exemplo 3 — Quantização (passo)
- Dado `a_11 = 88`, aplicar `q_11 = floor(a_11 / 10) = 8`. Repetir para todos os elementos da matriz para reduzir a paleta.

---

## Conclusão

- O vídeo introduz a definição de matriz, tipos básicos (linha, coluna, retangular), aplicações práticas em armazenamento de dados e imagens e demonstra uma operação concreta (reflexão horizontal por reindexação) que ilustra como algoritmos simples usam matrizes para manipular imagens.
- Os conceitos mostrados são suficientes para entender por que matrizes são a estrutura natural para problemas tabulares e para processamento de imagem, preparando o caminho para operações matriciais formais (adição, transposta, multiplicação) apresentadas em aulas seguintes.

---

## Análise crítica

- Pontos fortes: o vídeo usa exemplos concretos que facilitam a intuição (ex.: matrizes para exames clínicos; matrizes binárias para desenho de letras; reflexão por reindexação) e mostra como uma regra simples (B[i,j] = A[i, n+1-j]) resolve problemas práticos de manipulação de imagem.
- Limitações: o vídeo apresenta a ideia geral sem detalhar aspectos de eficiência e complexidade para matrizes grandes nem as implicações de desempenho em implementações vetorizadas (p.ex., uso de operações em blocos em bibliotecas como NumPy). Não há detalhamento de casos especiais (pivôs, memória, paralelização) — tópicos que são complementares para aplicações em larga escala.

---

## Sugestões de complementação

- Ler os capítulos iniciais sobre definição e notação de matrizes em um livro didático de Álgebra Linear (p.ex., Nicholson) para formalizar a notação e propriedades básicas.
- Implementar reindexação e quantização com Python + NumPy para experimentar com imagens reais e observar diferenças de desempenho entre loops explícitos e operações vetorizadas.
- Explorar operações de janelamento (filtros), conversão para escala de cinza (métodos ponderados por canais R,G,B) e compressão simples para entender aplicações práticas além da reindexação mostrada no vídeo.

---

## Exercícios (30) com resolução detalhada

Observação: todos os exercícios usam notação textual compatível com Markdown e cobrem definição de matriz, identificação de dimensões, classificação, reindexação (reflexão), submatrizes, quantização e operações elementares simples.

1. Exercício 1 — Identificar dimensão  
   Enunciado: Dada A =  
   ```
   [1 2
    3 4
    5 6]
   ```
   Qual a dimensão de A?  
   Resolução: A tem 3 linhas e 2 colunas → dimensão 3 × 2.

2. Exercício 2 — Classificar tipo  
   Enunciado: B = [7 8 9]. É matriz linha, coluna ou retangular?  
   Resolução: B tem 1 linha e 3 colunas → matriz linha (1 × 3).

3. Exercício 3 — Classificar tipo  
   Enunciado: C =  
   ```
   [1
    2
    3]
   ```
   Tipo?  
   Resolução: C tem 3 linhas e 1 coluna → matriz coluna (3 × 1).

4. Exercício 4 — Reflexão horizontal (simples)  
   Enunciado: A =  
   ```
   [1 0 0
    0 1 0]
   ```
   com m=2, n=3. Obtenha B usando B[i,j] = A[i, n + 1 - j].  
   Resolução: n + 1 = 4. Para i=1: B[1,1]=A[1,3]=0; B[1,2]=A[1,2]=0; B[1,3]=A[1,1]=1. Para i=2: B[2,1]=A[2,3]=0; B[2,2]=A[2,2]=1; B[2,3]=A[2,1]=0. Logo B =  
   ```
   [0 0 1
    0 1 0]
   ```

5. Exercício 5 — Reflexão horizontal em 4 × 4  
   Enunciado: A =  
   ```
   [ 1  2  3  4
     5  6  7  8
     9 10 11 12
    13 14 15 16 ]
   ```
   Obtenha B com B[i,j] = A[i, 4 + 1 - j].  
   Resolução: para cada linha invertemos a ordem das colunas (j → 5 - j). Resultado:
   ```
   B = [ 4  3  2  1
         8  7  6  5
        12 11 10  9
        16 15 14 13 ]
   ```

6. Exercício 6 — Propriedade de manutenção de linha  
   Enunciado: Mostre que B[i,j] = A[i, n + 1 - j] preserva o índice de linha.  
   Resolução: A fórmula usa o mesmo índice i em A e B; portanto, elementos da linha i de A são redistribuídos apenas entre colunas da mesma linha i em B. Conclusão: linhas são preservadas.

7. Exercício 7 — Pseudocódigo para reindexação (índices 1-based)  
   Enunciado: Escreva pseudocódigo que constrói B a partir de A.  
   Resolução:
   ```
   para i de 1 até m:
     para j de 1 até n:
       B[i,j] = A[i, n + 1 - j]
   ```
   Explicação: cada par (i,j) visita exatamente um elemento de A e o copia para a posição refletida em B.

8. Exercício 8 — Interpretação de matriz binária 5 × 7  
   Enunciado: Por que uma matriz 5×7 binária representa uma letra?  
   Resolução: cada posição (i,j) corresponde a um pixel; 1 indica pixel ligado; o padrão de 1s forma o contorno/traço que o observador interpreta como letra.

9. Exercício 9 — Quantização por elemento (exemplo)  
   Enunciado: Dado a_11 = 88, aplicar q_ij = floor(a_ij / 10).  
   Resolução: floor(88/10) = floor(8.8) = 8. Logo q_11 = 8.

10. Exercício 10 — Involutividade do reflexo  
    Enunciado: Mostre que aplicar a reindexação duas vezes recupera A.  
    Resolução: aplicar B[i,j] = A[i, n+1-j] e depois C[i,j] = B[i, n+1-j] dá C[i,j] = A[i, n+1-(n+1-j)] = A[i,j]. Conclusão: a operação é sua própria inversa.

11. Exercício 11 — Contagem de elementos  
    Enunciado: Quantos elementos há em uma matriz m × n?  
    Resolução: produto m · n (m linhas vezes n colunas).

12. Exercício 12 — Índices da primeira coluna  
    Enunciado: Para A 4×4, quais elementos formam a primeira coluna?  
    Resolução: a_11, a_21, a_31, a_41 (índices (1,1), (2,1), (3,1), (4,1)).

13. Exercício 13 — Extração de submatriz (slicing)  
    Enunciado: Dada A (3×4), como obter submatriz com colunas 2 e 3?  
    Resolução: construir C (3×2) com C[i,1] = A[i,2] e C[i,2] = A[i,3] para i = 1..3; é cópia direta por índice.

14. Exercício 14 — Reflexo da matriz identidade 2×2  
    Enunciado: A =  
    ```
    [1 0
     0 1]
    ```
    Aplique reflexão horizontal.  
    Resolução: troca de colunas → B =  
    ```
    [0 1
     1 0]
    ```

15. Exercício 15 — Reflexo vertical (fórmula)  
    Enunciado: Proponha fórmula para reflexo vertical e aplique à A do exercício 14.  
    Resolução: reflexo vertical: B[i,j] = A[m + 1 - i, j]. Com m = 2, B =  
    ```
    [0 1
     1 0]
    ```
    (no caso da identidade 2×2, resultado coincide com o reflexo horizontal).

16. Exercício 16 — Composição: horizontal + vertical → rotação 180°  
    Enunciado: Mostre que aplicar reflexo horizontal e depois vertical é rotação de 180°.  
    Resolução: composição: C[i,j] = B[m+1-i, n+1-j] = A[m+1-i, n+1-(n+1-j)] = A[m+1-i, j] aplicado após horizontal produz A[m+1-i, n+1-j], que é rotação 180° (ambos índices invertidos).

17. Exercício 17 — Coluna fixa para n ímpar  
    Enunciado: Para n ímpar, qual coluna fica fixa pela reflexão horizontal?  
    Resolução: coluna central j0 = (n + 1) / 2, pois n + 1 - j0 = j0.

18. Exercício 18 — Redução de paleta 0–255 → 0–15  
    Enunciado: Explique efeito de mapear v → floor(v / 16).  
    Resolução: cada faixa de 16 valores originais é mapeada para um único valor 0..15; reduz variabilidade e tamanho efetivo da paleta, útil para compressão ou estilização.

19. Exercício 19 — Reflexo e simetria de matriz  
    Enunciado: Se A é simétrica (a_ij = a_ji), o reflexo horizontal preserva simetria?  
    Resolução: em geral não. Exemplo: A = [ [0,1],[1,0] ] é simétrica; reflexo horizontal dá B = [ [1,0],[0,1] ], que também é simétrica neste caso. Mas para matrizes não-quadradas ou outros padrões, a simetria pode ser perdida porque a operação altera apenas colunas.

20. Exercício 20 — Detectar pixel ligado na borda esquerda  
    Enunciado: Como detectar se há pixel ligado na coluna 1?  
    Resolução: verificar existência de i tal que A[i,1] = 1; equivalem a soma da coluna 1 ser ≥ 1.

21. Exercício 21 — Permutação geral de colunas  
    Enunciado: Defina B[i,j] = A[i, π(j)]. Explique caso π(j) = n + 1 - j.  
    Resolução: π é permutação das colunas; para π(j) = n + 1 - j obtemos reflexo horizontal; permutações compõem-se por função composta.

22. Exercício 22 — Reflexo em matriz retangular 2×5  
    Enunciado: Aplique B[i,j] = A[i, 5 + 1 - j] a exemplo retangular.  
    Resolução: mesma fórmula; exemplo concreto:
    ```
    A = [1 2 3 4 5
         6 7 8 9 10]
    ```
    B =
    ```
    [5 4 3 2 1
     10 9 8 7 6]
    ```

23. Exercício 23 — Cálculo de armazenamento (1 byte por pixel)  
    Enunciado: Quantos bytes para imagem 1024×768?  
    Resolução: 1024 · 768 = 786432 bytes ≈ 768 KB (768 KiB ≈ 786432 bytes).

24. Exercício 24 — Deslocamento de coluna (shift) por k posições  
    Enunciado: Defina B[i,j] = A[i, j - k] (com preenchimento). Como tratar índices fora?  
    Resolução: duas opções: preencher com zero quando j - k < 1; ou usar wrap-around com índice modular: source = ((j - k - 1) mod n) + 1.

25. Exercício 25 — Provar que π(j) = n + 1 - j é involução  
    Enunciado: Prove que π ∘ π = id.  
    Resolução: π(π(j)) = n + 1 - (n + 1 - j) = j, portanto π é sua própria inversa.

26. Exercício 26 — Esquema de armazenamento de exames (linhas = pacientes)  
    Enunciado: Como representar novos pacientes?  
    Resolução: adicionar nova linha (incrementar m); em implementações práticas usa-se estruturas que suportam crescimento (dataframe, arrays dinâmicos).

27. Exercício 27 — Detectar coluna inteira zero  
    Enunciado: Como verificar existência de coluna com todos elementos 0?  
    Resolução: para cada coluna j verificar se ∀i, A[i,j] = 0 (p.ex., somar coluna e testar se soma = 0).

28. Exercício 28 — Composição de permutações de colunas  
    Enunciado: Se aplico σ depois π, qual permutação ocorre?  
    Resolução: permutação resultante é π ∘ σ (j ↦ π(σ(j))). Ordem importa (não comutam em geral).

29. Exercício 29 — Quantização seguida de reflexão (numérico)  
    Enunciado: A =  
    ```
    [88 45
     67 12]
    ```
    Quantize por q = floor(a/10) e depois reflita horizontalmente.  
    Resolução: quantização →  
    ```
    Q = [8 4
         6 1]
    ```
    reflexão (n = 2) troca colunas →  
    ```
    B = [4 8
         1 6]
    ```

30. Exercício 30 — Matriz coluna como vetor em R^m (conceito)  
    Enunciado: Explique por que matriz coluna m×1 representa vetor em R^m e utilidade para imagens.  
    Resolução: vetor em R^m é sequência ordenada de m números; representá-lo como coluna permite usar operações matriciais (transformações lineares, combinações) e facilita representar canais ou linhas/colunas de uma imagem como vetores para processamento vetorizado.

---

## Bibliografia (formato ABNT)

- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015. Acesso em 11 out. 2025.  
- UNIVESP. Geometria Analítica e Álgebra Linear — O que são matrizes? [vídeo]. UNIVESP TV, YouTube, 9 maio 2022. Transcrição usada. Acesso em 11 out. 2025.  
- e-AULAS USP. Definição de matrizes numéricas. Acesso em 11 out. 2025.

---

## Materiais complementares

- NICHOLSON, W. Keith. Álgebra Linear. AMGH Editora, 2. ed., 2015. (Capítulos iniciais sobre definição e notação de matrizes).  
- UNIVESP — página do curso e materiais de apoio (módulos sobre matrizes e operações). Acesso em 11 out. 2025.  
- Tutoriais de NumPy para manipulação de arrays e imagens (busca online recomendada para material atualizado).  

---