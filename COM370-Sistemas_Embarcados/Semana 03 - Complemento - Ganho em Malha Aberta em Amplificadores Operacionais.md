# Ganho em Malha Aberta em Amplificadores Operacionais

---

## Introdução

Em sistemas embarcados, o amplificador operacional é amplamente utilizado como elemento de condicionamento de sinais. Entretanto, sua operação prática quase nunca ocorre de forma isolada. O comportamento que realmente utilizamos — estável, previsível e linear — depende da **realimentação negativa**.

Antes de compreender o papel da realimentação, é essencial entender o conceito de **malha aberta** e, principalmente, o que representa o **ganho em malha aberta**.

Esse parâmetro é um dos mais importantes do amplificador operacional, pois determina:

* A sensibilidade do sistema à diferença entre entradas
* A precisão da realimentação
* A estabilidade do circuito
* A redução da impedância de saída

Sem compreender o ganho em malha aberta, não é possível entender por que o amplificador operacional funciona de maneira tão precisa quando realimentado.

---

# 1. O que é “Malha”?

Em eletrônica, uma **malha** é um caminho fechado percorrido por um sinal dentro de um circuito.

Quando parte da saída retorna para a entrada, formando um ciclo fechado, temos uma **malha fechada**.

Quando esse caminho de retorno não existe, temos **malha aberta**.

---

# 2. O que é Malha Aberta?

Um amplificador operacional está em **malha aberta** quando:

* Nenhuma parte da saída é conectada às entradas.
* Não existe realimentação.

Ou seja, o amplificador opera apenas com seu ganho interno natural.

Representação conceitual:

```
Vin+  →|\
       | \
Vin-  →|  \____ Vout
```

Sem qualquer ligação da saída para as entradas.

---

# 3. Definição de Ganho em Malha Aberta

O ganho em malha aberta é representado por:

$$
A_{OL}
$$

(OL = Open Loop)

A equação fundamental do amplificador operacional é:

$$
V_{out} = A_{OL} \cdot (V^+ - V^-)
$$

Onde:

* $V^+$ = tensão na entrada não inversora
* $V^-$ = tensão na entrada inversora
* $A_{OL}$ = ganho em malha aberta

---

# 4. Qual é o Valor do Ganho em Malha Aberta?

Idealmente:

$$
A_{OL} \to \infty
$$

Na prática:

* Amplificadores comuns: $10^5$ a $10^6$
* Em dB:

$$
A_{OL(dB)} = 20 \log_{10}(A_{OL})
$$

---

## Exemplo Numérico

Se:

$$
A_{OL} = 100000
$$

Calculando em decibéis:

$$
A_{OL(dB)} = 20 \log_{10}(100000)
$$

Sabemos que:

$$
\log_{10}(100000) = 5
$$

Logo:

$$
A_{OL(dB)} = 20 \times 5 = 100 , dB
$$

Isso significa que o sinal diferencial é amplificado 100 dB.

---

# 5. O Problema da Malha Aberta

Vamos analisar o que acontece na prática.

Suponha:

* $A_{OL} = 100000$
* $V^+ - V^- = 1,mV = 0,001V$

Aplicando a equação:

$$
V_{out} = 100000 \cdot 0,001
$$

$$
V_{out} = 100V
$$

Mas o amplificador pode estar alimentado com ±15V.

Portanto, a saída irá saturar no trilho máximo disponível.

---

## Conclusão Parcial

Em malha aberta:

* Pequeníssimas diferenças entre entradas causam saturação.
* O amplificador se comporta como comparador.
* Não é útil para amplificação linear.

---

# 6. Resposta em Frequência do Ganho em Malha Aberta

O ganho em malha aberta não é constante com a frequência.

Ele decai conforme a frequência aumenta.

Representação típica:

O comportamento é aproximadamente:

* Alto ganho em baixas frequências
* Queda de -20 dB/década após a frequência de corte

---

# 7. Modelo Matemático Simplificado

O ganho pode ser modelado como:

$$
A_{OL}(f) = \frac{A_0}{\sqrt{1 + \left(\frac{f}{f_c}\right)^2}}
$$

Onde:

* $A_0$ = ganho em DC
* $f_c$ = frequência de corte

Para $f \gg f_c$:

$$
A_{OL}(f) \approx \frac{A_0 f_c}{f}
$$

Esse comportamento leva ao conceito de **Produto Ganho-Banda (GBW)**:

$$
GBW = A_{OL}(f) \cdot f
$$

Esse produto é aproximadamente constante.

---

# 8. Exemplo de Produto Ganho-Banda

Se:

$$
GBW = 1,MHz
$$

E desejamos ganho:

$$
A = 10
$$

Então a frequência máxima será:

$$
f = \frac{GBW}{A}
$$

$$
f = \frac{1,MHz}{10}
$$

$$
f = 100,kHz
$$

Isso mostra que o ganho em malha aberta influencia diretamente o desempenho em malha fechada.

---

# 9. Por que o Ganho em Malha Aberta Precisa Ser Alto?

Porque a realimentação negativa depende dele.

O ganho em malha fechada é:

$$
A_{CL} = \frac{A_{OL}}{1 + A_{OL}\beta}
$$

Onde:

* $\beta$ = fator de realimentação

Se $A_{OL}$ for muito grande:

$$
A_{CL} \approx \frac{1}{\beta}
$$

Ou seja, o ganho passa a depender apenas dos componentes externos.

Esse é o grande poder da realimentação.

---

# 10. Interpretação Física

O ganho em malha aberta representa:

* A sensibilidade interna do amplificador
* A capacidade de reagir à diferença entre entradas

Ele é o “motor” que permite que a realimentação funcione.

Sem ganho alto:

* O erro entre entradas seria significativo
* O sistema não se estabilizaria corretamente

---

# 11. Malha Aberta vs Malha Fechada

| Característica | Malha Aberta           | Malha Fechada       |
| -------------- | ---------------------- | ------------------- |
| Realimentação  | Não existe             | Existe              |
| Ganho          | Muito alto e impreciso | Controlado          |
| Linearidade    | Baixa                  | Alta                |
| Uso típico     | Comparador             | Amplificação linear |

---

# 12. Análise Crítica

O ganho em malha aberta:

* Não é infinito
* Varia com temperatura
* Varia com frequência
* Pode introduzir instabilidade

Projetistas utilizam compensação interna para garantir estabilidade.

---

# Conclusão

A **malha aberta** é a condição em que o amplificador opera sem realimentação.

O **ganho em malha aberta** é a amplificação interna do sinal diferencial:

$$
V_{out} = A_{OL}(V^+ - V^-)
$$

Esse ganho é extremamente alto e depende da frequência.

Ele torna o amplificador:

* Inutilizável para amplificação linear sem realimentação
* Extremamente poderoso quando realimentado

Em síntese, o ganho em malha aberta é a base matemática e física que possibilita a precisão dos circuitos em malha fechada.

---

