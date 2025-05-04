# Representação de Números com Sinal e Aritmética Binária

Este documento reúne as principais informações sobre como representar números com sinal e executar operações aritméticas em binário. A abordagem integra o conteúdo visto na aula com os aprofundamentos extraídos do livro *Sistemas Digitais: Princípios e Aplicações* (Tocci, Widmer & Moss, 2011), oferecendo uma visão mais abrangente e prática dos conceitos.

---

## Objetivos da Aula

- **Compreender os métodos de representação de números com sinal**  
  - Comparar os sistemas de sinal‑magnitute, complemento de 1 e complemento de 2.
  - Analisar as vantagens e limitações de cada abordagem.
  - Reconhecer a importância de um intervalo simétrico ou assimétrico (por exemplo, para um sistema com *n* bits, a representação em complemento de 2 vai de –2^(n–1) até 2^(n–1)–1).

- **Realizar operações aritméticas em binário**  
  - Executar soma e subtração considerando a presença do carry ou borrow, respectivamente.
  - Implementar a multiplicação por meio do deslocamento e soma dos parciais.

- **Aplicar estratégias de detecção de erro em circuitos digitais**  
  - Uso de flags como **carry-out** e **overflow** para identificar quando o resultado ultrapassa os limites do sistema.

> **Complemento (do livro):**  
> A obra ressalta que o sistema de complemento de 2 é o método preferido para representações de números com sinal em sistemas digitais modernos, justamente por sua simplicidade na implementação das operações aritméticas e pela representação única do zero.

---

## 1. Operações Aritméticas Básicas

### 1.1 Soma Binária

- **Regras Básicas (sem Carry-In):**
  - 0 + 0 = 0  (carry-out = 0)
  - 0 + 1 ou 1 + 0 = 1  (carry-out = 0)
  - 1 + 1 = 0  (carry-out = 1)
  
- **Com Carry-In:**
  - O bit adicional influencia o resultado de cada coluna, mantendo a mesma lógica.

> **Complemento (do livro):**  
> O livro enfatiza que as operações em complemento de 2 precisam observar cuidadosamente o *overflow*. Em circuitos aritméticos, a comparação entre o carry gerado na entrada e na saída do bit de sinal é essencial para garantir que o resultado esteja dentro do intervalo representável.

#### Exemplo Prático: Soma de +23 e -12 (em complemento de 2 – 8 bits)

1. **Representação dos operandos:**  
   - **+23:**  
     Em 8 bits:  
     `00010111`  
     (23 = 16 + 4 + 2 + 1)
     
   - **-12:**  
     Primeiro, represente +12:  
     `00001100`  
     Gera o complemento de 1:  
     `11110011`  
     Adiciona 1 para obter o complemento de 2:  
     `11110100`

2. **Execução da soma:**  

   ```
     00010111   (+23)
   + 11110100   (-12)
   -----------
     00001011   (+11)   → Despreza-se o carry extra
   ```

   **Interpretação:**  
   O resultado `00001011` corresponde a +11, confirmando que 23 + (–12) = 11.

---

### 1.2 Subtração Binária

- **Abordagem Lógica:**
  - A subtração em sistemas digitais é frequentemente implementada convertendo a operação em uma soma: subtrai-se somando o complemento (para números em complemento de 2).
  - A operação requer o tratamento de *borrow*, que é naturalmente acomodado quando utilizamos a soma em complemento de 2.

> **Complemento (do livro):**  
> Ao converter a subtração para uma operação de adição (através do complemento do subtraendo), é possível utilizar o mesmo circuito somador. Essa abordagem unifica o tratamento de números positivos e negativos e simplifica a lógica do circuito.

#### Exemplo Prático: Subtração de 7 - 12 (em complemento de 2 – 8 bits)

1. **Representação dos operandos:**  
   - **7:**  
     Em 8 bits:  
     `00000111`
     
   - **12:**  
     Em 8 bits:  
     `00001100`  
     Para obter –12, calcula-se o complemento de 2:  
     - Inverter bits: `11110011`  
     - Adicionar 1: `11110100`

2. **Reescrevendo a subtração como soma:**  
   7 – 12 = 7 + (–12)

3. **Realizando a soma:**  

   ```
     00000111   (7)
   + 11110100   (-12)
   -----------
     11111011   (Resultado em complemento de 2)
   ```

4. **Verificação:**  
   Para interpretar `11111011`, inverta os bits e adicione 1:  
   - Inverter: `00000100`  
   - Adicionar 1: `00000101` → 5 em decimal  
   Portanto, o resultado representa –5, o que confirma que 7 – 12 = –5.

---

### 1.3 Multiplicação Binária

- **Método de Deslocamento e Soma:**  
  A multiplicação binária pode ser realizada através da técnica de deslocamento (shift) e soma de parciais. Em sistemas que utilizam números em complemento de 2, é importante garantir a extensão do sinal (sign extension) ao realizar os deslocamentos, principalmente quando os números possuem sinal.

> **Complemento (do livro):**  
> Apesar de a ênfase geralmente ser em projetos dos circuitos aritméticos de soma e subtração, a multiplicação em sistemas digitais – mesmo quando envolvem números com sinal – baseia-se em deslocamentos e somas de parciais. Essa técnica é fundamental para a implementação de unidades aritméticas (ALUs) em processadores modernos.

#### Exemplo Prático: Multiplicação de -3 × 4 (em complemento de 2 – 8 bits)

1. **Representação dos Operandos:**  
   - **-3:**  
     Para 3 em 8 bits:  
     `00000011`  
     → Inverter para obter o complemento de 1: `11111100`  
     → Adicionar 1 para o complemento de 2: `11111101`
     
   - **4:**  
     Em 8 bits (positivo):  
     `00000100`

2. **Processo de Multiplicação por Deslocamento e Soma:**  
   Como o multiplicador (4) possui um único bit 1 na posição 2 (contando a partir do bit 0), o algoritmo de shift-and-add produz apenas um parcial:
   
   - **Partial Product:**  
     Desloca-se o multiplicando (-3) 2 posições à esquerda (equivalente a multiplicar por 2² = 4).  
     Deslocamento de `11111101` (–3) em 2 bits:  
     → Resultado: `11110100`
     
3. **Interpretação do Resultado:**  
   O valor `11110100` em complemento de 2 (8 bits) representa –12.  
   *Verificação:*  
   - Inverter `11110100`: `00001011`  
   - Adicionar 1: `00001100` → 12 em decimal  
   → Sendo o MSB 1, o resultado é negativo, logo –12.  
   
   Assim, –3 × 4 = –12, conforme esperado.

---

## 2. Representações de Números com Sinal

### 2.1 Sinal‑Magnitude

- **Definição:**
  - O bit mais significativo (MSB) identifica o sinal (0 para positivo e 1 para negativo) e os demais bits representam a magnitude.
- **Limitações:**
  - Representação dupla para o zero (“+0” e “–0”).
  - Operações aritméticas exigem lógica diferenciada para tratar o bit de sinal.

> **Complemento (do livro):**  
> Apesar de ser intuitiva, a forma sinal‑magnitute acarreta complexidade na implementação de operações aritméticas, pois o circuito precisa tratar de forma especial o bit de sinal.

---

### 2.2 Complemento de 1

- **Definição:**
  - Números positivos são representados normalmente.
  - Para números negativos, obtém-se a representação invertendo (complementando) todos os bits do número positivo.
- **Desvantagens:**
  - Mantém a duplicidade na representação do zero.

> **Complemento (do livro):**  
> Embora reduza alguns problemas da representação sinal‑magnitute, o complemento de 1 não elimina a ambiguidade do zero.

---

### 2.3 Complemento de 2

- **Definição e Vantagens:**
  - Para números negativos, inverte-se todos os bits do número positivo e adiciona-se 1.
  - Permite que o mesmo circuito (somador) trate números positivos e negativos.
  - Garante a representação única para o zero.
  
- **Exemplo (em 8 bits):**
  - Intervalo representável: de –128 a +127.
  - Para representar –23:  
    1. +23 em binário: `00010111`  
    2. Inverter os bits: `11101000`  
    3. Adicionar 1: `11101001`

> **Complemento (do livro):**  
> O complemento de 2 é a escolha preferida para sistemas digitais por permitir uma implementação eficiente das unidades aritméticas e facilitar a detecção de overflow.

---

## 3. Operações com Números em Complemento de 2

- **Execução das Operações:**
  - Soma e subtração podem ser realizadas diretamente, tratando números negativos como seus complementos.
  - Subtrair um número equivale a somar seu complemento.

- **Mecanismos de Detecção de Erros:**
  - **Carry-Out:**  
    Indica que a soma excedeu os bits disponíveis (principalmente útil para números sem sinal).
  - **Overflow:**  
    Detectado quando dois números do mesmo sinal geram um resultado com sinal diferente.
    
> **Complemento (do livro):**  
> A verificação do carry entre o penúltimo e o último bit (relacionado ao sinal) é crucial para identificar um overflow, garantindo que o valor obtido esteja dentro do intervalo permitido.

---

## 4. Implementação em Circuitos

- **Circuitos Aritméticos Básicos:**
  - **Somador/Subtrator:**  
    Utiliza circuitos como o meio-somador e o somador completo (*full-adder*) para agregar bits e propagar o carry.
  - **Exemplo Prático:**  
    A implementação de um somador ripple-carry encadeia vários full-adders para operações em múltiplos bits.
    
- **Uso de Linguagens de Descrição de Hardware (HDL):**
  - Linguagens como VHDL permitem descrever, simular e sintetizar os circuitos aritméticos.
  - Facilita a implementação prática dos conceitos em dispositivos programáveis (PLDs).

> **Complemento (do livro):**  
> As seções dedicadas aos HDLs exemplificam o projeto de circuitos aritméticos, como uma ALU, utilizando VHDL – integrando os conceitos teóricos e as técnicas modernas de design digital.

---

## 5. Exemplos de Código VHDL

Esta seção apresenta implementações práticas em VHDL dos conceitos de aritmética binária e representação de números com sinal vistos anteriormente.

### 5.1 Somador/Subtrator de 8 bits com Detecção de Overflow

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity somador_subtrator_8bits is
    Port (
        a, b : in STD_LOGIC_VECTOR(7 downto 0);    -- Operandos de entrada
        op : in STD_LOGIC;                         -- 0 para soma, 1 para subtração
        resultado : out STD_LOGIC_VECTOR(7 downto 0); -- Resultado da operação
        overflow : out STD_LOGIC;                  -- Flag de overflow
        carry_out : out STD_LOGIC                  -- Carry out da operação
    );
end somador_subtrator_8bits;

architecture Behavioral of somador_subtrator_8bits is
    signal b_complemento : STD_LOGIC_VECTOR(7 downto 0);
    signal soma_tmp : STD_LOGIC_VECTOR(8 downto 0);
    signal a_ext, b_ext : STD_LOGIC_VECTOR(8 downto 0);
begin
    -- Complemento de 2 condicional para operação de subtração
    b_complemento <= not b + 1 when op = '1' else b;
    
    -- Extensão de sinal para cálculos internos
    a_ext <= a(7) & a;
    b_ext <= b_complemento(7) & b_complemento;
    
    -- Operação de soma
    soma_tmp <= a_ext + b_ext;
    
    -- Resultado da operação
    resultado <= soma_tmp(7 downto 0);
    
    -- Carry out (útil para operações com números sem sinal)
    carry_out <= soma_tmp(8);
    
    -- Detecção de overflow para números com sinal:
    -- Ocorre quando dois números do mesmo sinal produzem um resultado de sinal diferente
    overflow <= '1' when 
        ((a(7) = b_complemento(7)) and (a(7) /= soma_tmp(7))) 
        else '0';
end Behavioral;
```

### 5.2 Full-Adder (Somador Completo)

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity full_adder is
    Port (
        a, b : in STD_LOGIC;       -- Bits a serem somados
        cin : in STD_LOGIC;        -- Carry in
        sum : out STD_LOGIC;       -- Resultado da soma
        cout : out STD_LOGIC       -- Carry out
    );
end full_adder;

architecture Behavioral of full_adder is
begin
    sum <= a xor b xor cin;
    cout <= (a and b) or (cin and (a xor b));
end Behavioral;
```

### 5.3 Somador Ripple-Carry de 8 bits

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity ripple_carry_adder is
    Port (
        a, b : in STD_LOGIC_VECTOR(7 downto 0);
        cin : in STD_LOGIC;
        sum : out STD_LOGIC_VECTOR(7 downto 0);
        cout : out STD_LOGIC
    );
end ripple_carry_adder;

architecture Behavioral of ripple_carry_adder is
    component full_adder is
        Port (
            a, b, cin : in STD_LOGIC;
            sum, cout : out STD_LOGIC
        );
    end component;
    
    signal carry : STD_LOGIC_VECTOR(8 downto 0);
begin
    carry(0) <= cin;
    
    -- Conexão em cascata de full-adders
    gen_adders: for i in 0 to 7 generate
        fa_i: full_adder port map (
            a => a(i),
            b => b(i),
            cin => carry(i),
            sum => sum(i),
            cout => carry(i+1)
        );
    end generate;
    
    cout <= carry(8);
end Behavioral;
```

### 5.4 Multiplicador Binário (Shift-and-Add)

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.NUMERIC_STD.ALL;

entity multiplicador_4bits is
    Port (
        a, b : in STD_LOGIC_VECTOR(3 downto 0);   -- Operandos de 4 bits
        produto : out STD_LOGIC_VECTOR(7 downto 0) -- Resultado de 8 bits
    );
end multiplicador_4bits;

architecture Behavioral of multiplicador_4bits is
    -- Sinais para armazenar produtos parciais
    type parciais_array is array (0 to 3) of unsigned(7 downto 0);
    signal parciais : parciais_array;
begin
    process(a, b)
        variable a_unsigned : unsigned(7 downto 0);
    begin
        -- Extensão do sinal de a para 8 bits
        a_unsigned := "0000" & unsigned(a);
        
        -- Calcula os produtos parciais
        for i in 0 to 3 loop
            if b(i) = '1' then
                -- Desloca 'a' i posições à esquerda quando o bit correspondente em 'b' é 1
                parciais(i) <= shift_left(a_unsigned, i);
            else
                parciais(i) <= (others => '0');
            end if;
        end loop;
        
        -- Soma todos os produtos parciais
        produto <= std_logic_vector(parciais(0) + parciais(1) + parciais(2) + parciais(3));
    end process;
end Behavioral;
```

### 5.5 Conversor de Complemento de 2

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity conversor_complemento2 is
    Port (
        entrada : in STD_LOGIC_VECTOR(7 downto 0);   -- Número em complemento de 2
        saida : out STD_LOGIC_VECTOR(7 downto 0);    -- Valor convertido
        negativo : out STD_LOGIC                     -- Indicador de valor negativo
    );
end conversor_complemento2;

architecture Behavioral of conversor_complemento2 is
    signal valor_absoluto : STD_LOGIC_VECTOR(7 downto 0);
begin
    -- Se o bit mais significativo é 1, o número é negativo
    negativo <= entrada(7);
    
    -- Para valores negativos, calculamos o complemento de 2
    -- Para valores positivos, mantemos o valor original
    process(entrada)
    begin
        if entrada(7) = '1' then
            valor_absoluto <= (not entrada) + 1;  -- Complemento de 2
        else
            valor_absoluto <= entrada;
        end if;
    end process;
    
    saida <= valor_absoluto;
end Behavioral;
```

> **Nota sobre os Exemplos:**  
> Os códigos VHDL acima demonstram a implementação prática dos conceitos de representação de números com sinal e operações aritméticas. Em um ambiente de desenvolvimento real, esses códigos podem ser simulados e sintetizados para dispositivos programáveis como FPGAs ou CPLDs.

### 5.6 Testbench para o Somador/Subtrator

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.NUMERIC_STD.ALL;

entity somador_subtrator_tb is
end somador_subtrator_tb;

architecture Behavioral of somador_subtrator_tb is
    -- Componente a ser testado
    component somador_subtrator_8bits
        Port (
            a, b : in STD_LOGIC_VECTOR(7 downto 0);
            op : in STD_LOGIC;
            resultado : out STD_LOGIC_VECTOR(7 downto 0);
            overflow : out STD_LOGIC;
            carry_out : out STD_LOGIC
        );
    end component;
    
    -- Sinais para o testbench
    signal a_tb, b_tb, resultado_tb : STD_LOGIC_VECTOR(7 downto 0);
    signal op_tb, overflow_tb, carry_out_tb : STD_LOGIC;
    
begin
    -- Instância do módulo a ser testado
    UUT: somador_subtrator_8bits port map (
        a => a_tb,
        b => b_tb,
        op => op_tb,
        resultado => resultado_tb,
        overflow => overflow_tb,
        carry_out => carry_out_tb
    );
    
    -- Processo de estímulos
    stimulus: process
    begin
        -- Teste 1: Soma de dois números positivos (23 + 12 = 35)
        a_tb <= "00010111";  -- +23
        b_tb <= "00001100";  -- +12
        op_tb <= '0';        -- Soma
        wait for 10 ns;
        
        -- Teste 2: Soma de positivo e negativo (23 + (-12) = 11)
        a_tb <= "00010111";  -- +23
        b_tb <= "11110100";  -- -12 (em complemento de 2)
        op_tb <= '0';        -- Soma
        wait for 10 ns;
        
        -- Teste 3: Subtração (7 - 12 = -5)
        a_tb <= "00000111";  -- +7
        b_tb <= "00001100";  -- +12
        op_tb <= '1';        -- Subtração
        wait for 10 ns;
        
        -- Teste 4: Testa overflow (120 + 20 = 140, que excede 127 para 8 bits)
        a_tb <= "01111000";  -- +120
        b_tb <= "00010100";  -- +20
        op_tb <= '0';        -- Soma
        wait for 10 ns;
        
        -- Finaliza simulação
        wait;
    end process;
end Behavioral;
```

---

## Bibliografia

- **Vídeo Aula:**  
  [Circuitos Digitais - Representação de Números com Sinal e Aritmética Binária (YouTube)](https://www.youtube.com/watch?v=MyD2-GWd6kM)  
  *UNIVESP – Curso de Circuitos Digitais (2020.1)*

- **Livro:**  
  Tocci, R. J., Widmer, N. S. & Moss, G. L. (2011). *Sistemas Digitais: Princípios e Aplicações* (11ª ed.). São Paulo: Pearson Prentice Hall.
