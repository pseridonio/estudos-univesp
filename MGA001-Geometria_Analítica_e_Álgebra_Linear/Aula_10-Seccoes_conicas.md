# Seções Cônicas: Uma Análise Completa

As **seções cônicas** surgem da interseção de um plano com um **cone duplo**. Dependendo do ângulo de corte do plano em relação ao eixo do cone, temos curvas distintas:  
- **Circunferência:** Caso especial da elipse obtido quando o corte é perpendicular à base do cone.  
- **Elipse:** Quando o corte não é paralelo a nenhuma geratriz do cone, desde que não passe pelo vértice.  
- **Parábola:** Quando o plano é paralelo a uma geratriz do cone.  
- **Hipérbole:** Quando o corte intercepta ambas as “folhas” do cone.  

Além dessas, podem ocorrer as chamadas **cônicas degeneradas**, que podem se reduzir a um ponto, uma reta ou um par de retas, dependendo das condições do corte.

---

## 1. Introdução

O estudo das seções cônicas remonta à Grécia antiga e foi aprimorado com a sistematização da geometria analítica por René Descartes e Pierre de Fermat. Atualmente, a representação algébrica de cada cônica por meio de equações canônicas facilita a análise de suas propriedades, suas aplicações em física, engenharia, astronomia e em diversas áreas do conhecimento.

---

## 2. Tipos de Seções Cônicas e suas Propriedades

### 2.1. Círculo
- **Definição:** Conjunto de pontos equidistantes de um ponto fixo (centro).  
- **Equação canônica:**  
  \[
  (x - h)^2 + (y - k)^2 = r^2
  \]
  onde \((h,k)\) é o centro e \(r\) é o raio.

### 2.2. Elipse
- **Definição:** Conjunto de pontos em que a soma das distâncias a dois pontos fixos (focos) é constante.  
- **Equação canônica:**  
  \[
  \frac{(x-h)^2}{a^2} + \frac{(y-k)^2}{b^2} = 1
  \]
  com \(a > b\) (quando o eixo maior é horizontal) e os focos localizados a uma distância \(c\) do centro, onde  
  \[
  c = \sqrt{a^2 - b^2}.
  \]

### 2.3. Parábola
- **Definição:** Conjunto de pontos que estão equidistantes de um ponto fixo (foco) e de uma reta fixa (diretriz).  
- **Equação canônica (parábola vertical):**  
  \[
  (x-h)^2 = 4p(y-k)
  \]
  ou (parábola horizontal):
  \[
  (y-k)^2 = 4p(x-h)
  \]
  onde \((h,k)\) é o vértice e \(p\) representa a distância do vértice ao foco. O sinal de \(p\) indica a direção de abertura.

### 2.4. Hipérbole
- **Definição:** Conjunto de pontos cuja diferença absoluta das distâncias a dois pontos fixos (focos) é constante.  
- **Equação canônica (hipérbole com eixo horizontal):**  
  \[
  \frac{(x-h)^2}{a^2} - \frac{(y-k)^2}{b^2} = 1
  \]
  ou (hipérbole com eixo vertical):
  \[
  \frac{(y-k)^2}{a^2} - \frac{(x-h)^2}{b^2} = 1.
  \]

### 2.5. Cônicas Degeneradas
Dependendo das condições do corte (por exemplo, quando o plano passa pelo vértice do cone ou é tangente a este), as seções cônicas podem degenerar em:
- Um único ponto;
- Uma reta;
- Um par de retas concorrentes.

---

## 3. Aplicações

As seções cônicas são fundamentais em diversas áreas, como:  
- **Parábolas:** Trajetórias de projéteis, antenas parabólicas, coletores de energia solar.  
- **Elipses:** Órbitas planetárias, propriedades ópticas e acústicas, design e arquitetura.  
- **Hipérboles:** Sistemas de comunicação, modelagem de trajetórias em certos regimes físicos.  
- **Circunferências:** Movimentos circulares, simetria em projetos gráficos e engenharia.

---

## 4. Exercícios e Resoluções Detalhadas

A seguir, uma lista de 30 exercícios sobre seções cônicas com suas resoluções completas.

### **Exercício 1: Identificação de Círculo**  
- **Enunciado:** Identifique o tipo de cônica representada pela equação  
  \[
  (x-3)^2 + (y+2)^2 = 16.
  \]
- **Resolução:**  
  A equação está na forma canônica de um **círculo** com centro em \( (3, -2) \) e raio \( r = \sqrt{16} = 4 \).

---

### **Exercício 2: Centro e Raio de um Círculo**  
- **Enunciado:** Encontre o centro e o raio do círculo cuja equação é  
  \[
  x^2 + y^2 - 6x + 4y - 12 = 0.
  \]
- **Resolução:**  
  Agrupe os termos de \(x\) e \(y\):
  \[
  x^2 - 6x + y^2 + 4y = 12.
  \]
  Complete os quadrados:
  - Para \(x\): \(x^2 - 6x = (x-3)^2 - 9\).
  - Para \(y\): \(y^2 + 4y = (y+2)^2 - 4\).
  
  Assim:
  \[
  (x-3)^2 + (y+2)^2 = 12 + 9 + 4 = 25.
  \]
  O círculo tem centro \( (3, -2) \) e raio \( r = 5 \).

---

### **Exercício 3: Identificação de Elipse**  
- **Enunciado:** Determine o tipo de cônica representada por  
  \[
  \frac{(x-1)^2}{25} + \frac{(y+2)^2}{9} = 1.
  \]
- **Resolução:**  
  Esta é a equação canônica de uma **elipse** com centro em \( (1, -2) \), semieixo maior \( a = 5 \) e semieixo menor \( b = 3 \).

---

### **Exercício 4: Focos de uma Elipse**  
- **Enunciado:** Para a elipse  
  \[
  \frac{(x+2)^2}{36} + \frac{(y-3)^2}{16} = 1,
  \]
  determine as coordenadas dos focos.
- **Resolução:**  
  O centro é \( (-2, 3) \). Aqui, \(a^2 = 36\) e \(b^2 = 16\) (com \(a = 6\) e \(b = 4\)).  
  O parâmetro \(c\) é dado por:  
  \[
  c = \sqrt{a^2 - b^2} = \sqrt{36 - 16} = \sqrt{20} = 2\sqrt{5}.
  \]
  Assim, os focos estão em:
  \[
  F_1 = \left(-2 + 2\sqrt{5},\, 3\right) \quad \text{e} \quad F_2 = \left(-2 - 2\sqrt{5},\, 3\right).
  \]

---

### **Exercício 5: Equação Geral para Círculo**  
- **Enunciado:** Prove que a equação  
  \[
  x^2 + y^2 + 4x - 2y - 11 = 0
  \]
  representa um círculo e determine seu centro e raio.
- **Resolução:**  
  Reescreva agrupando os termos:
  \[
  x^2 + 4x + y^2 - 2y = 11.
  \]
  Complete os quadrados:
  - \(x^2 + 4x = (x+2)^2 - 4\).
  - \(y^2 - 2y = (y-1)^2 - 1\).
  
  Assim:
  \[
  (x+2)^2 + (y-1)^2 = 11 + 4 + 1 = 16.
  \]
  O círculo tem centro \( (-2, 1) \) e raio \( r = 4 \).

---

### **Exercício 6: Transformação da Equação de uma Elipse**  
- **Enunciado:** Transforme a equação  
  \[
  9x^2 + 16y^2 - 54x + 64y + 61 = 0
  \]
  para sua forma canônica e identifique a cônica.
- **Resolução:**  
  Agrupe os termos:
  \[
  9x^2 - 54x + 16y^2 + 64y = -61.
  \]
  Para \(x\):  
  \[
  9(x^2 - 6x) = 9[(x-3)^2 - 9].
  \]
  Para \(y\):  
  \[
  16(y^2 + 4y) = 16[(y+2)^2 - 4].
  \]
  Substituindo:
  \[
  9(x-3)^2 - 81 + 16(y+2)^2 - 64 = -61.
  \]
  Reorganize:
  \[
  9(x-3)^2 + 16(y+2)^2 = 84.
  \]
  Dividindo ambos os lados por 84:
  \[
  \frac{(x-3)^2}{84/9} + \frac{(y+2)^2}{84/16} = 1.
  \]
  Essa é a equação de uma **elipse** com centro em \( (3, -2) \).

---

### **Exercício 7: Identificação de Parábola**  
- **Enunciado:** Determine o tipo de cônica representada pela equação  
  \[
  y^2 - 8y - 4x + 16 = 0.
  \]
- **Resolução:**  
  Organize os termos:
  \[
  y^2 - 8y = 4x - 16.
  \]
  Complete o quadrado em \(y\):
  \[
  y^2 - 8y + 16 = 4x - 16 + 16,
  \]
  ou seja,
  \[
  (y-4)^2 = 4x.
  \]
  Esta é a equação canônica de uma **parábola** com vértice em \( (0,4) \) que abre para a direita.

---

### **Exercício 8: Vértice e Foco de uma Parábola**  
- **Enunciado:** Encontre o vértice e o foco da parábola dada por  
  \[
  (x+2)^2 = 12(y-3).
  \]
- **Resolução:**  
  Comparando com a forma \((x-h)^2 = 4p(y-k)\), temos:
  - \(h = -2,\; k = 3\),
  - \(4p = 12 \Rightarrow p = 3\).
  
  Assim, o vértice é \( (-2, 3) \) e o foco é \( (-2, 3+3) = (-2, 6) \).

---

### **Exercício 9: Identificação de Hipérbole**  
- **Enunciado:** Classifique a cônica e determine seu centro e vértices para a equação  
  \[
  9x^2 - 16y^2 = 144.
  \]
- **Resolução:**  
  Dividindo ambos os lados por 144:
  \[
  \frac{x^2}{16} - \frac{y^2}{9} = 1.
  \]
  Trata-se de uma **hipérbole** com centro em \( (0,0) \) e vértices em \( (\pm4, 0) \).

---

### **Exercício 10: Assíntotas da Hipérbole**  
- **Enunciado:** Encontre as equações das assíntotas para a hipérbole  
  \[
  \frac{(x-1)^2}{9} - \frac{(y+2)^2}{16} = 1.
  \]
- **Resolução:**  
  O centro é \( (1, -2) \) com \(a = 3\) e \(b = 4\). As assíntotas são dadas por:
  \[
  y + 2 = \pm \frac{b}{a}(x-1) = \pm \frac{4}{3}(x-1).
  \]

---

### **Exercício 11: Cônica Degenerada (Ponto)**  
- **Enunciado:** Mostre que a equação  
  \[
  x^2 + 4x + 4 + y^2 - 6y + 9 = 0
  \]
  representa um único ponto.
- **Resolução:**  
  Reescreva como:
  \[
  (x+2)^2 + (y-3)^2 = 0.
  \]
  A única solução é \( x = -2 \) e \( y = 3 \); assim, a cônica degenera em um **ponto**.

---

### **Exercício 12: Cônica Degenerada (Retas)**  
- **Enunciado:** Explique por que a equação  
  \[
  x^2 - y^2 = 0
  \]
  representa duas retas concorrentes.
- **Resolução:**  
  Fatorando:
  \[
  x^2 - y^2 = (x-y)(x+y) = 0,
  \]
  obtemos as equações das retas:
  \[
  x - y = 0 \quad \text{ou} \quad x + y = 0,
  \]
  correspondendo às retas \( y = x \) e \( y = -x \).

---

### **Exercício 13: Excentricidade de uma Elipse**  
- **Enunciado:** Calcule a excentricidade da elipse  
  \[
  \frac{x^2}{16} + \frac{y^2}{9} = 1.
  \]
- **Resolução:**  
  Aqui, \(a = 4\) e \(b = 3\). Assim:
  \[
  e = \frac{\sqrt{a^2 - b^2}}{a} = \frac{\sqrt{16-9}}{4} = \frac{\sqrt{7}}{4}.
  \]

---

### **Exercício 14: Excentricidade de uma Hipérbole**  
- **Enunciado:** Determine a excentricidade da hipérbole  
  \[
  \frac{x^2}{25} - \frac{y^2}{9} = 1.
  \]
- **Resolução:**  
  Neste caso, \(a = 5\) e \(b = 3\). A excentricidade é:
  \[
  e = \sqrt{1 + \frac{b^2}{a^2}} = \sqrt{1 + \frac{9}{25}} = \sqrt{\frac{34}{25}} = \frac{\sqrt{34}}{5}.
  \]

---

### **Exercício 15: Diretriz de uma Parábola**  
- **Enunciado:** Determine a equação da diretriz da parábola  
  \[
  (x-2)^2 = 12(y+3).
  \]
- **Resolução:**  
  Comparando com \((x-h)^2 = 4p(y-k)\), temos \(h = 2\), \(k = -3\) e \(4p = 12\) (portanto, \(p = 3\)).  
  Como a parábola abre para cima, a diretriz é:
  \[
  y = k - p = -3 - 3 = -6.
  \]

---

### **Exercício 16: Elipse a Partir dos Focos**  
- **Enunciado:** Uma elipse tem focos em \((0, 4)\) e \((0, -4)\) e o comprimento do eixo maior é 10. Encontre sua equação.
- **Resolução:**  
  O centro é \( (0,0) \) e \( 2a = 10 \) (ou seja, \( a=5 \)). Como os focos estão no eixo vertical, temos \( c = 4 \) e:
  \[
  b^2 = a^2 - c^2 = 25 - 16 = 9.
  \]
  A equação, considerando que o eixo maior é vertical, é:
  \[
  \frac{x^2}{9} + \frac{y^2}{25} = 1.
  \]

---

### **Exercício 17: Hipérbole a Partir dos Focos e Vértices**  
- **Enunciado:** Uma hipérbole tem focos em \((\pm7, 0)\) e vértices em \((\pm5, 0)\). Encontre sua equação.
- **Resolução:**  
  O centro é \( (0,0) \) e \( a = 5 \). Com \( c = 7 \), temos:
  \[
  b^2 = c^2 - a^2 = 49 - 25 = 24.
  \]
  Assim, a equação da hipérbole é:
  \[
  \frac{x^2}{25} - \frac{y^2}{24} = 1.
  \]

---

### **Exercício 18: Equação da Parábola a Partir de Foco e Diretriz**  
- **Enunciado:** Dada uma parábola com foco em \((2, 3)\) e diretriz \(y = 1\), encontre sua equação.
- **Resolução:**  
  O vértice é o ponto médio entre o foco e a diretriz. Assim, o vértice é \( (2, 2) \) e \( p = 1 \) (distância do vértice até o foco).  
  A equação canônica é:
  \[
  (x-2)^2 = 4(y-2).
  \]

---

### **Exercício 19: Elipse com Centro e Eixos Dadas**  
- **Enunciado:** Encontre a equação da elipse com centro em \((-1, 2)\), eixo maior horizontal de comprimento 12 e eixo menor vertical de comprimento 8.
- **Resolução:**  
  Temos:  
  - \(a = \frac{12}{2} = 6\),  
  - \(b = \frac{8}{2} = 4\).  
  
  A equação da elipse é:
  \[
  \frac{(x+1)^2}{36} + \frac{(y-2)^2}{16} = 1.
  \]

---

### **Exercício 20: Identificação de Cônica a Partir da Equação Geral**  
- **Enunciado:** Classifique a cônica e determine seu centro para a equação  
  \[
  4x^2 + 9y^2 - 24x + 36y + 36 = 0.
  \]
- **Resolução:**  
  Reorganize os termos:
  \[
  4x^2 - 24x + 9y^2 + 36y = -36.
  \]
  Complete os quadrados:  
  - Para \(x\): \(4(x^2 - 6x + 9) = 4(x-3)^2\) (adicione \(4 \times 9 = 36\)).  
  - Para \(y\): \(9(y^2 + 4y + 4) = 9(y+2)^2\) (adicione \(9 \times 4 = 36\)).
  
  Assim:
  \[
  4(x-3)^2 + 9(y+2)^2 = -36 + 36 + 36 = 36.
  \]
  Dividindo ambos os lados por 36:
  \[
  \frac{(x-3)^2}{9} + \frac{(y+2)^2}{4} = 1.
  \]
  Trata-se de uma **elipse** com centro em \( (3, -2) \).

---

### **Exercício 21: Hipérbole com Assíntotas Dadas**  
- **Enunciado:** Encontre a equação da hipérbole com centro em \( (0,0) \), vértices em \( ( \pm 4, 0) \) e assíntotas \( y = \pm \frac{3}{4}x \).
- **Resolução:**  
  Aqui, \( a = 4 \) e, como as assíntotas são \( y = \pm \frac{b}{a}x \), temos:
  \[
  \frac{b}{4} = \frac{3}{4} \quad \Rightarrow \quad b = 3.
  \]
  A equação é:
  \[
  \frac{x^2}{16} - \frac{y^2}{9} = 1.
  \]

---

### **Exercício 22: Parábola com Vértice e Foco Dado**  
- **Enunciado:** Encontre a equação da parábola com vértice em \( (1, -1) \) e foco em \( (1, 2) \).
- **Resolução:**  
  A distância entre o vértice e o foco é \( p = 3 \) (parábola vertical). Assim, a equação é:
  \[
  (x-1)^2 = 4 \cdot 3 \,(y + 1) \quad \Rightarrow \quad (x-1)^2 = 12(y+1).
  \]

---

### **Exercício 23: Transformação de Equação Geral para Forma Canônica**  
- **Enunciado:** Transforme a equação  
  \[
  9x^2 + 16y^2 - 18x + 32y - 11 = 0
  \]
  para sua forma canônica.
- **Resolução:**  
  Organize os termos:
  \[
  9x^2 - 18x + 16y^2 + 32y = 11.
  \]
  Complete os quadrados:
  - Para \(x\): \(9(x^2 - 2x)\). Adicione e subtraia \(9(1)=9\) para formar \((x-1)^2\).
  - Para \(y\): \(16(y^2 + 2y)\). Adicione e subtraia \(16(1)=16\) para formar \((y+1)^2\).
  
  Assim:
  \[
  9(x-1)^2 + 16(y+1)^2 = 11 + 9 + 16 = 36.
  \]
  Dividindo por 36:
  \[
  \frac{(x-1)^2}{4} + \frac{(y+1)^2}{\frac{36}{16}} = 1 \quad \text{ou} \quad \frac{(x-1)^2}{4} + \frac{(y+1)^2}{\frac{9}{4}} = 1.
  \]
  Trata-se de uma **elipse** com centro em \( (1, -1) \).

---

### **Exercício 24: Interseção de uma Elipse com uma Reta**  
- **Enunciado:** Dada a elipse  
  \[
  \frac{x^2}{16} + \frac{y^2}{9} = 1,
  \]
  e a reta \( y = 2 \), encontre os pontos de interseção.
- **Resolução:**  
  Substitua \( y = 2 \) na equação da elipse:
  \[
  \frac{x^2}{16} + \frac{4}{9} = 1 \quad \Rightarrow \quad \frac{x^2}{16} = 1 - \frac{4}{9} = \frac{5}{9}.
  \]
  Assim,
  \[
  x^2 = 16 \cdot \frac{5}{9} = \frac{80}{9} \quad \Rightarrow \quad x = \pm \sqrt{\frac{80}{9}} = \pm \frac{4\sqrt{5}}{3}.
  \]
  Os pontos de interseção são:
  \[
  \left(\frac{4\sqrt{5}}{3}, 2\right) \quad \text{e} \quad \left(-\frac{4\sqrt{5}}{3}, 2\right).
  \]

---

### **Exercício 25: Reta Tangente à Elipse**  
- **Enunciado:** Encontre a reta tangente à elipse  
  \[
  \frac{x^2}{9} + \frac{y^2}{4} = 1,
  \]
  no ponto \( (3,0) \).
- **Resolução:**  
  Como \( (3,0) \) é um ponto da elipse, e para \( x = 3 \) temos \( \frac{9}{9}+\frac{0}{4}=1 \), nota-se que a reta tangente é vertical.  
  Portanto, a reta é:
  \[
  x = 3.
  \]

---

### **Exercício 26: Reta Tangente à Parábola**  
- **Enunciado:** Encontre a reta tangente à parábola \( y^2 = 8x \) no ponto \( (2, 4) \).
- **Resolução:**  
  Diferenciando implicitamente \( y^2 = 8x \):
  \[
  2y \frac{dy}{dx} = 8 \quad \Rightarrow \quad \frac{dy}{dx} = \frac{4}{y}.
  \]
  No ponto \( (2,4) \), \( \frac{dy}{dx} = \frac{4}{4} = 1 \). Utilizando a forma ponto-inclinação:
  \[
  y - 4 = 1 \cdot (x - 2) \quad \Rightarrow \quad y = x + 2.
  \]

---

### **Exercício 27: Distância Entre os Focos de uma Elipse**  
- **Enunciado:** Calcule a distância entre os focos da elipse  
  \[
  \frac{(x-1)^2}{49} + \frac{(y+2)^2}{25} = 1.
  \]
- **Resolução:**  
  Aqui, \( a^2 = 49 \) (logo, \( a = 7 \)) e \( b^2 = 25 \) (logo, \( b = 5 \)). O parâmetro \( c \) é:
  \[
  c = \sqrt{a^2 - b^2} = \sqrt{49 - 25} = \sqrt{24} = 2\sqrt{6}.
  \]
  Assim, a distância entre os focos é:
  \[
  2c = 4\sqrt{6}.
  \]
  (Observação: os focos, nesta elipse horizontal, são \( \left(1 \pm 2\sqrt{6}, -2\right) \).)

---

### **Exercício 28: Hipérbole com Assíntotas e Ponto Dado**  
- **Enunciado:** Determine a equação da hipérbole com assíntotas \( y = \pm \frac{2}{3}x \) que passa pelo ponto \( (6,6) \).
- **Resolução:**  
  Uma hipérbole com centro em \( (0,0) \) e com eixo vertical pode ser escrita como:
  \[
  \frac{y^2}{b^2} - \frac{x^2}{a^2} = 1,
  \]
  com assíntotas \( y = \pm \frac{b}{a}x \). Para termos \( \frac{b}{a} = \frac{2}{3} \), basta definir \( b = \frac{2a}{3} \).  
  Como o ponto \( (6,6) \) deve satisfazer a equação:
  \[
  \frac{36}{b^2} - \frac{36}{a^2} = 1,
  \]
  substitua \( b = \frac{2a}{3} \) (então \( b^2 = \frac{4a^2}{9} \)):
  \[
  \frac{36 \cdot 9}{4a^2} - \frac{36}{a^2} = 1 \quad \Rightarrow \quad \frac{324}{4a^2} - \frac{36}{a^2} = 1.
  \]
  Simplificando:
  \[
  \frac{324 - 144}{4a^2} = 1 \quad \Rightarrow \quad \frac{180}{4a^2} = 1 \quad \Rightarrow \quad a^2 = \frac{180}{4} = 45.
  \]
  Assim, \( a = \sqrt{45} = 3\sqrt{5} \) e \( b = \frac{2a}{3} = 2\sqrt{5} \).  
  A equação da hipérbole é:
  \[
  \frac{y^2}{(2\sqrt{5})^2} - \frac{x^2}{45} = 1 \quad \Rightarrow \quad \frac{y^2}{20} - \frac{x^2}{45} = 1.
  \]

---

### **Exercício 29: Coordenadas do Foco de uma Parábola**  
- **Enunciado:** Encontre as coordenadas do foco da parábola dada por  
  \[
  y^2 = 12x.
  \]
- **Resolução:**  
  Comparando com \( y^2 = 4px \), temos \( 4p = 12 \) e, portanto, \( p = 3 \).  
  Assim, o foco da parábola é:
  \[
  (3, 0).
  \]

---

### **Exercício 30: Aplicação Prática – Antena Parabólica**  
- **Enunciado:** Uma antena parabólica tem a equação da sua seção transversal dada por  
  \[
  (x-2)^2 = 8(y+1).
  \]
  Determine o foco da parábola, que corresponde ao ponto onde o sinal é concentrado.
- **Resolução:**  
  Comparando com \((x-h)^2 = 4p(y-k)\), temos:
  - \(h = 2\) e \(k = -1\);
  - \(4p = 8\) resultando em \(p = 2\).
  
  Portanto, o foco é:
  \[
  (2,\, -1 + 2) = (2, 1).
  \]

---

## 5. Bibliografia

1. **Univesp.** Geometria Analítica e Álgebra Linear – Seções Cônicas. Disponível no YouTube: [Geometria analítica e álgebra linear – Seções Cônicas](https://www.youtube.com/watch?v=JFw57fQ5oe8&t=824s).
2. **Toda Matéria.** Artigos e materiais sobre seções cônicas e exercícios.
3. **Mundo Educação.** Seções Cônicas: Conceitos, exemplos e aplicações.
4. Outros recursos confiáveis em educação matemática e geometria analítica.

