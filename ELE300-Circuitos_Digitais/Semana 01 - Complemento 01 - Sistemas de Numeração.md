# Sistemas de Numeração: Decimal, Binário, Octal e Hexadecimal

## Introdução

Esta aula inaugura o curso de Eletrônica Digital e apresenta os quatro principais sistemas de numeração utilizados em circuitos digitais: decimal, binário, octal e hexadecimal. Compreender esses sistemas é essencial para interpretar dados, projetar circuitos e realizar conversões entre diferentes bases numéricas.

---

## Desenvolvimento (Explicado e Didático)

### 🔟 Sistema Decimal (Base 10)

É o sistema que usamos no dia a dia. Ele possui **10 algarismos**: 0 a 9. Cada algarismo tem um valor que depende da **posição** que ocupa no número. Essa característica é chamada de **notação posicional**.

#### 🧠 Como funciona?

Cada posição representa uma **potência de 10**:

| Posição | Potência de 10 | Valor |
|---------|----------------|-------|
| Centena | \(10^2\)       | 100   |
| Dezena  | \(10^1\)       | 10    |
| Unidade | \(10^0\)       | 1     |

**Exemplo:**
O número **575** é composto por:
- \(5 \times 10^2 = 500\)
- \(7 \times 10^1 = 70\)
- \(5 \times 10^0 = 5\)
- **Total: 575**

#### 📌 E os números com vírgula?

A parte fracionária usa potências **negativas** de 10:

**Exemplo:**
\(2358.49 = 2 \times 10^3 + 3 \times 10^2 + 5 \times 10^1 + 8 \times 10^0 + 4 \times 10^{-1} + 9 \times 10^{-2}\)

---

### ⚙️ Sistema Binário (Base 2)

É o sistema usado pelos computadores e circuitos digitais. Possui **apenas dois algarismos**: 0 e 1. Cada posição representa uma **potência de 2**.

#### 🧠 Como funciona?

| Posição | Potência de 2 | Valor |
|---------|----------------|-------|
| \(b_2\) | \(2^2\)         | 4     |
| \(b_1\) | \(2^1\)         | 2     |
| \(b_0\) | \(2^0\)         | 1     |

**Exemplo:**
O número binário **101**:
- \(1 \times 2^2 = 4\)
- \(0 \times 2^1 = 0\)
- \(1 \times 2^0 = 1\)
- **Total: 5**

#### 📌 E com vírgula?

A parte fracionária usa potências **negativas** de 2:

**Exemplo:**
\(1011.01 = 8 + 0 + 2 + 1 + 0 + 0.25 = 11.25\)

#### 🔍 Observação prática

Cada bit representa um estado físico (ligado/desligado). Por isso, o binário é ideal para representar sinais digitais.

---

### 🧮 Sistema Octal (Base 8)

Usa **8 algarismos**: 0 a 7. É útil para representar números binários de forma compacta, pois **cada dígito octal equivale a 3 bits**.

#### 🧠 Como funciona?

| Posição | Potência de 8 | Valor |
|---------|----------------|-------|
| \(o_2\) | \(8^2\)         | 64    |
| \(o_1\) | \(8^1\)         | 8     |
| \(o_0\) | \(8^0\)         | 1     |

**Exemplo:**
Número octal **425**:
- \(4 \times 64 = 256\)
- \(2 \times 8 = 16\)
- \(5 \times 1 = 5\)
- **Total: 277**

#### 📌 E com vírgula?

**Exemplo:**
\(2456.3_8 = 1024 + 256 + 40 + 6 + 0.375 = 1326.375\)

#### 🔍 Observação prática

Muito usado em sistemas embarcados e programação de baixo nível.

---

### 🧠 Sistema Hexadecimal (Base 16)

Usa **16 símbolos**: 0 a 9 e A (10) a F (15). Cada dígito hexadecimal representa **4 bits**, o que facilita a leitura de grandes números binários.

#### 🧠 Como funciona?

| Posição | Potência de 16 | Valor |
|---------|----------------|-------|
| \(h_2\) | \(16^2\)        | 256   |
| \(h_1\) | \(16^1\)        | 16    |
| \(h_0\) | \(16^0\)        | 1     |

**Exemplo:**
Número hexadecimal **2AC**:
- C = 12 → \(12 \times 1 = 12\)
- A = 10 → \(10 \times 16 = 160\)
- 2 → \(2 \times 256 = 512\)
- **Total: 684**

#### 📌 E com vírgula?

**Exemplo:**
\(456.3_{16} = 1024 + 80 + 6 + 0.1875 = 1110.1875\)

#### 🔍 Observação prática

Muito usado em endereçamento de memória, cores em HTML/CSS e linguagens de máquina.

---

## Conclusão

A aula apresentou os fundamentos dos sistemas de numeração utilizados em eletrônica digital. Compreender como cada sistema funciona e como converter entre eles é essencial para o desenvolvimento de circuitos e algoritmos digitais.

## Análise crítica

O vídeo é bem estruturado e didático, com exemplos numéricos claros e progressivos. A explicação sobre notação posicional e a relação entre base e potência é especialmente útil. Seria interessante incluir exercícios práticos com aplicações em circuitos digitais para reforçar o conteúdo.

## Sugestões de complementação

- Introduzir conversões entre bases (decimal ↔ binário, binário ↔ hexadecimal).
- Aplicar os sistemas em contextos reais, como endereçamento de memória.
- Explorar como os sistemas são usados em linguagens de programação.

## Exercícios (com resolução detalhada)

### 1. Converta o número decimal 275 para binário.
**Resolução:**
- Divisões sucessivas por 2:
  - 275 ÷ 2 = 137 → resto 1
  - 137 ÷ 2 = 68 → resto 1
  - 68 ÷ 2 = 34 → resto 0
  - 34 ÷ 2 = 17 → resto 0
  - 17 ÷ 2 = 8 → resto 1
  - 8 ÷ 2 = 4 → resto 0
  - 4 ÷ 2 = 2 → resto 0
  - 2 ÷ 2 = 1 → resto 0
  - 1 ÷ 2 = 0 → resto 1
- Binário: **100010011**

### 2. Converta o número binário 110101 para decimal.
**Resolução:**
- \(1 \times 2^5 + 1 \times 2^4 + 0 \times 2^3 + 1 \times 2^2 + 0 \times 2^1 + 1 \times 2^0 = 32 + 16 + 0 + 4 + 0 + 1 = 53\)

### 3. Converta o número octal 745 para decimal.
**Resolução:**
- \(7 \times 8^2 + 4 \times 8^1 + 5 \times 8^0 = 448 + 32 + 5 = 485\)

### 4. Converta o número hexadecimal 3F para decimal.
**Resolução:**
- F = 15 → \(15 \times 16^0 = 15\)
- 3 → \(3 \times 16^1 = 48\)
- **Total: 63**

### 5. Converta o número decimal 684 para hexadecimal.
**Resolução:**
- 684 ÷ 16 = 42 → resto 12 → C
- 42 ÷ 16 = 2 → resto 10 → A
- 2 ÷ 16 = 0 → resto 2
- Hexadecimal: **2AC**

## Bibliografia

- Tocci, Ronald J.; Widmer, Neal S.; Moss, Gregory L. *Sistemas digitais: princípios e aplicações*. Pearson, 11ª edição, 2011.
- [Circuitos de Armazenamento – UFSC](https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf) – Acesso em 09/10/2025.
- [Vídeo da aula – Decimal, binário, octal e hexadecimal](https://www.youtube.com/watch?v=dr57yeIaIBM) – Acesso em 09/10/2025.

## Materiais complementares

- Livro *Sistemas digitais: princípios e aplicações* – Tocci, Widmer e Moss.
- [PDF sobre Circuitos de Armazenamento – UFSC](https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf)

---