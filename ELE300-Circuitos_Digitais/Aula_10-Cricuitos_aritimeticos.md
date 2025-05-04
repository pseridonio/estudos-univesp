# Circuitos Aritméticos

Esta aula aborda os fundamentos dos circuitos aritméticos em sistemas digitais, enfatizando a construção e o funcionamento de somadores, subtratores e comparadores. O conteúdo também é enriquecido com conceitos do livro *Sistemas Digitais: Princípios e Aplicações*, que aprofunda as implicações de projeto para circuitos de alta performance e a utilização de linguagens de descrição de hardware (como VHDL).

---

## 1. Objetivos da Aula

- **Reconhecimento e Compreensão:**
  - Entender o funcionamento e as aplicações dos **meio-somadores** e **somadores completos**.
  - Analisar os conceitos de **carry-out**, **carry propagado** e **carry antecipado**, que afetam o tempo de propagação dos sinais em circuitos somadores.

- **Aplicações no Projeto de Circuitos:**
  - Construir somadores e subtratores utilizando os blocos aritméticos básicos.
  - Desenvolver circuitos comparadores para determinar relações de igualdade, maior ou menor entre números binários.
  - Preparar a transição do projeto teórico para a implementação prática em VHDL.

- **Complementos Extraídos do Livro:**
  - Explorar as vantagens do sistema **em complemento de 2** para operações aritméticas.
  - Discutir as estratégias para mitigar o tempo de propagação em somadores de múltiplos bits (por exemplo, empregando blocos com carry-lookahead em vez de ripple-carry).
  - Abordar a complexidade crescente dos circuitos conforme aumenta o número de bits.

---

## 2. Circuitos Somadores

### 2.1 Meio-Somador

O **meio-somador** é o circuito básico que soma dois bits sem levar em conta um possível *carry-in*. Ele possui:

- **Entradas:** A e B (1 bit cada)  
- **Saídas:**
  - **Soma (Σ):** Realizada pela operação **XOR** entre A e B.
  - **Carry-Out:** Obtido pela operação **AND** entre A e B.

#### Tabela Verdade – Meio-Somador

| A | B | Σ = A XOR B | Carry-Out = A AND B |
|:-:|:-:|:-----------:|:-------------------:|
| 0 | 0 |      0      |         0           |
| 0 | 1 |      1      |         0           |
| 1 | 0 |      1      |         0           |
| 1 | 1 |      0      |         1           |

> **Comentário:**  
> Conforme apresentado na aula, o meio-somador é o componente fundamental para a soma binária simples e define o funcionamento da operação “A XOR B” para a soma e “A AND B” para o carry.

---

### 2.2 Somador Completo

O **somador completo** amplia o meio-somador para incluir um terceiro sinal: o **carry-in** (*C_in*). Ele realiza a soma de três bits (A, B e Carry-in), produzindo:

- **Saída de Soma (Σ):**  
  Calculada por:  
  `Σ = A XOR B XOR C_in`

- **Carry-Out:**  
  Obtido pela expressão:  
  `Carry-Out = (A AND B) OR [(A XOR B) AND C_in]`

#### Tabela Verdade – Somador Completo

| A | B | C_in | Σ (Soma)  | Carry-Out |
|:-:|:-:|:----:|:---------:|:---------:|
| 0 | 0 |  0   |     0     |     0     |
| 0 | 0 |  1   |     1     |     0     |
| 0 | 1 |  0   |     1     |     0     |
| 0 | 1 |  1   |     0     |     1     |
| 1 | 0 |  0   |     1     |     0     |
| 1 | 0 |  1   |     0     |     1     |
| 1 | 1 |  0   |     0     |     1     |
| 1 | 1 |  1   |     1     |     1     |

> **Implementação:**  
> Uma forma prática de construir um somador completo é utilizando dois meio-somadores e uma porta OR, conforme demonstrado na aula. O primeiro meio-somador calcula uma soma parcial e o segundo incorpora o carry-in. Essa estrutura, amplamente usada, aparece também nos exemplos do livro, que destaca a importância do somador completo como bloco básico para unidades aritméticas (ALUs) em processadores.

---

### 2.3 Somador de N Bits (Ripple-Carry Adder)

Uma vez definidos o meio-somador e o somador completo, podemos construir um somador para números de múltiplos bits conectando vários somadores completos em cascata. Esse tipo de implementação é conhecido como **ripple-carry adder**.

- **Como funciona:**
  - O **carry-out** de cada estágio (bit menos significativo) é conectado diretamente ao **carry-in** do próximo estágio (bit seguinte).
  - A propagação do carry pode ocasionar um atraso significativo, proporcional ao número de bits somados.

> **Observação do Livro:**  
> Apesar de sua simplicidade, o ripple-carry adder tem uma desvantagem quanto à velocidade. Conforme o número de bits aumenta, o tempo total de propagação do sinal (carry) cresce linearmente, o que pode limitar o desempenho em sistemas de alta velocidade. Alternativas como o **carry-lookahead adder** são propostas para reduzir esses atrasos, embora impliquem em um aumento na complexidade do circuito.

---

## 3. Circuito Somador/Subtrator

Para construir um circuito que realize tanto a soma quanto a subtração, pode-se aproveitar o mesmo somador de N bits, alterando a forma de entrada dos bits do segundo operando (B):

- **Operação de Subtração com Complemento de 2:**
  - Quando o sinal de controle (geralmente denominado **ADD/SUB**) está ativo para subtração:
    - **Cada bit de B** é invertido utilizando uma porta **XOR** controlada pelo sinal.
    - Um **carry-in** extra (normalmente igual a 1) é aplicado ao bit menos significativo para formar o complemento de 2.
  - A subtração, portanto, é efetuada somando o complemento de 2 de B a A.

> **Complemento do Livro:**  
> O livro enfatiza que esta abordagem unifica as operações de soma e subtração no mesmo bloco aritmético, aproveitando a natureza do complemento de 2 que dispensa a necessidade de circuitos diferenciados para números positivos e negativos.

---

## 4. Comparadores

Os circuitos **comparadores** avaliam a relação entre dois números binários, determinando se são iguais, ou se um é maior ou menor que o outro.

### 4.1 Comparador de Igualdade

- **Construção:**
  - Use uma série de portas **XNOR** para comparar bit a bit os dois operandos.
  - As saídas dos XNOR são então conectadas a uma porta **AND** (ou a uma cadeia que verifique se todas são 1) para que a igualdade total seja confirmada.
  
- **Conceito:**  
  Se todos os bits comparados forem iguais (cada XNOR gera 1), o circuito indica que os números são iguais.

### 4.2 Comparador de Maior e Menor

- **Construção e Lógica:**
  - A comparação inicia pelo **bit mais significativo**:
    - Se o bit mais significativo de A for 1 e o de B for 0, A é maior que B; se ao contrário, B é maior.
  - Caso os bits mais significativos sejam iguais, procede-se a comparar os bits subsequentes até encontrar a primeira diferença.
  
> **Nota:**  
> Para circuitos com mais de um bit, esta comparação pode ser realizada de forma hierárquica, usando sub-circuitos que avaliam a igualdade e a ordem dos bits. O livro traz exemplos detalhados de comparadores de 4 bits e enfatiza a importância da otimização para reduzir o número de portas lógicas necessárias.

---

## 5. Integração de Conceitos e Implementação

Além dos aspectos teóricos, a aula também enfatiza a transição para a implementação prática usando linguagens de descrição de hardware como o **VHDL**. Ao combinar:

- **Somadores e Subtratores:**  
  Permite criar unidades de processamento aritmético (ALUs).

- **Comparadores:**  
  Essenciais para operações condicionais e fluxos de decisão em circuitos digitais.

> **Complemento do Livro:**  
> *Sistemas Digitais: Princípios e Aplicações* apresenta exemplos práticos e simulações que demonstram não somente o funcionamento dos blocos aritméticos individualmente, mas também a integração destes em sistemas complexos, ressaltando desafios como o tempo de propagação, consumo de energia e otimização do número de portas lógicas.

---

## 6. Implementações em VHDL

Esta seção apresenta exemplos de código VHDL para implementar os circuitos aritméticos discutidos teoricamente. Estas implementações podem ser utilizadas como ponto de partida para projetos práticos em dispositivos programáveis como FPGAs e CPLDs.

### 6.1 Meio-Somador (Half-Adder)

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity meio_somador is
    Port (
        a, b : in STD_LOGIC;          -- Entradas de 1 bit
        soma : out STD_LOGIC;         -- Resultado da soma
        carry_out : out STD_LOGIC     -- Carry de saída
    );
end meio_somador;

architecture comportamental of meio_somador is
begin
    -- Implementação direta das equações lógicas
    soma <= a XOR b;        -- Soma = A ⊕ B
    carry_out <= a AND b;   -- Carry = A · B
end comportamental;
```

### 6.2 Somador Completo (Full-Adder)

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity somador_completo is
    Port (
        a, b : in STD_LOGIC;          -- Bits a serem somados
        carry_in : in STD_LOGIC;      -- Carry de entrada
        soma : out STD_LOGIC;         -- Resultado da soma
        carry_out : out STD_LOGIC     -- Carry de saída
    );
end somador_completo;

architecture comportamental of somador_completo is
begin
    -- Implementação das equações lógicas do somador completo
    soma <= a XOR b XOR carry_in;
    carry_out <= (a AND b) OR ((a XOR b) AND carry_in);
end comportamental;

-- Implementação alternativa usando dois meio-somadores
architecture estrutural of somador_completo is
    component meio_somador is
        Port (
            a, b : in STD_LOGIC;
            soma : out STD_LOGIC;
            carry_out : out STD_LOGIC
        );
    end component;
    
    signal soma_parcial : STD_LOGIC;
    signal carry1, carry2 : STD_LOGIC;
begin
    -- Primeiro meio-somador: soma A e B
    HA1: meio_somador port map (
        a => a,
        b => b,
        soma => soma_parcial,
        carry_out => carry1
    );
    
    -- Segundo meio-somador: soma o resultado parcial com carry_in
    HA2: meio_somador port map (
        a => soma_parcial,
        b => carry_in,
        soma => soma,
        carry_out => carry2
    );
    
    -- O carry final é a OR dos carries parciais
    carry_out <= carry1 OR carry2;
end estrutural;
```

### 6.3 Somador de 4 bits (Ripple-Carry)

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity somador_4bits is
    Port (
        a, b : in STD_LOGIC_VECTOR(3 downto 0);   -- Operandos de 4 bits
        carry_in : in STD_LOGIC;                  -- Carry inicial
        soma : out STD_LOGIC_VECTOR(3 downto 0);  -- Resultado da soma
        carry_out : out STD_LOGIC                 -- Carry final
    );
end somador_4bits;

architecture estrutural of somador_4bits is
    -- Declaração do componente somador completo
    component somador_completo is
        Port (
            a, b, carry_in : in STD_LOGIC;
            soma, carry_out : out STD_LOGIC
        );
    end component;
    
    -- Sinais para interconexão dos carries entre os somadores
    signal c1, c2, c3 : STD_LOGIC;
begin
    -- Instância para o bit menos significativo (bit 0)
    FA0: somador_completo port map (
        a => a(0),
        b => b(0),
        carry_in => carry_in,
        soma => soma(0),
        carry_out => c1
    );
    
    -- Instância para o bit 1
    FA1: somador_completo port map (
        a => a(1),
        b => b(1),
        carry_in => c1,
        soma => soma(1),
        carry_out => c2
    );
    
    -- Instância para o bit 2
    FA2: somador_completo port map (
        a => a(2),
        b => b(2),
        carry_in => c2,
        soma => soma(2),
        carry_out => c3
    );
    
    -- Instância para o bit mais significativo (bit 3)
    FA3: somador_completo port map (
        a => a(3),
        b => b(3),
        carry_in => c3,
        soma => soma(3),
        carry_out => carry_out
    );
end estrutural;
```

### 6.4 Somador/Subtrator de 4 bits

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity somador_subtrator_4bits is
    Port (
        a, b : in STD_LOGIC_VECTOR(3 downto 0);     -- Operandos de 4 bits
        modo : in STD_LOGIC;                        -- 0: soma, 1: subtração
        resultado : out STD_LOGIC_VECTOR(3 downto 0); -- Resultado da operação
        carry_out : out STD_LOGIC;                  -- Carry/borrow final
        overflow : out STD_LOGIC                    -- Detecção de overflow
    );
end somador_subtrator_4bits;

architecture comportamental of somador_subtrator_4bits is
    component somador_4bits is
        Port (
            a, b : in STD_LOGIC_VECTOR(3 downto 0);
            carry_in : in STD_LOGIC;
            soma : out STD_LOGIC_VECTOR(3 downto 0);
            carry_out : out STD_LOGIC
        );
    end component;
    
    signal b_complementado : STD_LOGIC_VECTOR(3 downto 0);
    signal carry_final : STD_LOGIC;
    signal penultimo_carry, ultimo_carry : STD_LOGIC;
begin
    -- Complemento condicional de B para subtração
    -- Quando modo = '1', xor inverte os bits de B
    b_complementado(0) <= b(0) XOR modo;
    b_complementado(1) <= b(1) XOR modo;
    b_complementado(2) <= b(2) XOR modo;
    b_complementado(3) <= b(3) XOR modo;
    
    -- Instância do somador de 4 bits
    -- O carry_in recebe 'modo' para adicionar 1 na subtração (complemento de 2)
    ADDER: somador_4bits port map (
        a => a,
        b => b_complementado,
        carry_in => modo,
        soma => resultado,
        carry_out => carry_final
    );
    
    -- Atribuição do carry_out
    carry_out <= carry_final;
    
    -- Detecção de overflow para números com sinal:
    -- Ocorre quando soma dois números positivos e resulta negativo
    -- ou soma dois números negativos e resulta positivo
    overflow <= (a(3) AND b_complementado(3) AND NOT resultado(3)) OR
                (NOT a(3) AND NOT b_complementado(3) AND resultado(3));
end comportamental;
```

### 6.5 Comparadores

#### 6.5.1 Comparador de Igualdade de 4 bits

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity comparador_igualdade_4bits is
    Port (
        a, b : in STD_LOGIC_VECTOR(3 downto 0);  -- Números a serem comparados
        igual : out STD_LOGIC                    -- '1' se A = B, '0' caso contrário
    );
end comparador_igualdade_4bits;

architecture comportamental of comparador_igualdade_4bits is
    signal eq_bits : STD_LOGIC_VECTOR(3 downto 0);
begin
    -- Comparação bit a bit usando XNOR
    -- XNOR é '1' quando os bits são iguais
    eq_bits(0) <= a(0) XNOR b(0);
    eq_bits(1) <= a(1) XNOR b(1);
    eq_bits(2) <= a(2) XNOR b(2);
    eq_bits(3) <= a(3) XNOR b(3);
    
    -- A saída 'igual' é '1' apenas se todos os bits forem iguais
    igual <= eq_bits(0) AND eq_bits(1) AND eq_bits(2) AND eq_bits(3);
end comportamental;
```

#### 6.5.2 Comparador Completo de 4 bits (Maior, Menor, Igual)

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity comparador_completo_4bits is
    Port (
        a, b : in STD_LOGIC_VECTOR(3 downto 0);  -- Números a serem comparados
        maior : out STD_LOGIC;                   -- '1' se A > B
        igual : out STD_LOGIC;                   -- '1' se A = B
        menor : out STD_LOGIC                    -- '1' se A < B
    );
end comparador_completo_4bits;

architecture comportamental of comparador_completo_4bits is
    signal eq_bits : STD_LOGIC_VECTOR(3 downto 0);
begin
    -- Comparação de igualdade bit a bit
    eq_bits(0) <= a(0) XNOR b(0);
    eq_bits(1) <= a(1) XNOR b(1);
    eq_bits(2) <= a(2) XNOR b(2);
    eq_bits(3) <= a(3) XNOR b(3);
    
    -- Comparação de igualdade completa
    igual <= eq_bits(0) AND eq_bits(1) AND eq_bits(2) AND eq_bits(3);
    
    -- A > B se:
    -- 1. A(3) = 1 e B(3) = 0, ou
    -- 2. A(3) = B(3) e A(2) = 1 e B(2) = 0, ou
    -- 3. A(3) = B(3) e A(2) = B(2) e A(1) = 1 e B(1) = 0, ou
    -- 4. A(3) = B(3) e A(2) = B(2) e A(1) = B(1) e A(0) = 1 e B(0) = 0
    maior <= (a(3) AND NOT b(3)) OR 
             (eq_bits(3) AND a(2) AND NOT b(2)) OR
             (eq_bits(3) AND eq_bits(2) AND a(1) AND NOT b(1)) OR
             (eq_bits(3) AND eq_bits(2) AND eq_bits(1) AND a(0) AND NOT b(0));
    
    -- A < B se não é maior nem igual (complemento lógico)
    menor <= NOT (maior OR igual);
end comportamental;
```

### 6.6 Testbench para Somador/Subtrator

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.NUMERIC_STD.ALL;

entity tb_somador_subtrator is
end tb_somador_subtrator;

architecture simulacao of tb_somador_subtrator is
    -- Declaração do componente a ser testado
    component somador_subtrator_4bits is
        Port (
            a, b : in STD_LOGIC_VECTOR(3 downto 0);
            modo : in STD_LOGIC;
            resultado : out STD_LOGIC_VECTOR(3 downto 0);
            carry_out : out STD_LOGIC;
            overflow : out STD_LOGIC
        );
    end component;
    
    -- Sinais para interconexão com o testbench
    signal a_tb, b_tb, resultado_tb : STD_LOGIC_VECTOR(3 downto 0);
    signal modo_tb, carry_out_tb, overflow_tb : STD_LOGIC;
    
begin
    -- Instância do dispositivo sob teste (DUT)
    DUT: somador_subtrator_4bits port map (
        a => a_tb,
        b => b_tb,
        modo => modo_tb,
        resultado => resultado_tb,
        carry_out => carry_out_tb,
        overflow => overflow_tb
    );
    
    -- Processo de estímulos
    processo_estimulo: process
    begin
        -- Teste 1: Soma sem carry (3 + 2 = 5)
        a_tb <= "0011";  -- 3 em decimal
        b_tb <= "0010";  -- 2 em decimal
        modo_tb <= '0';  -- Modo soma
        wait for 10 ns;
        
        -- Teste 2: Soma com carry (9 + 8 = 17, carry=1, resultado=1)
        a_tb <= "1001";  -- 9 em decimal
        b_tb <= "1000";  -- 8 em decimal
        modo_tb <= '0';  -- Modo soma
        wait for 10 ns;
        
        -- Teste 3: Subtração sem borrow (7 - 3 = 4)
        a_tb <= "0111";  -- 7 em decimal
        b_tb <= "0011";  -- 3 em decimal
        modo_tb <= '1';  -- Modo subtração
        wait for 10 ns;
        
        -- Teste 4: Subtração com borrow (3 - 7 = -4)
        a_tb <= "0011";  -- 3 em decimal
        b_tb <= "0111";  -- 7 em decimal
        modo_tb <= '1';  -- Modo subtração
        wait for 10 ns;
        
        -- Teste 5: Soma que causa overflow (7 + 2 = 9, mas interpretado como -7 em complemento de 2)
        a_tb <= "0111";  -- 7 em decimal
        b_tb <= "0010";  -- 2 em decimal
        modo_tb <= '0';  -- Modo soma
        wait for 10 ns;
        
        wait; -- Encerra a simulação
    end process processo_estimulo;
end simulacao;
```

> **Nota sobre as Implementações:**  
> Os exemplos de código VHDL apresentados seguem os princípios discutidos na parte teórica do documento e são sintetizáveis para implementação em dispositivos programáveis reais. Para projetos mais complexos, pode-se explorar técnicas adicionais de otimização como carry-lookahead adders ou utilizar blocos aritméticos especializados disponíveis em FPGAs modernas.

---

## 7. Conclusão Final

A implementação em VHDL dos circuitos aritméticos estudados permite a transição da teoria para a prática, possibilitando a simulação e a posterior síntese em dispositivos programáveis. Os exemplos apresentados demonstram como os conceitos fundamentais são traduzidos em código HDL, tendo em vista aspectos como:

- **Modularidade:** A criação de componentes reutilizáveis (meio-somador, somador completo) que podem ser instanciados em designs mais complexos.
- **Hierarquia:** A estruturação do código em níveis (como no somador de 4 bits que utiliza múltiplas instâncias de somadores completos).
- **Diferentes Arquiteturas:** Implementações alternativas para o mesmo circuito, destacando a flexibilidade do VHDL.

Estes exemplos servem como base para o desenvolvimento de unidades aritméticas mais sofisticadas, incluindo multiplicadores, divisores e unidades de ponto flutuante, fundamentais para o projeto de processadores e sistemas digitais avançados.

---

## Bibliografia

- **Vídeo Aula:**  
  [Circuitos Digitais - Circuitos Aritméticos (YouTube)](https://www.youtube.com/watch?v=kPD7Aw1SrdY&t=1040s)  
  *UNIVESP – Engenharia de Computação, Curso de Circuitos Digitais (2020.1)*

- **Livro:**  
  Tocci, R. J., Widmer, N. S. & Moss, G. L. (2011). *Sistemas Digitais: Princípios e Aplicações.* São Paulo: Pearson Prentice Hall.

---

## Conclusão

Nesta aula, exploramos os blocos fundamentais que compõem os circuitos aritméticos em sistemas digitais: o meio-somador, o somador completo, os somadores de múltiplos bits (ripple-carry), os circuitos somador/subtrator e os comparadores. Além disso, os conceitos extraídos da literatura especializada ampliam a compreensão sobre os desafios (como tempo de propagação e complexidade de circuito) e as estratégias de otimização empregadas em projetos reais. Na próxima etapa, abordaremos a implementação prática desses circuitos em VHDL, levando a teoria para a prática em dispositivos programáveis.

---