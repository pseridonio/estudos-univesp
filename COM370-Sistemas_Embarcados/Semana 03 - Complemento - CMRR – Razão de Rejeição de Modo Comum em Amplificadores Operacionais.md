# CMRR – Razão de Rejeição de Modo Comum em Amplificadores Operacionais

---

## Introdução

Em sistemas embarcados, especialmente aqueles que trabalham com sensores de baixa amplitude (milivolts ou microvolts), a integridade do sinal é um dos maiores desafios de projeto. Ambientes industriais, automotivos e biomédicos são repletos de ruídos elétricos induzidos por motores, fontes chaveadas, cabos longos e interferência eletromagnética.

Muitos desses ruídos aparecem **simultaneamente nas duas entradas** de um amplificador. A capacidade de ignorar esse tipo de interferência é medida por um parâmetro fundamental chamado **CMRR — Common-Mode Rejection Ratio**, ou **Razão de Rejeição de Modo Comum**.

O CMRR é um dos parâmetros mais importantes em amplificadores operacionais e, principalmente, em amplificadores de instrumentação.

---

## Conceito de Sinal Diferencial e Sinal em Modo Comum

Para entender o CMRR, precisamos primeiro distinguir dois tipos de sinais aplicados às entradas de um amplificador operacional.

### 1. Sinal Diferencial

É a diferença entre as tensões nas duas entradas:

$$
V_d = V^+ - V^-
$$

Esse é o sinal que **queremos amplificar**.

---

### 2. Sinal em Modo Comum

É a parte do sinal que aparece **igual nas duas entradas**.

Definimos:

$$
V_{cm} = \frac{V^+ + V^-}{2}
$$

Esse é, geralmente, o **ruído indesejado**.

---

## Modelo Real de Amplificação

Um amplificador ideal amplificaria apenas o sinal diferencial. Porém, na prática, ele também amplifica parcialmente o sinal de modo comum.

O modelo mais completo da saída é:

$$
V_{out} = A_d \cdot V_d + A_{cm} \cdot V_{cm}
$$

Onde:

* $A_d$ = ganho diferencial
* $A_{cm}$ = ganho de modo comum

Idealmente:

$$
A_{cm} = 0
$$

Mas na prática, $A_{cm}$ é pequeno, porém diferente de zero.

---

# Definição Formal de CMRR

O CMRR é definido como a razão entre o ganho diferencial e o ganho de modo comum:

$$
CMRR = \frac{A_d}{A_{cm}}
$$

Como essa razão costuma ser muito alta, é comum expressá-la em decibéis:

$$
CMRR_{dB} = 20 \log_{10} \left( \frac{A_d}{A_{cm}} \right)
$$

---

## Interpretação Física

* Quanto maior o CMRR → melhor o amplificador ignora ruído comum.
* Quanto menor o CMRR → mais o ruído aparece na saída.

---

# Exemplo Numérico Completo

Suponha:

* $A_d = 1000$
* $A_{cm} = 0,01$

Calculando:

$$
CMRR = \frac{1000}{0,01}
$$

$$
CMRR = 100000
$$

Convertendo para dB:

$$
CMRR_{dB} = 20 \log_{10}(100000)
$$

Sabemos que:

$$
\log_{10}(100000) = 5
$$

Logo:

$$
CMRR_{dB} = 20 \times 5 = 100, dB
$$

Isso significa que o sinal diferencial é amplificado 100 dB a mais que o ruído comum.

---

# Exemplo Prático em Sistema Embarcado

Imagine um sensor diferencial medindo 10 mV.

Durante a medição, há um ruído de 2 V induzido igualmente nos dois cabos do sensor.

Temos:

$$
V_d = 10mV
$$

$$
V_{cm} = 2V
$$

Se o amplificador tiver:

* $A_d = 100$
* CMRR = 100 dB

Primeiro convertemos 100 dB para razão:

$$
100 = 20 \log_{10}(CMRR)
$$

Dividindo por 20:

$$
5 = \log_{10}(CMRR)
$$

Logo:

$$
CMRR = 10^5 = 100000
$$

Sabemos que:

$$
CMRR = \frac{A_d}{A_{cm}}
$$

Então:

$$
100000 = \frac{100}{A_{cm}}
$$

Isolando $A_{cm}$:

$$
A_{cm} = \frac{100}{100000}
$$

$$
A_{cm} = 0,001
$$

Agora calculamos a contribuição do ruído:

$$
V_{ruido\_saida} = A_{cm} \cdot V_{cm}
$$

$$
V_{ruido\_saida} = 0,001 \cdot 2
$$

$$
V_{ruido\_saida} = 0,002V = 2mV
$$

Enquanto o sinal útil amplificado será:

$$
V_{sinal} = 100 \cdot 0,01
$$

$$
V_{sinal} = 1V
$$

Portanto:

* Sinal útil = 1 V
* Ruído residual = 2 mV

O ruído foi drasticamente reduzido.

---

# CMRR em Amplificadores de Instrumentação

Amplificadores de instrumentação são projetados para ter CMRR extremamente alto (100 dB a 130 dB ou mais).

Isso é fundamental quando se mede:

* Ponte de Wheatstone
* Sensores de strain gauge
* Sinais biomédicos (ECG, EEG)
* Sensores industriais com cabos longos

---

# Por que o CMRR não é infinito na prática?

O CMRR real é limitado por:

1. Desbalanceamento interno de resistores
2. Descasamento entre transistores
3. Variação térmica
4. Imperfeições na fabricação
5. Assimetria no circuito externo

Especialmente em amplificadores diferenciais discretos, pequenas diferenças de resistor podem reduzir drasticamente o CMRR.

---

# Impacto do Casamento de Resistores

No amplificador diferencial clássico, para que o CMRR seja alto, deve-se manter:

$$
\frac{R_2}{R_1} = \frac{R_4}{R_3}
$$

Se essa igualdade não for exata, parte do modo comum será convertida em modo diferencial, degradando o CMRR.

Por isso amplificadores de instrumentação utilizam resistores internos ajustados por laser.

---

# Conclusão

O CMRR mede a capacidade do amplificador de distinguir entre:

* O sinal que queremos (diferença entre entradas)
* O ruído que aparece igualmente nas duas entradas

Matematicamente:

$$
CMRR = \frac{A_d}{A_{cm}}
$$

E em decibéis:

$$
CMRR_{dB} = 20 \log_{10} \left( \frac{A_d}{A_{cm}} \right)
$$

Quanto maior o CMRR, melhor a rejeição de ruído.

Em sistemas embarcados que trabalham com sensores de baixa amplitude, o CMRR não é apenas um parâmetro desejável — ele é determinante para a qualidade da medição.
