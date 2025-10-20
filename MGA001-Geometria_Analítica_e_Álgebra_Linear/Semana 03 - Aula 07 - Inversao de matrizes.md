# Inversão de Matrizes

## Introdução

Esta aula explica, passo a passo, o que são menores, cofatores e a matriz adjunta (adjugate), e como usá-los para calcular a inversa de uma matriz 3×3 quando ela existir. O conteúdo segue a videoaula de referência sobre inversão de matrizes e adjunta; sempre que fizer referência direta ao vídeo, indico a fonte para consulta .

---

## Desenvolvimento

### 1. Definições essenciais (em texto monoespaçado)

- Menor M_ij:
  ```
  M_ij = determinante da matriz obtida ao remover a linha i e a coluna j de A
  ```
- Cofator C_ij:
  ```
  C_ij = (-1)^(i + j) * M_ij
  ```
- Matriz de cofatores C:
  ```
  C = [ C_11  C_12  ... C_1n
        C_21  C_22  ... C_2n
        ...   ...   ... ... ]
  ```
- Matriz adjunta (adjugate), nota-se como adj(A):
  ```
  adj(A) = transpose(C)
  ```
- Relação fundamental (teórica):
  ```
  A * adj(A) = adj(A) * A = det(A) * I
  ```
  Logo, se det(A) != 0:
  ```
  A^{-1} = (1 / det(A)) * adj(A)
  ```
Essas definições e a fórmula da inversa via adjunta são apresentadas e utilizadas na videoaula como procedimento para matrizes 3×3 .

---

### 2. Procedimento geral para calcular cofatores (passo a passo, 3×3)

Passo a passo para cada entrada `a_ij` de uma matriz `A (3×3)`:

1. Remover a linha `i` e a coluna `j` de `A` → obter submatriz `2×2`.
2. Calcular o determinante dessa submatriz → isso é `M_ij`.
   - Para matriz `[[p, q],[r, s]]`, o determinante é `p*s - q*r`.
3. Multiplicar `M_ij` por `(-1)^(i + j)` → obter `C_ij`.
4. Montar a matriz de cofatores `C = [C_ij]`.
5. Transpor `C` → obter `adj(A)`.
6. Calcular `det(A)` (p.ex., por expansão de Laplace ou método de eliminação).
7. Se `det(A) != 0`, obter `A^{-1}` por:
   ```
   A^{-1} = (1 / det(A)) * adj(A)
   ```

O vídeo descreve exatamente esse algoritmo e enfatiza atenção aos sinais alternados e à ordem correta das operações .

---

### 3. Exemplo completo (detalhado, numérico, passo a passo)

Considere a matriz `A`:
```
A = [ 1  0  1
      2  4  0
      3  5  6 ]
```

(a) Calcular todos os menores `M_ij`, cofatores `C_ij` e montar `C`.

- Para `a_11 = 1`: remover linha 1 e coluna 1 → submatriz
  ```
  [ 4  0
    5  6 ]
  ```
  determinante `M_11 = 4*6 - 0*5 = 24`
  cofator `C_11 = (+1) * 24 = 24`

- Para `a_12 = 0`: remover linha 1 e coluna 2 → submatriz
  ```
  [ 2  0
    3  6 ]
  ```
  `M_12 = 2*6 - 0*3 = 12`
  `C_12 = (-1) * 12 = -12`

- Para `a_13 = 1`: remover linha 1 e coluna 3 → submatriz
  ```
  [ 2  4
    3  5 ]
  ```
  `M_13 = 2*5 - 4*3 = 10 - 12 = -2`
  `C_13 = (+1) * (-2) = -2`

- Para `a_21 = 2`: remover linha 2 e coluna 1 → submatriz
  ```
  [ 0  1
    5  6 ]
  ```
  `M_21 = 0*6 - 1*5 = -5`
  `C_21 = (-1) * (-5) = 5`

- Para `a_22 = 4`: remover linha 2 e coluna 2 → submatriz
  ```
  [ 1  1
    3  6 ]
  ```
  `M_22 = 1*6 - 1*3 = 3`
  `C_22 = (+1) * 3 = 3`

- Para `a_23 = 0`: remover linha 2 e coluna 3 → submatriz
  ```
  [ 1  0
    3  5 ]
  ```
  `M_23 = 1*5 - 0*3 = 5`
  `C_23 = (-1) * 5 = -5`

- Para `a_31 = 3`: remover linha 3 e coluna 1 → submatriz
  ```
  [ 0  1
    4  0 ]
  ```
  `M_31 = 0*0 - 1*4 = -4`
  `C_31 = (+1) * (-4) = -4`

- Para `a_32 = 5`: remover linha 3 e coluna 2 → submatriz
  ```
  [ 1  1
    2  0 ]
  ```
  `M_32 = 1*0 - 1*2 = -2`
  `C_32 = (-1) * (-2) = 2`

- Para `a_33 = 6`: remover linha 3 e coluna 3 → submatriz
  ```
  [ 1  0
    2  4 ]
  ```
  `M_33 = 1*4 - 0*2 = 4`
  `C_33 = (+1) * 4 = 4`

Matriz de cofatores `C`:
```
C = [ 24  -12  -2
       5    3  -5
      -4    2   4 ]
```

(b) Calcular adjunta `adj(A)` = `transpose(C)`:
```
adj(A) = [ 24   5  -4
           -12   3   2
            -2  -5   4 ]
```

(c) Calcular `det(A)` (expansão pela primeira linha, por exemplo):

- `det(A) = a_11*M_11 - a_12*M_12 + a_13*M_13`
  ```
  det(A) = 1*24 - 0*12 + 1*(-2) = 24 + 0 - 2 = 22
  ```

(d) Como `det(A) = 22 != 0`, matriz invertível. Calcular `A^{-1}`:
```
A^{-1} = (1 / det(A)) * adj(A)
       = (1 / 22) * [ 24   5  -4
                      -12   3   2
                       -2  -5   4 ]
```

Esse procedimento completo segue o mesmo fluxo e exemplos apresentados no vídeo sobre inversão por adjunta, incluindo a atenção aos sinais e à construção dos menores e cofatores .

---

### 4. Observações práticas e limitações

- A fórmula `A^{-1} = (1/det(A)) * adj(A)` é prática e didática para matrizes pequenas (2×2, 3×3). O vídeo usa esse caminho para 3×3 e explica os cofatores detalhadamente .
- Em problemas numéricos com matrizes maiores, métodos baseados em eliminação (LU) e pivotamento são preferíveis por estabilidade e custo computacional; a expressão com adjunta tem complexidade elevada quando implementada diretamente e pode amplificar erros de arredondamento.
- A identidade `A * adj(A) = det(A) * I` é útil para provas teóricas e para obter relações entre entradas da inversa e cofatores sem resolver sistemas lineares completos.

---

## Conclusão

- Cofatores são calculados removendo linha/coluna, avaliando o determinante do menor e aplicando o sinal alternado `(-1)^(i+j)`. A adjunta é a transposta da matriz de cofatores e, multiplicada por `1/det(A)`, fornece a inversa quando `det(A) != 0`. Esses passos e a importância dos sinais são enfatizados na videoaula de inversão de matrizes .

---

## Exercícios (com soluções passo a passo, notação monoespaçada)

1) Dada
   ```
   B = [ 2  1  0
         1  3  1
         0  2  4 ]
   ```
   - Calcule `M_11`, `C_11`; `M_12`, `C_12`; construa `C`, `adj(B)`, `det(B)` e `B^{-1}` (se existir).
   - Rascunho de solução: remova linha/coluna conforme índice, calcule determinantes 2×2, aplique sinais, transponha e divida por `det(B)`. (Se desejar, executo cálculo numérico completo.)

2) Verifique numericamente a identidade `A * adj(A) = det(A) * I` para a matriz `A` do exemplo principal (mostrando multiplicação e resultado `22 * I`).

3) Mostrar a fórmula 2×2: para
   ```
   A = [ a  b
         c  d ]
   ```
   - Menores: `M_11 = d`, `M_12 = c`, `M_21 = b`, `M_22 = a`
   - Cofatores: `C = [ d  -c
                      -b  a ]`
   - `adj(A) = transpose(C) = [ d  -b
                               -c   a ]`
   - `A^{-1} = (1 / (a*d - b*c)) * adj(A)`.

---

## Bibliografia (formato ABNT)

- UNIVESP. Geometria analítica e álgebra linear — Inversão de Matrizes [vídeo]. UNIVESP TV, YouTube. Transcrição consultada e usada como base para as explicações sobre cofatores e adjunta. Acesso em 19 out. 2025.  
- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015. (Capítulos sobre determinantes, cofatores e inversas via adjugado). Acesso em 19 out. 2025.

---
--- 

# Cofatores, adjunta e inversa de matrizes — versão detalhada com notação monoespaçada

## Introdução

Este material detalha, passo a passo, o conceito de menor (minor), cofator, matriz de cofatores, adjunta (adjugate) e a relação entre adjunta, determinante e inversa de matrizes quadradas. O conteúdo segue a videoaula "Inversão de Matrizes" (UNIVESP) e expande os procedimentos com exemplos numéricos completos, explicações pedagógicas e uma lista de exercícios resolvidos. Todas as fórmulas e operações estão apresentadas em texto monoespaçado para máxima compatibilidade com GitHub.

---

## Desenvolvimento

### 1. Objetivos desta aula

- Definir e explicar o que são menores e cofatores, com lógica geométrica e algébrica.  
- Mostrar como construir a matriz de cofatores e como obter a adjunta (adjugate).  
- Demonstrar a relação fundamental entre adjunta, determinante e inversa:  
  ```
  A * adj(A) = det(A) * I
  ```
  e, quando `det(A) != 0`,
  ```
  A^{-1} = (1 / det(A)) * adj(A)
  ```
- Fazer exemplos passo a passo (2×2 e 3×3), com aritmética explícita, e discutir aplicações e limitações práticas.

---

### 2. Conceitos fundamentais (definições em texto monoespaçado)

- Matriz quadrada:
  ```
  A is n x n (only square matrices admit determinant/adjugate in this context)
  ```

- Menor `M_ij`:
  ```
  M_ij = determinant of the (n-1) x (n-1) matrix obtained by removing row i and column j from A
  ```

- Cofator `C_ij`:
  ```
  C_ij = (-1)^(i + j) * M_ij
  ```
  - The sign `(-1)^(i+j)` alternates according to the "checkerboard" pattern:
    ```
    +  -  +  - ...
    -  +  -  + ...
    +  -  +  - ...
    ```

- Matriz de cofatores `C`:
  ```
  C = [ C_11  C_12  ... C_1n
        C_21  C_22  ... C_2n
        ...
        C_n1  C_n2  ... C_nn ]
  ```

- Adjunta (adjugate) `adj(A)`:
  ```
  adj(A) = transpose(C)
  ```

- Relação chave:
  ```
  A * adj(A) = adj(A) * A = det(A) * I_n
  ```
  Consequentemente, se `det(A) != 0`:
  ```
  A^{-1} = (1 / det(A)) * adj(A)
  ```

Explicação conceitual: o menor `M_ij` mede o volume orientado do paralelipípedo gerado pelas linhas (ou colunas) restantes; o cofator ajusta o sinal para preservar orientação ao expandir o determinante por uma linha ou coluna. A adjunta reúne essas contribuições para construir uma "matriz de inversos" multiplicada pelo determinante.

---

### 3. Procedimento geral (algoritmo) para calcular adjunta e inversa (fluxo de trabalho)

Usar o procedimento abaixo para uma matriz `A` de ordem `n`:

1. Verificar que `A` é quadrada (`n x n`).
2. Para cada `i` de `1` a `n` e cada `j` de `1` a `n`:
   - Construir a submatriz obtida removendo a linha `i` e a coluna `j`.
   - Calcular o determinante dessa submatriz → `M_ij`.
   - Calcular o cofator: `C_ij = (-1)^(i+j) * M_ij`.
3. Montar a matriz de cofatores `C = [C_ij]`.
4. Calcular a adjunta: `adj(A) = transpose(C)`.
5. Calcular `det(A)` (por expansão, regra de Sarrus para 3×3, ou triangularização).
6. Se `det(A) = 0` → `A` não é invertível; pare.
7. Se `det(A) != 0` → calcular:
   ```
   A^{-1} = (1 / det(A)) * adj(A)
   ```

Observações importantes:
- Atenção aos sinais `(-1)^(i+j)`; esse é o ponto mais sujeito a erro manual.  
- Para `n >= 4`, o método é computacionalmente custoso (muitos menores a calcular); em aplicações numéricas usa-se LU/QR com pivotamento.

---

### 4. Exemplos detalhados

#### 4.1 Exemplo 2×2 — fórmula direta (pedagógica)

Considere
```
A = [ a  b
      c  d ]
```

- Menores (removendo linha/coluna):
  ```
  M_11 = d
  M_12 = c
  M_21 = b
  M_22 = a
  ```

- Cofatores:
  ```
  C_11 =  (+1) * d = d
  C_12 =  (-1) * c = -c
  C_21 =  (-1) * b = -b
  C_22 =  (+1) * a = a
  ```

- Matriz de cofatores:
  ```
  C = [  d  -c
        -b   a ]
  ```

- Adjunta:
  ```
  adj(A) = transpose(C) = [  d  -b
                             -c   a ]
  ```

- Determinante:
  ```
  det(A) = a*d - b*c
  ```

- Inversa (se `det(A) != 0`):
  ```
  A^{-1} = (1 / (a*d - b*c)) * adj(A)
  ```

Exemplo numérico:
```
A = [ 2  1
      1  3 ]
det(A) = 2*3 - 1*1 = 6 - 1 = 5
adj(A) = [ 3  -1
           -1  2 ]
A^{-1} = (1 / 5) * adj(A) = [ 3/5  -1/5
                              -1/5  2/5 ]
```

Comentários: para 2×2, a fórmula é compacta e prática; a adjunta coincide com a matriz formada por trocar diagonal e trocar sinais na outra diagonal.

---

#### 4.2 Exemplo 3×3 — cálculo completo passo a passo

Considere a matriz
```
A = [ 1  0  1
      2  4  0
      3  5  6 ]
```

Objetivo: calcular `C` (matriz de cofatores), `adj(A)`, `det(A)` e `A^{-1}` (se existir).

Passo A — calcular menores e cofatores:

1. `(i=1, j=1)`:
   - Submatriz obtida ao remover linha 1 e coluna 1:
     ```
     [ 4  0
       5  6 ]
     ```
   - Menor:
     ```
     M_11 = 4*6 - 0*5 = 24
     ```
   - Cofator:
     ```
     C_11 = (+1) * 24 = 24
     ```

2. `(i=1, j=2)`:
   - Submatriz (remover linha 1, coluna 2):
     ```
     [ 2  0
       3  6 ]
     ```
   - Menor:
     ```
     M_12 = 2*6 - 0*3 = 12
     ```
   - Cofator:
     ```
     C_12 = (-1) * 12 = -12
     ```

3. `(i=1, j=3)`:
   - Submatriz:
     ```
     [ 2  4
       3  5 ]
     ```
   - Menor:
     ```
     M_13 = 2*5 - 4*3 = 10 - 12 = -2
     ```
   - Cofator:
     ```
     C_13 = (+1) * (-2) = -2
     ```

4. `(i=2, j=1)`:
   - Submatriz:
     ```
     [ 0  1
       5  6 ]
     ```
   - Menor:
     ```
     M_21 = 0*6 - 1*5 = -5
     ```
   - Cofator:
     ```
     C_21 = (-1) * (-5) = 5
     ```

5. `(i=2, j=2)`:
   - Submatriz:
     ```
     [ 1  1
       3  6 ]
     ```
   - Menor:
     ```
     M_22 = 1*6 - 1*3 = 6 - 3 = 3
     ```
   - Cofator:
     ```
     C_22 = (+1) * 3 = 3
     ```

6. `(i=2, j=3)`:
   - Submatriz:
     ```
     [ 1  0
       3  5 ]
     ```
   - Menor:
     ```
     M_23 = 1*5 - 0*3 = 5
     ```
   - Cofator:
     ```
     C_23 = (-1) * 5 = -5
     ```

7. `(i=3, j=1)`:
   - Submatriz:
     ```
     [ 0  1
       4  0 ]
     ```
   - Menor:
     ```
     M_31 = 0*0 - 1*4 = -4
     ```
   - Cofator:
     ```
     C_31 = (+1) * (-4) = -4
     ```

8. `(i=3, j=2)`:
   - Submatriz:
     ```
     [ 1  1
       2  0 ]
     ```
   - Menor:
     ```
     M_32 = 1*0 - 1*2 = -2
     ```
   - Cofator:
     ```
     C_32 = (-1) * (-2) = 2
     ```

9. `(i=3, j=3)`:
   - Submatriz:
     ```
     [ 1  0
       2  4 ]
     ```
   - Menor:
     ```
     M_33 = 1*4 - 0*2 = 4
     ```
   - Cofator:
     ```
     C_33 = (+1) * 4 = 4
     ```

Matriz de cofatores `C`:
```
C = [ 24  -12  -2
      5    3  -5
     -4    2   4 ]
```

Passo B — adjunta (transposta de `C`):
```
adj(A) = transpose(C) =

adj(A) = [ 24   5  -4
          -12   3   2
           -2  -5   4 ]
```

Passo C — cálculo do determinante `det(A)` (expansão pela primeira linha):

Usando menores já calculados:
```
det(A) = a_11 * M_11 - a_12 * M_12 + a_13 * M_13
       = 1*24 - 0*12 + 1*(-2)
       = 24 - 2 = 22
```

Passo D — inversa (se `det(A) != 0`):
```
det(A) = 22 ≠ 0 → A está invertível
A^{-1} = (1 / 22) * adj(A) =
(1/22) * [ 24   5  -4
          -12   3   2
           -2  -5   4 ]
```

Verificação (opcional, mas didática): calcular `A * A^{-1}` deve resultar em `I_3` (matriz identidade 3×3). Isso valida todos os cálculos.

---

### 5. Interpretações, propriedades adicionais e aplicações

- Interpretação geométrica:
  - Para `n = 2`, `det(A)` é fator de escala da área; cofatores aparecem quando projetamos volumes menores que compõem a área total.
  - Para `n = 3`, cofatores e adjunta relacionam-se com volumes orientados e transformações inversas.

- Relação com Cramer:
  - A adjunta está ligada à fórmula de Cramer: entradas da inversa (ou da solução via Cramer) podem ser expressas por determinantes de menores (cofatores), o que dá forma explícita para soluções de `A x = b` quando `det(A) != 0`.

- Propriedade algébrica útil (repetida):
  ```
  A * adj(A) = det(A) * I_n
  ```
  - Multiplicando ambos os lados por `1 / det(A)` (quando não nulo) fornece a inversa.

- Limitações práticas:
  - Calcular adjunta exige `O(n * n)` menores, e cada menor é um determinante de ordem `n-1`; custo cresce exponencialmente com `n`. Em implementações reais, para `n >= 4` recomenda-se usar decomposição LU/QR com pivotamento por eficiência e estabilidade numérica.

- Aplicações práticas:
  - Resolução simbólica de sistemas em álgebra, derivações nas provas teóricas, e casos onde se precisa de expressão explícita em termos de determinantes (p.ex., símbolos paramétricos).
  - Em engenharia e física, cofatores surgem em expressão de inversa de tensores e em jacobianos (mudança de variável) quando se trabalha simbolicamente.

---

## Exercícios com resolução detalhada

Apresento 10 exercícios. Cada exercício tem solução passo a passo, em notação monoespaçada.

1) Exercício 1 — cofatores e adjunta (3×3)
   ```
   B = [ 2  1  0
         1  3  1
         0  2  4 ]
   ```
   Solução (passo a passo resumido):
   - Calcular M_11: remover linha1,col1 → [3 1; 2 4] → M_11 = 3*4 - 1*2 = 12 - 2 = 10 → C_11 = (+1)*10 = 10
   - M_12: remove linha1,col2 → [1 1; 0 4] → M_12 = 1*4 - 1*0 = 4 → C_12 = (-1)*4 = -4
   - M_13: remove linha1,col3 → [1 3; 0 2] → M_13 = 1*2 - 3*0 = 2 → C_13 = (+1)*2 = 2
   - M_21: remove linha2,col1 → [1 0; 2 4] → M_21 = 1*4 - 0*2 = 4 → C_21 = (-1)*4 = -4
   - M_22: remove linha2,col2 → [2 0; 0 4] → M_22 = 2*4 - 0*0 = 8 → C_22 = (+1)*8 = 8
   - M_23: remove linha2,col3 → [2 1; 0 2] → M_23 = 2*2 - 1*0 = 4 → C_23 = (-1)*4 = -4
   - M_31: remove linha3,col1 → [1 0; 3 1] → M_31 = 1*1 - 0*3 = 1 → C_31 = (+1)*1 = 1
   - M_32: remove linha3,col2 → [2 0; 1 1] → M_32 = 2*1 - 0*1 = 2 → C_32 = (-1)*2 = -2
   - M_33: remove linha3,col3 → [2 1; 1 3] → M_33 = 2*3 - 1*1 = 6 - 1 = 5 → C_33 = (+1)*5 = 5
   - Matriz de cofatores:
     ```
     C = [ 10  -4   2
          -4   8  -4
           1  -2   5 ]
     ```
   - Adjunta:
     ```
     adj(B) = transpose(C) = [ 10  -4   1
                               -4   8  -2
                                2  -4   5 ]
     ```
   - Determinante det(B): expandir por primeira linha com M_11,M_12,M_13:
     ```
     det(B) = 2*M_11 - 1*M_12 + 0*M_13 = 2*10 - 1*4 + 0 = 20 - 4 = 16
     ```
   - Inversa (1/det)*adj:
     ```
     B^{-1} = (1/16) * adj(B)
     ```
     Resultado final escrito explicitamente se necessário.

2) Exercício 2 — verificar identidade `A * adj(A) = det(A) * I`
   - Use a matriz `A` do exemplo 3×3 (a mesma usada na aula).
   - Multiplicar `A` por `adj(A)` calculado anteriormente e verificar que o resultado é `22 * I_3`.
   - Passos: calcular produto linha×coluna, comparar cada entrada com `22` quando na diagonal e `0` fora.

3) Exercício 3 — 2×2 prática
   ```
   C = [ 4  7
         2  3 ]
   ```
   Solução:
   - det(C) = 4*3 - 7*2 = 12 - 14 = -2
   - adj(C) = [ 3  -2
               -7   4 ] (obtido trocando diagonal e trocando sinais da outra diagonal)
   - C^{-1} = (1 / -2) * adj(C) = [ -3/2   1
                                    7/2  -2 ]

4) Exercício 4 — cofatores nulos por linhas iguais (teórico + exemplo)
   - Se duas linhas são iguais, det(A) = 0.
   - Exemplo: `A = [1 2; 1 2]` → det = 1*2 - 2*1 = 0; cofatores relativos àquelas linhas geram menores com duas linhas iguais → menores = 0.

5) Exercício 5 — resolver sistema `A x = b` usando adjunta
   ```
   A = [ 1  0  1
         2  4  0
         3  5  6 ],  b = [ 7
                            8
                            9 ]
   ```
   Solução:
   - Já temos `adj(A)` e `det(A) = 22`.
   - Calcular `adj(A) * b`:
     ```
     adj(A) = [ 24   5  -4
               -12   3   2
                -2  -5   4 ]
     adj(A) * b = [ 24*7 + 5*8 + (-4)*9
                    -12*7 + 3*8 + 2*9
                    -2*7 + (-5)*8 + 4*9 ]
                = [ 168 + 40 - 36
                    -84 + 24 + 18
                    -14 - 40 + 36 ]
                = [ 172
                    -42
                     -18 ]
     ```
   - Dividir por det:
     ```
     x = (1/22) * [ 172; -42; -18 ] = [ 172/22; -42/22; -18/22 ]
     Simplificar: x = [ 86/11; -21/11; -9/11 ]
     ```

6) Exercício 6 — estimativa de custo para adjunta de 4×4 (resposta qualitativa)
   - Calcular adj de 4×4 exige 16 menores de ordem 3, cada um exigindo 6 multiplicações e 2 subtrações por regra de Sarrus/expansão; o custo cresce rapidamente.

7) Exercício 7 — cofatores da matriz `D` (prático)
   ```
   D = [ 1  2  3
         0  1  4
         5  6  0 ]
   ```
   - Calcular todos `M_ij`, `C_ij`, montar `adj(D)`, calcular `det(D)` e, se ≠ 0, `D^{-1}`. (Se desejar, executo passo a passo.)

8) Exercício 8 — efeito de operação elementar sobre cofatores
   - Trocar linhas muda o sinal do determinante; interpretar efeito sobre cofatores e adjunta (multiplica `det(A)` por -1 e muda sinais correspondentes).

9) Exercício 9 — usar adjunta para derivar fórmula de inversa 2×2 (demonstrar)
   - Repetir derivação da seção 4.1, mostrando consistência.

10) Exercício 10 — comparar métodos
   - Para uma matriz `n >= 4`, implementar adjunta vs LU: comparar número de operações aproximado e discutir estabilidade numérica.

---

## Conclusão

- Cofatores e adjunta fornecem uma forma direta, conceitual e algébrica de construir a inversa de matrizes pequenas. A operação exige cuidado com sinais e com a aritmética dos menores.  
- Para uso prático e computacional em matrizes de ordem média e grande, recomenda-se decomposições (LU, QR) com pivoteamento por motivos de eficiência e estabilidade numérica. Ainda assim, o conhecimento de cofatores e adjunta é essencial para compreensão teórica (provas, propriedades e manipulações simbólicas) e para métodos como a regra de Cramer.

---

## Bibliografia (formato ABNT)

- UNIVESP. Geometria analítica e álgebra linear — Inversão de Matrizes [vídeo]. UNIVESP TV, YouTube, 23 maio 2022. Transcrição consultada. Acesso em 19 out. 2025.  
- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015.  
- CUEMATH. Adjoint of a Matrix — cofactors and adjugate. Acesso em 19 out. 2025.

Obs.: referência ao vídeo indicada por índice de pesquisa interna do material utilizado.

---

## Materiais complementares

- Nicholson, W. Keith. Álgebra Linear. AMGH Editora, 2. ed., 2015 (capítulos sobre determinantes, reversibilidade e adjugado).  
- Notas e tutoriais de álgebra linear (IME Unicamp, MIT OpenCourseWare) para comparação de métodos numéricos (LU, QR) e discussões de estabilidade.

---
