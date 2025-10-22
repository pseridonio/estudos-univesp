# Representação de números com sinal e aritmética binária

## Introdução

A aula baseia‑se na videoaula “Circuitos Digitais - Representação de números com sinal e aritmética binária” (transcrição do vídeo usada como fonte principal) e apresenta as formas de representar inteiros com sinal, operações aritméticas básicas em binário, e as flags de erro (carry‑out e overflow) usadas em circuitos digitais. O objetivo é transformar a transcrição e exemplos do vídeo em um material didático organizado, com passos, explicações e exercícios resolvidos.

---

## Desenvolvimento

### 1. Soma binária: tabelas por caso e carry

- Conceito: soma binária é análoga à soma decimal, trabalhando bit a bit com geração de carry (vai‑um). As regras básicas sem carry‑in:
  - 0 + 0 = 0 (carry‑out = 0)  
  - 0 + 1 = 1 (carry‑out = 0)  
  - 1 + 0 = 1 (carry‑out = 0)  
  - 1 + 1 = 0 (carry‑out = 1).
- Com carry‑in (cin) presente, a operação é soma de três bits (a, b, cin). Tabela exemplo (resumo):
  - a + b + cin = (soma bit, carry‑out)
  - 0+0+0 = (0,0); 0+0+1 = (1,0); 0+1+1 = (0,1); 1+1+1 = (1,1).

Passo a passo (exemplo):
- Somar 1 1 0 1 (13) com 0 1 1 1 (7) em binário (4 bits):
  1. Bit LSB: 1 + 1 = 0, carry = 1.  
  2. Próximo: 0 + 1 + carry(1) = 0, carry = 1.  
  3. Próximo: 1 + 1 + carry(1) = 1, carry = 1.  
  4. MSB: 1 + 0 + carry(1) = 0, carry = 1 (carry‑out). Resultado de 4 bits = 0110 (6) e carry‑out = 1; para representar 20 (13+7) precisaríamos de 5 bits, por isso carry‑out indica excesso de capacidade na largura atual.

Definição: carry‑out sinaliza que o resultado não coube na largura disponível; é uma flag útil para aritmética sem sinal.

---

### 2. Subtração binária: borrow e relação com soma

- Conceito: subtração bit a bit usa borrow (empréstimo) semelhante ao carry. Tabelas básicas para borrow‑in = 0:
  - 0 − 0 = 0 (borrow‑out = 0)  
  - 0 − 1 = 1 (borrow‑out = 1)  
  - 1 − 0 = 1 (borrow‑out = 0)  
  - 1 − 1 = 0 (borrow‑out = 0).
- Com borrow‑in = 1, as combinações mudam; a subtração de multi‑bits pode ser realizada convertendo o subtraendo em complemento de 2 e somando, ou usando circuitos de borrow.

Exemplo detalhado (aplicando tabela do vídeo):
- Subtrair 7 (0111) de 13 (1101) com método bit a bit usando borrow: seguindo as tabelas do vídeo, o resultado final é 0110 (6), confirmando o processo explicado na transcrição.

---

### 3. Representações de números com sinal

O vídeo analisa três formas: sinal‑magnitude, complemento de 1 e complemento de 2, com suas vantagens/desvantagens.

#### 3.1 Sinal‑magnitude
- Estrutura: MSB é bit de sinal (0 positivo, 1 negativo); demais bits representam magnitude.  
- Intervalo em 8 bits: +0..+127 e −0..−127 (problema: duas representações para zero).  
- Operações: soma/subtração por lógica diferente entre sinais; implementação mais complexa. Ex.: +23 e −23 mantêm magnitude idêntica e mudam apenas o MSB.

#### 3.2 Complemento de 1
- Gerar negativo invertendo todos os bits da representação positiva.  
- Também apresenta dupla representação de zero (0000... e 1111...), e complicações nas operações aritméticas; intervalo em n bits: −(2^{n−1}−1) a +(2^{n−1}−1) (ex.: −127..+127 em 8 bits).

#### 3.3 Complemento de 2 (forma preferida)
- Gerar negativo: inverter bits (complemento de 1) e somar 1.  
- Vantagens: representação única para zero; soma/subtração podem ser feitas com o mesmo circuito adder; intervalo em 8 bits: −128..+127; o menor negativo (−128) tem representação distinta.  
- Importante: para soma em complemento de 2, carry‑out do MSB é ignorado; flag relevante para erro é o overflow (diferença entre sinais).

Explicação passo a passo para converter +23 para −23 em complemento de 2 (8 bits):
1. +23 em binário 8 bits = 0001 0111.  
2. Inverter bits → 1110 1000 (complemento de 1).  
3. Somar 1 → 1110 1001 (complemento de 2: representação de −23).

---

### 4. Flags: carry‑out vs overflow

- Carry‑out: indica que a soma produziu um bit além do MSB — relevante para números sem sinal (unsigned) e para indicar que a soma excedeu a largura disponível.
- Overflow: detecta erro na representação em complemento de 2; ocorre quando a soma de dois números com mesmo sinal produz resultado com sinal oposto. Exemplo: somar dois positivos e obter resultado negativo (bit de sinal do resultado difere dos bits de sinal dos operandos) — então overflow = 1.
- Observação do vídeo: existem casos onde carry e overflow têm valores distintos (um ligado e o outro desligado), portanto ambos são relevantes e distintos na verificação de erros aritméticos.

---

### 5. Implementação de somadores e subtratores (visão prática)

- Meio‑somador (half‑adder): soma dois bits a e b → sum = a xor b; carry = a and b.  
- Somador completo (full‑adder): soma a, b e carry‑in → sum = a xor b xor cin; cout = majority(a,b,cin) ou (a·b) + (b·cin) + (a·cin).  
- Ripple‑carry adder: encadeia full‑adders por cada bit; simples, mas com atraso linear ao número de bits (propagação de carry). O vídeo indica que esses circuitos serão estudados a seguir nas aulas de somadores/subtratores.

Passo a passo para somador de 4 bits (ripple):
1. Implementar 4 full‑adders em série.  
2. Conectar carry‑out de cada etapa ao carry‑in da próxima.  
3. Resultado: bits de soma e carry‑out final; detectar overflow comparando sinais conforme complemento de 2.

---

## Conclusão

- As representações com sinal têm trade‑offs: sinal‑magnitude e complemento de 1 apresentam dupla representação de zero; complemento de 2 elimina esse problema e facilita implementação de somas/subtrações usando o mesmo circuito adder.  
- Carry‑out e overflow são flags distintas; compreender quando usar cada uma é essencial para projetar corretamente verificações de erro em hardware.  
- O vídeo fornece exemplos numéricos e demonstra a técnica de deslocamento e soma para multiplicação, além de exercícios de soma/subtração e análise de flags que consolidam conceitos apresentados.

---

## Análise crítica

- O conteúdo do vídeo está didático e cobre os pontos essenciais: tabelas de soma/subtração, representações de sinal e flags. A transcrição deixa explícito os exemplos passo a passo, o que facilita conversão para material didático.  
- Pontos que o vídeo não explora em profundidade e que deveriam ser complementados:  
  - Comparação prática de custo (portas, atraso) entre implementações em sinal‑magnitude, complemento de 1 e complemento de 2;  
  - Implementações alternativas de adder (carry‑lookahead, carry‑save) para reduzir atraso em designs reais;  
  - Exemplos de implementação em VHDL de somadores completos e de detecção de overflow/carry usados em sistemas embarcados.  
  Esses tópicos devem ser estudados com o material complementar sugerido abaixo.

---

## Sugestões de complementação

- Acrescentar um módulo prático em VHDL que implemente: meio‑somador, somador completo, ripple‑adder de 4 bits, e teste de overflow/carry simulado.  
- Incluir uma tabela comparativa de custos (portas lógicas e latência) entre ripple‑carry e carry‑lookahead para somadores de 8 e 16 bits.  
- Exercícios práticos sobre multiplicação por deslocamento+soma e análise de overflow em operações reais (ex.: soma de 8‑bit em complemento de 2).

---

## Exercícios (com resolução detalhada, passo a passo)

Obs.: todos os exercícios usam exemplos numéricos seguindo a transcrição do vídeo como base.

### Exercício 1 — Soma binária simples
Some 4‑bit A = 1101 (13) e B = 0111 (7). Mostre passo a passo a soma, indique carry‑out e interprete resultado em unsigned.

Resolução:
1. LSB: 1 + 1 = 0, carry = 1.  
2. Próximo: 0 + 1 + carry(1) = 0, carry = 1.  
3. Próximo: 1 + 1 + carry(1) = 1, carry = 1.  
4. MSB: 1 + 0 + carry(1) = 0, carry = 1 (carry‑out).  
Resultado de 4 bits = 0110 (6), carry‑out = 1.  
Interpretação unsigned: 13 + 7 = 20; com 4 bits não há espaço para 20, por isso carry‑out = 1 indica excesso; para valor correto precisa‑se de 5 bits (10100).

### Exercício 2 — Soma em complemento de 2 e overflow
Some X = 0100 (+4) e Y = 0101 (+5) em 4 bits (complemento de 2). Indique resultado, carry‑out e overflow.

Resolução:
1. Soma bit a bit: 0+1 =1 no LSB, prosseguir com carries como necessário. Calculando: 0100 + 0101 = 1001 (9) sem carry‑out no 4º bit.  
2. carry‑out = 0.  
3. Overflow? Somamos dois positivos (+4 e +5) e obtivemos 1001 cujo MSB = 1 (interpretação em complemento de 2 = −7) → sinal do resultado difere dos sinais dos operandos → overflow = 1.  
Interpretação: em complemento de 2, ocorreu overflow porque o resultado real (+9) não cabe em 4 bits (intervalo −8..+7). Portanto flag overflow = 1 deve ser usada para detectar erro.

### Exercício 3 — Converter −23 para complemento de 2 (8 bits)
Mostre passo a passo como obter representação de −23.

Resolução:
1. +23 em 8 bits: 0001 0111.  
2. Complemento de 1: inverter bits → 1110 1000.  
3. Somar 1 → 1110 1001.  
Resultado: 1110 1001 representa −23 em complemento de 2.

### Exercício 4 — Verificação de zero único em complemento de 2
Mostre por que complemento de 2 não tem dupla representação de zero.

Resolução:
1. Zero positivo: 0000...0.  
2. Complemento de 1 de zero: 1111...1; somando 1 → 0000...0 com carry descartado. Logo a transformação para negativo e volta produzem o mesmo zero único. Assim complemento de 2 tem representação única de zero, ao contrário de sinal‑magnitude e complemento de 1.

### Exercício 5 — Multiplicação por deslocamento e soma (exemplo do vídeo)
Multiplique 1101 (13) por 1001 (9) usando deslocamento e soma, mostrando as linhas intermediárias.

Resolução:
1. Segundo multiplicando bits LSB→MSB (1001): bit0=1 → copiar base 1101 (sem deslocamento).  
2. bit1=0 → copiar 0000 e deslocar 1 → 00000.  
3. bit2=0 → 000000 deslocado 2 → 000000.  
4. bit3=1 → copiar base e deslocar 3 → 1101 000.  
5. Somar linhas: 00001101 + 00000000 + 00000000 + 1101000 = resultado final (em binário) → realizar soma bit a bit. (Detalhe: siga os deslocamentos e somas da mesma maneira que no vídeo; resultado decimal = 117).  
Comentário: técnica do vídeo demonstra claramente deslocamentos por casas e somas parciais como mecanismo de multiplicação binária por soma de produtos parciais.

---

## Bibliografia (formato ABNT)

- UNIVESP. Circuitos Digitais - Representação de números com sinal e aritmética binária. Vídeo aula (YouTube). Professor André Ricardo Fioravanti. UNIVESP; 3 nov. 2021. Acesso em: 20 out. 2025.  
- TOCCI, R. J.; WIDMER, N. S.; MOSS, G. L. Sistemas digitais: princípios e aplicações. 12. ed. São Paulo: Pearson, 2018. E‑book. Disponível em: https://plataforma.bvirtual.com.br. Acesso em: 20 out. 2025.  
- FLOYD, Thomas. Sistemas digitais. 9. ed. Porto Alegre: Bookman, 2011. Acesso em: 20 out. 2025.  
- GUNTZEL, J. Circuitos de Armazenamento. Instituto de Informática, UFSC. Disponível em: https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf. Acesso em: 20 out. 2025.

---

## Materiais complementares

- Slides e transcrição da videoaula usada como fonte principal (UNIVESP).  
- Livro TOCCI et al., Sistemas digitais: princípios e aplicações — capítulos sobre representações e somadores (consulta recomendada).  
- GUNTZEL, J. — notas sobre lógica digital e circuitos de armazenamento — complementam compreensão de implementação física e memória usada em somadores/subtratores. Acesso em: 20 out. 2025.

---