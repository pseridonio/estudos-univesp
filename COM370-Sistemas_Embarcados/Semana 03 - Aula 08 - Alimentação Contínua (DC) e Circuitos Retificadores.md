# Retificação de Tensão Alternada e Geração de Alimentação Contínua em Sistemas Embarcados

---

## Introdução

Grande parte dos sistemas embarcados opera com **tensão contínua (DC)**. Microcontroladores, sensores, memórias e circuitos de comunicação digital exigem níveis estáveis de tensão para funcionarem corretamente. Entretanto, a energia elétrica disponível na rede pública é fornecida na forma de **tensão alternada (AC)**.

Essa diferença entre a forma de fornecimento e a forma de utilização impõe uma etapa fundamental no projeto eletrônico: a **conversão de AC para DC**, processo denominado **retificação**.

Neste capítulo, estudaremos de forma aprofundada:

* A natureza matemática e física da tensão alternada
* O funcionamento do diodo como elemento retificador
* Retificador de meia onda
* Retificador de onda completa
* Cálculo do valor médio da tensão retificada
* Filtragem com capacitor e análise de ripple

O objetivo é compreender não apenas o circuito, mas o comportamento físico e matemático por trás da conversão de energia.

---

## Desenvolvimento

## Tensão Alternada (AC)

### Contexto

A rede elétrica fornece energia sob a forma de tensão alternada senoidal. No Brasil, a frequência é 60 Hz, ou seja, a tensão completa 60 ciclos por segundo.

Sistemas embarcados conectados à rede precisam converter essa forma de onda antes de alimentar seus circuitos internos.

---

### Conceito Matemático

Uma tensão senoidal ideal pode ser descrita por:

$$
v(t) = V_p \sin(\omega t)
$$

Onde:

* $V_p$ é o valor de pico da tensão
* $\omega = 2\pi f$ é a frequência angular
* $f$ é a frequência da rede
* $t$ é o tempo

Como a função seno assume valores entre −1 e +1, a tensão alterna entre valores positivos e negativos.

Fisicamente, isso significa que a corrente também alterna seu sentido.

---

## Necessidade da Retificação

Circuitos digitais não toleram inversão constante de polaridade. Uma alimentação alternada provocaria inversão contínua da corrente, tornando impossível o funcionamento adequado de semicondutores.

A solução consiste em converter a forma de onda alternada em uma forma **unidirecional**, ainda que pulsante.

---

## O Diodo como Elemento Retificador

### Contexto

O diodo semicondutor é o componente que permite condução elétrica em apenas um sentido.

---

### Funcionamento

Quando polarizado diretamente, conduz corrente. Quando polarizado reversamente, bloqueia a corrente.

Durante condução, há uma queda de tensão típica:

* Aproximadamente $0,7,V$ para diodos de silício

Podemos representar essa queda por:

$$
V_{out} = V_{in} - V_D
$$

Onde $V_D$ é a tensão direta do diodo.

---

## Retificador de Meia Onda

### Conceito

O retificador de meia onda utiliza apenas um diodo para permitir a passagem de um único semiciclo da tensão alternada.

---

### Funcionamento Físico

Se a entrada é:

$$
v(t) = V_p \sin(\omega t)
$$

Temos dois casos:

* Quando $\sin(\omega t) > 0$, o diodo está polarizado diretamente e conduz.
* Quando $\sin(\omega t) < 0$, o diodo está polarizado reversamente e bloqueia.

Portanto, a saída é descrita matematicamente por uma função por partes:

$$
v_{out}(t) =
\begin{cases}
V_p \sin(\omega t), & \text{se } \sin(\omega t) > 0 \
0, & \text{se } \sin(\omega t) \le 0
\end{cases}
$$

Essa expressão representa exatamente o comportamento físico do diodo:

* Preserva o semiciclo positivo
* Elimina o semiciclo negativo

---

### Interpretação Angular

Sabemos que:

* $\sin(\theta) > 0$ quando $0 < \theta < \pi$
* $\sin(\theta) < 0$ quando $\pi < \theta < 2\pi$

Substituindo $\theta = \omega t$:

$$
v_{out}(t) =
\begin{cases}
V_p \sin(\omega t), & 0 < \omega t < \pi \
0, & \pi < \omega t < 2\pi
\end{cases}
$$

Essa forma se repete a cada período.

---

### Forma Alternativa Compacta

Também podemos escrever:

$$
v_{out}(t) = \max(0, V_p \sin(\omega t))
$$

Isso indica que qualquer valor negativo da senoide é substituído por zero.

---

## Valor Médio do Retificador de Meia Onda

O valor médio é obtido integrando a função ao longo de um período.

A expressão final é:

$$
V_{médio} = \frac{V_p}{\pi}
$$

---

### Exemplo Numérico

Considere $V_p = 12,V$.

$$
V_{médio} = \frac{12}{\pi}
$$

$$
V_{médio} \approx \frac{12}{3,1416}
$$

$$
V_{médio} \approx 3,82,V
$$

Observe que o valor médio é relativamente baixo comparado ao valor de pico.

---

## Retificador de Onda Completa

### Conceito

O retificador de onda completa utiliza quatro diodos em configuração de ponte, permitindo o aproveitamento de ambos os semiciclos.

Independentemente da polaridade da entrada, a corrente na carga flui sempre no mesmo sentido.

---

### Valor Médio

O valor médio da tensão retificada em onda completa é:

$$
V_{médio} = \frac{2V_p}{\pi}
$$

Observe que esse valor é o dobro do retificador de meia onda.

---

### Exemplo Numérico

Se $V_p = 12,V$:

$$
V_{médio} = \frac{2 \cdot 12}{\pi}
$$

$$
V_{médio} \approx \frac{24}{3,1416}
$$

$$
V_{médio} \approx 7,64,V
$$

Comparando:

* Meia onda: $3,82,V$
* Onda completa: $7,64,V$

A eficiência energética praticamente dobra.

---

## Filtragem com Capacitor

### Contexto

Mesmo após a retificação, a tensão ainda é pulsante. Para aplicações em sistemas embarcados, é necessário reduzir a ondulação, chamada **ripple**.

---

### Funcionamento do Capacitor

O capacitor é ligado em paralelo com a carga.

* Durante o pico da onda, ele carrega até o valor máximo.
* Entre os picos, ele descarrega lentamente, mantendo a tensão mais estável.

---

### Cálculo Aproximado do Ripple

A tensão de ripple pode ser estimada por:

$$
V_{ripple} \approx \frac{I_{carga}}{f C}
$$

Onde:

* $I_{carga}$ é a corrente da carga
* $f$ é a frequência da ondulação
* $C$ é a capacitância

Para retificador de onda completa:

$$
f_{ripple} = 2f_{rede}
$$

No Brasil, isso significa 120 Hz.

---

### Exemplo

Suponha:

* $I_{carga} = 0,2,A$
* $f = 120,Hz$
* $C = 2200,\mu F = 2200 \times 10^{-6},F$

$$
V_{ripple} = \frac{0,2}{120 \cdot 2200 \times 10^{-6}}
$$

$$
V_{ripple} = \frac{0,2}{0,264}
$$

$$
V_{ripple} \approx 0,76,V
$$

Aumentar o capacitor reduz o ripple.

---

## Comparação Entre Métodos

| Característica    | Meia Onda | Onda Completa |
| ----------------- | --------- | ------------- |
| Número de diodos  | 1         | 4             |
| Aproveitamento    | 50%       | 100%          |
| Valor médio       | $V_p/\pi$ | $2V_p/\pi$    |
| Frequência ripple | 60 Hz     | 120 Hz        |
| Ripple            | Maior     | Menor         |

---

## Conclusão

A retificação é etapa fundamental na conversão da energia alternada da rede elétrica em alimentação contínua para sistemas embarcados. O retificador de meia onda apresenta simplicidade estrutural, mas baixo aproveitamento energético. O retificador de onda completa utiliza ambos os semiciclos, dobrando o valor médio da tensão e reduzindo ripple.

A associação com capacitor de filtragem aproxima o sinal de uma tensão DC ideal, tornando possível alimentar circuitos digitais com maior estabilidade.

---

## Análise Crítica

Apesar da melhoria com capacitor, a tensão ainda não é perfeitamente contínua. Para aplicações sensíveis, são necessários:

* Reguladores lineares
* Conversores chaveados
* Circuitos de regulação adicionais

Além disso, deve-se considerar a queda de tensão nos diodos e a dissipação térmica.

---

## Sugestões de Complementação

* Reguladores lineares (LM7805)
* Conversores buck e boost
* Análise detalhada de ripple por integração
* Projeto completo de fonte linear

---

## Exercícios Resolvidos

### Exercício 1

Uma senoide possui $V_p = 18,V$.

Calcule o valor médio para:

a) Meia onda
b) Onda completa

---

**Resolução**

Meia onda:

$$
V_{médio} = \frac{18}{\pi}
$$

$$
V_{médio} \approx 5,73,V
$$

Onda completa:

$$
V_{médio} = \frac{2 \cdot 18}{\pi}
$$

$$
V_{médio} \approx 11,46,V
$$

---

## Bibliografia

BOYLESTAD, R. L. Introdução à Análise de Circuitos. Pearson.

SEDRA, A.; SMITH, K. Microelectronic Circuits. Oxford University Press.

HAYT, W.; KEMMERLY, J. Análise de Circuitos em Engenharia. McGraw-Hill.

---

## Materiais Complementares

HOROWITZ, P.; HILL, W. The Art of Electronics. Cambridge University Press.
