# Conversão de Números Decimais para Binário, Octal e Hexadecimal

## Introdução

Nesta aula, aprendemos a realizar conversões de números decimais para outras bases numéricas: binária (base 2), octal (base 8) e hexadecimal (base 16). Esse processo é essencial para compreender como os sistemas digitais representam e manipulam dados. A conversão é feita em duas etapas: parte inteira e parte fracionária, utilizando divisões e multiplicações sucessivas.

## Desenvolvimento

### 🧮 Etapas da Conversão

A conversão de um número decimal para outra base é dividida em duas partes:

1. **Parte inteira** → usa divisões sucessivas pela nova base.
2. **Parte fracionária** → usa multiplicações sucessivas pela nova base.

---

### 🔢 Parte Inteira: Divisões Sucessivas

**Procedimento:**
- Divida o número inteiro pela base desejada.
- Anote o **resto** de cada divisão.
- Continue dividindo o quociente até ele ser zero.
- Os restos, lidos de baixo para cima, formam o número na nova base.

**Exemplo 1: Decimal 67 → Binário**
- 67 ÷ 2 = 33 → resto 1  
- 33 ÷ 2 = 16 → resto 1  
- 16 ÷ 2 = 8 → resto 0  
- 8 ÷ 2 = 4 → resto 0  
- 4 ÷ 2 = 2 → resto 0  
- 2 ÷ 2 = 1 → resto 0  
- 1 ÷ 2 = 0 → resto 1  
- **Resultado:** \(67_{10} = 1000011_2\)

**Exemplo 2: Decimal 92 → Octal**
- 92 ÷ 8 = 11 → resto 4  
- 11 ÷ 8 = 1 → resto 3  
- 1 ÷ 8 = 0 → resto 1  
- **Resultado:** \(92_{10} = 134_8\)

**Exemplo 3: Decimal 1000 → Hexadecimal**
- 1000 ÷ 16 = 62 → resto 8  
- 62 ÷ 16 = 3 → resto 14 (E)  
- 3 ÷ 16 = 0 → resto 3  
- **Resultado:** \(1000_{10} = 3E8_{16}\)

---

### 🔍 Parte Fracionária: Multiplicações Sucessivas

**Procedimento:**
- Multiplique a parte fracionária pela base.
- Anote a **parte inteira** do resultado como o próximo dígito.
- Use a parte fracionária restante para a próxima multiplicação.
- Repita até obter uma conversão exata ou atingir o número desejado de dígitos.

**Exemplo 1: Decimal 0.625 → Binário**
- 0.625 × 2 = 1.25 → parte inteira: 1  
- 0.25 × 2 = 0.5 → parte inteira: 0  
- 0.5 × 2 = 1.0 → parte inteira: 1  
- **Resultado:** \(0.625_{10} = 0.101_2\)

**Exemplo 2: Decimal 0.635 → Octal**
- 0.635 × 8 = 5.08 → parte inteira: 5  
- 0.08 × 8 = 0.64 → parte inteira: 0  
- 0.64 × 8 = 5.12 → parte inteira: 5  
- 0.12 × 8 = 0.96 → parte inteira: 0  
- 0.96 × 8 = 7.68 → parte inteira: 7  
- 0.68 × 8 = 5.44 → parte inteira: 5  
- 0.44 × 8 = 3.52 → parte inteira: 3  
- 0.52 × 8 = 4.16 → parte inteira: 4  
- **Resultado aproximado:** \(0.635_{10} ≈ 0.5057534_8\)

**Exemplo 3: Decimal 0.635 → Hexadecimal**
- 0.635 × 16 = 10.16 → parte inteira: 10 (A)  
- 0.16 × 16 = 2.56 → parte inteira: 2  
- 0.56 × 16 = 8.96 → parte inteira: 8  
- 0.96 × 16 = 15.36 → parte inteira: 15 (F)  
- 0.36 × 16 = 5.76 → parte inteira: 5  
- 0.76 × 16 = 12.16 → parte inteira: 12 (C)  
- **Resultado aproximado:** \(0.635_{10} ≈ 0.A28F5C_{16}\)

---

## Conclusão

A conversão de números decimais para outras bases é um processo sistemático que envolve divisões e multiplicações sucessivas. Com prática, é possível realizar essas conversões com precisão, o que é essencial para o entendimento de sistemas digitais e programação de baixo nível.

## Análise crítica

A aula apresenta os conceitos de forma clara e com exemplos bem escolhidos. A explicação das etapas separadas para parte inteira e fracionária é didática. Seria interessante incluir mais exercícios com diferentes bases e casos de dízimas periódicas para reforçar o entendimento.

## Sugestões de complementação

- Introduzir conversões inversas (de outras bases para decimal).
- Aplicar os conceitos em contextos reais, como endereçamento de memória.
- Explorar ferramentas digitais para automatizar conversões.

## Exercícios (com resolução detalhada)

### 1. Converta o número decimal 45 para binário.
**Resolução:**
- 45 ÷ 2 = 22 → resto 1  
- 22 ÷ 2 = 11 → resto 0  
- 11 ÷ 2 = 5 → resto 1  
- 5 ÷ 2 = 2 → resto 1  
- 2 ÷ 2 = 1 → resto 0  
- 1 ÷ 2 = 0 → resto 1  
- **Resultado:** \(45_{10} = 101101_2\)

### 2. Converta o número decimal 0.375 para binário.
**Resolução:**
- 0.375 × 2 = 0.75 → parte inteira: 0  
- 0.75 × 2 = 1.5 → parte inteira: 1  
- 0.5 × 2 = 1.0 → parte inteira: 1  
- **Resultado:** \(0.375_{10} = 0.011_2\)

### 3. Converta o número decimal 255 para hexadecimal.
**Resolução:**
- 255 ÷ 16 = 15 → resto 15 (F)  
- 15 ÷ 16 = 0 → resto 15 (F)  
- **Resultado:** \(255_{10} = FF_{16}\)

### 4. Converta o número decimal 0.1 para hexadecimal (4 dígitos).
**Resolução:**
- 0.1 × 16 = 1.6 → parte inteira: 1  
- 0.6 × 16 = 9.6 → parte inteira: 9  
- 0.6 × 16 = 9.6 → parte inteira: 9  
- 0.6 × 16 = 9.6 → parte inteira: 9  
- **Resultado aproximado:** \(0.1_{10} ≈ 0.1999_{16}\)

### 5. Converta o número decimal 123.625 para octal.
**Resolução:**
- Parte inteira:  
  - 123 ÷ 8 = 15 → resto 3  
  - 15 ÷ 8 = 1 → resto 7  
  - 1 ÷ 8 = 0 → resto 1  
  - Resultado: \(123_{10} = 173_8\)

- Parte fracionária:  
  - 0.625 × 8 = 5.0 → parte inteira: 5  
  - Resultado: \(0.625_{10} = 0.5_8\)

- **Resultado final:** \(123.625_{10} = 173.5_8\)

## Bibliografia

- Tocci, Ronald J.; Widmer, Neal S.; Moss, Gregory L. *Sistemas digitais: princípios e aplicações*. Pearson, 11ª edição, 2011.
- [Circuitos de Armazenamento – UFSC](https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf) – Acesso em 09/10/2025.
- [Vídeo da aula – Conversão de Números Decimais para Binário, Octal e Hexadecimal](https://www.youtube.com/watch?v=53msbl3hciY) – Acesso em 09/10/2025.