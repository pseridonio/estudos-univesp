# Mapa de Karnaugh: Simplificação de Expressões Booleanas e Projeto de Circuitos Combinacionais

Esta aula explora o uso do Mapa de Karnaugh como ferramenta para simplificar expressões booleanas na forma de Soma‑de‑Produtos (SOP) e para o projeto de circuitos lógicos combinacionais. São abordados desde a conversão para a forma canônica até técnicas avançadas de agrupamento, com informações extraídas dos capítulos 4.1 a 4.9 e 6.1 a 6.2 do livro *Sistemas Digitais: Princípios e Aplicações* e de um vídeo complementar que apresenta um passo a passo do mapa.

> **Observação:** Sempre que fórmulas são apresentadas em LaTeX, também incluímos um bloco de prompt em inglês com as instruções para a criação de imagens (SVG/PNG) que ilustrem os conceitos.

---

## 1. Objetivos da Aula

- **Converter expressões para a forma SOP:**  
  Identificar funções lógicas na forma de Soma de Produtos, onde cada mintermo representa um produto de literais.

- **Construir e interpretar mapas de Karnaugh:**  
  Organizar a tabela verdade de maneira geométrica (em ordem Gray) para facilitar a identificação de agrupamentos dos 1’s.

- **Simplificar expressões através do agrupamento:**  
  Formar grupos de 1’s com tamanho em potências de 2 (1, 2, 4, 8, etc.) para eliminar variáveis redundantes e obter a expressão mínima.

- **Aplicar a expressão simplificada no projeto de circuitos:**  
  Traduzir a função reduzida em um projeto lógico utilizando portas (AND, OR, NOT), otimizando custo, velocidade e consumo.

- **Utilizar termos “don’t care”:**  
  Incorporar condições irrelevantes para ampliar agrupamentos e obter uma simplificação superior.

---

## 2. Expressões SOP e Forma Canônica

### 2.1 Forma de Soma‑de‑Produtos (SOP)

- Uma função lógica na forma SOP é expressa como a soma (OR) de termos (produto lógico/AND) de literais.  
  - **Exemplo:**  
    $F = A\bar{B}C + AB\bar{C} + \bar{A}BC$

    \[
    F = A\bar{B}C + AB\bar{C} + \bar{A}BC
    \]

### 2.2 Forma Canônica

- Cada mintermo na forma canônica envolve todas as variáveis (na forma direta ou complementada).  
  - *Exemplo (para três variáveis):*  
    A combinação 0–1–0 gera o mintermo:  
    \[
    $F = \bar{A}B\bar{C}$
    \]

- **[SVG Image Prompt – Conversão para Forma Canônica]**  
  ```plaintext
  "Create a detailed SVG diagram showing the conversion of a non-canonical SOP term 'AB' (for variables A, B, C) into its canonical form by multiplying it by (C + NOT C), resulting in 'ABC' and 'AB NOT C'. Label each step clearly and use color coding for variables and the NOT operators."
  ```

---

## 3. Simplificação de Circuitos Lógicos e Algébrica

### 3.1 Simplificação de Circuitos Lógicos

- A aplicação das leis da álgebra booleana (absorção, distributividade, De Morgan, etc.) reduz a complexidade do circuito, diminuindo o número de portas lógicas e otimizando desempenho, custo e consumo energético.

### 3.2 Simplificação Algébrica

- Após aplicar as leis, a expressão é convertida para uma forma que facilite o agrupamento no mapa de Karnaugh.  
  - **Exemplo de identidade:**  
    \[
    $A\bar{B} + AB = A$
    \]

- **[SVG Image Prompt – Identity Simplification]**  
  ```plaintext
  "Create an SVG diagram illustrating the simplification of the boolean expression 'A AND (NOT B) OR A AND B' into 'A' using the absorption law. Use clear illustrations for the AND and OR operations and highlight the redundant term that is absorbed."
  ```

---

## 4. Projeto de Circuitos Lógicos Combinacionais

### 4.1 Implementação da Expressão Simplificada

- Após a simplificação, a expressão minimalista é implementada com portas lógicas:  
  - Cada termo do SOP corresponde a um bloco AND e a operação OR combina esses termos para formar a saída final.
- **Exemplo:**  
  Para 
  \[
  $F = \bar{A}C + AB$
  \]
  o circuito contém:  
  - Um bloco AND gerando \(\bar{A}\) AND \(C\) (utilizando uma porta NOT para A);  
  - Um bloco AND para \(A\) AND \(B\);  
  - Uma porta OR combinando as saídas dos dois blocos.
  
- **[SVG Image Prompt – Circuit Implementation]**  
  ```plaintext
  "Create an SVG diagram showing a simple logic circuit based on the simplified expression F = (NOT A AND C) OR (A AND B). Display the individual logic gates (NOT, AND, OR) and their interconnections leading to the final output. Clearly label each gate and wire."
  ```

---

## 5. Método do Mapa de Karnaugh

### 5.1 Construção do Mapa

- **Organização do Mapa:**  
  Transfira os valores da tabela verdade para um arranjo bidimensional organizado em ordem Gray, de modo que células adjacentes diferem em exatamente um bit.
  
  - **Exemplo para 2 Variáveis:**  
   
|       | B=0       | B=1       |
|-------|-----------|-----------|
| A=0   | $\bar{A}\bar{B}$ | $\bar{A}B$ |
| A=1   | $A\bar{B}$ | $AB$     |
  
- **[SVG Image Prompt – 4-Variable Karnaugh Map]**  
  ```plaintext
  "Create an SVG diagram of a 4-variable Karnaugh map (4x4 grid). Label the rows using Gray code combinations for variables A and B, and the columns with Gray code combinations for variables C and D. Include the minterm indices (0 to 15) in each cell."
  ```

### 5.2 Agrupamento e Extração dos Termos

- **Agrupamento de Células:**  
  Forme grupos retangulares de células que contêm 1 (e 'don’t care', se aplicável), onde o número de células do grupo seja uma potência de 2 (1, 2, 4, 8, etc.).  
  - **Regra Importante:**  
    Os agrupamentos devem considerar somente células adjacentes horizontal ou verticalmente; agrupamentos diagonais não são válidos.
  
- **Extração dos Termos Simplificados:**  
  Para cada grupo, identifique as variáveis que permanecem constantes (sem variação entre valor normal e complementado). Se uma variável aparece em ambos os estados dentro do grupo, ela é excluída do termo.
  - *Exemplo:*  
    Se, num grupo, a variável \(A\) aparece somente como 0, o termo incluirá \(\bar{A}\); se \(A\) varia dentre as células, ela não figura na expressão daquele grupo.
  
- **[SVG Image Prompt – Karnaugh Grouping]**  
  ```plaintext
  "Create an SVG diagram of a Karnaugh map (3-variable or 4-variable) with several groups highlighted in different colors. Annotate each group with its corresponding simplified term (e.g., 'NOT A', 'B') and include a legend explaining the grouping criteria."
  ```

### 5.3 Procedimento Passo a Passo

1. **Preenchimento:**  
   Transfira os valores da tabela verdade (1’s, 0’s e "don’t care") para as células do mapa.

2. **Identificação dos Agrupamentos:**  
   Forme os maiores grupos possíveis de acordo com as regras, priorizando agrupamentos que cubram o máximo de 1’s.

3. **Extração dos Termos:**  
   Para cada grupo, determine os literais constantes e construa o correspondente termo do produto.

4. **Expressão Final:**  
   Combine os termos obtidos com a operação OR para formar a expressão SOP mínima.

---

## 6. Aplicações Avançadas e Considerações Práticas

### 6.1 Circuitos para Habilitar/Desabilitar (Cap. 4.8)

- **Descrição:**  
  Circuitos de habilitação (enable/disable) permitem controlar quando um bloco de circuito opera.  
  - Um sinal de habilitação atua como “gate” para permitir ou bloquear o fluxo de dados.  
  - A simplificação da lógica de habilitação pode ser otimizada pelo agrupamento no mapa de Karnaugh.
  
- **[SVG Image Prompt – Enable/Disable Circuit]**  
  ```plaintext
  "Create an SVG diagram depicting a digital circuit with an enable input that controls the activation of a combinational logic block. Highlight the enable signal and show its influence (via a logic gate such as an AND gate) on the final output."
  ```

### 6.2 Características Básicas de CIs Digitais (Cap. 4.9)

- **Descrição:**  
  - Ao implementar circuitos em CIs digitais, considere atrasos de propagação, fan-out e consumo de energia.  
  - A redução da complexidade através da minimização com Karnaugh contribui para um design mais robusto e eficiente.
  
- **[SVG Image Prompt – Digital IC Characteristics]**  
  ```plaintext
  "Create an SVG diagram that illustrates typical characteristics of digital integrated circuits (ICs), such as propagation delay, power consumption, fan-out, and loading effects. Label these parameters and show how logic minimization via Karnaugh maps can improve performance."
  ```

### 6.3 Operações Aritméticas: Adição e Subtração (Cap. 6.1)

- **Descrição:**  
  - Operações aritméticas, como adição e subtração, são implementadas por somadores e subtratores, onde o cálculo do carry é crítico.  
  - Mapas de Karnaugh podem ser utilizados para minimizar a lógica combinacional dos circuitos de somador, otimizando a geração do carry-out e da soma.
  
- **[SVG Image Prompt – Binary Adder Diagram]**  
  ```plaintext
  "Create an SVG diagram illustrating a binary adder circuit. Show a full-adder block with inputs (A, B, Carry-In), a Sum output, and a Carry-Out. Include a small truth table for the full-adder operation."
  ```

### 6.4 Representação de Números com Sinal (Cap. 6.2)

- **Descrição:**  
  - A representação de números com sinal é normalmente realizada usando o complemento de dois.  
  - Em circuitos aritméticos, é crucial manipular corretamente o bit de sinal para evitar erros operacionais.
  
- **[SVG Image Prompt – Two's Complement Representation]**  
  ```plaintext
  "Create an SVG diagram illustrating two's complement representation for signed numbers. Show an example conversion for a binary number (e.g., converting +5 to its two's complement representation for -5) and label bit positions, including the sign bit, with clear annotations."
  ```

### 6.5 Dicas Extras do Vídeo "Mapa de Karnaugh passo a passo"

- **Principais Pontos do Vídeo:**  
  - Identificar corretamente as combinações que resultam em saída 1.  
  - Formar agrupamentos com número de células em potências de 2 (1, 2, 4, 8, etc.).  
  - Agrupar apenas células adjacentes (vertical ou horizontal) e evitar diagonais.  
  - Priorizar agrupamentos maiores para eliminar variáveis que assumem valores opostos no mesmo grupo – estas variáveis são canceladas no termo final.  
  - O método gráfico do mapa de Karnaugh frequentemente garante a expressão mínima, evitando ambiguidades da aplicação sequencial de teoremas booleanos.
  
- **[SVG Image Prompt – Step-by-Step Karnaugh Process]**  
  ```plaintext
  "Create an SVG flowchart illustrating the step-by-step process of solving a Karnaugh map. Include steps such as 'Identify combinations yielding 1', 'Fill in the Karnaugh map', 'Form groups (1, 2, 4, 8 cells)', 'Extract simplified terms by canceling variables that appear in both TRUE and FALSE states', and 'Combine terms to form the final SOP expression'. Use distinct shapes for each step, with arrows indicating the flow."
  ```

---

## 7. Exercícios

1. **Exercício 1 – Função 2 Variáveis Simples**  
   Dada a função F(A, B) definida pela tabela verdade:  
   - F(0,0) = 0  
   - F(0,1) = 1  
   - F(1,0) = 1  
   - F(1,1) = 1  
   Construa o mapa de Karnaugh e determine a expressão simplificada.

2. **Exercício 2 – Mintermos em 3 Variáveis**  
   Considere a função F(A, B, C) definida pelos mintermos m(1, 3, 5, 7). Construa o mapa e obtenha a expressão mínima.

3. **Exercício 3 – Agrupamento Básico em 3 Variáveis**  
   Seja F(A, B, C) = 1 para os mintermos m(0, 2, 5, 7). Construa o mapa de Karnaugh e simplifique a expressão.

4. **Exercício 4 – Uso de “Don’t Care” em 3 Variáveis**  
   Dada a função F(A, B, C) com F = 1 para m(2, 3, 6, 7) e don’t care para m(0, 1), determine a expressão mínima usando o mapa.

5. **Exercício 5 – Função em 4 Variáveis I**  
   Considere F(A, B, C, D) definida pelos mintermos m(1, 3, 7, 11, 15). Construa o mapa de Karnaugh e encontre a expressão simplificada.

6. **Exercício 6 – Função em 4 Variáveis II**  
   Seja F(A, B, C, D) = 1 para m(0, 2, 5, 7, 8, 10, 13, 15). Utilize o mapa de Karnaugh para determinar a forma mínima da função.

7. **Exercício 7 – Regiões Contíguas**  
   Dada a função F(A, B, C, D) que vale 1 para m(4, 5, 6, 7, 12, 13, 14, 15), obtenha a expressão simplificada.

8. **Exercício 8 – Inclusão de “Don’t Care” em 4 Variáveis**  
   Considere F(A, B, C, D) com F = 1 para m(1, 3, 8, 9, 10, 11) e don’t care para m(0, 7). Simplifique a função usando o mapa de Karnaugh.

9. **Exercício 9 – Função de Bloco**  
   Seja F(A, B, C, D) = 1 para todas as combinações em que A = 0 (ou seja, m(0 a 7)). Mostre que a função simplifica para uma expressão em função de A.

10. **Exercício 10 – Grupo Duplo**  
    Considere uma função F(A, B, C, D) cujo mapa de Karnaugh apresenta um grupo com m(0–7) e outro grupo com m(8, 9, 10, 11). Determine a expressão simplificada.

11. **Exercício 11 – Função em 3 Variáveis com “Don’t Care”**  
    Dada F(A, B, C) = 1 para m(3, 5, 7) e don’t care para m(1), obtenha a expressão mínima.

12. **Exercício 12 – Grupo com “Don’t Care” em 4 Variáveis**  
    Seja F(A, B, C, D) com F = 1 para m(2, 3, 8, 9, 10, 11) e don’t care para m(0, 7, 15). Encontre a expressão mínima.

13. **Exercício 13 – Função Complementar de AND (2 Variáveis)**  
    Considere a função F(B, C) de 2 variáveis onde F = 0 somente quando B = 1 e C = 1. Construa o mapa e obtenha a expressão simplificada.

14. **Exercício 14 – Exatamente Uma Verdadeira (3 Variáveis)**  
    Seja F(A, B, C) = 1 somente quando exatamente uma das variáveis vale 1. Construa o mapa de Karnaugh e escreva a expressão mínima.

15. **Exercício 15 – Bloco Central**  
    Dada uma função F(A, B, C, D) cujo mapa possui um bloco central formado pelas células m(5, 6, 9, 10), obtenha a expressão simplificada.

16. **Exercício 16 – Função com Muitos Uns**  
    Considere F(A, B, C, D) = 1 para os mintermos m(0, 1, 2, 4, 5, 6, 7, 8, 10, 11, 12, 13, 14). Determine a expressão mínima.

17. **Exercício 17 – Circuito de Controle**  
    Suponha que F seja 1 se A = 1 ou se (B = 1 e C = 0). Construa o mapa de Karnaugh (para 3 variáveis) e derive a expressão.

18. **Exercício 18 – Função com XOR**  
    Seja F(A, B, C) = 1 se A = 1 e (B XOR C) é verdadeiro. Obtenha a expressão simplificada utilizando o mapa de Karnaugh.

19. **Exercício 19 – Função com Múltiplos Mintermos**  
    Considere F(A, B, C, D) definida pelos mintermos m(1, 2, 3, 9, 11, 13, 15). Utilize o mapa para simplificar e obtenha a expressão mínima.

20. **Exercício 20 – Agrupamento com “Don’t Care” em 3 Variáveis**  
    Dada F(A, B, C) com F = 1 para m(0, 1, 3, 7) e don’t care para m(2, 5), determine a expressão simplificada.

21. **Exercício 21 – Linha Completa**  
    Construa o mapa de Karnaugh para F(A, B, C, D) onde F = 1 em todas as células da linha onde A = 0, e obtenha a expressão resultante.

22. **Exercício 22 – Função OR (2 Variáveis)**  
    Mostre, através do mapa de Karnaugh, que a função OR F(A, B) resulta na expressão F = A + B.

23. **Exercício 23 – Função MAJORITY (3 Variáveis)**  
    Considere F(A, B, C) = 1 se, pelo menos, duas variáveis forem 1 (função de maioria). Obtenha a expressão mínima pelo mapa.

24. **Exercício 24 – Paridade Par (4 Variáveis)**  
    Construa o mapa de Karnaugh para a função F(A, B, C, D) que é 1 quando o número de 1’s é par e obtenha a expressão simplificada (função de paridade par).

25. **Exercício 25 – Comparação com Condição**  
    Seja F(A, B, C) = 1 somente se A = 0 e B e C forem diferentes. Construa o mapa e determine a expressão mínima.

26. **Exercício 26 – Função com “Don’t Care” e Quatro Mintermos**  
    Considere F(A, B, C, D) = 1 para m(4, 6, 10, 12, 14) com don’t care para m(0, 2). Utilize o mapa de Karnaugh para obter a expressão simplificada.

27. **Exercício 27 – Restrição Condicional em 4 Variáveis**  
    Dada F(A, B, C, D) com F = 1 para m(0, 2, 8, 10, 12, 14) e 0 para os demais, determine a expressão mínima.

28. **Exercício 28 – Peso Exato em 3 Variáveis**  
    Seja F(A, B, C) = 1 se, e somente se, há exatamente dois 1’s na entrada. Construa o mapa e escreva a expressão mínima.

29. **Exercício 29 – Comparador de Metades**  
    Considere F(A, B, C, D) = 1 se o par (A, B) for igual ao par (C, D). Utilize o mapa para obter a expressão mínima.

30. **Exercício 30 – Função com Agrupamentos Múltiplos**  
    Dada F(A, B, C, D) definida pelos mintermos m(0, 1, 5, 7, 8, 9, 13, 15), construa o mapa, forme os grupos ideais e determine a expressão simplificada.

---

## 8. Resolução dos Exercícios

**Exercício 1 – Função 2 Variáveis Simples**  
- **Mapa:**  
  \[
  \begin{array}{c|cc}
  & B=0 & B=1 \\
  \hline
  A=0 & 0 & 1 \\
  A=1 & 1 & 1 \\
  \end{array}
  \]
- **Agrupamento:**  
  Um grupo que cobre as células com A = 1 (ambas as colunas) e, consequentemente, outro grupo que pode ser formado pela coluna em que B = 1.  
- **Solução:**  
  F = A + B.

---

**Exercício 2 – Mintermos em 3 Variáveis**  
- **Dados:**  
  Mintermos m(1)=001, m(3)=011, m(5)=101, m(7)=111.
- **Observação:**  
  Em todos os casos, C = 1.
- **Solução:**  
  F = C.

---

**Exercício 3 – Agrupamento Básico em 3 Variáveis**  
- **Dados:**  
  Mintermos: m(0)=000, m(2)=010, m(5)=101, m(7)=111.
- **Agrupamento:**  
  - Agrupe m(0) e m(2): ambas têm A=0 e C=0.  
  - Agrupe m(5) e m(7): ambas têm A=1 e C=1.
- **Solução:**  
  F = \(\bar{A}\bar{C} + AC\) (o que equivale a A XNOR C).

---

**Exercício 4 – Uso de “Don’t Care” em 3 Variáveis**  
- **Dados:**  
  F = 1 para mintermos m(2)=010, m(3)=011, m(6)=110, m(7)=111; don’t care para m(0) e m(1).  
- **Agrupamento:**  
  Note que m(2,3,6,7) formam um grupo com B = 1 em todas as células.
- **Solução:**  
  F = B.

---

**Exercício 5 – Função em 4 Variáveis I**  
- **Dados:**  
  Mintermos: m(1)=0001, m(3)=0011, m(7)=0111, m(11)=1011, m(15)=1111.
- **Agrupamento:**  
  - Os mintermos m(3), m(7), m(11) e m(15) compartilham C = 1 e D = 1 → termo: \(CD\).  
  - O mintermo m(1) isolado permanece como \(\bar{A}\bar{B}\bar{C}D\).
- **Solução:**  
  F = \(CD + \bar{A}\bar{B}\bar{C}D\).

---

**Exercício 6 – Função em 4 Variáveis II**  
- **Dados:**  
  Mintermos: m(0)=0000, m(2)=0010, m(5)=0101, m(7)=0111, m(8)=1000, m(10)=1010, m(13)=1101, m(15)=1111.
- **Agrupamento:**  
  Após análise dos grupos, obtém-se que variáveis B e D permanecem constantes em agrupamentos grandes.
- **Solução (resultado simplificado):**  
  F = \(\bar{B}\bar{D} + BD\) (o que equivale a um XNOR entre B e D).

---

**Exercício 7 – Regiões Contíguas**  
- **Dados:**  
  Mintermos: m(4)=0100, m(5)=0101, m(6)=0110, m(7)=0111, m(12)=1100, m(13)=1101, m(14)=1110, m(15)=1111.
- **Observação:**  
  Em todos esses casos, B = 1.
- **Solução:**  
  F = B.

---

**Exercício 8 – Inclusão de “Don’t Care” em 4 Variáveis**  
- **Dados:**  
  F = 1 para m(1)=0001, m(3)=0011, m(8)=1000, m(9)=1001, m(10)=1010, m(11)=1011; don’t care para m(0) e m(7).
- **Agrupamento:**  
  - m(8,9,10,11) → compartilham A=1 e B=0: termo = \(A\bar{B}\).  
  - m(1,3) → compartilham A=0, B=0 e D=1: termo = \(\bar{A}\bar{B}D\).
- **Solução:**  
  F = \(A\bar{B} + \bar{A}\bar{B}D\).  
  (Podendo ser fatorado como \( \bar{B}(A + \bar{A}D)\), e depois simplificado se conveniente).

---

**Exercício 9 – Função de Bloco**  
- **Dados:**  
  F(A, B, C, D) = 1 para todas as combinações com A = 0 (m(0) a m(7)).
- **Solução:**  
  F = \(\bar{A}\).

---

**Exercício 10 – Grupo Duplo**  
- **Dados:**  
  Suponha que o mapa permita formar dois grupos: um para m(0–7) e outro para m(8,9,10,11).
- **Agrupamento:**  
  - O grupo m(0–7) simplifica para \(\bar{A}\).  
  - O grupo m(8–11) pode simplificar para \(A\bar{B}\) (dependendo da disposição).
- **Solução:**  
  F = \(\bar{A} + A\bar{B}\).

---

**Exercício 11 – Função em 3 Variáveis com “Don’t Care”**  
- **Dados:**  
  F = 1 para m(3)=011, m(5)=101, m(7)=111; don’t care para m(1).
- **Observação:**  
  Em todos os mintermos com F = 1, o literal C = 1.
- **Solução:**  
  F = C.

---

**Exercício 12 – Grupo com “Don’t Care” em 4 Variáveis**  
- **Dados:**  
  F = 1 para m(2)=0010, m(3)=0011, m(8)=1000, m(9)=1001, m(10)=1010, m(11)=1011; don’t care para m(0), m(7) e m(15).
- **Agrupamento:**  
  - m(2,3) → dão \(\bar{A}\bar{B}C\).  
  - m(8–11) → dão \(A\bar{B}\).
- **Solução:**  
  F = \(\bar{A}\bar{B}C + A\bar{B}\) ou, fatorando \(\bar{B}\): F = \(\bar{B}(A + \bar{A}C)\).

---

**Exercício 13 – Função Complementar de AND (2 Variáveis)**  
- **Conceito:**  
  F = 0 somente quando B = 1 e C = 1.
- **Solução:**  
  F = \((B \cdot C)'\) = \(\bar{B} + \bar{C}\) (pelo Teorema de De Morgan).

---

**Exercício 14 – Exatamente Uma Verdadeira (3 Variáveis)**  
- **Condição:**  
  F = 1 para as combinações: (1,0,0), (0,1,0) e (0,0,1).
- **Expressão Canônica:**  
  F = \(A\bar{B}\bar{C} + \bar{A}B\bar{C} + \bar{A}\bar{B}C\).

---

**Exercício 15 – Bloco Central**  
- **Dados:**  
  Considere o bloco formado por m(5)=0101, m(6)=0110, m(9)=1001, m(10)=1010.
- **Observação:**  
  Em m(5) e m(6), A = 0 e B = 1; em m(9) e m(10), A = 1 e B = 0. Assim, em ambos os casos A e B são complementares.
- **Solução:**  
  F = \(A \oplus B\) (o que representa “A XOR B”).

---

**Exercício 16 – Função com Muitos Uns**  
- **Dados:**  
  F = 1 para m(0,1,2,4,5,6,7,8,10,11,12,13,14) em 4 variáveis.  
  (Os únicos não incluídos são m(3), m(9) e m(15).)
- **Solução:**  
  A análise pelo mapa de Karnaugh (com grupos grandes aproveitando o “don’t care” se houver) resulta em uma expressão mínima complexa.  
  Uma possível resposta simplificada obtida é:  
  F = \(A\bar{C} + \bar{A}\bar{B}D + B\bar{D} + \bar{B}C\).  
  *(Observação: Esta expressão pode variar conforme a técnica de agrupamento aplicada.)*

---

**Exercício 17 – Circuito de Controle**  
- **Condição:**  
  F = 1 se A = 1 ou se (B = 1 e C = 0).
- **Solução:**  
  F = \(A + (B \cdot \bar{C})\).

---

**Exercício 18 – Função com XOR**  
- **Condição:**  
  F = 1 se A = 1 e (B XOR C) é verdadeiro.
- **Expressão do XOR:**  
  \(B \oplus C = B\bar{C} + \bar{B}C\).
- **Solução:**  
  F = \(A\,(B\bar{C} + \bar{B}C)\).

---

**Exercício 19 – Função com Múltiplos Mintermos**  
- **Dados:**  
  Mintermos: m(1)=0001, m(2)=0010, m(3)=0011, m(9)=1001, m(11)=1011, m(13)=1101, m(15)=1111.
- **Agrupamento:**  
  - m(1,2,3) se agrupam com A=0 e B=0 ⇒ termo: \(\bar{A}\bar{B}\).  
  - m(9,11,13,15) se agrupam com A=1 e D=1 ⇒ termo: \(A\,D\).
- **Solução:**  
  F = \(\bar{A}\bar{B} + A\,D\).

---

**Exercício 20 – Agrupamento com “Don’t Care” em 3 Variáveis**  
- **Dados:**  
  F = 1 para m(0)=000, m(1)=001, m(3)=011, m(7)=111; don’t care para m(2) e m(5).
- **Agrupamento:**  
  - Agrupe m(0,1) → dá \(\bar{A}\bar{B}\).  
  - Agrupe m(3,7) → dá \(B\,C\).  
- **Solução:**  
  F = \(\bar{A}\bar{B} + B\,C\).

---

**Exercício 21 – Linha Completa**  
- **Dados:**  
  F = 1 para todas as células em que A = 0 (toda a linha correspondente), ou seja, m(0) a m(7).
- **Solução:**  
  F = \(\bar{A}\).

---

**Exercício 22 – Função OR (2 Variáveis)**  
- **Observação:**  
  Para a função OR, F = 1 sempre que A = 1 ou B = 1.
- **Solução:**  
  F = A + B.

---

**Exercício 23 – Função MAJORITY (3 Variáveis)**  
- **Condição:**  
  F = 1 se pelo menos duas das variáveis forem 1.
- **Solução:**  
  F = \(AB + AC + BC\).

---

**Exercício 24 – Paridade Par (4 Variáveis)**  
- **Condição:**  
  F = 1 quando o número de 1’s é par.
- **Solução:**  
  Uma forma compacta de expressar a paridade par é:  
  F = \(\overline{A \oplus B \oplus C \oplus D}\).

---

**Exercício 25 – Comparação com Condição**  
- **Condição:**  
  F = 1 somente se A = 0 e B e C forem diferentes (isto é, B XOR C = 1).
- **Solução:**  
  F = \(\bar{A}\,(B\bar{C} + \bar{B}C)\).

---

**Exercício 26 – Função com “Don’t Care” e Quatro Mintermos**  
- **Dados:**  
  F = 1 para m(4)=0100, m(6)=0110, m(10)=1010, m(12)=1100, m(14)=1110; don’t care para m(0) e m(2).
- **Agrupamento:**  
  Nota-se que todas as células possuem D = 0; além disso, os agrupamentos levam à expressão com fatores B e A C.
- **Solução:**  
  F = \(\bar{D}\,(B + AC)\).

---

**Exercício 27 – Restrição Condicional em 4 Variáveis**  
- **Dados:**  
  F = 1 para m(0)=0000, m(2)=0010, m(8)=1000, m(10)=1010, m(12)=1100, m(14)=1110.
- **Agrupamento:**  
  - Agrupe m(0,2,8,10): em que B = 0 e D = 0 ⇒ termo: \(\bar{B}\bar{D}\).  
  - Agrupe m(12,14): em que A = 1, B = 1 e D = 0 ⇒ termo: \(AB\bar{D}\).
- **Solução:**  
  F = \(\bar{B}\bar{D} + AB\bar{D} = \bar{D}(\bar{B} + AB)\).  
  Como \(\bar{B} + AB = \bar{B} + A\), temos:  
  F = \(\bar{D}(A + \bar{B})\).

---

**Exercício 28 – Peso Exato em 3 Variáveis**  
- **Condição:**  
  F = 1 se e somente se houver exatamente dois 1’s.
- **Mintermos:**  
  (A=1, B=1, C=0), (A=1, B=0, C=1) e (A=0, B=1, C=1).
- **Solução:**  
  F = \(AB\bar{C} + A\bar{B}C + \bar{A}BC\).

---

**Exercício 29 – Comparador de Metades**  
- **Condição:**  
  F = 1 se o par (A, B) for igual ao par (C, D).
- **Solução:**  
  Uma expressão que utiliza a equivalência (XNOR) é:  
  F = \((A \oplus C)' \cdot (B \oplus D)'\).

---

**Exercício 30 – Função com Agrupamentos Múltiplos**  
- **Dados:**  
  Mintermos: m(0)=0000, m(1)=0001, m(5)=0101, m(7)=0111, m(8)=1000, m(9)=1001, m(13)=1101, m(15)=1111.
- **Agrupamento:**  
  - Agrupe m(0,1) → comum: A=0, B=0, C=0 ⇒ termo: \(\bar{A}\bar{B}\bar{C}\).  
  - Agrupe m(5,7) → comum: A=0, B=1 e D=1 ⇒ termo: \(\bar{A}B\,D\).  
  - Agrupe m(8,9) → comum: A=1, B=0, C=0 ⇒ termo: \(A\bar{B}\bar{C}\).  
  - Agrupe m(13,15) → comum: A=1, B=1, D=1 ⇒ termo: \(AB\,D\).  
  - Notando que:  
    \(\bar{A}\bar{B}\bar{C} + A\bar{B}\bar{C} = \bar{B}\bar{C}\)  
    e  
    \(\bar{A}B\,D + AB\,D = B\,D\).
- **Solução:**  
  F = \(\bar{B}\bar{C} + B\,D\).

---

## 9. Bibliografia

- **Tocci, R. J., Widmer, N. S., & Moss, G. L.** (2011). *Sistemas Digitais: Princípios e Aplicações* (11ª ed.). São Paulo: Pearson Prentice Hall. ISBN: 978-85-4300-694-9.
- **Video Aula: Circuitos Digitais – Mapa de Karnaugh**  
  Professor André Ricardo Fioravanti (UNIVESP) – [Assistir ao vídeo](https://www.youtube.com/watch?v=hyCTj4WxkFY&t=984s).
- **Video Complementar: Mapa de Karnaugh passo a passo**  
  Cadmus Control – [Assistir ao vídeo](https://www.youtube.com/watch?v=KR_wcyBjbRE).