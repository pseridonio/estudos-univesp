### Ordem Gray e como aplicá‑la

#### O que é a ordem Gray
A ordem Gray (ou código Gray) é uma sequência de códigos binários em que dois valores consecutivos diferem em exatamente um único bit. Essa propriedade reduz transições simultâneas de vários bits e é usada para rotular colunas/linhas em mapas de Karnaugh (K-map) de modo que células adjacentes representem combinações que diferem em apenas uma variável, facilitando agrupamentos e simplificações.

#### Por que usar Gray em K-map
- Em K-map a adjacência lógica deve corresponder a diferença em 1 bit; a ordem Gray garante essa propriedade entre células vizinhas.  
- Com Gray, células que estão lado a lado (ou em wrap‑around nas bordas) representam mintermos que só mudam uma variável, permitindo eliminar essa variável ao agrupar. A videoaula usa explicitamente essa rotulagem Gray para construir mapas e agrupar mintermos.

#### Como construir a sequência Gray (prática)
Método direto (para n bits):
1. Comece pela sequência de 1 bit: 0, 1.  
2. Para gerar a sequência de n+1 bits, faça: copie a sequência n‑bits na ordem direta prefixando 0; copie a sequência n‑bits na ordem inversa prefixando 1.  
Exemplo:
- 1 bit: 0, 1  
- 2 bits: prefixar 0 → 00, 01 ; prefixar 1 na ordem inversa → 11, 10 → sequência: 00, 01, 11, 10  
- 3 bits: prefixar 0 → 000, 001, 011, 010 ; prefixar 1 na ordem inversa → 110, 111, 101, 100 → sequência: 000,001,011,010,110,111,101,100.

Fórmula de conversão binário → Gray (rápida):
- Gray = Binary xor (Binary >> 1) bit a bit.  
Exemplo: binário 1011 → deslocado 0101 → xor = 1110 (Gray).

Conversão Gray → binário (rápida):
- Faça bit MSB do binário igual ao MSB do Gray; cada bit seguinte do binário é xor do bit anterior do binário com o bit atual do Gray.  
Exemplo: Gray 1110 → bin MSB = 1; próximo = 1 xor 1 = 0; próximo = 0 xor 1 = 1; próximo = 1 xor 0 = 1 → binário 1011.

#### Aplicação prática em K-map (passo a passo)
1. Determine n (número de variáveis).  
2. Escolha layout: para 3 variáveis use 2×4 (linha = 1 bit, coluna = 2 bits); para 4 variáveis use 4×4 (linha = 2 bits, coluna = 2 bits).  
3. Rotule linhas e colunas usando a sequência Gray (cada rótulo é um subconjunto de bits).  
   - Ex.: 3 vars (A linha, BC colunas): colunas em Gray = 00, 01, 11, 10; linhas A = 0, 1.  
4. Preencha os valores da tabela‑verdade nas células correspondentes ao rótulo Gray.  
5. Agrupe células vizinhas — a ordem Gray garante que vizinhos horizontais/verticais diferem em 1 bit. Lembre‑se do wrap‑around: primeira e última coluna (ou linha) são adjacentes por Gray.

#### Exemplos numéricos
- 2 bits: Gray 00, 01, 11, 10. Observação: 01 e 11 diferem em 1 bit; 11 e 10 diferem em 1 bit; 10 e 00 diferem em 1 bit (wrap‑around).  
- Rótulos de K‑map 4×4 (4 variáveis AB × CD): linhas AB em Gray: 00, 01, 11, 10; colunas CD em Gray: 00, 01, 11, 10. A célula (linha 01, coluna 11) representa mintermo AB=01, CD=11 → mintermo decimal 3 (conforme indexação adotada).

#### Dicas práticas e armadilhas
- Sempre use ordem Gray para rótulos; rotular em ordem binária simples (00,01,10,11) quebra a propriedade de adjacência e leva a simplificações incorretas.  
- Visualize o mapa como superfície toroidal: bordas opostas são adjacentes. Isso ajuda a formar grupos que atravessam margens.  
- Ao gerar Gray manualmente, prefira o método de espelhamento (prefixar 0 e 1) para evitar erros.  
- Para checar rótulos rapidamente: compare dois rótulos vizinhos e confirme que apenas um bit difere. Se diferirem em 2 bits, a ordem está errada.

#### Resumo rápido
- Ordem Gray = sequência onde valores consecutivos diferem em 1 bit.  
- Gere recursivamente por espelhamento ou converta por xor (bin → Gray).  
- Use Gray para rotular linhas/colunas do K‑map; é essencial para que agrupamentos eliminem exatamente uma variável por adjacência e para permitir wrap‑around simplificações.

Referência: conteúdo e demonstrações da videoaula base sobre mapas de Karnaugh e organização Gray.