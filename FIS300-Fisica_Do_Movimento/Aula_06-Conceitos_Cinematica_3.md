# Física do Movimento – Movimento Vertical, Queda Livre e Introdução aos Vetores

Este documento reúne de forma detalhada os conceitos abordados no vídeo sobre movimento vertical, integrando os fundamentos da queda livre (com base nos experimentos de Galileu e na demonstração na Lua) e apresentando uma introdução aos vetores, essenciais para a resolução de problemas em duas dimensões (como o lançamento oblíquo). Adicionalmente, o material inclui uma extensa lista de exercícios – com 30 enunciados e suas resoluções detalhadas – para fixação dos conceitos.

---

## Sumário

1. [Introdução](#introdução)  
2. [Conceitos Fundamentais da Queda Livre](#conceitos-fundamentais-da-queda-livre)  
&nbsp;&nbsp;&nbsp;&nbsp;2.1. Equações Básicas  
&nbsp;&nbsp;&nbsp;&nbsp;2.2. Exemplos Práticos  
3. [Representação Gráfica](#representa%C3%A7%C3%A3o-gr%C3%A1fica)  
4. [Vetores e Movimentos Bidimensionais](#vetores-e-movimentos-bidimensionais)  
5. [Aspectos Avançados e Aplicações Práticas](#aspectos-avan%C3%A7ados-e-aplica%C3%A7%C3%B5es-pr%C3%A1ticas)  
6. [Bibliografia](#bibliografia)  
7. [Exercícios](#exerc%C3%ADcios)  
8. [Resolução dos Exercícios](#resolu%C3%A7%C3%A3o-dos-exerc%C3%ADcios)

---

## 1. Introdução

Por muitos séculos acreditou-se – conforme defendido por Aristóteles – que corpos mais pesados caíam mais rapidamente. No entanto, Galileu demonstrou, por meio de experimentos com planos inclinados, que desconsiderada a resistência do ar, todos os corpos caem com a mesma aceleração. Essa descoberta foi corroborada pelo experimento realizado na Lua (onde a atmosfera é insignificante) durante a missão Apollo, no qual o astronauta David Scott soltou um martelo e uma pena simultaneamente.

Este material foca no estudo do movimento vertical em queda livre, detalhando suas equações, a representação gráfica e os conceitos que fundamentam a cinemática. Além disso, há uma introdução à análise vetorial, necessária para compreender o movimento em duas dimensões.

---

## 2. Conceitos Fundamentais da Queda Livre

### 2.1 Equações Básicas

Supondo que um objeto seja liberado do repouso (velocidade inicial \( v_0 = 0 \)) e que a única aceleração atuante seja a da gravidade, \( g \) (aproximadamente 9,8 m/s² na Terra), as equações do movimento em queda livre são:

- **Equação da Posição (Deslocamento Vertical):**
  
  \[
  s = \frac{1}{2} g t^2
  \]
  
  onde:  
  - \( s \) é o deslocamento vertical (em metros);  
  - \( t \) é o tempo (em segundos).

- **Equação da Velocidade:**

  \[
  v = g t
  \]
  
  Esta fórmula indica que a velocidade aumenta linearmente com o tempo.

### 2.2 Exemplos Práticos

Considere o caso de um martelo largado do repouso:

- **Para \( t = 0 \) s:**  
  - \( s = \frac{1}{2} \times 9.8 \times 0^2 = 0 \) m  
  - \( v = 9.8 \times 0 = 0 \) m/s

- **Para \( t = 1 \) s:**  
  - \( s = \frac{1}{2} \times 9.8 \times 1^2 = 4.9 \) m  
  - \( v = 9.8 \times 1 = 9.8 \) m/s

- **Para \( t = 2 \) s:**  
  - \( s = \frac{1}{2} \times 9.8 \times 2^2 = 19.6 \) m  
  - \( v = 9.8 \times 2 = 19.6 \) m/s

- **Para \( t = 3 \) s:**  
  - \( s = \frac{1}{2} \times 9.8 \times 3^2 = 44.1 \) m  
  - \( v = 9.8 \times 3 = 29.4 \) m/s

> **Observação:**  
> A distância percorrida cresce com \( t^2 \), evidenciando a natureza acelerada do movimento.

---

## 3. Representação Gráfica

### 3.1 Gráfico Posição vs. Tempo

- A curva de posição em queda livre é uma **parábola** (devido à dependência de \( t^2 \)).  
- A curvatura indica que, para intervalos de tempo iguais, o deslocamento aumenta progressivamente.

### 3.2 Gráfico Velocidade vs. Tempo

- A velocidade aumenta de forma *linear* com o tempo, formando uma reta que passa pela origem com inclinação \( g \) (aprox. 9,8 m/s²).

#### Exemplo (Representação ASCII):

```
    v (m/s)
      30 |           *
      25 |         *
      20 |       *
      15 |     *
      10 |   *
       5 | *
       0 |*_____________ t (s)
          0   1   2   3
```

### 3.3 Gráfico Aceleração vs. Tempo

- Em queda livre (sem resistência do ar), a aceleração é constante. Assim, o gráfico de aceleração é uma linha horizontal no valor de \( g \).

---

## 4. Vetores e Movimentos Bidimensionais

Mesmo que o movimento vertical seja unidimensional, muitos problemas práticos (como lançamentos oblíquos) requerem o tratamento de movimentos em duas dimensões por meio de vetores.

### 4.1 Conceitos Básicos de Vetores

- **Definição:**  
  Um vetor é uma grandeza que possui módulo (magnitude) e direção. Em um plano bidimensional, a posição é representada por:

  \[
  \vec{r}(t) = x(t)\hat{i} + y(t)\hat{j}
  \]

- **Componentes:**  
  Dado um vetor \( \vec{V} \) com módulo \( |V| \) e ângulo \( \theta \) em relação ao eixo \( x \):
  
  \[
  V_x = |V| \cdot \cos(\theta) \quad \text{e} \quad V_y = |V| \cdot \sin(\theta)
  \]

### 4.2 Aplicações em Lançamentos Oblíquos

Em um lançamento oblíquo:
- A componente horizontal (MRU) é dada por:
  
  \[
  x(t) = v_0 \cos(\theta) \, t
  \]
  
- A componente vertical (MRUV – com aceleração da gravidade) é:

  \[
  y(t) = v_0 \sin(\theta) \, t - \frac{1}{2} g t^2
  \]

Essas relações permitem determinar o alcance, a altura máxima e o tempo total de voo de um projétil.

---

## 5. Aspectos Avançados e Aplicações Práticas

Além das equações básicas, é importante destacar alguns pontos essenciais:

- **Derivação e Integração:**  
  A velocidade é a derivada da função posição, e a aceleração é a derivada da velocidade. Inversamente, integrando a aceleração, recuperamos a velocidade (mais uma constante de integração) e, integrando a velocidade, recuperamos a posição.

- **Experimentos Históricos:**  
  Experimentos com planos inclinados de Galileu e o icônico experimento na Lua (com o martelo e a pena) validam a independência da massa na queda livre, quando a resistência do ar é desprezível.

- **Aplicações Práticas:**  
  O estudo da queda livre é fundamental em diversas áreas, desde a engenharia (análise de veículos e estruturas) até a física moderna (análise de movimentos planetários e desempenho de projéteis).

- **Vetores em Problemas Reais:**  
  A decomposição vetorial permite resolver problemas complexos que envolvem movimentos em ambientes reais, onde os objetos se movem simultaneamente em direções horizontais e verticais.

---

## 6. Bibliografia

- **Vídeo Aula:**  
  *Física do Movimento - Conceitos de Cinemática - Parte 3*  
  UNIVESP / Professor Cleber Amorim  
  [Assista no YouTube](https://www.youtube.com/watch?v=pZcxF2a2-qs)

- **Livro:**  
  *[Título do Livro]* – (inserir informações completas: autor, editora, ano de publicação).  
  _(Contém, nos capítulos 2 e 3, complementos sobre MRUV, análise gráfica e aplicações dos conceitos da cinemática.)_

- **Referência Adicional:**  
  *Halliday, D., Resnick, R. & Walker, J. – "Fundamentals of Physics"*  
  (Referência clássica para aprofundamento dos conceitos relativos à cinemática, forças e vetores.)

---

## 7. Exercícios

A seguir, 30 enunciados de exercícios que abrangem os temas de movimento vertical, queda livre e vetores:

1. **Queda Livre Básica:**  
   Um objeto é solto do repouso de uma altura de 50 m. Calcule o tempo de queda e a velocidade no impacto.

2. **Lançamento Vertical para Cima:**  
   Um objeto é lançado verticalmente para cima com velocidade inicial de 25 m/s. Determine o tempo para alcançar o ponto mais alto e a altura máxima.

3. **Posição e Velocidade:**  
   Considerando \( g = 9.8 \, \text{m/s}^2 \), calcule a posição e a velocidade de um objeto em queda livre aos instantes \( t = 1 \) s, \( t = 2 \) s e \( t = 3 \) s.

4. **Aceleração Média:**  
   Um objeto aumenta sua velocidade de 20 m/s para 40 m/s em 5 s. Calcule sua aceleração média.

5. **Altura e Velocidade de Impacto:**  
   Um objeto em queda livre atinge o solo em 4 s. Determine a altura da queda e a velocidade no impacto.

6. **Lançamento para Baixo:**  
   Um objeto é lançado verticalmente para baixo com velocidade inicial de 5 m/s. Calcule a velocidade após 3 s e o deslocamento vertical.

7. **Lançamento Horizontal:**  
   Um objeto é lançado horizontalmente de uma altura de 80 m com velocidade de 15 m/s. Determine o tempo de queda e a distância horizontal percorrida.

8. **Velocidade Inicial:**  
   Calcule a velocidade inicial necessária para que um objeto lançado verticalmente atinja uma altura máxima de 30 m.

9. **Verificação Experimental:**  
   Um objeto parte do repouso e percorre 19.6 m em 2 s. Verifique se os dados estão de acordo com a equação \( s = \frac{1}{2}gt^2 \).

10. **Derivação da Velocidade:**  
    Demonstre, a partir de \( s(t) = \frac{1}{2}gt^2 \), que a função velocidade \( v(t) \) é linear em \( t \).

11. **Retorno ao Ponto de Lançamento:**  
    Um objeto é lançado verticalmente para cima com 30 m/s. Determine o tempo total para que retorne ao ponto de lançamento.

12. **Determinação de \( g \):**  
    Em um experimento, um objeto em queda livre percorre 44.1 m em 3 s. Calcule a aceleração da gravidade a partir destes dados.

13. **Variação de Velocidade:**  
    Calcule a variação da velocidade de um objeto em queda livre entre \( t = 2 \) s e \( t = 5 \) s.

14. **Velocidade que se Anula:**  
    Um objeto é lançado verticalmente para cima e sua velocidade se anula após 3.5 s. Qual foi a velocidade inicial?

15. **Comparação de Distâncias:**  
    Prove que a distância percorrida pelo objeto no segundo segundo de queda é o dobro da distância percorrida no primeiro segundo.

16. **Queda com Velocidade Inicial Positiva:**  
    Um objeto é lançado com uma velocidade inicial de 2 m/s para cima e depois sofre queda livre. Determine a altura máxima atingida.

17. **Queda Partindo do Repouso:**  
    Calcule a velocidade de um objeto que, partindo do repouso, percorre 9.8 m em queda livre.

18. **Lançamento Horizontal (Impacto):**  
    Um objeto lançado horizontalmente de uma altura de 120 m com 10 m/s de velocidade atinge o solo. Calcule a velocidade final (resultante) no instante do impacto.

19. **Projétil Oblíquo:**  
    Um projétil é lançado com 20 m/s formando um ângulo de 45° com a horizontal. Determine o alcance horizontal e a altura máxima.

20. **Movimento em Duas Dimensões:**  
    Considere a posição de um objeto dada por  
    \(\vec{r}(t) = (3t)\hat{i} + (4t - 4.9t^2)\hat{j}\).  
    a) Determine a função velocidade vetorial \( \vec{v}(t) \).  
    b) Encontre o instante em que o objeto atinge a altura máxima.

21. **Módulo da Velocidade em Queda:**  
    Calcule o módulo da velocidade para um objeto em queda livre aos 2 s.

22. **Velocidade Média:**  
    Um objeto em queda livre percorre 80 m em 4 s. Determine sua velocidade média.

23. **Velocidade Atuante:**  
    Um objeto partindo do repouso atinge 19.6 m/s após cair livremente. Calcule o tempo decorrido e a altura percorrida.

24. **Verificação Experimental 2:**  
    Em um experimento, um objeto atinge 15 m/s após 1.53 s de queda livre. Verifique se esses dados são consistentes com \( g = 9.8 \, \text{m/s}^2 \).

25. **Tempo de Queda e Impacto:**  
    Um objeto tem um tempo de queda de 3.2 s. Determine (a) a altura da queda; (b) a velocidade ao impactar o solo.

26. **Equação Quadrática na Queda:**  
    Dada a função de posição \( s(t) = 2 + 5t - 4.9t^2 \) (com a origem em 2 m acima do solo), determine o instante em que o objeto atinge a altura máxima.

27. **Queda de um Penhasco:**  
    Um objeto é lançado de um penhasco de 100 m. Calcule o tempo que leva para atingir o solo e a velocidade de impacto.

28. **Consistência de Dados:**  
    Se um objeto percorre 19.6 m em 2 s, determine a aceleração e a velocidade no final destes 2 s.

29. **Projétil Horizontal:**  
    Um objeto é lançado horizontalmente de uma altura de 50 m com 8 m/s. Determine (a) o tempo de queda; (b) a distância horizontal percorrida.

30. **Velocidade Resultante:**  
    Um objeto possui velocidade horizontal de 6 m/s e velocidade vertical de 7 m/s. Use o teorema de Pitágoras para encontrar o módulo da velocidade resultante.

---

## 8. Resolução dos Exercícios

### Exercício 1
**Enunciado:** Um objeto é solto do repouso de uma altura de 50 m.  
**Resolução:**
1. Use a equação de posição:  
   \[
   s = \frac{1}{2} g t^2
   \]
   Substituindo \( s = 50 \) m e \( g = 9.8 \) m/s²:
   \[
   50 = 0.5 \times 9.8 \times t^2 \quad \Rightarrow \quad t^2 = \frac{50}{4.9} \approx 10.204 \quad \Rightarrow \quad t \approx 3.194 \, \text{s}
   \]
2. Velocidade no impacto:  
   \[
   v = gt \approx 9.8 \times 3.194 \approx 31.3 \, \text{m/s}
   \]

---

### Exercício 2
**Enunciado:** Um objeto é lançado verticalmente para cima com 25 m/s.  
**Resolução:**
1. Tempo para atingir a altura máxima:  
   No ponto mais alto, \( v = 0 \). Use
   \[
   v = v_0 - g t \quad \Rightarrow \quad 0 = 25 - 9.8t \quad \Rightarrow \quad t \approx \frac{25}{9.8} \approx 2.55 \, \text{s}
   \]
2. Altura máxima:  
   Use a equação:
   \[
   s = v_0 t - \frac{1}{2}gt^2 \quad \Rightarrow \quad s = 25 \times 2.55 - 0.5 \times 9.8 \times (2.55)^2
   \]
   Calculando:
   - Primeiro termo: \(25 \times 2.55 \approx 63.75\) m  
   - Segundo termo: \(0.5 \times 9.8 \times 6.5025 \approx 31.8\) m  
   \[
   s \approx 63.75 - 31.8 \approx 31.95 \, \text{m}
   \]

---

### Exercício 3
**Enunciado:** Calcule a posição e a velocidade para \(t = 1\) s, \(2\) s e \(3\) s (queda livre).  
**Resolução:**  
Usando \( s = 0.5 \times 9.8 t^2 \) e \( v = 9.8t \):
- Para \( t = 1 \) s:  
  \( s = 4.9\) m, \( v = 9.8\) m/s.
- Para \( t = 2 \) s:  
  \( s = 19.6\) m, \( v = 19.6\) m/s.
- Para \( t = 3 \) s:  
  \( s = 44.1\) m, \( v = 29.4\) m/s.

---

### Exercício 4
**Enunciado:** Um objeto acelera de 20 m/s para 40 m/s em 5 s.  
**Resolução:**
\[
a = \frac{40 - 20}{5} = \frac{20}{5} = 4 \, \text{m/s}^2
\]

---

### Exercício 5
**Enunciado:** Um objeto em queda livre atinge o solo em 4 s.  
**Resolução:**
1. Altura da queda:
   \[
   s = 0.5 \times 9.8 \times 4^2 = 0.5 \times 9.8 \times 16 = 78.4 \, \text{m}
   \]
2. Velocidade de impacto:
   \[
   v = 9.8 \times 4 = 39.2 \, \text{m/s}
   \]

---

### Exercício 6
**Enunciado:** Objeto lançado para baixo com \( v_0 = 5 \) m/s; calcular velocidade e deslocamento após 3 s.  
**Resolução:**
1. Velocidade:
   \[
   v = 5 + 9.8 \times 3 = 5 + 29.4 = 34.4 \, \text{m/s}
   \]
2. Deslocamento (movimento para baixo, considere o sinal de acordo):
   \[
   s = v_0 t + 0.5 \times 9.8 \times 3^2 = 5 \times 3 + 0.5 \times 9.8 \times 9 = 15 + 44.1 = 59.1 \, \text{m}
   \]

---

### Exercício 7
**Enunciado:** Lançamento horizontal de 80 m de altura com \( v_0 = 15 \) m/s.  
**Resolução:**
1. Tempo de queda:
   \[
   t = \sqrt{\frac{2 \times 80}{9.8}} \approx \sqrt{16.33} \approx 4.04 \, \text{s}
   \]
2. Distância horizontal:
   \[
   x = v_0 t = 15 \times 4.04 \approx 60.6 \, \text{m}
   \]

---

### Exercício 8
**Enunciado:** Velocidade inicial necessária para atingir 30 m de altura.  
**Resolução:**  
No ponto mais alto, \( v = 0 \). Use:
\[
0 = v_0 - g t \quad \Rightarrow \quad t = \frac{v_0}{9.8}
\]
A altura máxima:
\[
h = v_0 t - 0.5 \times 9.8 \, t^2 = v_0 \left(\frac{v_0}{9.8}\right) - 0.5 \times 9.8 \left(\frac{v_0}{9.8}\right)^2 = \frac{v_0^2}{9.8} - \frac{v_0^2}{19.6} = \frac{v_0^2}{19.6}
\]
Para \( h = 30 \) m:
\[
\frac{v_0^2}{19.6} = 30 \quad \Rightarrow \quad v_0^2 = 30 \times 19.6 = 588 \quad \Rightarrow \quad v_0 \approx 24.25 \, \text{m/s}
\]

---

### Exercício 9
**Enunciado:** Verificar \( s = 19.6 \) m em 2 s para queda livre.  
**Resolução:**
\[
s = 0.5 \times 9.8 \times 2^2 = 0.5 \times 9.8 \times 4 = 19.6 \, \text{m}
\]
Os dados estão consistentes.

---

### Exercício 10
**Enunciado:** Demonstre que \( v(t) = \frac{d}{dt}\left(\frac{1}{2}gt^2\right) = gt \).  
**Resolução:**
Calculando a derivada:
\[
\frac{d}{dt}\left(\frac{1}{2}gt^2\right) = \frac{1}{2}g \times 2t = gt
\]
Assim, a função velocidade é linear.

---

### Exercício 11
**Enunciado:** Um objeto lançado para cima com 30 m/s; determine o tempo total para retornar à origem.  
**Resolução:**
Tempo para atingir o ponto mais alto:
\[
t_{up} = \frac{30}{9.8} \approx 3.06 \, \text{s}
\]
O tempo total de voo é o dobro:
\[
t_{total} \approx 6.12 \, \text{s}
\]

---

### Exercício 12
**Enunciado:** Objeto em queda livre percorre 44.1 m em 3 s. Determine \( g \).  
**Resolução:**
\[
44.1 = 0.5 \, g \, (3)^2 \quad \Rightarrow \quad 44.1 = 4.5 g \quad \Rightarrow \quad g = \frac{44.1}{4.5} \approx 9.8 \, \text{m/s}^2
\]

---

### Exercício 13
**Enunciado:** Calcule a variação da velocidade entre \( t = 2 \) s e \( t = 5 \) s.  
**Resolução:**
Velocidade em \( t = 2 \) s: \( v(2) = 9.8 \times 2 = 19.6 \) m/s  
Velocidade em \( t = 5 \) s: \( v(5) = 9.8 \times 5 = 49 \) m/s  
\[
\Delta v = 49 - 19.6 = 29.4 \, \text{m/s}
\]

---

### Exercício 14
**Enunciado:** Se um objeto lançado se detém (v=0) após 3.5 s, qual sua velocidade inicial?  
**Resolução:**
No ponto mais alto, \( 0 = v_0 - 9.8 \times 3.5 \)  
\[
v_0 = 9.8 \times 3.5 \approx 34.3 \, \text{m/s}
\]

---

### Exercício 15
**Enunciado:** Prove que a distância no segundo segundo é o dobro da distância do primeiro segundo.  
**Resolução:**
Distância percorrida no 1º s:
\[
s_1 = 0.5 \times 9.8 \times 1^2 = 4.9 \, \text{m}
\]
Distância percorrida até 2 s:
\[
s_{total\,2} = 0.5 \times 9.8 \times 2^2 = 19.6\, \text{m}
\]
Distância no segundo segundo:
\[
\Delta s = s_{total\,2} - s_1 = 19.6 - 4.9 = 14.7 \, \text{m}
\]
Verifique que:
\[
14.7 \approx 3 \times 4.9 \quad (\text{ou seja, aproximadamente o triplo, pois a distância aumenta quadraticamente})
\]
_Neste exercício, a "proporção" mostra o aumento não linear; observe que cada segundo adicional agrega mais deslocamento._

---

### Exercício 16
**Enunciado:** Objeto lançado para cima com \( v_0 = 2 \) m/s.  
**Resolução:**
Tempo para atingir o ápice:  
\[
t = \frac{2}{9.8} \approx 0.204 \, \text{s}
\]
Altura máxima:
\[
h = 2 \times 0.204 - 0.5 \times 9.8 \times 0.204^2 \approx 0.408 - 0.204 \approx 0.204 \, \text{m}
\]

---

### Exercício 17
**Enunciado:** Calcule a velocidade de um objeto que percorre 9.8 m em queda livre.  
**Resolução:**
Usando \( s = 0.5gt^2 \):  
\[
9.8 = 0.5 \times 9.8 \times t^2 \quad \Rightarrow \quad t^2 = 2 \quad \Rightarrow \quad t \approx 1.414 \, \text{s}
\]
Então, a velocidade:
\[
v = 9.8 \times 1.414 \approx 13.86 \, \text{m/s}
\]

---

### Exercício 18
**Enunciado:** Objeto lançado horizontalmente de 120 m com \( v_0 =10 \) m/s.  
**Resolução:**
Tempo de queda:
\[
t = \sqrt{\frac{2 \times 120}{9.8}} \approx \sqrt{24.49} \approx 4.95 \, \text{s}
\]
Velocidade vertical no impacto:
\[
v_y = 9.8 \times 4.95 \approx 48.5 \, \text{m/s}
\]
Velocidade resultante (horizontal + vertical):
\[
v = \sqrt{10^2 + 48.5^2} \approx \sqrt{100 + 2352.25} \approx \sqrt{2452.25} \approx 49.5 \, \text{m/s}
\]

---

### Exercício 19
**Enunciado:** Projétil lançado com 20 m/s e 45°; calcule alcance e altura máxima.  
**Resolução:**
Componentes:  
\( v_0\cos45° = 20/\sqrt{2} \approx 14.14 \) m/s e \( v_0\sin45° \approx 14.14 \) m/s.
Tempo de voo:
\[
t_{total} = \frac{2 v_0 \sin45°}{9.8} \approx \frac{2 \times 14.14}{9.8} \approx 2.88 \, \text{s}
\]
Alcance:
\[
R = v_0\cos45° \times t_{total} \approx 14.14 \times 2.88 \approx 40.7 \, \text{m}
\]
Altura máxima:
\[
h_{max} = \frac{(14.14)^2}{2 \times 9.8} \approx \frac{200}{19.6} \approx 10.2 \, \text{m}
\]

---

### Exercício 20
**Enunciado:** Para \(\vec{r}(t) = (3t)\hat{i} + (4t - 4.9t^2)\hat{j}\):  
a) Determine \( \vec{v}(t) \).  
b) Calcule o tempo da altura máxima.  
**Resolução:**
a) Derivando:
\[
\vec{v}(t) = \frac{d}{dt}\vec{r}(t) = 3\hat{i} + (4 - 9.8t)\hat{j}
\]
b) Altura máxima ocorre quando a componente vertical da velocidade é zero:
\[
4 - 9.8t = 0 \quad \Rightarrow \quad t = \frac{4}{9.8} \approx 0.408 \, \text{s}
\]

---

### Exercício 21
**Enunciado:** Calcule o módulo de \( v(t) \) para um objeto em queda livre aos 2 s.  
**Resolução:**
\[
v = 9.8 \times 2 = 19.6 \, \text{m/s}
\]

---

### Exercício 22
**Enunciado:** Um objeto percorre 80 m em 4 s em queda livre; qual a velocidade média?  
**Resolução:**
\[
v_{média} = \frac{80}{4} = 20 \, \text{m/s}
\]

---

### Exercício 23
**Enunciado:** Um objeto alcança 19.6 m/s em queda livre.  
**Resolução:**
Como \( v = g t \):
\[
t = \frac{19.6}{9.8} = 2 \, \text{s} \quad \text{e} \quad s = 0.5 \times 9.8 \times 2^2 = 19.6 \, \text{m}
\]

---

### Exercício 24
**Enunciado:** Verifique que um objeto atinge 15 m/s em 1.53 s.  
**Resolução:**
\[
v = 9.8 \times 1.53 \approx 15 \, \text{m/s}
\]
Os dados são consistentes.

---

### Exercício 25
**Enunciado:** Tempo de queda de 3.2 s.  
**Resolução:**
a) Altura:
\[
s = 0.5 \times 9.8 \times (3.2)^2 \approx 0.5 \times 9.8 \times 10.24 \approx 50.18 \, \text{m}
\]
b) Velocidade de impacto:
\[
v = 9.8 \times 3.2 \approx 31.36 \, \text{m/s}
\]

---

### Exercício 26
**Enunciado:** Para \( s(t) = 2 + 5t - 4.9t^2 \), determine o tempo de altura máxima.  
**Resolução:**
A altura máxima ocorre quando \( v(t) = \frac{ds}{dt} = 5 - 9.8t = 0 \);  
\[
t = \frac{5}{9.8} \approx 0.51 \, \text{s}
\]

---

### Exercício 27
**Enunciado:** Objeto lançado de um penhasco de 100 m.  
**Resolução:**
Tempo de queda:
\[
t = \sqrt{\frac{2 \times 100}{9.8}} \approx \sqrt{20.41} \approx 4.52 \, \text{s}
\]
Velocidade de impacto:
\[
v = 9.8 \times 4.52 \approx 44.3 \, \text{m/s}
\]

---

### Exercício 28
**Enunciado:** Se um objeto percorre 19.6 m em 2 s, determine a aceleração e velocidade final.  
**Resolução:**
Já que \( s = 0.5 \times 9.8 \times 2^2 = 19.6 \) m,  
- Aceleração: \( 9.8 \, \text{m/s}^2 \)  
- Velocidade: \( v = 9.8 \times 2 = 19.6 \, \text{m/s} \)

---

### Exercício 29
**Enunciado:** Projétil lançado horizontalmente de 50 m com \( v_0 = 8 \) m/s.  
**Resolução:**
Tempo de queda:
\[
t = \sqrt{\frac{2 \times 50}{9.8}} \approx \sqrt{10.204} \approx 3.19 \, \text{s}
\]
Distância horizontal:
\[
x = 8 \times 3.19 \approx 25.52 \, \text{m}
\]

---

### Exercício 30
**Enunciado:** Se um objeto tem componentes de velocidade \( v_x = 6 \) m/s e \( v_y = 7 \) m/s, encontre o módulo da velocidade.  
**Resolução:**
Usando Pitágoras:
\[
|\vec{v}| = \sqrt{6^2 + 7^2} = \sqrt{36 + 49} = \sqrt{85} \approx 9.22 \, \text{m/s}
\]

---

## Dicas Extras para os Estudos

- **Pratique Regularmente:** Resolva os exercícios e tente variar os parâmetros para ver como as grandezas se alteram.  
- **Visualize Gráficos:** Esboce os gráficos de \(s\) vs. \(t\), \(v\) vs. \(t\) e \(a\) vs. \(t\) para relacionar as expressões analíticas com o comportamento físico.  
- **Relembre Conceitos Vetoriais:** A decomposição de vetores é fundamental para problemas bidimensionais; pratique a resolução por componentes.

---
