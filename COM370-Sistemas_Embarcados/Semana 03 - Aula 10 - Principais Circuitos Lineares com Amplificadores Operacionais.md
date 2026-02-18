# Amplificadores Operacionais em Sistemas Embarcados

---

## Introdução

Em sistemas embarcados, frequentemente lidamos com sinais analógicos provenientes de sensores: temperatura, pressão, corrente, vibração, sinais biomédicos, entre outros. Esses sinais raramente estão em níveis adequados para conversores A/D ou para processamento confiável. Surge então a necessidade de condicionamento de sinais — etapa fundamental que envolve amplificação, filtragem e adaptação de impedância.

O componente central dessa etapa é o **Amplificador Operacional (AmpOp ou OAP)**. Trata-se de um dos blocos fundamentais da eletrônica analógica moderna, presente desde instrumentação industrial até dispositivos médicos e sistemas automotivos.

Historicamente, os amplificadores operacionais receberam esse nome porque eram utilizados em computadores analógicos para realizar operações matemáticas como soma, subtração, integração e derivação. Hoje, continuam desempenhando esse papel matemático, mas integrados em circuitos compactos e de alta precisão.

---

## Conceito Fundamental de Amplificador Operacional

Um amplificador operacional é um dispositivo eletrônico com duas entradas e uma saída, cuja função principal é amplificar a diferença de tensão entre suas entradas.

### Representação simbólica

O símbolo apresenta:

* Entrada não inversora (+)
* Entrada inversora (−)
* Saída
* Alimentação positiva ($V_{CC}$)
* Alimentação negativa ($V_{EE}$) ou referência ao GND em sistemas single supply

---

## Modelo Ideal do Amplificador Operacional

Para compreender seu funcionamento, parte-se do modelo ideal.

### 1. Ganho de tensão infinito

O ganho em malha aberta é definido como:

$$
V_{out} = A \cdot (V^+ - V^-)
$$

Onde:

* $A$ = ganho em malha aberta
* $V^+$ = tensão na entrada não inversora
* $V^-$ = tensão na entrada inversora

No modelo ideal:

$$
A \to \infty
$$

Isso implica que, mesmo para uma diferença infinitesimal entre as entradas, a saída tenderia à saturação.

---

### 2. Impedância de entrada infinita

Corrente nas entradas:

$$
I^+ = I^- = 0
$$

Isso significa que o amplificador não carrega o circuito anterior — ideal para sensores.

---

### 3. Impedância de saída nula

$$
R_{out} = 0
$$

Permite fornecer corrente à carga sem queda significativa de tensão.

---

### 4. Resposta em frequência infinita

O ganho seria constante para qualquer frequência. Na prática, há limitação pela largura de banda (produto ganho-banda).

---

## Realimentação Negativa

Sem realimentação, o ganho infinito torna o sistema impraticável. Portanto, utiliza-se **realimentação negativa**, conectando parte da saída à entrada inversora.

A condição fundamental sob realimentação negativa é:

$$
V^+ \approx V^-
$$

Esse fenômeno é chamado de **curto virtual**.

---

# Amplificador Inversor

## Estrutura

Entrada aplicada via resistor $R_1$ à entrada inversora. Realimentação por $R_f$.

---

## Análise Matemática Completa

Sabemos que:

$$
V^- = V^+ = 0 \quad (\text{pois } V^+ \text{ está aterrado})
$$

Logo, o nó inversor está em **terra virtual**.

Corrente em $R_1$:

$$
I_1 = \frac{V_{in} - 0}{R_1}
$$

Corrente em $R_f$:

$$
I_f = \frac{0 - V_{out}}{R_f}
$$

Como não entra corrente no op amp:

$$
I_1 = I_f
$$

Substituindo:

$$
\frac{V_{in}}{R_1} = \frac{-V_{out}}{R_f}
$$

Isolando $V_{out}$:

$$
V_{out} = - \frac{R_f}{R_1} V_{in}
$$

### Interpretação

* O sinal é invertido
* O ganho depende apenas da razão resistiva

---

# Amplificador Não Inversor

---

## Derivação

Como $V^- = V^+$:

$$
V^- = V_{in}
$$

Pela divisão de tensão:

$$
V^- = V_{out} \cdot \frac{R_1}{R_1 + R_f}
$$

Igualando:

$$
V_{in} = V_{out} \cdot \frac{R_1}{R_1 + R_f}
$$

Isolando $V_{out}$:

$$
V_{out} = V_{in} \left(1 + \frac{R_f}{R_1} \right)
$$

Não há inversão de fase.

---

# Seguidor de Tensão (Buffer)

Caso especial do não inversor:

$$
R_f = 0 \quad e \quad R_1 \to \infty
$$

Resultado:

$$
V_{out} = V_{in}
$$

Função: isolamento de impedância.

---

# Amplificador Somador (Inversor)

Para múltiplas entradas:

$$
V_{out} = -R_f \left( \frac{V_1}{R_1} + \frac{V_2}{R_2} + ... \right)
$$

Se todos resistores iguais:

$$
V_{out} = - (V_1 + V_2 + ...)
$$

---

# Amplificador Subtrator (Diferencial)

Equação geral:

$$
V_{out} = \left(\frac{R_2}{R_1}\right)(V_2 - V_1)
$$

Esse circuito rejeita sinais comuns às duas entradas.

---

# Amplificador de Instrumentação

Estrutura composta por:

1. Dois buffers de entrada
2. Um amplificador diferencial

Ganho típico:

$$
G = 1 + \frac{2R}{R_G}
$$

Vantagens:

* Alto CMRR
* Alta impedância de entrada
* Baixo offset

Modelos como IN118 e IN122 utilizam essa arquitetura com resistor externo $R_G$ para ajuste fino.

---

# Amplificadores em Cascata

Quando um único estágio não fornece ganho suficiente:

$$
G_{total} = G_1 \cdot G_2 \cdot G_3
$$

Exemplo:

* Estágio 1: ganho 10
* Estágio 2: ganho 20

$$
G_{total} = 10 \cdot 20 = 200
$$

Essa abordagem melhora estabilidade e largura de banda.

---

## Conclusão

O amplificador operacional é um dos blocos mais versáteis da eletrônica analógica. Seu comportamento ideal simplifica análises matemáticas, enquanto a realimentação negativa permite controle preciso de ganho. Em sistemas embarcados, é peça-chave no condicionamento de sinais, garantindo que sensores possam ser corretamente lidos por microcontroladores.

---

## Exercício Resolvido

**Problema:**
Projetar um amplificador inversor com ganho -5 para um sensor que fornece 200 mV.

**Solução:**

Queremos:

$$

* \frac{R_f}{R_1} = -5
  $$

Logo:

$$
\frac{R_f}{R_1} = 5
$$

Escolhendo:

* $R_1 = 10k\Omega$
* $R_f = 50k\Omega$

Saída:

$$
V_{out} = -5 \times 0.2 = -1V
$$

---

## Bibliografia

SEDRA, A. S.; SMITH, K. C. *Microelectronic Circuits*. Oxford University Press.
BOYLESTAD, R. L.; NASHELSKY, L. *Electronic Devices and Circuit Theory*. Pearson.
HOROWITZ, P.; HILL, W. *The Art of Electronics*. Cambridge University Press.

---

Se desejar, posso agora:

* Gerar versão em PDF formatado
* Criar lista extensa de exercícios progressivos
* Aprofundar em limitações reais (slew rate, ganho-banda, offset térmico)
* Aplicar ao contexto de sensores específicos (strain gauge, ponte de Wheatstone, etc.)
