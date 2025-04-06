# Operações com Matrizes

## Introdução
Matrizes são ferramentas matemáticas fundamentais para resolver problemas complexos em diversas áreas, como física, computação e engenharia. Nesta seção, exploraremos as principais operações realizadas com matrizes, incluindo:
1. **Soma de Matrizes**
2. **Subtração de Matrizes**
3. **Multiplicação Escalar**
4. **Transposição de Matrizes**
5. **Multiplicação de Matrizes**
6. **Propriedades das Operações com Matrizes**

---

## 1. Soma de Matrizes

A soma de matrizes é possível apenas entre matrizes que possuem o mesmo tamanho (mesmo número de linhas e colunas). Os elementos em posições correspondentes nas duas matrizes são somados.

### Exemplo:
Dadas as matrizes \(A\) e \(B\):

<table>
<tr>
<td> Matriz (A): </td>
<td> Matriz (B): </td>
<td> Soma (A + B): </td>
</tr>
<tr>
<td>

| 1 | 2 |
|---|---|
| 3 | 4 |

</td>
<td>

| 5 | 6 |
|---|---|
| 7 | 8 |

</td>
<td>

| 6  | 8  |
|----|----|
| 10 | 12 |

</td>
</tr>
</table>

---

## 2. Subtração de Matrizes

A subtração de matrizes segue o mesmo princípio da soma, sendo possível apenas entre matrizes de mesma ordem. Subtraímos os elementos correspondentes de cada matriz.

### Exemplo:
Dadas as matrizes \(A\) e \(B\):

<table>
<tr>
<td> Matriz (A): </td>
<td> Matriz (B): </td>
<td> Subtração <br/> (A - B): </td>
</tr>
<tr>
<td>

| 6 | 8 |
|---|---|
| 10 | 12 |

</td>
<td>

| 2 | 3 |
|---|---|
| 4 | 6 |

</td>
<td>

| 4 | 5 |
|---|---|
| 6 | 6 |

</td>
</tr>
</table>

---

## 3. Multiplicação Escalar

A multiplicação escalar consiste em multiplicar todos os elementos de uma matriz por um número real (\(k\)).

### Exemplo:
Dada a matriz \(A\) e o escalar \(k = 2\):

<table>
<tr>
<td> Matriz (A): </td>
<td> Escalar (k): </td>
<td> Multiplicação Escalar (k * A): </td>
</tr>
<tr>
<td>

| 1 | 2 |
|---|---|
| 3 | 4 |

</td>
<td> 

2 

</td>
<td>

| 2  | 4  |
|----|----|
| 6  | 8  |

</td>
</tr>
</table>

---

## 4. Transposição de Matrizes

A transposição de uma matriz consiste em trocar suas linhas pelas colunas, criando uma nova matriz.

### Exemplo:
Dada a matriz \(A\):

<table>
<tr>
<td> Matriz (A): </td>
<td> Transposta (A<sup>T</sup>): </td>
</tr>
<tr>
<td>

| 1 | 2 | 3 |
|---|---|---|
| 4 | 5 | 6 |

</td>
<td>

| 1 | 4 |
|---|---|
| 2 | 5 |
| 3 | 6 |

</td>
</tr>
</table>

---

## 5. Multiplicação de Matrizes

A multiplicação de matrizes exige que o número de **colunas da primeira matriz** seja igual ao número de **linhas da segunda matriz**. O resultado será uma nova matriz.

### Exemplo:
Dadas as matrizes \(A\) (\(2 \times 3\)) e \(B\) (\(3 \times 2\)):

<table>
<tr>
<td> Matriz (A): </td>
<td> Matriz (B): </td>
<td> Multiplicação (A * B): </td>
</tr>
<tr>
<td>

| 1 | 2 | 3 |
|---|---|---|
| 4 | 5 | 6 |

</td>
<td>

| 1 | 2 |
|---|---|
| 3 | 4 |
| 5 | 6 |

</td>
<td>

| 22 | 28 |
|----|----|
| 49 | 64 |

</td>
</tr>
</table>

#### Passo a Passo:
1. Primeiro elemento (\(C[1,1]\)):
   - Pegue a primeira linha de \(A\): \((1, 2, 3)\)
   - Multiplique pelos elementos da primeira coluna de \(B\): \((1, 3, 5)\)
   - Calcule: \(C[1,1] = (1 * 1) + (2 * 3) + (3 * 5) = 22\)

2. Segundo elemento (\(C[1,2]\)):
   - Pegue a primeira linha de \(A\): \((1, 2, 3)\)
   - Multiplique pelos elementos da segunda coluna de \(B\): \((2, 4, 6)\)
   - Calcule: \(C[1,2] = (1 * 2) + (2 * 4) + (3 * 6) = 28\)

---

## 6. Propriedades das Operações com Matrizes

### Propriedades da Soma e Subtração:
- **Associatividade**: \((A + B) + C = A + (B + C)\)
- **Comutatividade**: \(A + B = B + A\)
- **Elemento Neutro**: \(A + 0 = A\)
- **Existência de Oposto**: \(A + (-A) = 0\)

### Propriedades da Multiplicação Escalar:
- \(k(A + B) = kA + kB\)
- \((k + m)A = kA + mA\)
- \(k(mA) = (km)A\)
- \(0 * A = 0\)

### Propriedades da Multiplicação de Matrizes:
- **Associatividade**: \((AB)C = A(BC)\)
- **Distributividade**: \(A(B + C) = AB + AC\)
- **Identidade**: \(AI = IA = A\)
- Multiplicação não é comutativa: \(AB \neq BA\) na maioria dos casos.

---

## Apresentação Final
Esta seção detalhada cobre as operações básicas com matrizes, incluindo exemplos e propriedades fundamentais. Caso deseje adicionar mais exemplos ou explorar tópicos avançados, como determinantes ou matrizes inversas, posso ajudar! 😊
