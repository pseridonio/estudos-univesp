# Resumo da Aula: Circuitos Digitais – Portas Lógicas e Descrição de Circuitos

Nesta aula, além de conhecermos as principais portas lógicas e suas representações, é enfatizada a metodologia completa de **descrição e implementação de circuitos lógicos**. A seguir, temos duas partes:

1. **Portas Lógicas** – conceitos básicos e aplicações imediatas (conforme o vídeo).
2. **Descrição de Circuitos Lógicos** – fundamentos teóricos e metodológicos extraídos dos capítulos 3.1 a 3.9 do livro.

---

## 1. Portas Lógicas Apresentadas

### 1.1 Porta Inversora (NOT)
- **Conceito:** Inverte o valor lógico da entrada.
- **Tabela Verdade:**

  | A | S (= NOT A) |
  |---|-------------|
  | 0 | 1           |
  | 1 | 0           |

- **Representações:**
  - Símbolo: Triângulo com um círculo na extremidade.
  - Expressão: S = ¬A
  - Implementação CMOS: Utiliza um transistor PMOS e outro NMOS.

---

### 1.2 Porta E (AND)
- **Conceito:** A saída é 1 somente se todas as entradas forem 1.
- **Tabela Verdade (para 2 entradas):**

  | A | B | S (A AND B) |
  |---|---|-------------|
  | 0 | 0 | 0           |
  | 0 | 1 | 0           |
  | 1 | 0 | 0           |
  | 1 | 1 | 1           |

- **Expressão:** S = A · B

---

### 1.3 Porta OU (OR)
- **Conceito:** A saída é 1 se pelo menos uma das entradas estiver em 1.
- **Tabela Verdade (para 2 entradas):**

  | A | B | S (A OR B) |
  |---|---|------------|
  | 0 | 0 | 0          |
  | 0 | 1 | 1          |
  | 1 | 0 | 1          |
  | 1 | 1 | 1          |

- **Expressão:** S = A + B

---

### 1.4 Porta NE (NAND)
- **Conceito:** Combinação da operação AND seguida de inversão.
- **Tabela Verdade (para 2 entradas):**

  | A | B | S (NAND)  |
  |---|---|-----------|
  | 0 | 0 | 1         |
  | 0 | 1 | 1         |
  | 1 | 0 | 1         |
  | 1 | 1 | 0         |

- **Observação:** A porta NAND é considerada universal, podendo ser utilizada para implementar outras funções lógicas.

---

### 1.5 Porta NOU (NOR)
- **Conceito:** Combinação da operação OR seguida de inversão.
- **Tabela Verdade (para 2 entradas):**

  | A | B | S (NOR)   |
  |---|---|-----------|
  | 0 | 0 | 1         |
  | 0 | 1 | 0         |
  | 1 | 0 | 0         |
  | 1 | 1 | 0         |

- **Observação:** Assim como a NAND, a porta NOR também é considerada universal.

---

### 1.6 Porta OU-EXCLUSIVO (XOR) e Porta NOU-EXCLUSIVO (XNOR)
- **XOR:**
  - **Conceito:** A saída é 1 quando as entradas possuem valores diferentes.
  - **Expressão:** S = A ⊕ B ou, alternativamente, S = A'B + AB'
- **XNOR:**
  - **Conceito:** Complemento do XOR; a saída é 1 quando as entradas são iguais.
  - **Expressão:** S = (A ⊕ B)' ou S = A·B + A'·B'

---

## 2. Descrição de Circuitos Lógicos (Capítulos 3.1 a 3.9)

### 2.1 Capítulo 3.1 – Constantes e Variáveis Booleanas
- **Conceito:**  
  Introdução aos fundamentos do sistema binário;
  - **Constantes Booleanas:** os valores 0 e 1.
  - **Variáveis Booleanas:** elementos que podem assumir 0 ou 1, essenciais para a modelagem dos circuitos.

---

### 2.2 Capítulo 3.2 – Tabelas-Verdade
- **Definição:**  
  Lista de todas as combinações possíveis dos valores das entradas e suas respectivas saídas.
- **Utilidade:**  
  Essencial para determinar e validar o comportamento de qualquer circuito lógico.

---

### 2.3 Capítulo 3.3 – Operações OR com Porta OR
- **Detalhes:**  
  - **Funcionamento:** a saída é 1 se pelo menos uma entrada for 1.
  - **Expressão:** S = A + B.
  - **Aplicação:** Usada na implementação de funções que dependem da presença de pelo menos um sinal lógico alto.

---

### 2.4 Capítulo 3.4 – Operação AND com Porta AND
- **Detalhes:**
  - **Funcionamento:** a saída é 1 somente quando todas as entradas estão em nível 1.
  - **Expressão:** S = A · B.
  - **Aplicação:** Base para funções que requerem condições “tudo ou nada”.

---

### 2.5 Capítulo 3.5 – Operação NOT (Inversão)
- **Detalhes:**
  - **Conceito:** inverte o sinal de uma entrada; se A = 1, então NOT A = 0, e vice-versa.
  - **Importância:** fundamental para a construção de funções lógicas mais complexas, inclusive para as portas NAND e NOR.

---

### 2.6 Capítulo 3.6 – Descrevendo Circuitos Lógicos Algebricamente
- **Objetivo:**  
  Representar o comportamento dos circuitos utilizando expressões Booleanas.
- **Técnicas:**
  - Expressões na forma **Soma-de-Produtos (SOP)**
  - Expressões na forma **Produto-de-Somas (POS)**
- **Exemplo:**  
  Uma função lógica representada por S = A'B + AB' descreve o comportamento de uma porta XOR.

---

### 2.7 Capítulo 3.7 – Avaliando as Saídas dos Circuitos Lógicos
- **Processo:**
  - Analisar a tabela verdade ou expressões Booleanas para determinar a saída de um circuito.
  - Importante para validar projetos e garantir que todas as combinações de entrada produzem a saída desejada.

---

### 2.8 Capítulo 3.8 – Implementando Circuitos a Partir de Expressões Booleanas
- **Etapas:**
  1. **Desenvolvimento da Expressão Lógica:** Formular a função desejada em termos de variáveis Booleanas.
  2. **Mapeamento para Portas Lógicas:** Selecionar e interligar as portas necessárias (AND, OR, NOT etc.).
  3. **Montagem do Circuito:** Organizar o arranjo físico das portas para reproduzir a função lógica.

---

### 2.9 Capítulo 3.9 – Portas NOR e Portas NAND
- **Pontos-Chave:**
  - **Universalidade:**  
    Ambas podem ser combinadas para formar qualquer outra função lógica, eliminando a necessidade de múltiplos tipos de portas.
  - **Apresentação:**  
    Tabelas-verdade e diagramas ilustram seu funcionamento e integração em circuitos mais complexos.

---

## Conclusão

Este resumo integra os fundamentos práticos das portas lógicas, conforme o vídeo, com uma base teórica aprofundada proveniente dos capítulos 3.1 a 3.9 do livro *Sistemas Digitais: Princípios e Aplicações*. Os conceitos aqui abordados são essenciais não só para a compreensão do funcionamento dos circuitos digitais como também para a implementação e simplificação de funções lógicas em projetos de engenharia.

---

## Bibliografia

- **Tocci, R. J., Widmer, N. S., & Moss, G. L.** (2011). *Sistemas Digitais: Princípios e Aplicações* (11ª ed.). São Paulo: Pearson Prentice Hall. ISBN: 978-85-4300-694-9.  
  Disponível em: [Sistemas Digitais: Princípios e Aplicações](https://www.kufunda.net/publicdocs/Sistemas%20Digitais%20Princ%C3%ADpios%20e%20Aplica%C3%A7%C3%B5es%20(Ronald%20J.%20Tocci,%20Neal%20S.%20Widmer%20etc.).pdf)