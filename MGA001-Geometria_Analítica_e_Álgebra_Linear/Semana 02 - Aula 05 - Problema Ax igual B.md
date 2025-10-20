# O problema Ax = b

## Introdução

Esta aula baseia-se no vídeo "O problema Ax = b" (UNIVESP) e na transcrição desse vídeo como fonte principal, e apresenta a formulação matricial de sistemas lineares, a matriz ampliada, operações elementares e o método de eliminação de Gauss para resolver sistemas. Informações gerais sobre eliminação de Gauss e transformações de sistemas foram consultadas em material didático complementar.

---

## Desenvolvimento

### 1. Do sistema linear à forma matricial

- Definição prática (texto monoespaçado):
```
Sistema linear (m equações, n incógnitas):
a_11 x_1 + a_12 x_2 + ... + a_1n x_n = b_1
a_21 x_1 + a_22 x_2 + ... + a_2n x_n = b_2
...
a_m1 x_1 + a_m2 x_2 + ... + a_mn x_n = b_m
```
- Notação matricial equivalente (monoespaçado):
```
A x = b
onde A = [a_ij] (m x n),   x = column vector (n x 1),   b = column vector (m x 1)
```
- Observação: o vídeo mostra exatamente esse processo de montar a matriz de coeficientes, o vetor das incógnitas e o vetor de termos independentes para obter `A x = b`.

---

### 2. Matriz ampliada

- Definição e construção (monoespaçado):
```
Matriz ampliada [A | b] : formar uma única matriz juntando A e a coluna b
Exemplo (2x2 com termos):
[A | b] = [ a_11  a_12 | b_1 ]
          [ a_21  a_22 | b_2 ]
```
- Observação do vídeo: notação com "pipe" ou colchetes varia entre livros; ambos são aceitáveis e a matriz ampliada facilita aplicar operações nas linhas mantendo os termos independentes juntos.

---

### 3. Operações elementares sobre linhas (conservam soluções)

O vídeo lista três operações elementares permitidas sobre a matriz ampliada; repito-as com explicação lógica e exemplos:

- Trocar duas linhas:
  - Efeito: reordena equações sem alterar o conjunto solução.
  - Exemplo (texto): trocar L1 e L2 em `[A|b]`.

- Multiplicar uma linha por escalar não nulo `k`:
  - Efeito: escala uma equação inteira; não altera solução porque é equivalente multiplicar ambos os lados por `k`.
  - Exemplo: substituir L3 por `k * L3` com `k != 0`.

- Adicionar a uma linha um múltiplo de outra linha:
  - Efeito: transforma sistema em outro equivalente; é a operação mais usada para eliminar coeficientes.
  - Exemplo (texto): L2 <- L2 + ( -1 ) * L1 para zerar um coeficiente.

Essas três transformações são tratadas no vídeo como ferramentas para gerar sistemas equivalentes e formar uma matriz triangular superior durante o escalonamento.

---

### 4. Método de eliminação de Gauss (escalonamento) — algoritmo e lógica

- Objetivo: transformar a matriz ampliada `[A | b]` em forma triangular superior (ou forma escalonada), para depois resolver por substituição regressiva.

- Ideia geral (pseudocódigo em monoespaçado):
```
Para k = 1 .. min(m,n):
  Escolher pivô não nulo na coluna k (eventualmente trocar linhas)
  Para i = k+1 .. m:
    multiplicador = A[i,k] / A[k,k]
    L_i <- L_i - multiplicador * L_k
Fim
Depois: back-substitution para obter as incógnitas.
```

- Explicação passo a passo (intuição do vídeo):
  - Use o elemento não nulo da diagonal (pivô) para zerar todos os elementos abaixo dele na mesma coluna, aplicando operações do tipo "somar a linha i por um múltiplo da linha do pivô".
  - Repetir coluna a coluna até obter zeros abaixo da diagonal principal.
  - Resolver a partir da última equação (substituição regressiva).

- Observações práticas e cuidado (complemento didático): quando o pivô é muito pequeno ou zero, deve-se trocar linhas (pivoteamento parcial) para evitar divisões por zero e reduzir erros numéricos; isso é padrão em implementações numéricas do algoritmo.

---

### 5. Exemplo completo (concreto do vídeo, explicado com passo a passo e sem LaTeX)

Vídeo resolve o sistema (exemplo simples) usando escalonamento. Reproduzo com notação monoespaçada e todos os passos.

Enunciado (texto):
```
2x - y = 3
x + 2y = 2
```

Matriz ampliada inicial:
```
[ 2  -1 | 3 ]
[ 1   2 | 2 ]
```

Passo 1 — zerar posição (2,1):
- Multiplicador = (elemento da linha 2, coluna 1) / (pivô) = 1 / 2 = 0.5
- L2 <- L2 - 0.5 * L1
  - Nova L2 col1: 1 - 0.5*2 = 1 - 1 = 0
  - Nova L2 col2: 2 - 0.5*(-1) = 2 + 0.5 = 2.5
  - Novo termo independente: 2 - 0.5*3 = 2 - 1.5 = 0.5

Matriz ampliada após operação:
```
[ 2   -1  | 3  ]
[ 0  2.5  | 0.5]
```

Passo 2 — resolver por substituição:
- Segunda equação: `2.5 * y = 0.5` → `y = 0.5 / 2.5 = 0.2` (ou `1/5`)
- Substituir em primeira: `2x - y = 3` → `2x - 0.2 = 3` → `2x = 3.2` → `x = 1.6` (ou `8/5`)

Solução final:
```
x = 1.6,   y = 0.2
```

Observação: o vídeo demonstra processo idêntico e enfatiza que pequenas diferenças aritméticas nas etapas resultam em soluções numéricas específicas; o algoritmo é generalizável para matrizes maiores.

---

## Conclusão

- O problema `A x = b` é a forma matricial de sistemas lineares; escrever um sistema como `A x = b` e formar `[A | b]` permite aplicar operações elementares e o método de eliminação de Gauss para encontrar as soluções (única, infinita ou nenhuma), conforme ilustrado no vídeo e em materiais de referência.
- O procedimento de escalonamento é um algoritmo direto, passível de implementação em código e é a base de métodos numéricos e bibliotecas para resolver sistemas lineares em aplicações reais.

---

## Análise crítica

- O vídeo apresenta com clareza a montagem da matriz ampliada, as três operações elementares e o procedimento de escalonamento; é didático e adequado para iniciar o estudo de sistemas lineares.
- Observações críticas e complementos:
  - O vídeo não discute pivoteamento parcial de forma técnica nem as implicações de estabilidade numérica; para aplicações numéricas é importante adotar pivoteamento e considerar erros de arredondamento — tópico abordado em textos sobre eliminação de Gauss e cálculo numérico.
  - Também não há análise de custo computacional no vídeo; a complexidade clássica da eliminação direta é O(n^3) para matrizes n×n (ver referências de análise numérica).
  - Recomenda-se complementar com implementações em software (NumPy, Octave/Matlab) para ver comportamento com dados reais e grandes dimensões.

---

## Exercícios (20) com resolução detalhada — notação monoespaçada

Observação: exercícios focam no conteúdo da aula (matriz ampliada, operações elementares, escalonamento, tipos de solução). Todas as fórmulas e matrizes estão em texto monoespaçado.

1. Enunciado:
```
Resolva por escalonamento:
2x - y = 3
x + 2y = 2
```
Solução: (passos iguais ao exemplo da seção 5) → `x = 8/5 = 1.6`, `y = 1/5 = 0.2`.

2. Enunciado:
```
Escreva a matriz ampliada de:
x - y = 1
x + 2y = 4
```
Solução:
```
[A | b] = [ 1  -1 | 1
            1   2 | 4 ]
```

3. Enunciado:
```
Use operação elementar para zerar a[2,1] em:
[ 3  1 | 5
  2 -1 | 4 ]
```
Solução:
- Multiplicador = 2 / 3.
- L2 <- L2 - (2/3) * L1:
  - nova L2 col1: 2 - (2/3)*3 = 0
  - nova L2 col2: -1 - (2/3)*1 = -1 - 2/3 = -5/3
  - novo termo: 4 - (2/3)*5 = 4 - 10/3 = 2/3

4. Enunciado:
```
Classifique:
2x + 4y = 6
x + 2y = 3
```
Solução:
- Primeira = 2 × segunda → infinitas soluções; solução geral `x = 3 - 2t, y = t`.

5. Enunciado:
```
Classifique:
x + y = 1
2x + 2y = 5
```
Solução:
- Segund = 2 × primeira na esquerda, mas RHS difere → inconsistente → sem solução.

6. Enunciado:
```
Resolver:
3x + 2y = 7
x - y = 1
```
Solução:
- x = 1 + y → substituir → `3(1+y)+2y =7` → `3 + 5y =7` → `y = 4/5`, `x = 9/5`.

7. Enunciado:
```
Dada matriz ampliada:
[ 1  -1 | 1
  0   2 | 4 ]
Obtenha a solução.
```
Solução:
- Segunda equação: `2 y = 4` → `y = 2`.
- Primeira: `x - y =1` → `x = 1 + y = 3`.

8. Enunciado:
```
Mostre operação L2 <- L2 + 2*L1 aplicada a:
[ 1  2 | 3
  4  5 | 6 ]
```
Solução:
- Nova L2 col1: 4 + 2*1 = 6
- Nova L2 col2: 5 + 2*2 = 9
- Novo termo: 6 + 2*3 = 12
- Resultado:
```
[ 1  2 |  3
  6  9 | 12 ]
```

9. Enunciado:
```
Resolva por escalonamento:
x + y + z = 6
2x - y + 3z = 14
-x + 4y + z = 2
```
Solução (resumo dos passos):
- Montar ampliada 3×4, aplicar eliminações para triangularizar, obter z, y, x por substituição. (Executar passo a passo com multiplicadores conforme algoritmo; resultado final: x = 28/11, y = 4/11, z = 34/11 — ver uso de operações elementares para obter esses valores).

10. Enunciado:
```
Explique por que não se deve multiplicar uma linha por zero.
```
Solução:
- Multiplicar por zero transforma equação em `0 = 0` e descarta informação, alterando o sistema original; operação inválida para manter equivalência.

11. Enunciado:
```
Dada ampliada [A|b], após operações encontramos linha [0 0 | 1]. O que indica?
```
Solução:
- Indica contradição `0 = 1` → sistema inconsistente → sem solução.

12. Enunciado:
```
Apresente pseudocódigo simples (em texto) do algoritmo de Gauss.
```
Solução:
```
Para k = 1 .. n-1:
  Para i = k+1 .. n:
    m = A[i,k] / A[k,k]
    Para j = k .. n+1:
      A[i,j] = A[i,j] - m * A[k,j]
Fim
Back-substitution para x
```

13. Enunciado:
```
Resolva:
0.0001 x + y = 1
x + y = 2
```
Solução (pivoteamento parcial sugerido):
- Trocar linhas para evitar divisão por 0.0001; depois eliminar → resultados aproximados `x ≈ 1.0001`, `y ≈ 0.9999` (mostrar passos e atenção numérica).

14. Enunciado:
```
Forme a matriz aumentada do sistema:
x - 2y + z = 0
2x - 4y + 2z = 0
```
Solução:
- Observação: segunda = 2 × primeira → ampliada levará a linha dependente → infinitas soluções; matriz:
```
[ 1  -2  1 | 0
  2  -4  2 | 0 ]
```

15. Enunciado:
```
Explique a relação entre rank(A) e número de soluções (intuição).
```
Solução:
- Intuição: rank mede número de equações independentes; se rank(A) = rank([A|b]) = n → solução única; se rank(A)=rank([A|b])<n → infinitas; se rank(A)<rank([A|b]) → inconsistente. Formalização em tópicos posteriores do curso.

16. Enunciado:
```
Usando método de Gauss, encontre y em:
[ 2  -1 | 3
  0  5/2 | 1/2 ]
```
Solução:
- Segunda equação: `(5/2) y = 1/2` → `y = (1/2) / (5/2) = 1/5`.

17. Enunciado:
```
Em um sistema 4×4, explique objetivo de transformar em forma escada.
```
Solução:
- Objetivo: obter zeros abaixo de diagonal para permitir back-substitution; transforma sistema em triangular superior equivalente, simplificando solução.

18. Enunciado:
```
Por que trocar linhas (pivoteamento) pode ser necessário?
```
Solução:
- Para evitar divisão por zero ou por números muito pequenos (melhora estabilidade numérica) e para escolher um pivô com maior magnitude.

19. Enunciado:
```
Resolva o sistema triangular superior:
2x + 3y = 7
0x + 5y = 10
```
Solução:
- y = 10/5 = 2; x = (7 - 3*y) / 2 = (7 - 6)/2 = 1/2.

20. Enunciado:
```
Descreva como implementar Gauss em código (visão de alto nível).
```
Solução:
- Montar matriz ampliada; aplicar loops aninhados para triangularizar com pivoteamento; depois back-substitution; prestar atenção a detecção de singularidade.

---

## Bibliografia (formato ABNT) e fontes citadas

- UNIVESP. Geometria analítica e álgebra linear — O problema Ax = b [vídeo]. UNIVESP TV, YouTube. A transcrição do vídeo foi usada como base para este material. Acesso em 11 out. 2025.  
  Link do vídeo: https://www.youtube.com/watch?v=qDX-eT5ZpgU.

- ROMANAZZI, Giuseppe. Método direto de Eliminação de Gauss. Portal IME Unicamp. Disponível em: https://www.ime.unicamp.br/~roman/courses/MS211/1s2020/eliminacao.pdf. Acesso em 11 out. 2025.

- Material de consulta sobre Gauss-Jordan e prática de escalonamento (recursos didáticos): páginas de apoio e tutoriais consultados durante elaboração (consulta agregada).

---

## Materiais complementares recomendados

- NICHOLSON, W. Keith. Álgebra Linear. AMGH Editora, 2. ed., 2015 — capítulos sobre sistemas lineares, posto, eliminacão de Gauss (recomendado para fundamentação teórica).  
- IME Unicamp — notas sobre eliminação de Gauss (Romanazzi) para aprofundar algoritmo e custo computacional.  
- Implementação prática: experimentar o algoritmo com NumPy (função `numpy.linalg.solve` para sistemas quadrados e `numpy.linalg.lstsq` para casos sobre/underdeterminados) e comparar com implementação manual de escalonamento (pivoteamento parcial).

---
