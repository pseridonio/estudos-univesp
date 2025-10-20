### Conversão de uma Tabela-Verdade para Soma de Produtos (SoP) canônica

#### O que é a forma Sum of Products (SoP)
A forma Sum of Products (Soma de Produtos) é uma representação booleana em que a função é escrita como a soma lógica (OR) de termos produto (AND) de literais; quando cada produto contém todas as variáveis (em forma direta ou negada) chamamos SoP de canônica (cada produto é um *mintermo*). .

#### Por que usar a forma canônica
- Cada mintermo corresponde exatamente a uma linha da tabela-verdade onde a saída é 1; assim, a forma canônica liga explicitamente cada combinação de entradas que produz 1 na saída.  
- A forma canônica é útil para conversão automática entre tabela-verdade e expressão e para aplicar mapas de Karnaugh com clareza sobre quais mintermos devem ser cobertos.  

#### Passo a passo: obter a SoP canônica a partir da tabela-verdade
1. Liste as linhas (números de mintermo) da tabela-verdade onde a saída F = 1. Anote os índices decimais ou os vetores de bits correspondentes.  
2. Para cada linha onde F = 1, construa o mintermo: escreva cada variável na forma direta se o bit for 1, ou negada (com barra ou apóstrofo) se o bit for 0. Ex.: para A=0, B=1, C=1 → mintermo = A' B C.  
3. Some (OR) todos os mintermos identificados: F = m_i + m_j + ... . Essa é a SoP canônica (também chamada soma de mintermos).  
4. Se desejar, expresse a soma dos índices: F = Σ(m_i, m_j, ...).  

Exemplo completo (3 variáveis): tabela-verdade com 1 nas linhas 1, 3 e 5 → minterms m1, m3, m5 → F = A'B'C + A'BC + AB'C (cada mintermo contém A, B e C em forma direta ou negada).

#### Converter uma SoP não-canônica em canônica (quando termos não têm todas as variáveis)
- Use a identidade X + X' = 1: para cada termo que não contém uma variável X, multiplique o termo por (X + X') e aplique distributiva para expandir até que cada produto contenha todas as variáveis.  
- Procedimento: para um termo T que falta a variável X, substitua T por T·(X + X') = T·X + T·X' e repita para todas as variáveis ausentes até obter produtos completos (minterms).  
Ex.: termo AB (falta C) → AB·(C + C') = ABC + ABC' (dois mintermos).

---

### Forma canônica x forma mínima
- A SoP canônica é muito direta, porém normalmente não é mínima; após obter a canônica você pode simplificar usando álgebra Booleana ou mapas de Karnaugh para obter uma SoP mínima (menos termos e/ou literais) que implementa a mesma função.

---

## Mapas de Karnaugh — construção, leitura e dicas práticas

### O que é um mapa de Karnaugh (K-map)
O K-map é uma representação gráfica da tabela-verdade organizada de forma que células adjacentes diferem em exatamente um bit, permitindo visualizar e agrupar mintermos que podem ser combinados para eliminar variáveis e simplificar a expressão (mesma informação da tabela-verdade disposta geometricamente).

### Estrutura e sequência das células
- 2 variáveis: 2×2 (minterms 0–3)  
- 3 variáveis: 2×4 ou 4×2 (minterms 0–7) organizados em sequência Gray (0,1,3,2 / 4,5,7,6) para preservar adjacência por um bit.  
- 4 variáveis: 4×4 (minterms 0–15) com sequência Gray em linhas e colunas (cada eixo muda um conjunto de 2 bits), o que garante que células que diferem por 1 bit fiquem vizinhas, inclusive por “wrap-around” (borda conecta com borda oposta).

Dica prática: use a ordem Gray (0,1,3,2...) nas colunas e linhas — isso é a chave para que apenas 1 bit mude entre células adjacentes.

### Como montar o mapa (passo a passo)
1. Defina o número de variáveis n (2, 3, 4,...).  
2. Desenhe a grade: para n=3 use 2 linhas × 4 colunas; para n=4 use 4×4.  
3. Rotule as linhas e colunas com combinações das variáveis em ordem Gray; cada célula representa um mintermo (indexado 0..2^n-1).  
4. Preencha cada célula com o valor da saída (0, 1 ou X para don’t care) a partir da tabela-verdade.  

Exemplo (3 variáveis A,B,C): linhas = A (0 / 1), colunas = BC em Gray: 00, 01, 11, 10 → minterms 0,1,3,2 na linha A=0; 4,5,7,6 na linha A=1.

### Interpretação da adjacência
- Células adjacentes diferem exatamente em 1 variável (1 bit).  
- Adjacência considera wrap-around: bordas opostas são adjacentes (ex.: célula da coluna 0 é adjacente à coluna final).  
- Grupos podem atravessar margens e cantos — visualize o mapa como um toro (anel envolvente) para entender conexões.

---

## Regras de agrupamento (boas práticas e por que elas funcionam)
1. Grupos são retângulos contendo 2^k células (k ≥ 0): 1,2,4,8,...; apenas potências de dois.  
2. Cada grupo produz um termo com n − k literais (quanto maior o grupo, menos literais no termo). Ex.: grupo de 4 em um mapa de 4 variáveis resulta em termo com 2 literais.  
3. Os grupos devem conter somente células com valor 1 (células don’t care podem ser incluídas opcionalmente para ampliar grupos).  
4. Composição dos grupos: busque cobrir todos os 1s com o menor número de grupos e o maior tamanho possível; interseções entre grupos são permitidas se isso reduzir o número total de termos.  
5. Cada agrupamento representa a eliminação das variáveis que mudam entre as células do grupo; manter apenas as variáveis que são constantes dentro do grupo gera o produto simplificado.  
6. Priorize: primeiro formar grupos de maior tamanho; depois complete coberturas menores apenas quando necessário.

Dica operacional: marque 1s já cobertos para evitar cobrir com grupos menores desnecessários, mas permita sobreposição quando leva a menos termos finais.

---

## Como extrair a expressão a partir de um grupo
- Identifique quais variáveis têm o mesmo valor em todas as células do grupo: essas variáveis permanecem no termo; aquelas que mudam são eliminadas.  
- Se uma variável for sempre 1 no grupo, ela aparece direta; se sempre 0, aparece negada.  
Ex.: em mapa com variáveis A,B,C, um grupo vertical que cobre células onde A=0 em todas as células → termo = A'.

---

## Sequência de montagem e heurísticas para aprender o K-map

Passo preferencial (heurística eficiente):
1. Preencher mapa com 1s e Xs (don’t care).  
2. Procurar maiores grupos possíveis (8,4,2,1...) que incluam 1s — comece por 8 se houver (em mapas de 4 vars), então 4, depois 2, depois 1.  
3. Para cada 1 que ainda não está coberto por um grupo grande, tente agrupá-lo com vizinhos para formar o maior grupo possível.  
4. Utilize células don’t care para ampliar grupos quando isto reduzir o número de termos ou literais.  
5. Ao finalizar a cobertura, deduza um termo por grupo e efetue OR entre eles para obter a SoP simplificada.

Dica mnemônica para iniciantes: “maior antes, menor depois” — busque sempre o maior agrupamento que cubra cada 1.

---

## Tratamento de “don’t care” (X)
- “Don’t care” indica combinações de entrada impossíveis ou irrelevantes; podem ser tratados como 0 ou 1 conforme convier à simplificação.  
- Estratégia: utilize X como 1 quando isso permitir formar um grupo maior e reduzir a expressão; ignore como 0 quando não ajudar. Nunca force um X a ser 1 se ele criar um termo que gere saídas indevidas para combinações válidas.

---

## Exemplos detalhados (passo a passo)

### Exemplo A — 3 variáveis: tabela → SoP canônica → K-map → simplificação
Função F(A,B,C) com 1 nos minterms: m1, m3, m4, m7 (índices decimais).

1. SoP canônica direta: F = m1 + m3 + m4 + m7 = A'B'C + A'BC + AB'C' + ABC. (cada mintermo contém A,B,C).  
2. Montar K-map (linhas A=0/1; colunas BC = 00,01,11,10). Preencher: m1 (A=0,BC=01) =1; m3 (0,11)=1; m4 (1,00)=1; m7 (1,11)=1.  
3. Agrupamento: observe pares adjacentes: (m3,m7) vertical (coluna 11); (m1,m3) horizontal adjacente? m1 col 01, m3 col 11 são adjacentes (mudança em B) → possível grupo de 2; também m4 adjacente a m0 (se fosse 1) — aqui formar grupos ótimos: (m3,m7) → termo: C (coluna 11 tem C=1 e B=1; mas dependendo do grupo a variável que não muda é a que permanece). Faça grupos maiores quando possível.  
4. Resultado simplificado (após identificar variáveis constantes em cada grupo): por exemplo F_simpl = C + A'B' (ilustração: o processo exige checar quais variáveis dependem) — verifique passo a passo no K-map para confirmar o termo correto.  
(Observação: montar o mapa concretamente ajuda a identificar quais variáveis se mantêm constantes; consulte o exercício resolvido abaixo para implementação passo a passo).

### Exemplo B — 4 variáveis com don’t cares
Considere função F(W,X,Y,Z) verdadeira nos minterms {1,3,7,11} e don’t cares {10,14}.  
1. Desenhe 4×4 K-map com rotulagem Gray das colunas e linhas (0..15).  
2. Preencha 1s nas células correspondentes e Xs onde indicado.  
3. Busque formar grupos maiores: por exemplo X em 10 permite unir m10 com m11 para formar um grupo de 2 que cobre m11 e melhora simplificação; X em 14 pode ajudar a formar um grupo de 4 se existirem vizinhos adequados.  
4. Extraia termos por grupo (cada agrupamento reduz literais).  
Resultado: expressão mais simples que a soma canônica original; incluir Xs como 1s quando útil.

---

## Dicas práticas para dominar mapas de Karnaugh

- Treine a identificação de adjacência visual: pratique reconhecer vizinhos por 1 bit e por wrap-around.  
- Sempre rotule corretamente as linhas/colunas em Gray; se a ordem for linear (0,1,2,3) a adjacência estará errada.  
- Ao agrupar, pergunte: “que variável permanece constante neste retângulo?” — essa é a que aparece no termo simplificado.  
- Use papel quadriculado para visualizar grupos; desenhe retângulos que possam envolver bordas e cantos.  
- Quando em dúvida se sobrepor grupos é bom: prefira sobreposição se o número total de termos diminuir ou se um grupo maior eliminar mais literais.  
- Pratique com 2, 3 e 4 variáveis antes de avançar a mapas maiores; 4 variáveis é suficiente para entender wrap-around e agrupamentos complexos.

---

## Exercícios com resolução detalhada (passo a passo)

### Exercício 1 (3 variáveis)
Tabela-verdade: F=1 nos minterms {1,3,5,7}. Encontre SoP canônica e simplifique via K-map.

Resolução:
1. SoP canônica: liste minterms m1,m3,m5,m7:
   - m1: A' B' C
   - m3: A' B C
   - m5: A B' C
   - m7: A B C  
   So F = A'B'C + A'BC + AB'C + ABC .
2. K-map 2×4 (A linha, BC colunas Gray 00,01,11,10). Marque 1 em m1 (0,01), m3 (0,11), m5 (1,01), m7 (1,11).
3. Agrupamentos: observe duas colunas 01 e 11 com 1s em ambas linhas → podemos formar dois grupos verticais de 2 (coluna 01: m1 & m5, coluna 11: m3 & m7) ou um grupo de 4 se as colunas 01 e 11 forem adjacentes formando retângulo 4? Note que colunas 01 e 11 são adjacentes (mudança em B), combinando as duas colunas e as duas linhas forma um grupo de 4 cobrindo todos os 1s.  
4. Grupo de 4: todas as células têm C = 1 constante (BC = 01 ou 11 → C = 1 em ambas), enquanto A e B variam → termo simplificado = C.  
Resultado final: F = C (redução completa).  
Verificação: a SoP canônica expandida simplifica para C via K-map, mostrando como grupos maiores reduzem variáveis.

### Exercício 2 (4 variáveis com don’t care)
F(W,X,Y,Z) = 1 em {0,2,8,10}, don’t care em {3,11}. Simplifique.

Resolução:
1. Preencha K-map 4×4 com 1s em 0,2,8,10 e X em 3,11.  
2. Observe adjacências: m0 adjacente a m2 (difere em Y/Z), m8 adjacente a m10; X em 3 e 11 podem permitir formar grupos de 2/4 que incluam 0/2/8/10.  
3. Agrupe: por exemplo, usando don’t cares podemos unir {0,2,8,10} como dois grupos de 4 (dependendo da configuração) para reduzir a expressão a termos com 2 literais.  
4. Extraia os termos constantes para cada grupo conforme variáveis que não mudam.  
Resultado (ilustrativo): F simplificada com menos termos do que soma canônica; o uso criterioso de Xs permitiu agrupar e reduzir mais.

---

## Rápido resumo de ações para o aluno executar em cada problema
1. Obter tabela-verdade.  
2. Escrever SoP canônica (Σ minterms) se solicitado.  
3. Desenhar K-map com rotulagem Gray.  
4. Preencher 1/0/X.  
5. Agrupar buscando potências de 2, maior primeiro.  
6. Extrair termo por grupo (variáveis constantes).  
7. OR dos termos → expressão mínima (SoP).  
8. Verificar substituindo combinações ou conferindo tabela-verdade.

---

## Referências (ABNT) e materiais consultados
- UNIVESP. Circuitos Digitais - Mapa de Karnaugh. Vídeo-aula Professor André Ricardo Fioravanti. YouTube, 25 out. 2021. Disponível em: https://www.youtube.com/watch?v=hyCTj4WxkFY. Acesso em: 10 out. 2025.  
- GeeksforGeeks. Canonical and Standard Form. GeeksforGeeks, 20 set. 2025. Disponível em: https://www.geeksforgeeks.org/digital-logic/canonical-and-standard-form/. Acesso em: 10 out. 2025.  
- ElectricalTechnology. Sum Of Product (SOP) & Product Of Sum (POS) - Boolean Algebra. ElectricalTechnology.org, 2018. Disponível em: https://www.electricaltechnology.org/2018/05/sum-of-product-sop-product-of-sum-pos.html. Acesso em: 10 out. 2025.  
- ElectronicsHub. Boolean Logic: SOP And POS Form Truth Table & Examples. ElectronicsHub, 11 set. 2024. Disponível em: https://www.electronicshub.org/boolean-logic-sop-form-pos-form/. Acesso em: 10 out. 2025.

---
