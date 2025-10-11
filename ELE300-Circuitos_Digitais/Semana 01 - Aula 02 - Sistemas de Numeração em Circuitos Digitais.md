# Sistemas de Numeração em Circuitos Digitais

## Introdução

Nesta aula, exploramos os sistemas de numeração utilizados em circuitos digitais. Compreender diferentes bases numéricas é essencial para interpretar e projetar sistemas digitais, pois a informação nesses sistemas é representada por números em diversas bases, especialmente a binária. A aula aborda:

- Bases numéricas comuns e históricas.
- Conversão entre bases (inteiros e fracionários).
- Representações em ponto flutuante.
- Códigos numéricos especiais como BCD e Gray.

## Desenvolvimento

### 🧮 Bases Numéricas

#### Sistema Decimal (Base 10)
- Utiliza os dígitos de 0 a 9.
- É o sistema mais comum no cotidiano.
- Cada dígito tem um valor posicional: ex. \(123.8 = 1 \times 10^2 + 2 \times 10^1 + 3 \times 10^0 + 8 \times 10^{-1}\).

#### Sistema Duodecimal (Base 12)
- Utiliza os dígitos 0 a 9, A (10), B (11).
- Aplicações: tempo (12 horas), medidas imperiais (1 pé = 12 polegadas), contagem (dúzias).

#### Sistema Sexagesimal (Base 60)
- Legado dos babilônios.
- Usado em tempo: 60 minutos por hora, 60 segundos por minuto.

#### Sistema Binário (Base 2)
- Utiliza apenas os dígitos 0 e 1.
- Fundamental para sistemas digitais.
- Exemplo: \(1011.01 = 1 \times 2^3 + 0 \times 2^2 + 1 \times 2^1 + 1 \times 2^0 + 0 \times 2^{-1} + 1 \times 2^{-2} = 11.25\).

#### Sistema Octal (Base 8)
- Dígitos de 0 a 7.
- Conversão simples com binário: cada dígito octal equivale a 3 bits.

#### Sistema Hexadecimal (Base 16)
- Dígitos de 0 a 9 e letras A a F (10 a 15).
- Conversão com binário: cada dígito hexadecimal equivale a 4 bits.

### 🔄 Conversão entre Bases

#### Binário para Decimal
- Soma dos pesos das posições onde há 1.
- Exemplo: \(1101101.1011 = 64 + 32 + 8 + 4 + 1 + 0.5 + 0.125 + 0.0625 = 109.6875\).

#### Decimal para Binário

**Método de inspeção:**
- Decomposição em potências de 2.
- Exemplo: \(25 = 16 + 8 + 1 \Rightarrow 11001\).

**Método das divisões sucessivas:**
- Divide por 2 até o quociente ser zero.
- Os restos formam o número binário.

**Método das multiplicações sucessivas (para fracionários):**
- Multiplica a parte fracionária por 2 repetidamente.
- Exemplo: \(0.2125 \Rightarrow 0.0101\).

### 📐 Representação em Ponto Flutuante

Utilizada quando ponto fixo é inadequado (valores muito grandes ou pequenos).

**Padrão IEEE-754:**
- Precisão simples: 32 bits.
- Precisão dupla: 64 bits.
- Precisão estendida: 80 bits.

**Formato de 32 bits:**
- 1 bit para sinal.
- 8 bits para expoente polarizado.
- 23 bits para mantissa (parte fracionária).

### 🔢 Códigos Numéricos

#### Código BCD (Binary-Coded Decimal)
- Cada dígito decimal é representado por 4 bits.
- Exemplo: \(35 \Rightarrow 0011\ 0101\).

#### Código Gray
- Não é aritmético nem posicional.
- Apenas um bit muda entre números consecutivos.
- Usado em máquinas de estado para evitar erros de transição.

**Conversão Binário → Gray:**
1. Copia o MSB.
2. Soma bit atual com anterior (descarta carry).

**Conversão Gray → Binário:**
1. Copia o MSB.
2. Soma bit anterior com próximo bit Gray (descarta carry).

## Conclusão

A compreensão dos sistemas de numeração é essencial para o domínio dos circuitos digitais. Saber converter entre bases, entender representações numéricas e aplicar códigos como BCD e Gray permite projetar sistemas mais eficientes e confiáveis.

## Análise crítica

A aula apresenta os conceitos com clareza e bons exemplos. A explicação sobre conversões é prática e bem fundamentada. A única sugestão seria incluir mais exercícios aplicados com circuitos reais para reforçar a utilidade dos códigos.

## Sugestões de complementação

- Explorar aplicações dos códigos BCD e Gray em microcontroladores.
- Introduzir ferramentas de simulação para visualizar conversões.
- Discutir limitações da representação em ponto flutuante em sistemas embarcados.

## Exercícios (com resolução detalhada)

### 1. Converta o número binário 1011.01 para decimal.
**Resolução:**
- Parte inteira: \(1 \times 2^3 + 0 \times 2^2 + 1 \times 2^1 + 1 \times 2^0 = 8 + 0 + 2 + 1 = 11\)
- Parte fracionária: \(0 \times 2^{-1} + 1 \times 2^{-2} = 0 + 0.25 = 0.25\)
- Resultado: \(11.25\)

### 2. Converta o número decimal 25 para binário usando inspeção.
**Resolução:**
- \(25 = 16 + 8 + 1 = 2^4 + 2^3 + 2^0\)
- Binário: \(11001\)

### 3. Converta o número 0.2125 decimal para binário usando multiplicações sucessivas.
**Resolução:**
- \(0.2125 \times 2 = 0.425 → 0\)
- \(0.425 \times 2 = 0.85 → 0\)
- \(0.85 \times 2 = 1.7 → 1\)
- \(0.7 \times 2 = 1.4 → 1\)
- Binário: \(0.0011\)

### 4. Converta o número hexadecimal A0E para binário.
**Resolução:**
- A = 10 → 1010
- 0 = 0 → 0000
- E = 14 → 1110
- Resultado: \(1010\ 0000\ 1110\)

### 5. Converta o número binário 1010 para código Gray.
**Resolução:**
- MSB: 1
- 1 + 0 = 1
- 0 + 1 = 1
- 1 + 0 = 1
- Resultado: \(1111\)

## Bibliografia

- Tocci, Ronald J.; Widmer, Neal S.; Moss, Gregory L. *Sistemas digitais: princípios e aplicações*. Pearson, 11ª edição, 2011.
- [Circuitos de Armazenamento – UFSC](https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf) – Acesso em 09/10/2025.
- [Vídeo da aula – UNIVESP](https://www.youtube.com/watch?v=af5vKBsOAos) – Acesso em 09/10/2025.

## Materiais complementares

- Livro *Sistemas digitais: princípios e aplicações* – Tocci, Widmer e Moss.
- [PDF sobre Circuitos de Armazenamento – UFSC](https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf)

---