# Simulação de Circuitos — Somadores

## Introdução
Material baseado na videoaula da disciplina de Circuitos Digitais (transcrição do vídeo usada como fonte principal) para ensinar a modelagem e simulação de somadores em HDL, desde meio‑somador até somadores de múltiplos bits (ripple‑carry), incluindo observações sobre atraso, verificação por simulação e exemplos em VHDL para uso prático em ambiente de simulação.

## Desenvolvimento

### Meio‑somador: definição, lógica e simulação
- **Definição:** circuito que soma dois bits A e B e produz **Σ** (soma de bit) e **Cout** (carry out).  
- **Equações:**  
  - Σ = A XOR B  
  - Cout = A AND B  
- **Explicação das variáveis:** A, B = entradas (bits); Σ = bit de resultado no peso atual; Cout = bit de transporte para o próximo peso.  
- **Exemplo passo a passo e simulação:** para A=1 e B=1: Σ = 1 XOR 1 = 0; Cout = 1 AND 1 = 1. Em uma simulação funcional, observe as formas de onda dos sinais Σ e Cout quando A e B transitam nos instantes de estímulo para validar as expressões lógicas implementadas em VHDL.  

VHDL (meio‑somador — versão por portas):
```vhdl
library IEEE; use IEEE.STD_LOGIC_1164.ALL;
entity HalfAdder is port(A,B: in std_logic; SUM, COUT: out std_logic); end HalfAdder;
architecture RTL of HalfAdder is begin
  SUM  <= A xor B;
  COUT <= A and B;
end RTL;
```
Teste por simulação: aplique vetor de testes (00,01,10,11) e verifique Σ/Cout nas formas de onda; documente timestamps de transição e compare com a tabela‑verdade (validações típicas em aulas e slides).

### Somador completo: construção, expressão e simulação
- **Definição:** soma A, B e Cin; produz Σ e Cout.  
- **Equações principais:**  
  - Σ = A xor B xor Cin  
  - Cout = (A·B) + (A·Cin) + (B·Cin)  
- **Implementação estrutural via dois meio‑somadores:**  
  1. S1 = A xor B; C1 = A and B  
  2. Σ = S1 xor Cin; C2 = S1 and Cin  
  3. Cout = C1 or C2  
- **Exemplo com simulação:** A=1, B=1, Cin=1 → S1=0,C1=1; Σ=1,C2=0; Cout=1. Simule com estímulos para Cin variando em sincronia e verifique propagação e timming nos sinais intermediários S1, C1, C2 antes de considerar o resultado final.

VHDL (full adder estrutural reusando half‑adder):
```vhdl
library IEEE; use IEEE.STD_LOGIC_1164.ALL;
entity FullAdder is port(A,B,Cin: in std_logic; SUM,Cout: out std_logic); end FullAdder;
architecture Struct of FullAdder is
  signal S1, C1, C2: std_logic;
  component HalfAdder port(A,B: in std_logic; SUM,COUT: out std_logic); end component;
begin
  HA1: HalfAdder port map(A => A, B => B, SUM => S1, COUT => C1);
  HA2: HalfAdder port map(A => S1, B => Cin, SUM => SUM, COUT => C2);
  Cout <= C1 or C2;
end Struct;
```
Simule e inspecione sinais intermediários (S1, C1, C2) para validar a decomposição estrutural e identificar eventuais hazards nos níveis lógicos.

### Somador paralelo (ripple‑carry): montagem e análise de atraso
- **Topologia:** encadeamento de N full adders; Cout_i → Cin_{i+1}.  
- **Atraso crítico:** tempo total cresce aproximadamente linear com N porque cada estágio aguarda o carry anterior; fórmula prática: t_total ≈ N·t_FA (onde t_FA é atraso de um full adder).  
- **Simulação de atraso:** ao simular um ripple adder, gere vetores de testes que causem propagação máxima (por exemplo, cadeias que forçam carry a atravessar todos os estágios) e meça o tempo entre aplicação dos vetores e estabilização das saídas MSB para estimar o atraso real no modelo de porta usado.

Exemplo VHDL — ripple adder de 4 bits (esquema):
- Descrever entidade com A,B: std_logic_vector(3 downto 0); Cin: std_logic; SUM: std_logic_vector(3 downto 0); Cout: std_logic.  
- Use generate para instanciar 4 FullAdder e mapear carries intermediários; simule casos onde carries propagam através de todos os estágios para verificar atraso acumulado conforme exemplificado em material didático.

### Verificação por simulação: estratégias e testes
- **Banco de testes (testbench):** aplicar vetores exaustivos para N pequeno ou vetores selecionados para cobrir casos críticos: sem carry, com carry localizado, com carry propagado por todos os bits, casos de overflow (em complemento de 2) e casos de subtração via complemento.  
- **Observáveis:** sinais intermediários (S1, C1...), tempos de estabilização, ocorrência de glitches, e checagem automática dos resultados esperados por assert/checkers no testbench. Ferramentas típicas e fluxo de simulação são discutidos em guias de laboratório e slides de cursos sobre VHDL/FPGA.

### Boas práticas em modelagem e síntese
- Use atribuições combinacionais concisas para funções lógicas simples; reuso estrutural (component/port map) ajuda a organizar designs maiores e facilita depuração por sinais intermediários nas simulações.  
- Evite inferir latches acidentalmente; descreva lógica combinacional com atribuições em processos sensíveis a sinais apropriados ou com atribuições concorrentes. Valide a inferência observando o relatório de síntese e a netlist gerada pela ferramenta.

## Conclusão
Somadores são blocos fundamentais; a simulação é essencial para validar lógica funcional e temporização. Meio‑somador e full adder são blocos reutilizáveis; somadores paralelos (ripple) são simples de implementar mas apresentam atraso linear que deve ser observado em simulação e, se necessário, mitigado por arquiteturas mais rápidas (tema complementar).

## Exercícios (com resolução passo a passo)

1. Exercício — meio‑somador
   - Enunc.: Escreva VHDL do meio‑somador e simule para todos os vetores de entrada.  
   - Resolução: código apresentado na seção; simulação: (00 → SUM=0,COUT=0), (01 → 1,0), (10 → 1,0), (11 → 0,1). Documente timestamps e verifique coincidência com tabela‑verdade.

2. Exercício — full adder estrutural
   - Enunc.: Instancie dois half‑adders para obter um full adder e simule com A=1,B=1,Cin=1.  
   - Resolução passo a passo: HA1: S1=0,C1=1; HA2: Σ=1,C2=0; Cout=C1 or C2 = 1. Verifique sinais S1,C1,C2 no testbench para confirmar decomposição.

3. Exercício — ripple adder 4 bits (propagação máxima)
   - Enunc.: Modele ripple adder de 4 bits; simule A=1111, B=0001, Cin=0; meça tempo até SUM[3] estabilizar.  
   - Resolução: resultado SUM = 0000, Cout = 1; observe que carry se propaga por todos os estágios; registre atraso observado e compare com soma de atrasos de FAs conforme estimativa t_total ≈ 4·t_FA.

4. Exercício — subtração via complemento de 2 usando somador único
   - Enunc.: Descreva em VHDL um bloco que, quando SUB='1', inverte B via XOR e coloca Cin=SUB para realizar A−B; simule A=0101,B=0011,SUB=1.  
   - Resolução passo a passo: B_xor <= B xor (others => SUB); Cin <= SUB; somador(A,B_xor,Cin) → resultado esperado 0010 (2). Verifique nas formas de onda e valide bits de overflow se aplicável.

## Bibliografia (ABNT)
- UNIVESP. Circuitos Digitais - Simulação de Circuitos III. Vídeo aula (YouTube). Professor André Ricardo Fioravanti. UNIVESP; 3 nov. 2021. Acesso em: 20 out. 2025.  
- VIEIRA, A. et al. VHDL_3_MC_Circ_Arit_v1. Instituto de Computação, UNICAMP. Disponível em: https://www.ic.unicamp.br/~cortes/mc602/slides/VHDL/VHDL_3_MC_Circ_Arit_v1.pdf. Acesso em: 20 out. 2025.  
- JOHANN. lab07adder. Universidade Federal do Rio Grande do Sul (UFRGS). Disponível em: https://www.inf.ufrgs.br/~johann/circuitos/lab07adder.pdf. Acesso em: 20 out. 2025.  
- EMBARCADOS. Somador Completo no Tutorial de Verilog. Disponível em: https://embarcados.com.br/tutorial-de-verilog-somador-completo/. Acesso em: 20 out. 2025.

## Materiais complementares
- TOCCI, R. J.; WIDMER, N. S.; MOSS, G. L. Sistemas digitais: princípios e aplicações. 12. ed. São Paulo: Pearson, 2018. (consultar capítulos sobre aritmética e somadores).  
- GUNTZEL, J. Circuitos de Armazenamento. UFSC. Disponível em: https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf. Acesso em: 20 out. 2025.  
- Tutoriais online e slides de laboratório citados na bibliografia para exemplos de testbench, synth reports e análise de atraso em diferentes ferramentas CAD/VHDL (Quartus, ModelSim, GHDL).

---

Se desejar, eu gero agora: (a) o testbench VHDL completo para o ripple adder de 4 bits com vetores de estímulo e checks automáticos; (b) um diagrama ASCII dos FAs encadeados; ou (c) um relatório comparando atrasos ripple vs estimativa teórica usando parâmetros de porte — escolha uma opção.