# Circuítos Aritméticos

## Introdução

Esta aula resume e organiza o conteúdo da videoaula "Circuitos Digitais - Circuitos Aritméticos" (transcrição usada como fonte principal) e explica passo a passo os conceitos de meio‑somador, somador completo, somadores paralelos (ripple‑carry), técnicas de carry antecipado, uso de somador para subtração via complemento, e comparadores binários.

## Desenvolvimento

### Meio‑somador — definição, expressão lógica e exemplo passo a passo

- Definição: circuito que soma dois bits A e B e produz duas saídas: soma (Σ) e carry‑out (Cout). O carry‑out indica quando a soma não coube em um único bit (quando A = 1 e B = 1).  
- Expressões lógicas:
  - Σ = A XOR B  
  - Cout = A AND B  
  - Significado das variáveis: A, B são entradas (bits). Σ é o bit de soma (resultado no peso atual) e Cout é o bit de transporte para a próxima ordem.  
- Exemplo passo a passo:
  - Caso A=1, B=1 → A XOR B = 0 → Σ = 0; A AND B = 1 → Cout = 1. Interpretação: 1 + 1 = (Σ=0) com transporte 1 para o próximo bit.

Referência direta ao circuito e à motivação mostrada no vídeo: meio‑somador implementa exatamente essas duas portas e é o bloco básico para construir somadores maiores.

### Somador completo — estrutura, fórmulas e montagem a partir de meio‑somadores

- Definição: soma A, B e o carry‑in (Cin), produz Σ (soma do bit) e Cout (carry‑out).  
- Fórmulas:
  - Σ = A XOR B XOR Cin  
  - Cout = (A·B) + (A·Cin) + (B·Cin) (ou qualquer forma equivalente de majority)  
- Construção com meio‑somadores:
  1. Primeiro meio‑somador: soma A e B → S1 = A XOR B, C1 = A AND B.  
  2. Segundo meio‑somador: soma S1 e Cin → Σ = S1 XOR Cin, C2 = S1 AND Cin.  
  3. Cout = C1 OR C2.  
- Justificativa: essa decomposição reaproveita a lógica da soma e permite implementação com duas XOR, duas AND e uma OR, conforme demonstrado na transcrição.

Exemplo numérico (A=1, B=1, Cin=1):
- S1 = 1 XOR 1 = 0; C1 = 1 AND 1 = 1.  
- Σ = S1 XOR Cin = 0 XOR 1 = 1.  
- C2 = S1 AND Cin = 0 AND 1 = 0.  
- Cout = C1 OR C2 = 1 OR 0 = 1. Resultado: soma de 1+1+1 = binário 11 → (Σ=1, Cout=1).

### Somadores paralelos e ripple‑carry — operação e atraso

- Organização: para somar N bits usa‑se uma cadeia de N somadores completos conectando Cout de cada estágio ao Cin do próximo (LSB → MSB) — chamada topologia ripple‑carry (carry propagado).  
- Atraso: o tempo total pode crescer linearmente com N porque cada estágio aguarda o carry do anterior; o vídeo exemplifica o cálculo do atraso multiplicando tempo por estágio pelo número de estágios.  
- Observação prática: para N grande, o ripple‑carry pode se tornar ineficiente em desempenho, motivando técnicas alternativas.

Exemplo: somador de 4 bits com tempo de propagação t por estágio → atraso máximo ≈ 4·t (valor ilustrativo dado na transcrição).

### Carry antecipado (carry lookahead) — ideia e trade‑offs

- Ideia: decompor o carry em sinais de geração (G) e propagação (P) para antecipar Cout sem esperar a propagação linear, reduzindo atraso global.  
  - G_i = A_i·B_i (gera carry no estágio i)  
  - P_i = A_i ⊕ B_i (propaga carry do estágio anterior) — ou P_i = A_i + B_i dependendo da formulação.  
- Trade‑off: reduz atraso em troca de maior complexidade lógica (mais portas e interconexões) e custo físico; por isso o uso prático é híbrido (blocos de 4 bits com lookahead interconectados em ripple) conforme o vídeo.

### Subtração via complemento de 2 — implementação com somador

- Técnica: A − B = A + (complemento de 2 de B). Implementação prática: condicionar cada bit de B a passar por XOR com o sinal ADD/SUB (0→passa igual; 1→inverte) e usar Cin = ADD/SUB para adicionar 1 no caso de subtração (complemento de 2).  
- Passos (controle ADD/SUB):
  1. Quando ADD/SUB = 0 (soma): entradas Y entram diretamente no somador; Cin inicial = 0.  
  2. Quando ADD/SUB = 1 (subtração): cada bit Y passa por XOR com 1 (inversão) → complemento de 1; Cin inicial = 1 adiciona o +1 necessário → complemento de 2.  
- Observação: essa técnica permite reusar a mesma unidade de soma para somar e subtrair controladamente, conforme exemplificado na transcrição.

Exemplo: A=0101 (5), B=0011 (3), ADD/SUB=1 (subtração):
- B xor 1 = 1100 (complemento de 1); Cin=1 → somar A + 1100 + Cin = resultado A − B em complemento de 2.

### Comparadores — igualdade, maior/menor e implementação básica

- Igualdade: realizar XNOR bit a bit entre A_i e B_i; a saída final de igualdade é AND de todos os XNORs (1 somente se todos os bits são iguais).  
- Maior/menor (sem sinal): comparar bits do MSB ao LSB; A > B se no primeiro bit em que A e B diferem, A tiver 1 e B tiver 0; pode ser construído combinando XNORs e detectores de padrões para cada posição, conforme descrito na vídeo‑aula.  
- Observação: as mesmas ideias generalizam para números em complemento de 2 com adaptações de interpretação de sinal.

## Conclusão

- Meio‑somador e somador completo são blocos primários; somadores paralelos (ripple) são simples mas têm atraso linear e podem ser acelerados com carry‑lookahead.  
- A subtração é implementada eficientemente via complemento de 2 e reutilização do somador, controlada por um sinal ADD/SUB que alimenta XORs e Cin.  
- Comparadores de igualdade e ordem são construídos a partir de XNORs e lógica sequencial de bits mais significativos para menos significativos, conforme demonstrado no vídeo transcrito.

## Análise crítica

- O vídeo apresenta com clareza os blocos e as interconexões básicas; enfatiza corretamente o trade‑off entre atraso e complexidade (ripple vs carry antecipado) e mostra a reutilização prática do somador para subtração via complemento de 2.  
- Pontos que merecem complementação prática: quantificação precisa de atraso e custo (áreas e portas) para implementações reais; exemplos em VHDL e simulação com casos limite de overflow/carry devem ser incluídos para consolidar a compreensão (essenciais para implantação em FPGA). Essas sugestões alinham‑se com os materiais complementares indicados.

## Sugestões de complementação

- Implementar em VHDL: meio‑somador, somador completo, ripple‑adder de 4 bits e unidade soma/subtração controlada por ADD/SUB; simular casos com overflow e comparar tempos.  
- Estudo adicional: comparação de custos (portas e atraso) entre ripple‑carry, carry‑lookahead e arquiteturas híbridas (blocos de 4 bits lookahead + ripple entre blocos).  
- Exercícios práticos: projetar comparador de 4 bits e testar com todos os pares A,B; medir e comparar sinais de carry e overflow.

## Exercícios (com resolução detalhada, passo a passo)

Obs.: exercícios baseados nos exemplos e tabelas mostradas na transcrição do vídeo.

### Exercício 1 — Meio‑somador
Dado A = 1 e B = 0, determine Σ e Cout de um meio‑somador. Mostre as portas envolvidas e explique o resultado.

Resolução:
- Σ = A XOR B = 1 XOR 0 = 1.  
- Cout = A AND B = 1 AND 0 = 0.  
- Interpretação: 1 + 0 = 1 sem transporte. Implementação física: uma porta XOR para Σ e uma porta AND para Cout.

### Exercício 2 — Somador completo (um estágio)
Dados A = 1, B = 1, Cin = 0. Calcule Σ e Cout usando a decomposição em dois meios‑somadores.

Resolução:
1. Primeiro meio‑somador (A,B): S1 = A XOR B = 1 XOR 1 = 0; C1 = A AND B = 1.  
2. Segundo meio‑somador (S1, Cin): Σ = S1 XOR Cin = 0 XOR 0 = 0; C2 = S1 AND Cin = 0.  
3. Cout = C1 OR C2 = 1 OR 0 = 1. Resultado final: Σ=0, Cout=1 (representa soma 1+1+0 = 10₂).

### Exercício 3 — Somador de 4 bits (ripple) e carry‑out
Some A = 1101 (13) e B = 0111 (7) em 4 bits usando ripple. Indique bits de Σ e carry final.

Resolução (bit a bit LSB→MSB):
- LSB (bit0): 1+1 + Cin0(0) → Σ0=0, Cout0=1.  
- bit1: 0+1 + Cin1(1) → 0+1+1 = 0 (Σ1), Cout1=1.  
- bit2: 1+1 + Cin2(1) → 1+1+1 = 1 (Σ2), Cout2=1.  
- MSB (bit3): 1+0 + Cin3(1) → 1+0+1 = 0 (Σ3), Cout3=1 (carry final).  
Resultado Σ = 0110 (6), carry‑out = 1. Interpretação unsigned: 13+7=20; em 4 bits há estouro indicado por carry=1.

### Exercício 4 — Subtração via complemento de 2
Calcule A − B com A = 0101 (5), B = 0011 (3) usando a técnica ADD/SUB (com XOR nos bits de B e Cin = ADD/SUB). ADD/SUB = 1 para subtrair.

Resolução:
1. Inverter B bit a bit (XOR com 1): B' = 1100 (complemento de 1).  
2. Cin inicial = 1 → soma A + B' + 1.  
3. Soma 0101 + 1100 = 10001 (5 bits). Considerando 4 bits: Σ = 0001 (1), carry final = 1 → descartado ou interpretado conforme largura; em complemento de 2 o resultado correto é 0010? Vamos somar com pasos:
   - LSB:1+0+1 = 0, carry=1.  
   - bit1:0+0+1 = 1, carry=0.  
   - bit2:1+1+0 = 0, carry=1.  
   - bit3:0+1+1 = 0, carry=1. Resultado 0010 com carry final 1 → valor 2 (esperado: 5−3=2).  
4. Resultado concluído: Σ = 0010 (2).

### Exercício 5 — Comparador de igualdade 4 bits
Projete a lógica para determinar se A = B para A3A2A1A0 e B3B2B1B0. Explique as portas e o raciocínio.

Resolução:
1. Para cada i ∈ {0..3}, compute Xi = XNOR(Ai, Bi) (Xi=1 se Ai=Bi).  
2. Igualdade final E = X3 AND X2 AND X1 AND X0.  
3. Implementação: quatro portas XNOR bit a bit; em seguida uma porta AND de 4 entradas que unifica os resultados. A saída E=1 somente se todos os Xi forem 1, ou seja, todos os bits iguais.

## Bibliografia (formato ABNT)

- UNIVESP. Circuitos Digitais - Circuitos Aritméticos. Vídeo aula (YouTube). Professor André Ricardo Fioravanti. UNIVESP; 3 nov. 2021. Acesso em: 20 out. 2025.  
- TOCCI, Ronald J.; WIDMER, Neal S.; MOSS, Gregory L. Sistemas digitais: princípios e aplicações. 12. ed. São Paulo: Pearson, 2018. E‑book. Disponível em: https://plataforma.bvirtual.com.br. Acesso em: 20 out. 2025.  
- GUNTZEL, J. Circuitos de Armazenamento. Instituto de Informática, UFSC. Disponível em: https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf. Acesso em: 20 out. 2025.

## Materiais complementares

- Slides e transcrição da videoaula usada como fonte principal (UNIVESP) — transcrição consultada e utilizada como base para todos os exemplos e definições nesta aula.  
- TOCCI, R. J.; WIDMER, N. S.; MOSS, G. L. — capítulos sobre somadores, subtratores e representações com sinal para aprofundamento prático.  
- GUNTZEL, J. — notas sobre lógica digital e implementação de blocos lógicos em Níveis Físicos.

---