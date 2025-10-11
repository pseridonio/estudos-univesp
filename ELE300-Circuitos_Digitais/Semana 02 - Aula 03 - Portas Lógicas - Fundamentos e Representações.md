# Portas Lógicas: Fundamentos e Representações

## Introdução

Nesta aula, exploramos as sete principais portas lógicas utilizadas em circuitos digitais. As portas lógicas são os blocos fundamentais da eletrônica digital, responsáveis por realizar operações lógicas sobre sinais binários. Compreender seu funcionamento é essencial para projetar e analisar sistemas digitais, desde simples circuitos até microcontroladores complexos.

## Desenvolvimento

### 🔌 O que são Portas Lógicas?

Portas lógicas são dispositivos eletrônicos que realizam operações lógicas com sinais binários (nível lógico 0 ou 1). Cada porta possui uma ou mais entradas e uma única saída. A saída depende da combinação dos sinais de entrada, conforme definido por sua função lógica.

**Exemplo de circuito integrado (CI):**  
CI 7400 contém quatro portas NAND.

---

### 📊 Representações das Portas Lógicas

As portas podem ser representadas de várias formas:

- **Símbolo lógico:** Desenho padronizado usado em diagramas.
- **Tabela verdade:** Lista todas as combinações possíveis de entrada e suas respectivas saídas.
- **Diagrama de tempo:** Mostra a relação temporal entre entrada e saída.
- **Expressão algébrica:** Representação matemática da função lógica.
- **Descrição em VHDL:** Linguagem de descrição de hardware que especifica entradas, saídas e comportamento.

---

### 🔁 Tabela Verdade

Para um circuito com \( n \) entradas, a tabela verdade possui \( 2^n \) linhas.  
Exemplo: 3 entradas → \( 2^3 = 8 \) combinações possíveis.

---

### 🧠 As 7 Portas Lógicas Fundamentais

#### 1. Porta NOT (Inversora)

- **Função:** Inverte o valor lógico da entrada.
- **Tabela verdade:**

| Entrada (A) | Saída (S) |
|-------------|-----------|
| 0           | 1         |
| 1           | 0         |

- **Expressão algébrica:**  
  \( S = \overline{A} \) ou \( S = NOT(A) \)

- **VHDL:**
```vhdl
S <= NOT A;
```

- **CMOS:**  
  Utiliza transistores PMOS e NMOS para inverter o sinal.

---

#### 2. Porta AND (E)

- **Função:** Saída é 1 somente se todas as entradas forem 1.
- **Tabela verdade (2 entradas):**

| A | B | S |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

- **Expressão algébrica:**  
  \( S = A \cdot B \)

- **Analogia:** Multiplicação binária.

---

#### 3. Porta OR (OU)

- **Função:** Saída é 1 se pelo menos uma entrada for 1.
- **Tabela verdade (2 entradas):**

| A | B | S |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

- **Expressão algébrica:**  
  \( S = A + B \)

---

#### 4. Porta NAND (NE)

- **Função:** Inversão da porta AND.
- **Tabela verdade:**

| A | B | AND | NAND |
|---|---|-----|------|
| 0 | 0 | 0   | 1    |
| 0 | 1 | 0   | 1    |
| 1 | 0 | 0   | 1    |
| 1 | 1 | 1   | 0    |

- **Expressão algébrica:**  
  \( S = \overline{A \cdot B} \)

- **Equivalência:**  
  NAND ≡ OR com entradas invertidas.

---

#### 5. Porta NOR (NOU)

- **Função:** Inversão da porta OR.
- **Tabela verdade:**

| A | B | OR | NOR |
|---|---|----|-----|
| 0 | 0 | 0  | 1   |
| 0 | 1 | 1  | 0   |
| 1 | 0 | 1  | 0   |
| 1 | 1 | 1  | 0   |

- **Expressão algébrica:**  
  \( S = \overline{A + B} \)

- **Equivalência:**  
  NOR ≡ AND com entradas invertidas.

---

#### 6. Porta XOR (OU-Exclusivo)

- **Função:** Saída é 1 se as entradas forem diferentes.
- **Tabela verdade:**

| A | B | S |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

- **Expressão algébrica:**  
  \( S = A \oplus B \)

---

#### 7. Porta XNOR (NOU-Exclusivo)

- **Função:** Saída é 1 se as entradas forem iguais.
- **Tabela verdade:**

| A | B | S |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

- **Expressão algébrica:**  
  \( S = \overline{A \oplus B} \)

---

## Conclusão

As portas lógicas são os elementos básicos da construção de sistemas digitais. Cada porta possui uma função específica e pode ser representada de diversas formas, desde símbolos até linguagens de descrição de hardware. O domínio desses conceitos é essencial para o desenvolvimento de circuitos combinacionais e sequenciais.

---

## Análise Crítica

O vídeo apresenta os conceitos com clareza e boa didática, utilizando exemplos visuais e tabelas verdade. A explicação sobre equivalências entre portas e a introdução ao VHDL são pontos positivos. No entanto, seria interessante incluir simulações práticas ou aplicações reais para reforçar o aprendizado.

---

## Sugestões de Complementação

- Apresentar exemplos de circuitos combinacionais utilizando múltiplas portas.
- Incluir exercícios com expressões lógicas para simplificação.
- Demonstrar simulações em software como Logisim ou Quartus.

---

## Exercícios (com resolução detalhada)

### 1. Construa a tabela verdade da expressão:  
\( S = \overline{A \cdot B} \)

**Solução:**  

| A | B | A·B | S = ¬(A·B) |
|---|---|-----|------------|
| 0 | 0 | 0   | 1          |
| 0 | 1 | 0   | 1          |
| 1 | 0 | 0   | 1          |
| 1 | 1 | 1   | 0          |

---

### 2. Qual a saída da expressão:  
\( S = A \oplus B \) para A = 1 e B = 0?

**Solução:**
- Entradas diferentes → Saída = 1

---

### 3. Escreva a expressão lógica equivalente à porta NOR com entradas invertidas.

**Solução:**
- NOR ≡ AND com entradas invertidas  
- \( S = \overline{A} \cdot \overline{B} \)

---

### 4. Descreva em VHDL uma porta AND com duas entradas.

**Solução:**
```vhdl
S <= A AND B;
```

---

## Bibliografia

- TOCCI, Ronald J.; WIDMER, Neal S.; MOSS, Gregory L. *Sistemas digitais: princípios e aplicações*. 11. ed. São Paulo: Pearson Prentice Hall, 2011.
- GUNTZEL, J. *Circuitos de Armazenamento*. Disponível em: [inf.ufsc.br](https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf). Acesso em: 10 out. 2025.
- FIORAVANTI, André Ricardo. *Circuitos Digitais – Portas Lógicas*. YouTube, 2021. Disponível em: [YouTube](https://www.youtube.com/watch?v=AKcVR09WhaA). Acesso em: 10 out. 2025.

---

## Materiais Complementares

- Livro: TOCCI, Ronald J.; WIDMER, Neal S.; MOSS, Gregory L. *Sistemas digitais: princípios e aplicações*. 11. ed. São Paulo: Pearson Prentice Hall, 2011.
- PDF: GUNTZEL, J. *Circuitos de Armazenamento*. Disponível em: [inf.ufsc.br](https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf). Acesso em: 10 out. 2025.
- Sites confiáveis utilizados:
  - [Khan Academy – Portas Lógicas](https://pt.khanacademy.org/computing/computer-science/cryptography/logic-gates/a/logic-gates-review). Acesso em: 10 out. 2025.
  - [YouTube – Portas Lógicas](https://www.youtube.com/watch?v=AKcVR09WhaA)

---

