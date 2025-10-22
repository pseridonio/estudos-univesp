### Pergunta 1
> Os intervalos de valores de um número de 8 bits representando números inteiros sem sinal (NSS), números em complemento de um (C1) e número em complemento de dois (C2) são, respectivamente:  
>  
> a. NSS: de 0 a 255; C1: de -127 a 127; C2: de -127 a 128  
> b. NSS: de 0 a 255; C1: de -127 a 127; C2: de -128 a 127  
> c. NSS: de 0 a 512; C1: de -255 a 255; C2: de -256 a 255  
> d. NSS: de 0 a 7; C1: de -4 a 3; C2: de -3 a 4  
> e. NSS: de 0 a 255; C1: de 0 a 255; C2: de -128 a 127

### Resposta
Resposta: b. NSS: de 0 a 255; C1: de -127 a 127; C2: de -128 a 127.

### Justificativa — passo a passo completo
1. Interpretação inicial: precisamos determinar os intervalos representáveis por 8 bits nas três convenções mencionadas: sem sinal (unsigned), complemento de 1 (ones' complement) e complemento de 2 (two's complement).

2. Intervalo para números sem sinal (NSS):  
   - Fórmula: para n bits, o intervalo é 0 até 2^n − 1.  
   - Aplicando n = 8: 2^8 − 1 = 256 − 1 = 255.  
   - Conclusão: NSS em 8 bits representa 0..255.

3. Intervalo para complemento de 1 (C1, ones' complement):  
   - Propriedade: em “ones' complement” de n bits, o intervalo é de −(2^(n−1) − 1) até +(2^(n−1) − 1).  
   - Aplicando n = 8: 2^(8−1) − 1 = 128 − 1 = 127 → intervalo = −127..+127.  
   - Observação: ones' complement tem duas representações de zero (+0 e −0), por isso o alcance negativo não inclui −128.

4. Intervalo para complemento de 2 (C2, two's complement):  
   - Propriedade: em “two's complement” de n bits, o intervalo é de −2^(n−1) até +(2^(n−1) − 1).  
   - Aplicando n = 8: −2^7 = −128 até 2^7 − 1 = 127 → intervalo = −128..+127.  
   - Observação: two's complement tem representação única para zero e permite representar um valor negativo a mais que o positivo simétrico (−128 em 8 bits).

5. Comparação com as alternativas: a alternativa (b) lista exatamente NSS: 0..255; C1: −127..127; C2: −128..127, que coincide com os cálculos acima. As demais opções apresentam faixas incorretas (por exemplo, (a) inverte o sinal mínimo de C2; (e) erra a faixa de C1), logo estão incorretas.

6. Conclusão final: a opção correta é a letra b.

---  

### Pergunta 2

> Trabalhar com uma quantidade finita de bits é uma característica associada a circuitos somadores e subtratores. Esse é o motivo que os leva a ter de adotar alguns flags que se destinam a indicar erros, conforme a situação detectada na codificação da entrada. Por exemplo, na operação de soma, um flag é acionado caso se identifique o “mais um” na adição efetuada do MSB (Most Significant Bit, ou, em português, Bit Mais Significante). Tal flag serve ainda para apontar o erro na operação com números sem sinal.  
>  
> Assinale a alternativa que corresponde à descrição correta do flag em questão.  
> a. Carry-out.  
> b. Underflow.  
> c. Evenflow.  
> d. Come-on.  
> e. Carry-on.

### Resposta
Resposta: a. Carry-out.

### Justificativa — passo a passo completo
1. Interpretação inicial do enunciado: o enunciado descreve uma situação em que, ao somar dois números em representação binária com largura fixa, ocorre um “mais um” além do bit mais significativo (MSB). Em aritmética binária, esse sinal adicional que sai do MSB é usado para indicar que a soma excedeu a capacidade da largura (overflow no sentido de capacidade sem sinal).

2. Identificação do flag relevante: o termo técnico para o bit que sai do estágio do MSB numa cadeia de adição (isto é, o transporte gerado pelo MSB) é “carry‑out” (às vezes escrito cout). Esse sinal representa o transporte além da posição mais significativa e é usado especialmente para detectar estouro (overflow) em aritmética sem sinal.

3. Distinção entre conceitos próximos:
   - Carry‑out: transporte que sai do MSB, usado para indicar excesso em somas unsigned (sem sinal) e também como entrada para somadores encadeados (propagação de carry).  
   - Overflow (em complemento de dois): flag distinto usado para detectar erro de sinal na aritmética com sinal (two's complement); frequentemente calculado a partir de XOR entre carrys dos dois últimos estágios ou pela comparação dos sinais dos operandos e do resultado.  
   - Underflow, Evenflow, Come-on, Carry‑on: termos que não correspondem ao flag padrão descrito; “underflow” refere‑se a perda de precisão em ponto flutuante ou resultado abaixo do mínimo representável, não ao transporte do MSB; os demais são termos incorretos/inventados no contexto.

4. Aplicação ao enunciado: o enunciado descreve exatamente o transporte além do MSB e diz que ele aponta erro em operações com números sem sinal — isso é a definição prática do carry‑out. Portanto a alternativa correta é “Carry‑out”.

5. Verificação final e conclusão: a alternativa (a) está de acordo com a terminologia padrão em lógica digital e arquitetura de computadores; as demais alternativas estão incorretas para o contexto descrito. Conclusão: resposta correta = a. Carry-out.

---  
### Pergunta 3
