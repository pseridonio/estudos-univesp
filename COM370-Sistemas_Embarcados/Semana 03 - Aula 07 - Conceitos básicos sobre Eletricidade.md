# Fundamentos de Eletricidade Aplicados a Sistemas Embarcados

---

## Introdução

O estudo de sistemas embarcados exige domínio sólido dos fundamentos da eletricidade. Microcontroladores, sensores, atuadores e dispositivos de comunicação operam com sinais elétricos que obedecem a leis físicas bem estabelecidas. A compreensão da relação entre tensão, corrente e resistência é indispensável para projetar circuitos confiáveis, calcular consumo energético, evitar sobrecargas e interpretar corretamente esquemas eletrônicos.

A Lei de Ohm constitui a base dessa compreensão. A partir dela, torna-se possível analisar circuitos simples e complexos, prever comportamento elétrico e dimensionar componentes. Este material apresenta os conceitos fundamentais de forma estruturada e aprofundada, com foco em aplicações práticas em sistemas embarcados.

---

## Desenvolvimento

### A Natureza da Corrente Elétrica

#### Contexto

Todo sistema embarcado depende do fluxo controlado de energia elétrica. Sensores enviam sinais, processadores executam instruções e atuadores realizam trabalho físico. Esse funcionamento ocorre porque cargas elétricas se movimentam em um condutor.

#### Conceito

Corrente elétrica é o fluxo ordenado de cargas elétricas através de um material condutor. Sua unidade no Sistema Internacional é o ampère (A), em homenagem a André-Marie Ampère.

Formalmente, corrente é definida como a quantidade de carga elétrica que atravessa uma seção transversal de um condutor por unidade de tempo:

$$
I = \frac{Q}{t}
$$

Onde:

* $I$ = corrente elétrica (ampères)
* $Q$ = carga elétrica (coulombs)
* $t$ = tempo (segundos)

Um ampère corresponde à passagem de 1 coulomb por segundo.

#### Funcionamento Físico

Nos metais, os elétrons livres movimentam-se quando submetidos a um campo elétrico. Esse campo é criado por uma diferença de potencial aplicada ao material. Quanto maior a diferença de potencial, maior a força que impulsiona os elétrons.

Se não houver resistência significativa, a corrente pode atingir valores muito elevados, situação conhecida como curto-circuito.

---

### Tensão ou Diferença de Potencial

#### Contexto

A tensão é a “força motriz” que impulsiona as cargas elétricas. Em sistemas embarcados, é comum trabalhar com tensões como 3,3 V, 5 V ou 12 V.

#### Conceito

Tensão elétrica, ou diferença de potencial (DDP), é a energia por unidade de carga disponível entre dois pontos de um circuito.

Sua unidade é o volt (V), em homenagem a Alessandro Volta.

Pode ser definida como:

$$
V = \frac{E}{Q}
$$

Onde:

* $V$ = tensão (volts)
* $E$ = energia (joules)
* $Q$ = carga elétrica (coulombs)

#### Analogia Hidráulica

Imagine uma caixa d’água elevada. A altura representa a tensão. Quanto maior a altura, maior a pressão da água. A água corresponde à corrente. A tubulação representa o condutor. Se houver obstrução no cano, isso corresponde à resistência.

Essa analogia é útil para visualizar a interação entre tensão, corrente e resistência.

---

### Resistência Elétrica

#### Contexto

Nenhum material real permite passagem de corrente sem oposição. Essa oposição é a resistência elétrica.

#### Conceito

Resistência é a propriedade que um material possui de se opor à passagem da corrente elétrica. Sua unidade é o ohm (Ω), em homenagem a Georg Ohm.

Materiais condutores possuem baixa resistência (ex: cobre). Materiais isolantes possuem alta resistência (ex: borracha).

#### Fatores que Influenciam a Resistência

A resistência de um condutor depende de três fatores fundamentais:

1. Resistividade do material (ρ)
2. Comprimento (L)
3. Área da seção transversal (A)

A relação é dada por:

$$
R = \rho \frac{L}{A}
$$

Onde:

* $R$ = resistência (Ω)
* $\rho$ = resistividade (Ω·m)
* $L$ = comprimento (m)
* $A$ = área (m²)

#### Interpretação Física

* Quanto maior o comprimento, maior a resistência.
* Quanto maior a área, menor a resistência.
* Quanto maior a resistividade do material, maior a resistência.

#### Exemplo Numérico

Considere um fio de cobre com:

* $\rho = 1,7 \times 10^{-8} \ \Omega \cdot m$
* $L = 2 \ m$
* $A = 1 \times 10^{-6} \ m²$

Aplicando:

$$
R = 1,7 \times 10^{-8} \cdot \frac{2}{1 \times 10^{-6}}
$$

$$
R = 3,4 \times 10^{-2} \ \Omega
$$

Resultado: 0,034 Ω

Esse valor pequeno confirma que cobre é excelente condutor.

---

### Lei de Ohm

#### Conceito Fundamental

A Lei de Ohm estabelece a relação entre tensão, corrente e resistência:

$$
V = R \cdot I
$$

Podendo ser rearranjada como:

$$
I = \frac{V}{R}
$$

$$
R = \frac{V}{I}
$$

Essa relação é válida para materiais ôhmicos sob temperatura constante.

#### Interpretação Física

* Se a tensão aumenta e a resistência é constante, a corrente aumenta.
* Se a resistência aumenta e a tensão é constante, a corrente diminui.

#### Exemplo Resolvido

Suponha um resistor de 220 Ω ligado a 5 V.

$$
I = \frac{5}{220}
$$

$$
I = 0,0227 \ A
$$

Corrente ≈ 22,7 mA

Esse cálculo é típico em dimensionamento de LEDs em sistemas embarcados.

---

### Potência Elétrica

#### Conceito

Potência elétrica é a taxa de conversão de energia elétrica em outra forma de energia.

$$
P = V \cdot I
$$

Substituindo a Lei de Ohm:

$$
P = I^2 R
$$

ou

$$
P = \frac{V^2}{R}
$$

#### Exemplo

Para o resistor anterior:

$$
P = \frac{5^2}{220}
$$

$$
P = \frac{25}{220}
$$

$$
P \approx 0,1136 \ W
$$

Logo, deve-se usar resistor com potência nominal superior a 0,25 W para segurança.

---

## Resistores em Série

### Conceito

Quando resistores são ligados um após o outro, a mesma corrente atravessa todos.

### Resistência Equivalente

$$
R_{eq} = R_1 + R_2 + R_3 + ...
$$

### Interpretação

Adicionar resistores em série aumenta a resistência total, reduzindo a corrente.

### Exemplo

Dois resistores:

* R₁ = 100 Ω
* R₂ = 200 Ω

$$
R_{eq} = 100 + 200 = 300 \ \Omega
$$

Se ligados a 9 V:

$$
I = \frac{9}{300} = 0,03 \ A
$$

Corrente = 30 mA

### Comparação

Série é equivalente a alongar o “cano”. Quanto maior o caminho, maior a dificuldade da corrente passar.

---

## Resistores em Paralelo

### Conceito

Em paralelo, todos os resistores recebem a mesma tensão, mas as correntes se dividem.

### Fórmula

$$
\frac{1}{R_{eq}} = \frac{1}{R_1} + \frac{1}{R_2} + ...
$$

Para dois resistores:

$$
R_{eq} = \frac{R_1 \cdot R_2}{R_1 + R_2}
$$

### Exemplo

R₁ = 100 Ω
R₂ = 200 Ω

$$
R_{eq} = \frac{100 \cdot 200}{300}
$$

$$
R_{eq} = \frac{20000}{300}
$$

$$
R_{eq} \approx 66,7 \ \Omega
$$

Observe que o resultado é menor que 100 Ω (o menor resistor).

### Interpretação Física

Paralelo é como vários canos lado a lado. A água pode passar por múltiplos caminhos, reduzindo a resistência total.

---

## Comparação Entre Série e Paralelo

| Característica    | Série          | Paralelo                 |
| ----------------- | -------------- | ------------------------ |
| Corrente          | Igual em todos | Divide-se                |
| Tensão            | Divide-se      | Igual em todos           |
| Resistência total | Soma           | Sempre menor que a menor |

---

## Conclusão

A compreensão profunda de corrente, tensão e resistência permite analisar qualquer circuito elétrico básico. A Lei de Ohm fornece a base matemática para dimensionamento e análise. A associação de resistores em série e paralelo amplia as possibilidades de projeto e é essencial para desenvolvimento de sistemas embarcados confiáveis.

---

## Análise Crítica

A Lei de Ohm assume comportamento linear e temperatura constante. Em sistemas embarcados reais:

* A temperatura altera resistividade
* Componentes possuem tolerância
* Curto-circuitos podem danificar circuitos rapidamente

Projetos devem considerar margem de segurança.

---

## Sugestões de Complementação

* Estudo de divisores de tensão
* Análise de circuitos com Kirchhoff
* Introdução a capacitores e indutores

---

## Exercícios Resolvidos

### Exercício 1

Um LED opera a 2 V e 20 mA. Fonte de 5 V. Qual resistor usar?

Tensão no resistor:

$$
V_R = 5 - 2 = 3 \ V
$$

$$
R = \frac{3}{0,02}
$$

$$
R = 150 \ \Omega
$$

---

### Exercício 2

Três resistores de 100 Ω em paralelo.

$$
\frac{1}{R_{eq}} = \frac{1}{100} + \frac{1}{100} + \frac{1}{100}
$$

$$
\frac{1}{R_{eq}} = \frac{3}{100}
$$

$$
R_{eq} = 33,3 \ \Omega
$$

---

## Bibliografia

HALLIDAY, D.; RESNICK, R.; WALKER, J. Fundamentos de Física: Eletromagnetismo. Rio de Janeiro: LTC.

BOYLESTAD, R. L. Introdução à Análise de Circuitos. São Paulo: Pearson.

---

## Materiais Complementares

SEDRA, A.; SMITH, K. Microelectronic Circuits. Oxford University Press.
