# Circuitos Digitais – Simulação de Circuitos Sequenciais

Nesta aula, o professor aborda a modelagem, implementação e simulação de um circuito sequencial por meio do exemplo de um circuito “árbitro” para acesso a um recurso compartilhado. O circuito é descrito com base em uma máquina de estados do tipo Moore, demonstrando como os estados e transições são definidos, como a lógica é simplificada e, por fim, como o circuito é implementado em VHDL e validado por simulação.

---

## 1. Introdução

- **Contexto Geral:**  
  Circuitos sequenciais possuem memória, com seus estados definidos por entradas e atualizados em eventos de clock (síncronos). Esta característica é explorada para projetar controladores e dispositivos de lógica sequencial.

- **Objetivos da Aula:**  
  - Descrever os requisitos do projeto de um circuito sequencial via máquina de estados.  
  - Projetar o circuito usando diagramas de transição e tabelas de estados.  
  - Obter expressões simplificadas das funções lógicas (flip-flop e saídas) com base em mapas de Karnaugh.  
  - Implementar o circuito em VHDL (usando abordagens estrutural/fluxo de dados e comportamental).  
  - Validar o projeto por meio de simulação funcional, analisando os diagramas de tempo.

---

## 2. Caso de Estudo – Circuito ÁRBITRO de Recurso Compartilhado

- **Cenário:**  
  Imagine um sistema onde um recurso (por exemplo, um canal de comunicação) deve ser compartilhado entre três dispositivos. Cada dispositivo sinaliza sua necessidade de acesso através de um sinal de requisição (R1, R2 e R3). Por outro lado, o circuito “árbitro” fornece permissões de acesso por meio dos sinais de saída (G1, G2 e G3).

- **Prioridade:**  
  - Quando mais de um dispositivo solicita o recurso, o dispositivo 1 tem prioridade máxima, seguido pelo dispositivo 2 e, por fim, pelo dispositivo 3.  
  - O estado “L ZERO” indica que nenhum dispositivo possui o recurso (recurso disponível).  
  - Estados “L1”, “L2” e “L3” indicam que os dispositivos 1, 2 ou 3, respectivamente, possuem o recurso.

---

## 3. Modelagem por Máquina de Estados

### 3.1 Diagrama de Transição de Estados

- **Representação Gráfica:**  
  - **Nós (Estados):**  
    • L ZERO: Estado inicial, recurso livre.  
    • L1, L2, L3: Estados em que o recurso está alocado ao dispositivo 1, 2 ou 3, respectivamente.
  - **Transições:**  
    As setas indicam a mudança de estado com base nas requisições (entradas R1, R2, R3).  
    - Exemplo: Se em L ZERO o sinal R1 estiver ativo, a máquina transita para L1 imediatamente.

### 3.2 Tabela de Transição de Estados

Uma tabela de transição resume as condições para cada mudança de estado. Por exemplo:

| Estado Atual | Condição (Requisições)           | Próximo Estado | Comentário                            |
|--------------|----------------------------------|----------------|---------------------------------------|
| L ZERO       | R1 = 1 (independente dos demais) | L1             | Dispositivo 1 tem prioridade          |
| L ZERO       | R1 = 0, R2 = 1                   | L2             | Dispositivo 2 recebe o recurso         |
| L ZERO       | R1 = 0, R2 = 0, R3 = 1            | L3             | Dispositivo 3 recebe o recurso         |
| L1, L2, L3   | Requisição encerrada (R = 0)      | L ZERO       | Retorna ao estado inicial              |

> **Nota:** A tabela completa é construída considerando todas as condições de permanência e transição dos estados, respeitando a prioridade.

### 3.3 Simplificação por Mapas de Karnaugh

- **Objetivo:**  
  A partir da tabela de transição, as expressões para as entradas dos flip-flops (por exemplo, DX e DY) e para as saídas (G1, G2, G3) são simplificadas utilizando mapas de Karnaugh de cinco variáveis.
- **Importante:**  
  As expressões obtidas demonstram que, por se tratar de uma máquina de Moore, as saídas dependem apenas dos estados atuais e não diretamente das entradas.

---

## 4. Implementação do Circuito em VHDL

O professor apresenta duas abordagens na implementação:

### 4.1 Descrição Estrutural/Fluxo de Dados

- **Entidade e Portas:**  
  A entidade possui:
  - Entradas: CLOCK, RESET, R1, R2, R3 (sinais de 1 bit)  
  - Saídas: G1, G2, G3 (sinais de 1 bit)
- **Blocos Implementados:**  
  - Dois flip-flops do tipo D (para armazenar o estado atual, representado por sinais como X e Y).  
  - A utilização da diretiva `PORT MAP` para conectar os sinais intermediários e implementar a aquisição dos estados.

### 4.2 Descrição Comportamental

- **Estratégia Comum:**  
  São utilizados dois processos em VHDL:
  1. **Processo Síncrono:**  
     - Sensível ao CLOCK e RESET.  
     - Atualiza o estado atual com base no estado futuro.
  2. **Processo Combinacional:**  
     - Calcula o próximo estado a partir do estado atual e dos sinais de entrada (R1, R2, R3).  
     - Determina também o valor das saídas (G1, G2 e G3) conforme as regras da máquina de Moore.
- **Observação:**  
  Essa separação torna a implementação mais modular e facilita a síntese e verificação.

---

## 5. Simulação Funcional

### 5.1 Diagrama de Timing

- **Visualização:**  
  Durante a simulação, observa-se no diagrama de tempo (waveform) as seguintes características:
  - **Bordas de Clock:**  
    Destacadas por linhas vermelhas, que determinam os momentos de atualização dos flip-flops.
  - **Estados Iniciais:**  
    Inicialmente o circuito está em “L ZERO” (após RESET).
  - **Transições:**  
    Conforme os sinais R1, R2 e R3 variam, o sistema transita para os estados L1, L2 ou L3, de acordo com a prioridade definida.
  - **Retorno ao Estado Inicial:**  
    Ao cessar a necessidade (quando os sinais de requisição voltam a zero), o circuito retorna ao estado “L ZERO”.

### 5.2 Validação do Projeto

- **Propósito da Simulação:**  
  Verificar se todas as transições e regras definidas no diagrama e na tabela de estados são respeitadas.  
- **Comprovante:**  
  O diagrama de timing demonstrado durante a simulação confirma que o circuito funciona conforme o esperado, proporcionando a concessão do recurso com base nas prioridades e retornando ao estado inicial quando apropriado.

---

## 6. Conclusão e Reflexões

- **Resumo Geral:**  
  A aula reforça o caminho metodológico do projeto de circuitos sequenciais:
  1. Partir de uma especificação – neste caso, o circuito árbitro para um recurso compartilhado.
  2. Modelar o comportamento por meio de diagramas de estados e tabelas de transição.
  3. Simplificar as expressões lógicas utilizando técnicas como mapas de Karnaugh.
  4. Implementar a solução em VHDL (tanto de forma estrutural quanto comportamental).
  5. Validar o projeto por meio de simulação funcional e análise de diagramas de timing.
  
- **Aplicações Práticas:**  
  Este método é amplamente utilizado na síntese de circuitos para controladores, módulos em sistemas embarcados e na automação industrial, onde a correta sincronização e o gerenciamento de estados são cruciais.

- **Dicas para Aprofundamento:**  
  - Experimente modificar os cenários (por exemplo, alterando a prioridade ou adicionando novos dispositivos) para observar o impacto na máquina de estados.  
  - Investigue ferramentas de simulação, como Quartus II, Vivado ou ModelSim, para praticar a validação dos seus projetos.  
  - Explore a diferença entre modelagens estruturais e comportamentais em VHDL, entendendo as vantagens e limitações de cada abordagem.

---

## 7. Implementação do Circuito ÁRBITRO em VHDL

A seguir, apresentamos a implementação do circuito "árbitro" para acesso a um recurso compartilhado, utilizando VHDL. O circuito é baseado em uma máquina de estados do tipo Moore, conforme descrito na aula.

### 7.1 Descrição Comportamental

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity arbitro is
    Port (
        clk : in STD_LOGIC;          -- Sinal de clock
        reset : in STD_LOGIC;        -- Sinal de reset
        r1, r2, r3 : in STD_LOGIC;   -- Sinais de requisição
        g1, g2, g3 : out STD_LOGIC   -- Sinais de permissão
    );
end arbitro;

architecture comportamental of arbitro is
    -- Definição dos estados
    type state_type is (L_ZERO, L1, L2, L3);
    signal current_state, next_state : state_type;
begin
    -- Processo síncrono para atualizar o estado atual
    process(clk, reset)
    begin
        if reset = '1' then
            current_state <= L_ZERO; -- Estado inicial
        elsif rising_edge(clk) then
            current_state <= next_state;
        end if;
    end process;

    -- Processo combinacional para determinar o próximo estado e as saídas
    process(current_state, r1, r2, r3)
    begin
        -- Valores padrão
        next_state <= L_ZERO;
        g1 <= '0';
        g2 <= '0';
        g3 <= '0';

        case current_state is
            when L_ZERO =>
                if r1 = '1' then
                    next_state <= L1;
                elsif r2 = '1' then
                    next_state <= L2;
                elsif r3 = '1' then
                    next_state <= L3;
                else
                    next_state <= L_ZERO;
                end if;

            when L1 =>
                g1 <= '1'; -- Permissão para o dispositivo 1
                if r1 = '0' then
                    next_state <= L_ZERO;
                else
                    next_state <= L1;
                end if;

            when L2 =>
                g2 <= '1'; -- Permissão para o dispositivo 2
                if r2 = '0' then
                    next_state <= L_ZERO;
                else
                    next_state <= L2;
                end if;

            when L3 =>
                g3 <= '1'; -- Permissão para o dispositivo 3
                if r3 = '0' then
                    next_state <= L_ZERO;
                else
                    next_state <= L3;
                end if;

            when others =>
                next_state <= L_ZERO;
        end case;
    end process;
end comportamental;
```

### 7.2 Descrição Estrutural

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity arbitro_estrutural is
    Port (
        clk : in STD_LOGIC;          -- Sinal de clock
        reset : in STD_LOGIC;        -- Sinal de reset
        r1, r2, r3 : in STD_LOGIC;   -- Sinais de requisição
        g1, g2, g3 : out STD_LOGIC   -- Sinais de permissão
    );
end arbitro_estrutural;

architecture estrutural of arbitro_estrutural is
    -- Definição dos estados codificados em 2 bits
    signal state : STD_LOGIC_VECTOR(1 downto 0);
    signal next_state : STD_LOGIC_VECTOR(1 downto 0);

    -- Constantes para os estados
    constant L_ZERO : STD_LOGIC_VECTOR(1 downto 0) := "00";
    constant L1 : STD_LOGIC_VECTOR(1 downto 0) := "01";
    constant L2 : STD_LOGIC_VECTOR(1 downto 0) := "10";
    constant L3 : STD_LOGIC_VECTOR(1 downto 0) := "11";
begin
    -- Processo síncrono para atualizar o estado atual
    process(clk, reset)
    begin
        if reset = '1' then
            state <= L_ZERO;
        elsif rising_edge(clk) then
            state <= next_state;
        end if;
    end process;

    -- Processo combinacional para determinar o próximo estado
    process(state, r1, r2, r3)
    begin
        case state is
            when L_ZERO =>
                if r1 = '1' then
                    next_state <= L1;
                elsif r2 = '1' then
                    next_state <= L2;
                elsif r3 = '1' then
                    next_state <= L3;
                else
                    next_state <= L_ZERO;
                end if;

            when L1 =>
                if r1 = '0' then
                    next_state <= L_ZERO;
                else
                    next_state <= L1;
                end if;

            when L2 =>
                if r2 = '0' then
                    next_state <= L_ZERO;
                else
                    next_state <= L2;
                end if;

            when L3 =>
                if r3 = '0' then
                    next_state <= L_ZERO;
                else
                    next_state <= L3;
                end if;

            when others =>
                next_state <= L_ZERO;
        end case;
    end process;

    -- Processo combinacional para determinar as saídas
    process(state)
    begin
        g1 <= '0';
        g2 <= '0';
        g3 <= '0';

        case state is
            when L1 =>
                g1 <= '1';
            when L2 =>
                g2 <= '1';
            when L3 =>
                g3 <= '1';
            when others =>
                null;
        end case;
    end process;
end estrutural;
```

### 7.3 Testbench para o Circuito ÁRBITRO

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity tb_arbitro is
end tb_arbitro;

architecture testbench of tb_arbitro is
    -- Declaração do componente a ser testado
    component arbitro is
        Port (
            clk : in STD_LOGIC;
            reset : in STD_LOGIC;
            r1, r2, r3 : in STD_LOGIC;
            g1, g2, g3 : out STD_LOGIC
        );
    end component;

    -- Sinais para interconexão
    signal clk_tb, reset_tb, r1_tb, r2_tb, r3_tb : STD_LOGIC;
    signal g1_tb, g2_tb, g3_tb : STD_LOGIC;
begin
    -- Instância do DUT (Device Under Test)
    DUT: arbitro port map (
        clk => clk_tb,
        reset => reset_tb,
        r1 => r1_tb,
        r2 => r2_tb,
        r3 => r3_tb,
        g1 => g1_tb,
        g2 => g2_tb,
        g3 => g3_tb
    );

    -- Geração do clock
    clk_process: process
    begin
        clk_tb <= '0';
        wait for 10 ns;
        clk_tb <= '1';
        wait for 10 ns;
    end process;

    -- Estímulos de teste
    stimulus_process: process
    begin
        -- Reset inicial
        reset_tb <= '1';
        r1_tb <= '0'; r2_tb <= '0'; r3_tb <= '0';
        wait for 20 ns;
        reset_tb <= '0';

        -- Requisição do dispositivo 1
        r1_tb <= '1'; wait for 40 ns;
        r1_tb <= '0'; wait for 20 ns;

        -- Requisição do dispositivo 2
        r2_tb <= '1'; wait for 40 ns;
        r2_tb <= '0'; wait for 20 ns;

        -- Requisição do dispositivo 3
        r3_tb <= '1'; wait for 40 ns;
        r3_tb <= '0'; wait for 20 ns;

        -- Fim da simulação
        wait;
    end process;
end testbench;
```

> **Nota:**  
> O código acima implementa o circuito "árbitro" em VHDL, utilizando tanto a abordagem comportamental quanto estrutural. O testbench permite simular o comportamento do circuito, verificando as transições de estado e as saídas de permissão (G1, G2, G3) com base nas requisições (R1, R2, R3).

---

## 8. Bibliografia

1. **UNIVESP – Engenharia de Computação | Circuitos Digitais (2020.1).**  
   *Circuitos Digitais - Simulação de Circuitos V.* Disponível em: [YouTube: Circuitos Digitais - Simulação de Circuitos V](https://www.youtube.com/watch?v=vptxbsQtCmU&ab_channel=UNIVESP)
2. **Tocci, R. J., Widmer, N. S. & Moss, G. L. (2011).**  
   *Sistemas Digitais: Princípios e Aplicações*. São Paulo: Pearson Prentice Hall. Disponível em: [Pearson Education do Brasil](https://www.pearson.com/brasil)
3. **Mano, M. M. (2013).**  
   *Digital Design*. São Paulo: Pearson.
4. **Intel FPGA Documentation.**  
   Disponível em: [https://www.intel.com/content/www/us/en/programmable/documentation.html](https://www.intel.com/content/www/us/en/programmable/documentation.html)
5. **All About Circuits.**  
   Disponível em: [https://www.allaboutcircuits.com](https://www.allaboutcircuits.com)

