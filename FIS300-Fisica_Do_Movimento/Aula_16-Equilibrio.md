# Física do Movimento – Equilíbrio

Esta aula, ministrada pelo Professor Cleber Amorim da UNIVESP, aborda os conceitos e aplicações do equilíbrio em sistemas estáticos – fundamentos essenciais tanto em problemas de engenharia quanto na mecânica clássica. Essa síntese integra o conteúdo da videoaula, os conceitos básicos extraídos da obra *Física 1 – Mecânica* (Young & Freedman) e informações complementares de fontes confiáveis da internet.

---

## 1. Introdução

- **Objetivo:**  
  - Compreender o que significa um sistema estar em equilíbrio.  
  - Aplicar as condições de equilíbrio para a resolução de problemas práticos, desde estruturas simples até situações complexas em engenharia e mecânica.

- **Aplicações:**  
  - Projetos estruturais (vigas, pontes, cabos).  
  - Estabilidade de objetos cotidianos (livros na estante, blocos, etc.).  
  - Análise de sistemas em engenharia, onde o dimensionamento seguro de estruturas depende da correta aplicação do equilíbrio.

---

## 2. Conceitos Fundamentais

### 2.1 Equilíbrio
Um sistema está em **equilíbrio** quando:
- **Momento Linear (P):** Permanece constante (ou seja, não há aceleração translacional).
- **Momento Angular (L) ou Torque:** Permanece constante, de forma que não há tendência para rotação.
- **Força Resultante:** A soma vetorial de todas as forças externas atuantes é zero.
- **Torque Resultante:** A soma dos torques (ou momentos) em relação a qualquer ponto de referência é zero.

### 2.2 Centro de Massa e Centro de Gravidade
- **Centro de Massa:** Ponto onde a massa pode ser considerada concentrada.  
- **Centro de Gravidade:** Normalmente coincide com o centro de massa quando o campo gravitacional é uniforme.

### 2.3 Forças e Componentes
- As forças são vetores e podem ser decompostas em componentes nos eixos **X**, **Y** e **Z**.  
- Em equilíbrio, cada componente da soma vetorial deve ser zero:  
  - ΣFₓ = 0  
  - ΣFᵧ = 0  
  - ΣFₙ = 0 (onde "n" representa a terceira direção ou eixo)

### 2.4 Torque (Momento de Força)
- **Definição:** Produto da força (F) pelo braço de alavanca (d), isto é, a distância perpendicular da linha de ação da força até o ponto ou eixo de referência.  
  - Fórmula: τ = F × d
- **Condição:** Para que não haja rotação, a soma dos torques deve ser nula: Στ = 0.  
- A escolha do ponto de referência pode simplificar os cálculos, eliminando incógnitas.

---

## 3. Condições de Equilíbrio

Para que um corpo ou sistema esteja em equilíbrio estático, devem ser satisfeitas duas condições fundamentais:

1. **Equilíbrio Translacional:**  
   - A soma das forças em todas as direções deve ser zero: ΣF = 0.

2. **Equilíbrio Rotacional:**  
   - A soma dos torques em torno de qualquer ponto de referência deve ser zero: Στ = 0.

Essas condições garantem que o sistema não apresente aceleração – nem translacional nem rotacional.

---

## 4. Exemplos Práticos

### 4.1 Exemplo 1 – Livro na Estante
- **Situação:**  
  Um livro em repouso sobre uma estante possui seu centro de massa alinhado com a área de apoio.
- **Análise:**  
  - Em posição vertical, o peso (Fg) atua pelo centro de massa, mantendo o sistema em equilíbrio.  
  - Ao inclinar o livro, a linha de ação da força peso pode deslocar-se para fora da base, rompendo o equilíbrio, o que pode levar ao tombamento.  
  - Comparativamente, um bloco (como um cubo) tende a ter maior estabilidade, pois pequenas inclinações geralmente mantêm o centro de massa dentro da base de apoio.

### 4.2 Exemplo 2 – Viga Sustentada por Duas Balanças
- **Configuração:**  
  Uma viga de massa definida repousa sobre duas balanças (ou apoios). Um bloco adicional é posicionado em determinado ponto da viga.
- **Diagrama de Corpo Livre:**  
  - Forças atuantes:  
    - Peso da viga (M·g) atuando em seu centro.  
    - Peso do bloco (m·g) atuando no ponto de aplicação.  
    - Reações normais (FE e FD) nos pontos de apoio.
- **Condições Aplicadas:**  
  1. ΣFᵧ = 0 (equilíbrio vertical).  
  2. Στ = 0 (equilíbrio de momentos), escolhendo um dos apoios como referência.
- **Resultado:**  
  - As leituras das balanças variam conforme a posição do bloco; se este for colocado exatamente no centro, ambas exibirão o mesmo valor.

### 4.3 Exemplo 3 – Estrutura com Viga, Cabo e Caixote
- **Configuração:**  
  Uma viga com um caixote suspenso por meio de um cabo e apoiada por uma dobradiça.
- **Diagrama de Corpo Livre:**  
  - Considera-se o peso da viga e do caixote, a tensão na corda e as reações na dobradiça (decompostas em componentes horizontais e verticais).
- **Aplicação:**  
  - Determina-se σFₓ = 0 e σFᵧ = 0 para as forças, e στ = 0 para os torques, usando a dobradiça como ponto de referência.
- **Resultados Obtidos (segundo os cálculos da aula):**  
  - Tensão na corda ≈ 6100 N  
  - Força na dobradiça ≈ 7900 N  
  Esses exemplos demonstram a importância da análise cuidadosa das condições de equilíbrio para dimensionar sistemas reais.

---

## 5. Conceitos Avançados e Complementares  
_(Baseado em Young & Freedman e referências adicionais)_

### 5.1 Tipos de Equilíbrio
A análise do estado de equilíbrio pode aprofundar-se na identificação dos **tipos de equilíbrio**:
- **Equilíbrio Estável:**  
  Pequenas perturbações geram forças restauradoras que fazem o objeto retornar à posição de equilíbrio.  
  _Exemplo: Uma bola repousando no fundo de uma cavidade côncava._  
  Referências complementares ressaltam que o potencial energético aumenta quando o objeto é deslocado de sua posição de equilíbrio.

- **Equilíbrio Instável:**  
  Pequenos deslocamentos fazem com que o objeto se afaste ainda mais de sua posição original, pois as forças atuantes favorecem o deslocamento.  
  _Exemplo: Uma bola equilibrada no topo de uma colina; uma mínima perturbação pode fazê-la rolar._

- **Equilíbrio Indiferente (ou Neutro):**  
  O objeto permanece em equilíbrio mesmo após deslocamento, sem tendência de retornar à posição original ou se afastar.  
  _Exemplo: Um objeto deslizando sobre uma superfície plana sem atrito._  
  Esses conceitos estão bem ilustrados em materiais didáticos disponíveis online.

### 5.2 Análise Energética e Estabilidade
- **Energia Potencial:**  
  A estabilidade de um objeto pode ser examinada pelo seu potencial energético:  
  - Em equilíbrio estável, um pequeno deslocamento aumenta a energia potencial, gerando uma força restauradora.  
  - Em equilíbrio instável, o deslocamento resulta em diminuição da energia potencial, facilitando a movimentação do objeto para longe da posição original.
- Essa análise energética é fundamental em engenharia para avaliar a resiliência e a segurança estrutural de projetos.

### 5.3 Diagramas de Corpo Livre (DCL) e Estratégias de Resolução
- Um DCL é essencial para visualizar e decompôr as forças atuantes num objeto.  
- A estratégia inclui:  
  1. Identificar o corpo ou sistema a ser analisado.  
  2. Representar todas as forças (peso, tensões, reações) e seus respectivos pontos de aplicação.  
  3. Escolher um sistema de coordenadas que facilite a resolução das equações de equilíbrio (ΣF = 0 e Στ = 0).  
- Diversas fontes enfatizam a importância dos DCLs para simplificar a resolução de problemas complexos em mecânica estática.

### 5.4 Aplicações na Engenharia e na Resistencia dos Materiais
- **Estruturas Arquitetônicas:**  
  Análise das cargas atuantes em edifícios, pontes e viadutos.  
- **Máquinas e Dispositivos:**  
  No design de componentes mecânicos, o equilíbrio de forças ajuda a prevenir vibrações indesejadas e falhas estruturais.  
- **Resistência dos Materiais:**  
  Em disciplinas como a “Resistência dos Materiais”, o equilíbrio é estudado juntamente com a deformação e a tensão, para garantir o desempenho seguro de estruturas sob cargas diversas.

---

## 6. Habilidades Desenvolvidas na Aula

- Identificar e interpretar situações de **equilíbrio estático**.  
- Construir e analisar **diagramas de corpo livre** para visualizar as forças e torques.  
- Aplicar corretamente as **condições de equilíbrio** (translacional e rotacional) em problemas reais.  
- Diferenciar os tipos de equilíbrio (estável, instável e indiferente) e compreender sua relevância através da análise energética.

---

## 7. Exercícios Resolvidos

### Exercício 1: Equilíbrio Translacional Simples
**Enunciado:**  
Um bloco de 10 kg está em repouso sobre uma superfície horizontal sem atrito. Duas forças horizontais são aplicadas: 30 N para a direita e 30 N para a esquerda. Verifique se o bloco está em equilíbrio translacional.

**Solução Detalhada:**  
- A condição de equilíbrio translacional exige que a soma vetorial das forças seja zero:  
  

\[
  \sum F_x = +30\,\text{N} - 30\,\text{N} = 0\,\text{N}
  \]


- Como \(\sum F_x = 0\), não há aceleração, e o bloco está em equilíbrio.

---

### Exercício 2: Equilíbrio Rotacional em uma Alavanca
**Enunciado:**  
Uma haste leve de comprimento 4 m está apoiada em seu centro. Um peso de 20 N é pendurado a 1 m da extremidade esquerda e outro de 20 N é pendurado a 1 m da extremidade direita. Verifique se o sistema está em equilíbrio rotacional.

**Solução Detalhada:**  
- Escolha o ponto de apoio (o centro da haste) como referência.  
- Torque devido ao peso à esquerda:  
  

\[
  \tau_{\text{esq}} = 20\,\text{N} \times 1\,\text{m} = 20\,\text{Nm}
  \]


- Torque devido ao peso à direita:  
  

\[
  \tau_{\text{dir}} = 20\,\text{N} \times 1\,\text{m} = 20\,\text{Nm}
  \]


- Se os sentidos dos torques forem opostos, temos:  
  

\[
  \tau_{\text{total}} = 20\,\text{Nm} - 20\,\text{Nm} = 0\,\text{Nm}
  \]


- Portanto, o sistema está em equilíbrio rotacional.

---

### Exercício 3: Reações em uma Viga Simples
**Enunciado:**  
Uma viga horizontal de 3 m de comprimento e “leve” (massa desprezível) está apoiada em dois pontos (nas extremidades). Um bloco com peso de 50 N é colocado a 1 m da extremidade esquerda. Determine as reações \(R_A\) e \(R_B\) nos apoios.

**Solução Detalhada:**  
1. **Equilíbrio vertical:**  
   

\[
   R_A + R_B = 50\,\text{N}
   \]


2. **Equilíbrio de torques:**  
   Escolha o apoio esquerdo como ponto de referência. O torque devido ao peso é:
   

\[
   \tau = 50\,\text{N} \times 1\,\text{m} = 50\,\text{Nm}
   \]


   O apoio direito, distante 3 m, gera um torque em sentido oposto:
   

\[
   R_B \times 3\,\text{m} = 50\,\text{Nm} \quad\Longrightarrow\quad R_B = \frac{50}{3} \approx 16.67\,\text{N}
   \]


3. **Calcule \(R_A\):**
   

\[
   R_A = 50\,\text{N} - 16.67\,\text{N} \approx 33.33\,\text{N}
   \]



---

### Exercício 4: Cálculo do Centro de Massa de um Sistema
**Enunciado:**  
Dois blocos de massas de 3 kg e 7 kg estão separados por 2 m. Determine a posição do centro de massa do sistema, considerando a posição do bloco de 3 kg como \(x = 0\,\text{m}\).

**Solução Detalhada:**  
- A posição do centro de massa é dada por:
  

\[
  x_{\text{cm}} = \frac{m_1 x_1 + m_2 x_2}{m_1 + m_2}
  \]


  Sendo \(m_1 = 3\,\text{kg}\), \(x_1= 0\), \(m_2= 7\,\text{kg}\) e \(x_2 = 2\,\text{m}\):
  

\[
  x_{\text{cm}} = \frac{3 \times 0 + 7 \times 2}{3+7} = \frac{14}{10} = 1.4\,\text{m}
  \]


- O centro de massa está a 1,4 m do bloco de 3 kg.

---

### Exercício 5: Equilíbrio de uma Viga em Balanço
**Enunciado:**  
Uma viga homogênea de 6 m de comprimento e peso 120 N está presa em uma parede (ponto A) e livre na outra extremidade. Um objeto de 40 N é pendurado a 4 m do ponto A. Determine o torque total em relação ao ponto A e verifique se há tendência a rotacionar.

**Solução Detalhada:**  
1. O peso da viga age no seu centro, a 3 m de A:
   

\[
   \tau_{\text{viga}} = 120\,\text{N} \times 3\,\text{m} = 360\,\text{Nm} \quad \text{(sentido horário)}
   \]


2. O objeto pendente produz:
   

\[
   \tau_{\text{objeto}} = 40\,\text{N} \times 4\,\text{m} = 160\,\text{Nm} \quad \text{(sentido horário)}
   \]


3. O torque total:
   

\[
   \tau_{\text{total}} = 360\,\text{Nm} + 160\,\text{Nm} = 520\,\text{Nm}
   \]


- Como o torque não é nulo, há tendência de rotação. Para evitar a rotação, deve haver um sistema de contraforça (por exemplo, um cabo pendurado na extremidade oposta ou reforço na fixação).

---

### Exercício 6: Sistema de Balanças e Viga
**Enunciado:**  
Uma viga de 2,7 kg de massa está apoiada em duas balanças. Um bloco de 1,8 kg é colocado sobre a viga em um ponto que não fica no centro. Se a balança da direita indica 15 N, qual é a indicação da balança da esquerda? (Considere \(g = 10\,\text{m/s}^2\) para facilitar os cálculos.)

**Solução Detalhada:**  
1. Peso total do sistema:  
   

\[
   P_{\text{total}} = (2,7 + 1,8)\,\text{kg} \times 10\,\text{m/s}^2 = 45\,\text{N}
   \]


2. Se a balança direita marca 15 N, a balança esquerda deverá sustentar:
   

\[
   45\,\text{N} - 15\,\text{N} = 30\,\text{N}
   \]


- Assim, a indicação da balança esquerda é 30 N.

---

### Exercício 7: Gangorra (Alavanca com Cargas Diferentes)
**Enunciado:**  
Em uma gangorra de 4 m de comprimento, uma criança de 30 kg está sentada a 1 m do pivô. Onde deve sentar uma outra criança de 20 kg para que haja equilíbrio? (Use \(g = 10\,\text{m/s}^2\))

**Solução Detalhada:**  
1. Calcule o torque da criança de 30 kg:
   

\[
   \tau_1 = 30\,\text{kg} \times 10\,\text{m/s}^2 \times 1\,\text{m} = 300\,\text{Nm}
   \]


2. Para a criança de 20 kg, se \(d\) é a distância do pivô:
   

\[
   \tau_2 = 20\,\text{kg} \times 10\,\text{m/s}^2 \times d = 200d\,\text{Nm}
   \]


3. Para equilíbrio, é necessário que:
   

\[
   200d = 300 \quad\Longrightarrow\quad d = 1.5\,\text{m}
   \]


- A criança de 20 kg deve sentar a 1,5 m do pivô, no lado oposto.

---

### Exercício 8: Torque com Força Inclinada
**Enunciado:**  
Uma força de 50 N é aplicada com um ângulo de 30° em relação a uma haste de 2 m. Calcule o torque produzido em relação ao ponto de giro, considerando apenas a componente perpendicular da força.

**Solução Detalhada:**  
1. A componente perpendicular da força é:
   

\[
   F_{\perp} = 50\,\text{N} \times \sin(30°) = 50\,\text{N} \times 0.5 = 25\,\text{N}
   \]


2. O torque é:
   

\[
   \tau = F_{\perp} \times d = 25\,\text{N} \times 2\,\text{m} = 50\,\text{Nm}
   \]



---

### Exercício 9: Escada Contra a Parede
**Enunciado:**  
Uma escada de 5 m repousa contra uma parede sem atrito. A base da escada fica a 1,5 m da parede. Determine a força normal da parede sobre a escada e a força do solo (reação horizontal e vertical, respectivamente), considerando o peso da escada de 200 N, que age no seu centro.

**Solução Detalhada:**  
1. Distâncias: o centro de massa está a 2,5 m da base da escada; horizontalmente, a distância até a parede pode ser determinada pela semelhança de triângulos.  
2. Usando equilíbrio de torques em torno da base:
   

\[
   \tau_{\text{parede}} = N_{\text{parede}} \times 1,5\,\text{m}
   \]


   O torque do peso:
   

\[
   \tau_{\text{peso}} = 200\,\text{N} \times \text{distância horizontal do centro de massa}
   \]


   A distância horizontal do centro de massa \(= \frac{1,5}{5} \times 2,5 = 0,75\,\text{m}\) (aproximadamente, usando proporção).
   Assim,
   

\[
   200\,\text{N} \times 0,75\,\text{m} = N_{\text{parede}} \times 1,5\,\text{m} \quad\Longrightarrow\quad N_{\text{parede}} = \frac{150}{1,5} = 100\,\text{N}
   \]


3. A reação vertical do solo deve equilibrar o peso:
   

\[
   R_{\text{vertical}} = 200\,\text{N}
   \]


4. A reação horizontal do solo é igual a \(N_{\text{parede}}\) (por ação e reação):
   

\[
   R_{\text{horizontal}} = 100\,\text{N}
   \]


  
*Observação:* Os valores podem ser ajustados com uma análise geométrica mais precisa; aqui foi utilizada uma aproximação simples para exemplificar o método.

---

### Exercício 10: Torque em uma Porta
**Enunciado:**  
Em uma porta de 1,0 m de largura, uma pessoa aplica uma força de 30 N perpendicularmente à porta, na extremidade. Qual o torque produzido em relação às dobradiças?

**Solução Detalhada:**  
- O torque é dado por:
  

\[
  \tau = F \times d = 30\,\text{N} \times 1,0\,\text{m} = 30\,\text{Nm}
  \]


- Portanto, o torque aplicado é de 30 Nm.

---

### Exercício 11: Força Aplicada Fora do Centro
**Enunciado:**  
Um quadro de 15 kg é preso na parede por um suporte fixo. Uma força de 40 N é aplicada a 0,5 m do ponto de fixação para tentar derrubá-lo. Verifique se o momento gerado pela força é suficiente para vencer o momento gravitacional, considerando o centro de massa a 0,2 m do ponto de fixação.

**Solução Detalhada:**  
1. Torque aplicado pela força:
   

\[
   \tau_{\text{aplicada}} = 40\,\text{N} \times 0,5\,\text{m} = 20\,\text{Nm}
   \]


2. Torque devido ao peso do quadro:
   

\[
   \tau_{\text{peso}} = (15\,\text{kg} \times 10\,\text{m/s}^2) \times 0,2\,\text{m} = 150\,\text{N} \times 0,2\,\text{m} = 30\,\text{Nm}
   \]


3. Como \(20\,\text{Nm} < 30\,\text{Nm}\), a força aplicada não é suficiente para vencer o torque estabilizador do quadro.

---

### Exercício 12: Sistema de Duas Forças Não Paralelas
**Enunciado:**  
Dois vetores de força, um de 25 N fazendo 60° com a horizontal e outro de 15 N fazendo 150° com a horizontal, atuam em um ponto. Verifique se, quando somados, o vetor resultante é zero.

**Solução Detalhada:**  
1. Componentes da força de 25 N:
   

\[
   F_{1x} = 25 \cos(60°) = 25 \times 0.5 = 12.5\,\text{N}
   \]


   

\[
   F_{1y} = 25 \sin(60°) \approx 25 \times 0.866 = 21.65\,\text{N}
   \]


2. Componentes da força de 15 N:
   

\[
   F_{2x} = 15 \cos(150°) = 15 \times (-0.866) \approx -12.99\,\text{N}
   \]


   

\[
   F_{2y} = 15 \sin(150°) = 15 \times 0.5 = 7.5\,\text{N}
   \]


3. Soma das componentes:
   

\[
   \sum F_x \approx 12.5 - 12.99 \approx -0.49\,\text{N} \quad (\text{próximo de zero})
   \]


   

\[
   \sum F_y \approx 21.65 + 7.5 = 29.15\,\text{N}
   \]


- Como a componente vertical não se anula, o sistema não está em equilíbrio. (Para equilíbrio total seria necessário que ambos os somatórios fossem zero).

---

### Exercício 13: Equilíbrio com Forças em Direções Diferentes
**Enunciado:**  
Um bloco é submetido a três forças: 10 N para o leste, 15 N para o noroeste (45° acima do oeste) e uma terceira força desconhecida que garante o equilíbrio. Determine a magnitude e direção da terceira força.

**Solução Detalhada:**  
1. Calcule componentes das duas forças conhecidas.  
   - Para 10 N (leste):  
     

\[
     F_{1x} = 10\,\text{N};\quad F_{1y} = 0\,\text{N}
     \]


   - Para 15 N a 45° ao noroeste (ângulo 135° em relação ao leste):
     

\[
     F_{2x} = 15 \cos(135°) = 15 \times (-0.707) \approx -10.61\,\text{N}
     \]


     

\[
     F_{2y} = 15 \sin(135°) = 15 \times 0.707 \approx 10.61\,\text{N}
     \]


2. Soma parcial:
   

\[
   \sum F_x = 10 - 10.61 \approx -0.61\,\text{N}
   \]


   

\[
   \sum F_y = 0 + 10.61 = 10.61\,\text{N}
   \]


3. Para equilíbrio, a terceira força \( \vec{F}_3 \) deve ter:
   

\[
   F_{3x} = 0.61\,\text{N} \quad \text{(para anular o negativo)}
   \]


   

\[
   F_{3y} = -10.61\,\text{N}
   \]


4. Magnitude:
   

\[
   F_3 = \sqrt{(0.61)^2 + (-10.61)^2} \approx \sqrt{0.37 + 112.60} \approx \sqrt{112.97} \approx 10.63\,\text{N}
   \]


5. Direção (ângulo em relação ao leste):
   

\[
   \theta = \tan^{-1}\left(\frac{-10.61}{0.61}\right) \approx -86.7° 
   \]


   – ou seja, aproximadamente 86.7° abaixo do sentido leste.

---

### Exercício 14: Cálculo do Centro de Massa – Sistema de Barras
**Enunciado:**  
Considere duas barras homogêneas: uma de 2 m com massa 4 kg e outra de 3 m com massa 6 kg, dispostas de forma que uma extremidade se tocando em um ponto comum. Calcule a posição do centro de massa do sistema, medido a partir do início da barra de 2 m.

**Solução Detalhada:**  
1. Para a barra de 2 m, o centro de massa está a 1 m do início.  
2. Para a barra de 3 m, o centro de massa estará a 1,5 m a partir de seu início, mas como estão conectadas pela extremidade, esse centro está a \(2\,\text{m} + 1.5\,\text{m} = 3.5\,\text{m}\) do início.  
3. Centro de massa do sistema:
   

\[
   x_{\text{cm}} = \frac{4\,\text{kg}\times1\,\text{m} + 6\,\text{kg}\times3.5\,\text{m}}{4+6} = \frac{4 + 21}{10} = \frac{25}{10} = 2.5\,\text{m}
   \]



---

### Exercício 15: Torques em Diferentes Pontos de uma Viga
**Enunciado:**  
Uma viga uniforme de 8 m pesa 160 N. Um objeto de 60 N é colocado a 3 m da extremidade esquerda. Determine o torque total em relação a um apoio localizado na extremidade esquerda.

**Solução Detalhada:**  
1. O peso da viga age no centro, a 4 m da extremidade esquerda:
   

\[
   \tau_{\text{viga}} = 160\,\text{N} \times 4\,\text{m} = 640\,\text{Nm}
   \]


2. O objeto:  
   

\[
   \tau_{\text{objeto}} = 60\,\text{N} \times 3\,\text{m} = 180\,\text{Nm}
   \]


3. Torque total (sentidos iguais se ambos tendem a fazer rotação no mesmo sentido):
   

\[
   \tau_{\text{total}} = 640\,\text{Nm} + 180\,\text{Nm} = 820\,\text{Nm}
   \]


- Se não houver outro torque contrário para anular, a viga tende a rodar.

---

### Exercício 16: Sistema com Cabo e Caixote
**Enunciado:**  
Em uma estrutura, um cabo sustenta um caixote pendurado. Se o cabo exerce uma tensão de 6100 N e forma um ângulo de 45° com a horizontal, determine a componente vertical da tensão que sustenta o caixote.

**Solução Detalhada:**  
1. A componente vertical da tensão é:
   

\[
   T_{\text{vertical}} = 6100\,\text{N} \times \sin(45°) \approx 6100\,\text{N} \times 0.707 \approx 4313\,\text{N}
   \]



---

### Exercício 17: Forças em um Plano Inclinado
**Enunciado:**  
Um bloco de 20 kg repousa sobre um plano inclinado a 30° com a horizontal. Determine as componentes do peso (20 kg ×10 m/s² = 200 N) paralela e perpendicular ao plano.

**Solução Detalhada:**  
1. Componente paralela:
   

\[
   W_{\parallel} = 200\,\text{N} \times \sin(30°) = 200\,\text{N} \times 0.5 = 100\,\text{N}
   \]


2. Componente perpendicular:
   

\[
   W_{\perp} = 200\,\text{N} \times \cos(30°) = 200\,\text{N} \times 0.866 \approx 173.2\,\text{N}
   \]



---

### Exercício 18: Uso da Simetria para Simplificação (Viga Simples)
**Enunciado:**  
Uma viga homogênea de 4 m é apoiada em duas extremidades. Se um peso de 80 N é colocado exatamente no centro, determine as reações nos apoios.

**Solução Detalhada:**  
- Pela simetria, cada apoio sustenta metade do peso:
  

\[
  R = \frac{80\,\text{N}}{2} = 40\,\text{N}
  \]


- Portanto, ambas as reações são de 40 N.

---

### Exercício 19: Forças de Atrito e Equilíbrio
**Enunciado:**  
Um bloco de 50 kg está em repouso sobre uma superfície horizontal com coeficiente de atrito estático \(\mu_s = 0.4\). Qual a força máxima de atrito que mantém o bloco em repouso?

**Solução Detalhada:**  
1. Peso do bloco:
   

\[
   P = 50\,\text{kg} \times 10\,\text{m/s}^2 = 500\,\text{N}
   \]


2. Força máxima de atrito:
   

\[
   F_{\text{atrito,max}} = \mu_s \times P = 0.4 \times 500\,\text{N} = 200\,\text{N}
   \]


- Assim, o bloco permanece em equilíbrio se a força aplicada for inferior a 200 N.

---

### Exercício 20: Reações em uma Estrutura Engastada
**Enunciado:**  
Uma viga horizontal engastada em uma extremidade suporta uma carga concentrada de 100 N aplicada a 2 m do engaste. Determine o torque que o engaste deve suportar.

**Solução Detalhada:**  
- O torque no engaste é:
  

\[
  \tau = 100\,\text{N} \times 2\,\text{m} = 200\,\text{Nm}
  \]


- Este é o torque que o engaste deve resistir para evitar a rotação.

---

### Exercício 21: Equilíbrio em uma Ponte de Viga
**Enunciado:**  
Uma ponte simples de viga tem 10 m de comprimento e sustenta uma carga distribuída uniformemente de 200 N/m. Qual é a força total aplicada e onde ela age?

**Solução Detalhada:**  
1. Força total:
   

\[
   F_{\text{total}} = 200\,\text{N/m} \times 10\,\text{m} = 2000\,\text{N}
   \]


2. Em uma carga distribuída uniformemente, a resultante age no centro da viga, ou seja, a 5 m de uma das extremidades.
  
---

### Exercício 22: Equilíbrio em um Plano Inclinado (Bloco Parado)
**Enunciado:**  
Um bloco de 30 kg repousa em um plano inclinado a 25°. Determine a força de atrito necessária para evitar que o bloco deslize, supondo que nenhuma outra força paralela esteja aplicada (use \(g = 10\,\text{m/s}^2\)).

**Solução Detalhada:**  
1. Peso do bloco:
   

\[
   P = 30 \times 10 = 300\,\text{N}
   \]


2. Componente paralela:
   

\[
   W_{\parallel} = 300\,\text{N} \times \sin(25°) \approx 300 \times 0.4226 \approx 126.78\,\text{N}
   \]


3. A força de atrito deve ser igual à componente paralela para o equilíbrio:
   

\[
   F_{\text{atrito}} \approx 127\,\text{N}
   \]



---

### Exercício 23: Equilíbrio com Múltiplas Forças e Torques
**Enunciado:**  
Um objeto é submetido a três forças concorrentes, aplicadas em pontos diferentes de seu corpo. Se os torques calculados em relação a um ponto escolhido são 50 Nm, -20 Nm e -30 Nm, verifique se o objeto está em equilíbrio rotacional.

**Solução Detalhada:**  
- Some os torques:
  

\[
  \tau_{\text{total}} = 50\,\text{Nm} - 20\,\text{Nm} - 30\,\text{Nm} = 0\,\text{Nm}
  \]


- Como o torque total é zero, o objeto está em equilíbrio rotacional.

---

### Exercício 24: Determinação de Tensões em um Sistema com Polias
**Enunciado:**  
Dois cabos, formando ângulos de 30° e 60° com a horizontal, sustentam uma carga de 500 N em equilíbrio. Determine, de forma aproximada, as tensões nos cabos.

**Solução Detalhada:**  
1. Para equilíbrio vertical:
   

\[
   T_1 \sin(30°) + T_2 \sin(60°) = 500\,\text{N}
   \]


   Sabendo que \(\sin(30°)=0.5\) e \(\sin(60°)\approx0.866\).
2. Para equilíbrio horizontal:
   

\[
   T_1 \cos(30°) = T_2 \cos(60°)
   \]


   Com \(\cos(30°)\approx0.866\) e \(\cos(60°)=0.5\), obtemos:
   

\[
   T_1 = \frac{0.5}{0.866} T_2 \approx 0.577 T_2
   \]


3. Substituindo na equação vertical:
   

\[
   (0.577 T_2)(0.5) + T_2(0.866) = 500 \quad\Longrightarrow\quad 0.2885T_2 + 0.866T_2 = 500
   \]


   

\[
   1.1545 T_2 \approx 500 \quad\Longrightarrow\quad T_2 \approx 433\,\text{N}
   \]


   Então,
   

\[
   T_1 \approx 0.577 \times 433 \approx 250\,\text{N}
   \]



---

### Exercício 25: Estabilidade de um Objeto Sobre uma Base
**Enunciado:**  
Um cubo de 2 m de lado é colocado sobre uma superfície. Determine a condição para que o cubo não tombe se for inclinado; ou seja, defina a relação entre o deslocamento do centro de massa e a dimensão da base.

**Solução Detalhada:**  
- O centro de massa de um cubo está no centro geométrico, a 1 m do fundo da base.  
- Para que o cubo não tombe, o centro de massa deve permanecer dentro da base de apoio.  
- Assim, o deslocamento máximo permitido horizontalmente é de 1 m a partir do centro.  
- Se o centro deslocar mais de 1 m, a projeção do peso excede a borda da base e o cubo tombará.

---

### Exercício 26: Sistema com Polias e Rebalanceamento
**Enunciado:**  
Dois blocos são ligados por uma corda passando por uma polia sem atrito. Se os blocos possuem 40 kg e 60 kg, determine a tensão na corda na situação de equilíbrio (supondo que o sistema esteja parado).

**Solução Detalhada:**  
- Em equilíbrio, a tensão (T) deve equilibrar o peso do bloco mais leve, pois o sistema não se move:  
  Para o bloco de 40 kg:
  

\[
  T = 40\,\text{kg} \times 10\,\text{m/s}^2 = 400\,\text{N}
  \]


- Todavia, para esse equilíbrio em um sistema real os dois pesos devem ser iguais;  
  Assim, o sistema está em equilíbrio se uma força externa (ou um mecanismo de bloqueio) mantiver o sistema parado.  
- A tensão, portanto, se aproxima de 400 N, assumindo que a diferença de peso é compensada por esse mecanismo.

---

### Exercício 27: Treliça e Equilíbrio Estático
**Enunciado:**  
Considere uma treliça simples composta por três barras rígidas formando um triângulo. Se uma força vertical de 300 N é aplicada no vértice superior, determine qualitativamente (sem cálculos numéricos exatos) como os membros da treliça distribuem as tensões para manter o equilíbrio.

**Solução Detalhada:**  
- A força aplicada é dividida entre os membros inclinados e o horizontal por meio de decomposição vetorial.  
- Cada membro inclinado carrega uma componente vertical e uma horizontal; a componente vertical repassa parte do peso para os apoios e a horizontal equilibra forças internas.  
- O equilíbrio exige que a soma das forças em cada nó seja zero.  
- Assim, as tensões se ajustam para que os momentos e as forças resultantes sejam anulados, mantendo a treliça em equilíbrio.

---

### Exercício 28: Distribuição de Cargas em uma Mesa
**Enunciado:**  
Uma mesa retangular é carregada com objetos cujos pesos somados totalizam 200 N. Se a distribuição de massa não é uniforme e o centro de massa do conjunto está a 0,4 m de um dos apoios, determine a reação em cada apoio, considerando uma mesa de 1,2 m de comprimento.

**Solução Detalhada:**  
1. Seja \(R_1\) e \(R_2\) as reações nos apoios (nas extremidades).  
   

\[
   R_1 + R_2 = 200\,\text{N}
   \]


2. Tomando o apoio da esquerda como referência para o equilíbrio de torques:
   

\[
   R_2 \times 1.2\,\text{m} = 200\,\text{N} \times 0.4\,\text{m} \quad\Longrightarrow\quad R_2 = \frac{80}{1.2} \approx 66.67\,\text{N}
   \]


3. Então:
   

\[
   R_1 = 200\,\text{N} - 66.67\,\text{N} \approx 133.33\,\text{N}
   \]



---

### Exercício 29: Torques e Ponto de Aplicação de Força
**Enunciado:**  
Uma força de 80 N é aplicada em uma viga de 5 m num ponto desconhecido, e a viga está em equilíbrio com uma reação de 50 N em uma extremidade e 30 N na outra. Determine a distância a partir da extremidade onde a força foi aplicada.

**Solução Detalhada:**  
- Sabe-se que a soma das reações é igual ao peso total aplicado:  
  \(50 + 30 = 80\,\text{N}\).  
- Para o equilíbrio de torques, escolha a extremidade onde atua a reação de 50 N como referência. Seja \(d\) a distância da aplicação da força em relação à essa extremidade.
  

\[
  80\,\text{N} \times d = 30\,\text{N} \times 5\,\text{m}
  \]


  

\[
  d = \frac{150}{80} = 1.875\,\text{m}
  \]



---

### Exercício 30: Equilíbrio Estático vs. Instável (Análise Energética)
**Enunciado:**  
Explique, por meio de uma análise qualitativa, a diferença entre equilíbrio estático estável, instável e neutro com base na variação da energia potencial em função do deslocamento do centro de massa.

**Solução Detalhada:**  
- **Equilíbrio Estável:** Quando o centro de massa é deslocado um pouco, a energia potencial aumenta, gerando uma força restauradora que retorna o objeto à posição original. Exemplo: Uma bola depositada no fundo de uma tigela.
- **Equilíbrio Instável:** Um pequeno deslocamento diminui a energia potencial e não cria força restauradora; pelo contrário, tende a empurrar o objeto para longe da posição original. Exemplo: Uma bola equilibrada no topo de uma colina.
- **Equilíbrio Neutro:** Pequenos deslocamentos não alteram significativamente a energia potencial; o objeto permanece em uma nova posição sem tendência a retornar nem a se afastar. Exemplo: Um cilindro sobre uma superfície perfeitamente plana.
- Dessa forma, a análise energética permite identificar a natureza do equilíbrio em sistemas físicos.

---

## 8. Informações Complementares e Fontes Confiáveis

Além dos conceitos abordados na aula e na obra de Young & Freedman, outras fontes apresentam informações relevantes:

- **Brasil Escola:**  
  Explica de maneira didática os tipos de equilíbrio (estável, instável e indiferente) e disponibiliza exercícios resolvidos que auxiliam o entendimento das condições de equilíbrio, enfatizando a importância do somatório das forças e torques ser nulo.

- **Mundo Educação:**  
  Discute tanto o equilíbrio estático quanto o dinâmico e explica como as leis de Newton se aplicam na manutenção ou mudança de estado de um corpo. A classificação dos tipos de equilíbrio também é detalhada nessa fonte, ressaltando o retorno à posição original em casos de equilíbrio estável ou o afastamento em equilíbrio instável.

- **Toda Matéria:**  
  Fornece uma visão comparativa entre equilíbrio estático e dinâmico, ressaltando que mesmo objetos em repouso (equilíbrio estático) obedecem à condição fundamental de que a soma das forças e dos momentos é nula. Essa fonte também menciona aplicações práticas em estruturas e engenharia.

- **Modern Physics (modern-physics.org):**  
  Apresenta uma análise aprofundada sobre o equilíbrio de forças, demonstrando como as equações de equilíbrio se aplicam no design e na análise de estruturas. Esse material reforça a importância da decomposição vetorial das forças e da análise dos torques para assegurar a estabilidade dos sistemas em estudo.

---

## Bibliografia

- **UNIVESP.** Videoaula *"Física do Movimento – Equilíbrio"*. Disponível em: [https://www.youtube.com/watch?v=n80xhVGCe1g](https://www.youtube.com/watch?v=n80xhVGCe1g). Acessado em: 15 de maio de 2025.  
- **Young, H. D., & Freedman, R. A.** *Física 1 – Mecânica* (14ª ed.).  
- **Brasil Escola.** Equilíbrio estático: tipos e exercícios resolvidos. Disponível em: [https://brasilescola.uol.com.br/fisica/equilibrio-estatico.htm](https://brasilescola.uol.com.br/fisica/equilibrio-estatico.htm).  
- **Mundo Educação.** Equilíbrio estático e dinâmico. Disponível em: [https://mundoeducacao.uol.com.br/fisica/equilibrio-estatico-dinamico.htm](https://mundoeducacao.uol.com.br/fisica/equilibrio-estatico-dinamico.htm).  
- **Toda Matéria.** O que é o equilíbrio estático e dinâmico e quais suas diferenças. Disponível em: [https://www.todamateria.com.br/equilibrio-estatico-e-dinamico/](https://www.todamateria.com.br/equilibrio-estatico-e-dinamico/).  
- **Modern Physics.** Equilíbrio de Forças | Fundamentos, Aplicações e Análise em Estática. Disponível em: [https://modern-physics.org/equilibrio-de-forcas-fundamentos-aplicacoes-e-analise-em-estatica/](https://modern-physics.org/equilibrio-de-forcas-fundamentos-aplicacoes-e-analise-em-estatica/).

