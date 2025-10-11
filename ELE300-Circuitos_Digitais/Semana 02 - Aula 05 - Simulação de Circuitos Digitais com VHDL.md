# Simulação de Circuitos Digitais com VHDL

## Introdução

Nesta aula, iniciamos a prática de simulação de circuitos digitais utilizando linguagens de descrição de hardware, com foco na linguagem VHDL. A simulação permite validar o comportamento lógico de um circuito antes de sua implementação física, sendo uma etapa essencial no desenvolvimento de sistemas digitais.

## Desenvolvimento

### 🧠 O que é uma Linguagem de Descrição de Hardware (HDL)?

Uma HDL ("Hardware Description Language") é uma linguagem textual usada para descrever o funcionamento, estrutura e comportamento de circuitos digitais. Ela permite:

- Definir a interface do circuito (entradas e saídas).
- Especificar a lógica interna.
- Simular e testar o circuito antes da implementação física.

As principais linguagens HDL são:

- **VHDL** (VHSIC Hardware Description Language)
- **Verilog**
- **SystemVerilog**

Neste curso, utilizamos **VHDL** por sua robustez e padronização.

---

### 📜 Histórico da VHDL

- Desenvolvida pelo Departamento de Defesa dos EUA nos anos 1980.
- Criada para documentar projetos do programa VHSIC (Very High Speed Integrated Circuits).
- Padronizada pelo IEEE (Institute of Electrical and Electronics Engineers).
- Usada amplamente por engenheiros e fabricantes de ferramentas de desenvolvimento de hardware.

---

### 🧩 Estrutura de um Código VHDL

Um código VHDL é composto por dois blocos principais:

#### 1. ENTITY (Entidade)

Define a interface do circuito: nome, entradas e saídas.

**Exemplo:**
```vhdl
ENTITY circuito01 IS
  PORT (
    A, B, C : IN STD_LOGIC;
    Y       : OUT STD_LOGIC
  );
END circuito01;
```

- `ENTITY`: palavra-chave que inicia o bloco.
- `PORT`: define os sinais de entrada e saída.
- `STD_LOGIC`: tipo de sinal lógico padrão.

#### 2. ARCHITECTURE (Arquitetura)

Define o comportamento interno do circuito.

**Exemplo:**
```vhdl
ARCHITECTURE comportamento OF circuito01 IS
  SIGNAL M : STD_LOGIC;
BEGIN
  M <= A AND B;
  Y <= M OR C;
END comportamento;
```

- `SIGNAL`: define sinais internos (não visíveis externamente).
- `BEGIN`: inicia a descrição funcional.
- `AND`, `OR`: operadores lógicos.

---

### 🔧 Simulação com Quartus/ModelSim

A simulação é feita com ferramentas como:

- **Intel Quartus Prime**
- **ModelSim**
- **Xilinx Vivado**
- **GHDL**

Neste curso, utilizamos **Quartus/ModelSim**.

#### Etapas da simulação:

1. Criar projeto e nomear a entidade principal.
2. Criar arquivo VHDL com a descrição do circuito.
3. Realizar análise e síntese para verificar erros de sintaxe.
4. Criar canais de entrada para teste.
5. Definir formas de onda para sinais de entrada.
6. Executar a simulação e verificar o comportamento da saída.

---

### 🧪 Exemplo de Simulação

**Circuito descrito:**
- Entradas: A, B, C
- Saída: Y
- Sinal intermediário: M = A AND B
- Saída Y = M OR C

**Resultado da simulação:**
- Y está em nível lógico alto quando:
  - C está em nível alto, ou
  - A e B estão simultaneamente em nível alto

✅ Isso valida o comportamento esperado do circuito.

---

## Conclusão

A simulação de circuitos digitais com VHDL é uma ferramenta poderosa para validar projetos antes da implementação física. Com a definição clara da entidade e arquitetura, é possível testar o comportamento lógico e corrigir erros de forma eficiente. O uso de ferramentas como Quartus e ModelSim facilita esse processo, tornando-o acessível e confiável.

---

## Análise Crítica

A aula apresenta com clareza os fundamentos da linguagem VHDL e sua aplicação prática. A explicação sobre a estrutura ENTITY/ARCHITECTURE é bem detalhada, e o exemplo de simulação reforça o aprendizado. Seria interessante incluir mais exemplos com diferentes tipos de lógica e explorar simulações com sinais temporais.

---

## Sugestões de Complementação

- Introduzir simulações com sinais temporizados (clock).
- Apresentar exemplos com lógica sequencial (flip-flops).
- Demonstrar uso de bibliotecas e pacotes VHDL.
- Explorar ferramentas alternativas como GHDL e Vivado.

---

## Exercícios (com resolução detalhada)

### 1. Escreva um código VHDL para um circuito com duas entradas A e B e uma saída Y = A AND B.

**Solução:**
```vhdl
ENTITY circuito02 IS
  PORT (
    A, B : IN STD_LOGIC;
    Y    : OUT STD_LOGIC
  );
END circuito02;

ARCHITECTURE comportamento OF circuito02 IS
BEGIN
  Y <= A AND B;
END comportamento;
```

---

### 2. Modifique o circuito anterior para que Y = A AND B OR C.

**Solução:**
```vhdl
ENTITY circuito03 IS
  PORT (
    A, B, C : IN STD_LOGIC;
    Y       : OUT STD_LOGIC
  );
END circuito03;

ARCHITECTURE comportamento OF circuito03 IS
  SIGNAL M : STD_LOGIC;
BEGIN
  M <= A AND B;
  Y <= M OR C;
END comportamento;
```

---

### 3. Descreva o comportamento esperado da saída Y para as seguintes entradas:

| A | B | C | M = A AND B | Y = M OR C |
|---|---|---|-------------|------------|
| 0 | 0 | 0 | 0           | 0          |
| 0 | 1 | 0 | 0           | 0          |
| 1 | 1 | 0 | 1           | 1          |
| 0 | 0 | 1 | 0           | 1          |

---

## Bibliografia

- TOCCI, Ronald J.; WIDMER, Neal S.; MOSS, Gregory L. *Sistemas digitais: princípios e aplicações*. 11. ed. São Paulo: Pearson Prentice Hall, 2011.
- GUNTZEL, J. *Circuitos de Armazenamento*. Disponível em: [inf.ufsc.br](https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf). Acesso em: 10 out. 2025.
- FIORAVANTI, André Ricardo. *Circuitos Digitais – Simulação de Circuitos I*. YouTube, 2021. Disponível em: [YouTube](https://www.youtube.com/watch?v=zSZryTGc6Fs). Acesso em: 10 out. 2025.

---

## Materiais Complementares

- Livro: TOCCI, Ronald J.; WIDMER, Neal S.; MOSS, Gregory L. *Sistemas digitais: princípios e aplicações*. 11. ed. São Paulo: Pearson Prentice Hall, 2011.
- PDF: GUNTZEL, J. *Circuitos de Armazenamento*. Disponível em: [inf.ufsc.br](https://www.inf.ufsc.br/~j.guntzel/isd/isd5.pdf). Acesso em: 10 out. 2025.
- Sites confiáveis utilizados:
  - [Intel Quartus Prime](https://www.intel.com/content/www/us/en/software/programmable/quartus-prime/overview.html). Acesso em: 10 out. 2025.
  - [ModelSim – Mentor Graphics](https://www.mentor.com/products/fv/modelsim/). Acesso em: 10 out. 2025.

---  

