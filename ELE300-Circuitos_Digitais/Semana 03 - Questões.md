## Pergunta

Considere o seguinte código VHDL:  

```vhdl
ENTITY Circuito is  
PORT(a,b    : IN  STD_LOGIC;  
     y      : OUT STD_LOGIC);  
END Circuito;  

ARCHITECTURE Functional OF Circuito IS  
BEGIN  
    in_bits <= a & b;  
    WITH in_bits SELECT  
        y <= '1' WHEN "00",  
             '0' WHEN "01",  
             '0' WHEN "10",  
             '1' WHEN "11",  
END Functional  
```

 
A porta lógica com entradas a e b, e saída y, descrita pelo código VHDL, é:  
a. NOR.  
b. OR.  
c. XOR.  
d. XNOR.  
e. NAND.

### Resposta
d. XNOR.

### Motivo
O selecione zera y para as combinações "01" e "10" e define y = '1' para "00" e "11". Isso significa que y = 1 exatamente quando a e b têm o mesmo valor (ambos 0 ou ambos 1), que é a definição funcional da operação XNOR (equivalência lógica). Em termos booleanos, y = a ⊙ b (ou y = a XNOR b) = (a·b) + (a'·b').

---  

### Pergunta
Cada uma das entradas de uma porta NOR de 2 entradas recebe um pulso. Na primeira entrada, um pulso vai para nível ALTO em t = 0 e retorna para nível BAIXO em t = 1 ms. Na segunda entrada, o pulso vai para nível ALTO em t = 0,8 ms e retorna para nível BAIXO em t = 3 ms. Assumindo tempo de propagação nulo, o pulso de saída ao longo do tempo, inicialmente ALTO em t < 0:

a. vai para nível BAIXO em t = 0,8 ms e retorna para nível ALTO em t = 3 ms.  
b. vai para nível BAIXO em t = 0,8 ms e retorna para nível ALTO em t = 1 ms.  
c. vai para nível BAIXO em t = 0 e retorna para nível ALTO em t = 3 ms.  
d. vai para nível ALTO em t = 0,8 ms e retorna para nível BAIXO em t = 1 ms.  
e. vai para nível BAIXO em t = 0 e permanece em nível BAIXO durante todo o período.

### Resposta
c. vai para nível BAIXO em t = 0 e retorna para nível ALTO em t = 3 ms.

### Motivo
A saída de uma porta NOR de 2 entradas é y = NOT(a OR b). Inicialmente (t < 0) ambas as entradas estão em 0, logo y = 1 (ALTO).  
- Em t = 0 a primeira entrada sobe para 1 → (a OR b) = 1 → y = 0. Assim a saída já vai para BAIXO em t = 0.  
- Em t = 0,8 ms a segunda entrada também sobe para 1, mas isso não muda o fato de que (a OR b) já era 1, então y permanece 0.  
- Em t = 1 ms a primeira entrada volta a 0, porém a segunda ainda está em 1 (até t = 3 ms), então (a OR b) continua sendo 1 e y continua 0.  
- Só em t = 3 ms, quando a segunda entrada retorna a 0 e ambas entradas ficam 0, (a OR b) = 0 e portanto y = 1 (retorna a ALTO).

Com tempo de propagação nulo, todas essas mudanças são refletidas instantaneamente na saída, portanto o intervalo em que a saída fica BAIXO é de t = 0 até t = 3 ms.

---  
### Pergunta
 Considere a seguinte tabela-verdade:  
  
 | A | B | X |
 |---|---|---|---|
 | 0 | 0 | 1 |
 | 0 | 1 | 1 |
 | 1 | 0 | 1 |
 | 1 | 1 | 0 | 
  
 A porta lógica com entradas A e B, e saída X, descrita pela tabela-verdade é:  
 a. XNOR  
 b. OR  
 c. NAND  
 d. XOR  
 e. NOR

### Resposta
c. NAND

### Motivo
A saída X vale 1 para todas as combinações de entradas exceto quando A = 1 e B = 1, quando X = 0. Essa é exatamente a verdade-função da porta NAND, cuja tabela é: NAND(A,B) = NOT(A AND B) — ou seja, somente quando ambas as entradas são 1 a saída é 0; em todos os outros casos a saída é 1. As outras alternativas não batem com essa tabela: OR e XOR teriam saídas 0 em (0,0), XNOR seria 1 em (0,0) e (1,1) (não condiz) e NOR seria 1 apenas em (0,0). Portanto a correspondência correta é NAND.

--- 

### Pergunta
 Um multiplexador (usualmente referenciado de maneira abreviada como “mux”) é um circuito combinatório — portanto, de saídas exclusivamente dependentes das entradas — que atua de forma a rotear para uma única saída informações das mais diversas entradas. Para um mux, existem duas especificações principais, sendo uma delas o número de entradas.  
  
 Assinale a alternativa que corresponde à descrição correta da outra especificação em questão.  
  
 a. Origem da informação.  
 b. Tamanho das entradas.  
 c. Potência de saída.  
 d. Capacidade de escoamento.  
 e. Custo de produção.

### Resposta
b. Tamanho das entradas.

### Motivo
Além do número de linhas de entrada (quantas fontes o mux pode selecionar), a outra especificação essencial de um multiplexador é quantos bits cada entrada tem — ou seja, a largura dos sinais de entrada (tamanho do "bus" ou vetor que é roteado). Um mux pode selecionar entre, por exemplo, 4 entradas de 1 bit (mux 4:1 1‑bit) ou 4 entradas de 8 bits (mux 4:1 8‑bit); essa largura define quantos bits são roteados simultaneamente para a saída e é requisito fundamental para projetar a lógica e a interface com outros blocos. As demais alternativas (origem da informação, potência de saída, capacidade de escoamento, custo de produção) não são especificações padrão usadas para caracterizar funcionalmente um mux em lógica digital.

---

### Pergunta
Os circuitos com capacidade de detectar a presença de uma dada combinação de valores (portanto, expressa de forma codificada) de suas entradas é denominado “decodificador”. Na mais usual de suas formas, o decodificador dispõe de n entradas que se relacionam a uma quantidade equivalente a 2ⁿ saídas — de toda forma, apenas uma saída fica destacada por vez. Outra característica que lhe é peculiar é dispor de um sinal de enable, que se destina a determinada função.  
 
Assinale a alternativa que corresponde à descrição correta da função do sinal de enable.  
a. Habilitar ou desabilitar o funcionamento.  
b. Prover o devido aterramento elétrico.  
c. Resetar a memória do equipamento.  
d. Servir de fonte de alimentação extra.  
e. Transmitir mensagens cifradas.

### Resposta
a. Habilitar ou desabilitar o funcionamento.

### Motivo
O sinal "enable" é um controle lógico que ativa ou desativa a operação do bloco: quando enable = 1 (ou nível ativo definido), o decodificador realiza sua função normal e uma das 2ⁿ saídas é selecionada conforme as entradas; quando enable = 0 (nível inativo), o decodificador é desabilitado e normalmente força todas as saídas a um estado inativo (por exemplo, todas zero ou todas zero exceto uma, conforme projeto). As demais alternativas descrevem funções elétricas ou de sistema que não correspondem ao propósito lógico e de controle do sinal enable.

--- 

### Pergunta
Considere a seguinte função booleana, dada a partir de seus mintermos e estados de don’t care  
 
G(X,Y,Z) = Σm(5,6) + ΣD(1,2,4)  
 
Quais das expressões a seguir podem ser utilizadas para implementar corretamente G?  
 
I. Z̅ + X̅ Y Z  
II. X ( Y̅ + Z̅ )  
III. X Y̅ + Y̅ Z  
IV. Y̅ Z + Y Z̅  
 
a. II e IV apenas.  
b. II apenas.  
c. IV apenas.  
d. II, III e IV apenas.  
e. I, II, III e IV.

### Resposta
a. II e IV apenas.

### Motivo
- A função requerida tem 1s obrigatórios em m5 (101) e m6 (110). Os mintermos m1, m2 e m4 são "don’t care" e podem ser tratados como 0 ou 1 para facilitar a simplificação, mas não podem forçar 1s em mintermos que não pertencem a {1,2,4,5,6}. Os mintermos restantes (0,3,7) devem ser 0.

- Verificação das expressões:
  - I (Z̅ + X̅ Y Z) simplifica: Z̅ + X̅ Y Z = Z̅ + (Z·X̅ Y) = Z̅ + Z·(X̅ Y) = Z̅ + Z·(...) = Z̅ + Z = 1? Na verdade Z̅ + Z = 1, mas atenção: algebraicamente Z̅ + Z·K = Z̅ + Z·K = Z̅ + Z·K = Z̅ + Z·K = Z̅ + Z·K. Using consensus, Z̅ + Z·K = Z̅ + Z·K = Z̅ + Z·K = Z̅ + Z·K — o termo não reduz para Z nem para 1 automaticamente; avaliando em minterm m6 (110) onde Z=0 → Z̅=1 → I = 1, mas m6 precisa ser 1 (ok); porém em m5 (101) Z=1 → Z̅=0 e X̅ Y Z =0 (pois X̅=0) → I=0, mas m5 requer 1 → falha. Assim I é inválida.
  - II X (Y̅ + Z̅) = X·(¬(Y·Z)) = X·(Y⊙Z)' . Avaliando m5 (101): X=1, Y̅+Z̅ = 1+0 =1 → saída 1; m6 (110): X=1, Y̅+Z̅ = 0+1 =1 → saída 1. Para minterms proibidos (por ex. m7=111): X=1, Y̅+Z̅ =0+0=0 → saída 0. II produz 1 nos mintermos exigidos e só pode produce 1 em outras posições que são don’t cares (o que é permitido). Portanto II é válida.
  - III X Y̅ + Y̅ Z = Y̅ (X + Z). Teste m6 (110): Y̅=0 → expressão =0, mas m6 deve ser 1 → falha. III é inválida.
  - IV Y̅ Z + Y Z̅ = Y ⊕ Z (XOR between Y and Z). Avaliando:
    - m5 (101): Y=0,Z=1 → IV = 1 (ok);
    - m6 (110): Y=1,Z=0 → IV = 1 (ok);
    - m0(000): IV=0 (ok — m0 must be 0);
    - m1,m2,m4 são don’t cares — IV pode be 1 there without problema.
    - IV não gera 1 em minterms proibidos (m3,m7) so it fits constraints. Therefore IV is valid.

- Conclusão: apenas as expressões II e IV implementam corretamente G (dando 1 para m5,m6 e não forçando 1s em minterms que devem ser 0); logo a alternativa correta é a.

---  

### Pergunta
É de certa forma trivial declarar nomes para as entradas e as saídas de um dado circuito lógico simples, mediante a designação deles como bits ou “dígitos binários únicos”. Contudo, para que se possa representar uma entrada, uma saída ou mesmo um sinal composto de diversos bits, o HDL requer que se defina o tipo do sinal e também o intervalo de valores considerados aceitáveis.  
 
Avalie as afirmativas a seguir e a relação proposta entre elas.  
 
I. Matriz de bits e vetor de bits são conceitos alheios à descrição de ports com bits numerados por uma ordem crescente ou decrescente,  
 
PORQUE  
 
II. cada posição do bit é descrita com base em um único número-índice referente a cada elemento individual do port.  
 
Avaliando-se as afirmativas, conclui-se que:

a. as duas afirmativas são verdadeiras, e a segunda não justifica a primeira.  
b. as duas afirmativas são falsas.  
c. a primeira afirmativa é verdadeira, e a segunda é falsa.  
d. as duas afirmativas são verdadeiras, e a segunda justifica a primeira.  
e. a primeira afirmativa é falsa, e a segunda é verdadeira.

### Resposta
e. a primeira afirmativa é falsa, e a segunda é verdadeira.

### Motivo
- A afirmativa I é falsa porque "matriz de bits" e "vetor de bits" não são conceitos alheios à descrição de ports em HDL; ao contrário, vetores (std_logic_vector) e matrizes de bits são exatamente as formas usadas para declarar ports compostos por múltiplos bits, e a ordenação (downto ou to) determina se os índices crescem ou decrescem.  
- A afirmativa II é verdadeira: cada posição de um vetor de bits é referenciada por um único índice (um número) que identifica o elemento individual do port (por exemplo, signal(3) ou signal(0) em VHDL). Esse índice é a base para endereçar cada bit dentro do vetor.  
- Como I é falsa e II é verdadeira, a opção que corresponde à avaliação correta é a alternativa e.