# Impedância de Entrada Infinita e Impedância de Saída Nula em Amplificadores Operacionais

---

## Introdução

No estudo de amplificadores operacionais dentro da disciplina de Sistemas Embarcados, dois conceitos frequentemente geram dúvida conceitual profunda:

* O que significa dizer que a **impedância de entrada é infinita**?
* Como é possível existir **corrente na saída** se **não entra corrente na entrada**?

Essas afirmações fazem parte do modelo ideal do amplificador operacional e são fundamentais para compreender por que esse dispositivo é tão poderoso no condicionamento de sinais.

Em sistemas embarcados, sensores de alta impedância, como sensores piezoelétricos, strain gauges e sensores biomédicos, exigem circuitos que não interfiram na medição. Ao mesmo tempo, o sinal precisa ser entregue a cargas que podem demandar corrente significativa, como estágios seguintes ou conversores A/D. O amplificador operacional resolve essa aparente contradição.

Para entender isso com rigor técnico, precisamos recorrer aos conceitos de impedância, conservação de energia e estrutura interna do dispositivo.

---

# 1. O que é Impedância?

Antes de discutir impedância infinita ou nula, precisamos formalizar o conceito.

A impedância é definida como a razão entre tensão e corrente:

$$
Z = \frac{V}{I}
$$

Onde:

* $Z$ = impedância (Ω)
* $V$ = tensão aplicada
* $I$ = corrente resultante

No regime puramente resistivo:

$$
R = \frac{V}{I}
$$

Logo:

* Se a corrente for muito pequena → impedância é muito grande.
* Se a corrente for muito grande → impedância é pequena.

---

# 2. Impedância de Entrada Infinita

## Conceito

Dizer que a impedância de entrada é infinita significa que:

$$
I_{entrada} = 0
$$

Mesmo que exista tensão aplicada.

Voltando à definição:

$$
Z_{in} = \frac{V_{in}}{I_{in}}
$$

Se:

$$
I_{in} \to 0
$$

Então:

$$
Z_{in} \to \infty
$$

---

## Interpretação Física

Isso significa que o amplificador **não retira corrente da fonte de sinal**.

Ou seja:

* Ele “observa” a tensão
* Mas não “puxa” corrente

Isso é crucial em sensores de alta impedância.

---

## Exemplo Numérico

Suponha um sensor que fornece:

$$
V = 2V
$$

Se a corrente de entrada for:

$$
I = 2,\mu A
$$

Então:

$$
Z = \frac{2}{2 \times 10^{-6}} = 1,M\Omega
$$

Agora suponha que:

$$
I = 2,nA
$$

Então:

$$
Z = \frac{2}{2 \times 10^{-9}} = 1,G\Omega
$$

Quanto menor a corrente, maior a impedância.

Em amplificadores operacionais modernos com entrada FET, a impedância pode atingir dezenas de GΩ.

---

# 3. Estrutura Física que Permite Alta Impedância

A alta impedância é possível porque o estágio de entrada utiliza:

* Transistores bipolares (BJT) ou
* Transistores de efeito de campo (JFET/MOSFET)

No caso de FET:

* A corrente de gate é praticamente zero.
* O controle é feito por campo elétrico, não por fluxo de corrente.

Isso explica fisicamente a baixa corrente de entrada.

---

# 4. Impedância de Saída Nula

## Definição

Impedância de saída é:

$$
Z_{out} = \frac{\Delta V_{out}}{\Delta I_{out}}
$$

Se pequenas variações de corrente na carga não alteram a tensão de saída, então:

$$
Z_{out} \approx 0
$$

Isso significa que o amplificador consegue fornecer corrente mantendo a tensão estável.

---

# 5. A Pergunta Fundamental

Como pode haver corrente na saída se não entra corrente na entrada?

Essa é uma dúvida clássica — e a resposta está na **alimentação do amplificador**.

---

# 6. Conservação de Energia

O amplificador operacional não cria energia.

Ele é alimentado por fontes externas:

* $+V_{CC}$
* $-V_{EE}$ (ou GND em single supply)

A energia fornecida à carga vem dessas fontes.

A entrada apenas controla o comportamento do circuito interno.

---

## Analogia

Imagine uma torneira elétrica:

* O botão (entrada) controla
* A água (energia) vem da rede hidráulica (alimentação)

O botão não fornece água — apenas regula.

---

# 7. Modelo Energético Simplificado

A potência na saída é:

$$
P_{out} = V_{out} \cdot I_{out}
$$

Essa potência vem da alimentação:

$$
P_{fonte} = V_{CC} \cdot I_{CC}
$$

A entrada apenas modula os transistores internos.

---

# 8. Exemplo Numérico Completo

Suponha:

* $V_{out} = 5V$
* Carga: $R_L = 100\Omega$

Corrente na carga:

$$
I_{out} = \frac{V}{R}
$$

$$
I_{out} = \frac{5}{100}
$$

$$
I_{out} = 0,05A = 50mA
$$

Potência fornecida:

$$
P = 5 \cdot 0,05
$$

$$
P = 0,25W
$$

Essa potência NÃO vem da entrada.

Ela vem da alimentação do amplificador.

---

# 9. Estrutura do Estágio de Saída

O estágio de saída geralmente é:

* Push-pull
* Classe AB
* Com transistores complementares

Ele funciona como um amplificador de potência controlado pelo estágio diferencial interno.

---

# 10. Separação Entre Controle e Potência

O amplificador operacional possui:

1. Estágio diferencial (alta impedância)
2. Estágio de ganho intermediário
3. Estágio de saída (fornecimento de corrente)

O estágio de entrada controla o fluxo interno de corrente entre os trilhos de alimentação.

A corrente que sai na carga é redirecionada das fontes.

---

# 11. Implicação Prática em Sistemas Embarcados

Essa arquitetura permite:

* Conectar sensores frágeis sem carregá-los.
* Fornecer corrente suficiente para ADCs.
* Isolar estágios de circuito.
* Criar buffers (seguidores de tensão).

O seguidor de tensão é o melhor exemplo:

$$
V_{out} = V_{in}
$$

Mas:

* $I_{in} \approx 0$
* $I_{out}$ pode ser significativo

---

# 12. Análise Crítica

Na prática:

* A impedância de entrada não é infinita.
* A impedância de saída não é zero.

Valores típicos:

* $Z_{in}$: 1 MΩ a 10 GΩ
* $Z_{out}$: 10 Ω a 100 Ω (em malha aberta)
* Com realimentação negativa, $Z_{out}$ é reduzida drasticamente.

A realimentação reduz a impedância de saída por:

$$
Z_{out,fb} = \frac{Z_{out}}{1 + A\beta}
$$

Onde:

* $A$ = ganho em malha aberta
* $\beta$ = fator de realimentação

Se $A\beta$ for grande:

$$
Z_{out,fb} \to 0
$$

---

# Conclusão

A impedância de entrada infinita significa que o amplificador mede tensão sem retirar corrente significativa da fonte.

A impedância de saída nula significa que ele consegue fornecer corrente mantendo a tensão estável.

A corrente de saída não vem da entrada — vem das fontes de alimentação.

O amplificador operacional é, essencialmente, um dispositivo que separa:

* Controle (entrada)
* Energia (alimentação)
* Potência entregue (saída)

Esse desacoplamento é o que torna o amplificador operacional um dos blocos mais importantes da eletrônica analógica e dos sistemas embarcados.

---
