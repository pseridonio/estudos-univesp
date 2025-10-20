# Multiplexadores, vetores em VHDL e conversor BCD → 7 segmentos (aula baseada no vídeo atual)

## Introdução

Esta aula usa como base o vídeo "Circuitos Digitais - Simulação de Circuitos II" e sua transcrição para ensinar, detalhadamente, como descrever e simular em VHDL: multiplexadores (2:1 e 4:1) para sinais escalares e vetoriais, e um decodificador BCD para display de 7 segmentos. A aula aborda conceitos, sintaxe VHDL, exemplos concretos, recomendações práticas e exercícios resolvidos passo a passo.

---

## Desenvolvimento

### Conceito e tabela-verdade do multiplexador 2:1 (1 bit)

- Definição: o multiplexador 2:1 seleciona entre duas entradas W0 e W1 com base em um seletor S e encaminha a entrada selecionada para a saída F. É um roteador lógico simples cuja tabela-verdade é:
  - S = '0' → F = W0
  - S = '1' → F = W1
- Interpretação temporal: quando S muda, a saída passa a refletir a entrada correspondente nos instantes em que os sinais de entrada estão estáveis; a simulação visualiza essa correspondência temporal entre S e F nas janelas de tempo apresentadas no vídeo.

Explicação passo a passo da implementação lógica (AND/NOT/OR):
- Fórmula: F = (W0 AND (NOT S)) OR (W1 AND S).  
  - Variáveis: W0, W1, S, F (bits lógicos).  
  - Lógica: quando S=0, (NOT S)=1 → termo (W0 AND 1)=W0 ativa; segundo termo (W1 AND 0)=0 → F = W0. Quando S=1, primeiro termo =0, segundo termo = W1 → F = W1.  
- Essa expressão é diretamente traduzida em portas lógicas e serve como base para a versão com sinais intermediários em VHDL mostrada no vídeo.

#### VHDL (versão com sinais intermediários)
Código (explicativo):
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity MUX2_1 is
  port (
    W0, W1 : in  std_logic;
    S      : in  std_logic;
    F      : out std_logic
  );
end MUX2_1;

architecture RTL of MUX2_1 is
  signal M1, M2 : std_logic;
begin
  M1 <= W0 and not S;  -- ativa quando S='0' e W0='1'
  M2 <= W1 and S;      -- ativa quando S='1' e W1='1'
  F  <= M1 or M2;      -- saída é a união das contribuições
end RTL;
```
Explicação detalhada das linhas:
- M1 calcula W0·S' (linha por linha, identidade booleana usada: A·B).
- M2 calcula W1·S.
- F é OR entre M1 e M2; aplica-se A + B.

#### VHDL (versão com atribuição condicional "when")
Código:
```vhdl
architecture RTL_when of MUX2_1 is
begin
  F <= W0 when S = '0' else W1;
end RTL_when;
```
Explicação: a construção "when ... else" avalia S; quando S='0' atribui W0 a F; caso contrário, atribui W1. Esta forma é equivalente à implementação por portas, mas mais concisa e legível para descrição de tabelas-verdade.

---

### Multiplexador 2:1 com vetores (4 bits)

- Motivação: em sistemas digitais tratamos sinais multibit (buses). Em VHDL, vetores são representados com o tipo "std_logic_vector(n downto 0)". A mesma lógica funcional do 2:1 aplica-se a vetores inteiros: quando S='0' copia-se o vetor W0 em F; quando S='1' copia-se W1.

VHDL (exemplo):
```vhdl
entity MUX2_1_4bits is
  port(
    W0, W1 : in  std_logic_vector(3 downto 0);
    S      : in  std_logic;
    F      : out std_logic_vector(3 downto 0)
  );
end MUX2_1_4bits;

architecture RTL of MUX2_1_4bits is
begin
  F <= W0 when S = '0' else W1;
end RTL;
```

Detalhes e observações:
- A atribuição copia todos os bits simultaneamente, preservando indexação (3 downto 0).
- Comparações entre vetores usam aspas duplas ("00", "1010") quando necessário; escalars usam aspas simples ('0','1').
- Em síntese, o código gera multiplexação bit-a-bit sem necessidade de descrever manualmente cada bit.

---

### Multiplexador 4:1 com vetores de 4 bits

- Estrutura: entradas W0..W3 (cada std_logic_vector(3 downto 0)), seleção S (std_logic_vector(1 downto 0)), saída F (std_logic_vector(3 downto 0)).  
- Tabela-verdade:
  - S = "00" → F = W0
  - S = "01" → F = W1
  - S = "10" → F = W2
  - S = "11" → F = W3

VHDL (atribuição encadeada):
```vhdl
entity MUX4_1_4bits is
  port(
    W0, W1, W2, W3 : in  std_logic_vector(3 downto 0);
    S              : in  std_logic_vector(1 downto 0);
    F              : out std_logic_vector(3 downto 0)
  );
end MUX4_1_4bits;

architecture RTL of MUX4_1_4bits is
begin
  F <= W0 when S = "00" else
       W1 when S = "01" else
       W2 when S = "10" else
       W3;
end RTL;
```

Explicações importantes:
- Uso de aspas duplas em literal de vetor S = "01" (VHDL diferencia string-like para vetores).
- A ordem dos casos pode incluir "others" para cobrir situações residuais, embora aqui S tem domínio completo de 2 bits.
- Em síntese, essa atribuição gera lógica de multiplexação eficiente, e ferramentas de síntese mapeiam para muxes ou implementações XOR/AND/OR conforme otimização.

---

### Conversor BCD → 7 segmentos (decodificador)

#### Objetivo e convenções
- Entrada: W : std_logic_vector(3 downto 0) representando BCD (mais significativo W3, menos significativo W0) enumerado conforme video; saída SEG : std_logic_vector(6 downto 0) com bits indexados de 0 (LSB) a 6 (MSB), onde '1' ativa segmento e '0' desativa, conforme a convenção adotada no vídeo.
- Requisito funcional: mapear 0..9 para os padrões de segmentos; valores fora de 0..9 → SEG <= (others => '0') (todos segmentos apagados), conforme a aula.

#### Estrutura em VHDL (exemplo parcial)
```vhdl
entity BCDto7Seg is
  port(
    W   : in  std_logic_vector(3 downto 0);
    SEG : out std_logic_vector(6 downto 0)
  );
end BCDto7Seg;

architecture RTL of BCDto7Seg is
begin
  SEG <= "0110000" when W = "0000" else  -- 0
         "1001111" when W = "0001" else  -- 1
         "0010010" when W = "0010" else  -- 2  (exemplos)
         -- ... completar para 2..9 conforme tabela
         (others => '0');                -- entradas inválidas
end RTL;
```

Detalhamento e passo a passo:
- Ordem de bits: no vídeo SEG[0] foi declarado como menos significativo; portanto a string literal deve ser escrita com o bit LSB em primeiro caractere (conforme convenção usada na transcrição) para manter compatibilidade entre entidade e arquitetura e com a tabela-verdade mostrada.
- Verificação por simulação: testar W="0000"→SEG deve igualar padrão de '0' no display; para W maiores que "1001" (9) a saída é "0000000".
- Para displays físicos: adaptar padrão (inversão) se o display for common-anode (nível ativo invertido) e usar resistores/drivers conforme exigência elétrica (ponto ressaltado na análise crítica do vídeo).

---

### Boas práticas e questões de síntese / hardware

- Confirmar a convenção de ordenação de bits (LSB/MSB) entre a especificação, o código e o hardware; inconsistências causam mapeamentos errados dos segmentos no display.
- Usar (others => '0') para valores inválidos simplifica e é seguro para decodificadores BCD que não esperam entradas indevidas.
- Em implementações multi-dígito, usar controlador de refresh e multiplexação de dígitos; escolher taxa de refresh típica para evitar cintilação perceptível (ex.: 1–16 ms por digit total de varredura) e projetar drivers para corrente dos LEDs (buffers/transistores) conforme necessidades práticas e segurança do hardware (não detalhado na transcrição, mas recomendado na prática).

---

## Conclusão

A descrição de multiplexadores e decodificadores em VHDL pode ser feita de forma muito direta usando atribuições condicionais e selecionadas. Vetores ("std_logic_vector") simplificam manipulação de buses multi-bit. O fluxo apresentado no vídeo demonstra claramente a transição da tabela-verdade para a implementação em VHDL e validação por simulação; práticas adicionais (drivers, common-cathode/anode, refresh) devem ser consideradas ao migrar da simulação para o hardware real.

---

## Análise crítica

- O vídeo explicita bem o uso de "when/else" e vetores, e mostra simulações que validam comportamento temporal das seleções; contudo, a transcrição e os slides não aprofundam implementação elétrica do display (drivers, resistores), nem discutem timing de atualização em sistemas multi-dígito. Essas considerações são essenciais para implantação em FPGAs/placas físicas e foram apontadas como pontos a complementar.
- A transição da descrição para síntese em FPGA depende do alvo; práticas de codificação (uso de inferência de MUX, evitar latches indesejados) e constraints de síntese não foram exploradas no vídeo e são recomendadas como complementos.

---

## Exercícios (com resolução detalhada, passo a passo)

### Exercício 1 — MUX 2:1 (1 bit) — escrever e analisar
a) Escreva o código VHDL (entidade + arquitetura) para o multiplexador 2:1 usando sinais intermediários.  
b) Mostre a tabela-verdade e demonstre, passo a passo, que a arquitetura implementa a tabela.

Resolução:
- Código: ver seção de Desenvolvimento (versão com sinais intermediários).  
- Tabela-verdade:
  - S=0, W0=0, W1=0 → M1=0·1=0, M2=0·0=0 → F=0
  - S=0, W0=1, W1=0 → M1=1·1=1, M2=0 → F=1
  - S=1, W0=0, W1=1 → M1=0·0=0, M2=1·1=1 → F=1
  - S=1, W0=1, W1=1 → M1=1·0=0, M2=1·1=1 → F=1
- Verificação linha a linha:
  - Avalie M1 e M2 conforme expressões; F = M1 OR M2 fornece exatamente W0 quando S=0 e W1 quando S=1. Isso confirma correção.

### Exercício 2 — MUX 2:1 (4 bits) — comportamento com vetores
Dado W0 = "1010", W1 = "0101", S = '0', qual será F? E se S = '1'?

Resolução:
- S='0' → F <= W0 → F = "1010".
- S='1' → F <= W1 → F = "0101".
- Explicação: a atribuição condicional copia todo o vetor; não há operação bitwise explícita do usuário porque VHDL faz a atribuição de vetor inteiro.

### Exercício 3 — MUX 4:1 (4 bits) — derivar lógica mínima
Dado um MUX4_1_4bits com W0..W3 e S="10", indique qual entrada é roteada para F. Explique como a síntese implementa isso (conceitualmente).

Resolução:
- S="10" → tabela indica F <= W2.
- Implementação: síntese pode implementar por hierarquia de multiplexadores 2:1 ou por lógica combinacional otimizada; conceitualmente, S[1] e S[0] decodificam a seleção e portas AND/OR direcionam bits correspondentes.

### Exercício 4 — Conversor BCD → 7 segmentos (testes)
Implemente (mentalmente) e verifique três casos:
a) W = "0000" (0) → SEG esperado = padrão para '0'.  
b) W = "0001" (1) → padrão para '1'.  
c) W = "1010" (10) → entrada inválida → SEG = "0000000".

Resolução (exemplo com os padrões usados no vídeo):
- a) W="0000" → SEG <= "0110000" (conforme tabela do slide) → descreve segmentos para 0.  
- b) W="0001" → SEG <= "1001111" → segmentos correspondentes a 1.  
- c) W="1010" (>9) → SEG <= (others => '0') → saída "0000000" → todos segmentos apagados.  
Validação: simule vetores e observe na janela de tempo que SEG assume os vetores correspondentes; se for hardware, verificar inversão de nível caso display seja common-anode.

### Exercício 5 — Implementação por Shannon (aplicação prática)
Considere uma função F(A,B,C) definida como F = A'B'C + AB'C' + ABC. Aplique expansão de Shannon em A e proponha uma implementação por MUX 2:1, indicando entradas (cofatores) a serem ligadas ao MUX.

Resolução:
1. Cofator A=0: F_{A=0} = substitua A=0 → A'=1 → F_{A=0} = B'·C.  
2. Cofator A=1: F_{A=1} = substitua A=1 → termos com A=1: AB'C' + ABC → F_{A=1} = B'·C' + B·C = (B xor C)'? (não simplifica diretamente para literal única).  
3. Shannon: F = A'·(B'·C) + A·(B'·C' + B·C).  
4. MUX 2:1 com seletor A: entrada0 = B'·C; entrada1 = B'·C' + B·C. Implementação: inverter B, criar ANDs e OR conforme cofator; conectar como entradas do MUX.  
Comentário: escolher A como seletor pode reduzir lógica dependendo de simplicidade dos cofatores; essa técnica foi destacada no vídeo para síntese modular usando MUXs.

---

## Bibliografia (formato ABNT)

- UNIVESP. Circuitos Digitais - Simulação de Circuitos II. Vídeo aula (YouTube). Professor André Ricardo Fioravanti. UNIVESP; 25 out. 2021. Acesso em: 18 out. 2025.  
- TOCCI, Ronald J.; WIDMER, Neal S.; MOSS, Gregory L. Sistemas Digitais: princípios e aplicações. 11. ed. São Paulo: Pearson, 2011. Acesso em: 18 out. 2025.  
- GUNTZEL, J. Circuitos de Armazenamento. Instituto de Informática, UFSC. Disponível em: https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf. Acesso em: 18 out. 2025.

---

## Materiais complementares

- Slides e transcrição do vídeo base (UNIVESP) usados como referência para exemplos e convenções de bit-order e vetores.  
- Tutoriais práticos sobre BCD → 7‑seg e multiplexação em VHDL (FPGA4Student, PiEmbSysTech) para implementação física e exemplos de driver; consulte para detalhes de hardware e refresh de displays.  
- Ferramentas de simulação e síntese (ModelSim, GHDL, Vivado) para validar comportamento e verificar inferência de MUXs a partir de atribuições condicionais.

---