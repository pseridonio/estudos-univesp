---
title: O Plano Cartesiano — pontos, distâncias, retas e lugares geométricos
---

# O Plano Cartesiano — pontos, distâncias, retas e lugares geométricos

## Introdução

Este material desenvolve, de forma organizada e didática, os conceitos tratados na videoaula "O Plano Cartesiano" (transcrição disponível na aba atual): definição do plano cartesiano, quadrantes, distância entre pontos, lugares geométricos (circunferência), equações de retas e procedimentos práticos para resolver problemas geométricos. O conteúdo foi construído a partir da transcrição do vídeo e complementado com referências didáticas confiáveis.

---

## Desenvolvimento

### Plano cartesiano: definição e representação
- Definição e componentes principais:
  - O plano cartesiano é o conjunto de pares ordenados \((x,y)\) com dois eixos perpendiculares: o eixo horizontal \(x\) e o eixo vertical \(y\).
  - Cada ponto \(P\) no plano é identificado por um par ordenado \(P=(x,y)\), onde \(x\) é a abscissa e \(y\) é a ordenada.
- Observações práticas:
  - A ordem das coordenadas importa: \((x,y)\) não é, em geral, igual a \((y,x)\).
  - Os eixos determinam a grade de referência para localizar pontos e desenhar figuras.

(Conteúdo alinhado com a explicação e exemplos da videoaula sobre identificação de pontos e eixos.)

---

### Quadrantes do plano
- Classificação:
  - Quadrante I: \(x>0, y>0\).  
  - Quadrante II: \(x<0, y>0\).  
  - Quadrante III: \(x<0, y<0\).  
  - Quadrante IV: \(x>0, y<0\).
- Uso: ao analisar sinais das coordenadas fica mais rápido prever posição aproximada de um ponto sem cálculo.

---

### Distância entre dois pontos — dedução e fórmula
- Problema: dados \(A=(x_1,y_1)\) e \(B=(x_2,y_2)\), encontrar a distância \(d(A,B)\).  
- Lógica geométrica (teorema de Pitágoras):
  - Construa o ponto auxiliar \(C=(x_2,y_1)\). Os segmentos \(AC\) e \(CB\) formam os catetos de um triângulo retângulo cuja hipotenusa é \(AB\).
  - Comprimentos dos catetos:
    - \(AC = |x_2 - x_1|\).
    - \(CB = |y_2 - y_1|\).
- Fórmula final :  
  \[
  d(A,B)=\sqrt{(x_2-x_1)^2 + (y_2-y_1)^2}.
  \]
- Casos especiais:
  - Mesma altura (\(y_1=y_2\)): \(d=|x_2-x_1|\).
  - Mesma abscissa (\(x_1=x_2\)): \(d=|y_2-y_1|\).
- Exemplo resolvido:
  - \(A=(1,1)\), \(B=(3,2)\).
  - Cálculo:
    \[
    d(A,B)=\sqrt{(3-1)^2+(2-1)^2}=\sqrt{4+1}=\sqrt{5}.
    \]

(Explicação alinhada com a construção e a motivação geométrica exibidas na videoaula.)

---

### Lugar geométrico e circunferência
- Definição de lugar geométrico:
  - Conjunto de pontos que satisfazem uma propriedade geométrica dada por uma equação ou condição.
- Circunferência:
  - Uma circunferência de centro \((a,b)\) e raio \(R\) é o conjunto de pontos \((x,y)\) que satisfazem:
    \[
    (x-a)^2 + (y-b)^2 = R^2.
    \]
  - Interpretação: todos os pontos cuja distância até \((a,b)\) é igual a \(R\).
- Observação sobre função vs. lugar geométrico:
  - Nem todo lugar geométrico é gráfico de função \(y=f(x)\): por exemplo, uma circunferência normalmente tem dois valores de \(y\) para um mesmo \(x\), portanto não é função única de \(x\).

---

### Equação da reta: formas e construção por dois pontos
- Formas usuais:
  - Forma geral (implícita):
    \[
    a x + b y = c, \qquad (a, b) \neq (0,0).
    \]
  - Forma ponto-declive (slope-intercept / point-slope):
    \[
    y - y_1 = m (x - x_1),
    \]
    onde \(m\) é o coeficiente angular.
- Cálculo do coeficiente angular a partir de dois pontos \(P_1=(x_1,y_1)\) e \(P_2=(x_2,y_2)\) (quando \(x_1\neq x_2\)):
  \[
  m = \frac{y_2-y_1}{x_2-x_1}.
  \]
- Retas especiais:
  - Reta vertical: \(x=x_0\) (quando \(x_1=x_2=x_0\)).
  - Reta horizontal: \(y=y_0\) (quando \(y_1=y_2=y_0\)).
- Exemplo resolvido:
  - \(P_1=(0,1)\), \(P_2=(1,0)\).
  - \(m=(0-1)/(1-0)=-1\).
  - Equação: \(y-1=-1(x-0)\) ⇒ \(y=-x+1\) ⇒ forma geral \(x+y=1\).

(Apresentação e exemplos coerentes com a videoaula que mostra variações de parâmetros e efeitos geométricos sobre a reta.)

---

## Aplicações práticas e dicas de resolução

- Ao calcular distâncias, use primeiro os casos especiais (mesma abscissa ou mesma ordenada) para simplificar.
- Ao traçar curvas, explore simetrias do lugar geométrico (e.g., circunferência centrada no eixo).
- Ao obter interseção reta–circunferência, substitua a expressão de \(y\) (ou \(x\)) na equação da circunferência e resolva o polinômio resultante.
- Para obter uma reta por dois pontos, sempre verifique se não há divisão por zero no cálculo do declive (caso de reta vertical).

---

## Exercícios (com resolução detalhada)

Cada exercício tem solução passo a passo; as fórmulas estão em LaTeX.

1) Distância entre pontos  
   - Enunciado: calcule a distância entre \(A=(2,-1)\) e \(B=(-1,3)\).  
   - Solução:  
     \[d(A,B)=\sqrt{(-1-2)^2+(3-(-1))^2}=\sqrt{(-3)^2+4^2}=\sqrt{9+16}=\sqrt{25}=5.\]  

2) Reta definida por dois pontos
   - Enunciado: encontre a equação da reta que passa por \(P_1=(1,2)\) e \(P_2=(4,5)\).
   - Solução:  
     \[
     m=\frac{5-2}{4-1}=1,\qquad y-2=1(x-1)\Rightarrow y=x+1.
     \]

3) Circunferência por centro e raio
   - Enunciado: escreva a equação da circunferência de centro \((0,0)\) e raio \(3\).
   - Solução:
     \[
     x^2+y^2=9.
     \]

4) Interseção reta–circunferência
   - Enunciado: encontre os pontos de interseção entre \(y=x+1\) e \(x^2+y^2=9\).
   - Solução:
     \[
     x^2+(x+1)^2=9 \Rightarrow 2x^2+2x-8=0 \Rightarrow x^2+x-4=0.
     \]
     Aplicando a fórmula quadrática:
     \[
     x=\frac{-1\pm\sqrt{1+16}}{2}=\frac{-1\pm\sqrt{17}}{2},
     \]
     e \(y=x+1\) fornece os correspondentes valores de \(y\).

5) Pertinência a um círculo
   - Enunciado: verifica se \(P=(3,4)\) pertence ao círculo \((x-1)^2+(y-2)^2=5\).
   - Solução:
     \[
     (3-1)^2+(4-2)^2=2^2+2^2=4+4=8\neq5,
     \]
     logo \(P\) não pertence ao círculo.

6) Reta vertical
   - Enunciado: encontre a reta que passa por \(P_1=(2,-1)\) e \(P_2=(2,3)\).
   - Solução: como \(x_1=x_2=2\) a reta é \(x=2\).

7) Distância ponto–reta (introdução)
   - Enunciado: calcule a distância do ponto \(P_0=(x_0,y_0)\) à reta \(a x + b y + c = 0\).
   - Fórmula:
     \[
     d=\frac{|a x_0 + b y_0 + c|}{\sqrt{a^2+b^2}}.
     \]
   - Observação: aplicar quando solicitado; dedução via projeção ortogonal.

8) Lugar geométrico (elipse simples)
   - Enunciado: descreva o lugar geométrico dos pontos cuja soma das distâncias a \(F_1=(1,0)\) e \(F_2=(-1,0)\) é constante igual a \(4\).
   - Solução: é uma elipse com focos \(F_1,F_2\) e semi-eixo maior \(a=2\).

9) Converter forma ponto-declive para geral
   - Enunciado: converter \(y-2=-2(x-3)\) para a forma geral.
   - Solução:
     \[
     y-2=-2x+6 \Rightarrow 2x+y=8.
     \]

10) Problema aplicado (integração de conceitos)
    - Enunciado: determinar a equação da reta que passa pelo ponto médio entre \(A=(0,2)\) e \(B=(4,0)\) e é perpendicular à reta que passa por \(A\) e \(B\).
    - Solução:
      - Ponto médio \(M=\left(\frac{0+4}{2},\frac{2+0}{2}\right)=(2,1)\).
      - Reta \(AB\): declive \(m_{AB}=\frac{0-2}{4-0}=-\tfrac{1}{2}\).
      - Reta perpendicular tem declive \(m=-\frac{1}{m_{AB}}=2\).
      - Equação: \(y-1=2(x-2)\) ⇒ \(y=2x-3\).

---

## Conclusão

- O plano cartesiano é a base para representar posições e estudar figuras geométricas em \(\mathbb{R}^2\). A fórmula da distância resulta diretamente do teorema de Pitágoras; a equação da circunferência e formas de reta são ferramentas centrais para modelagem e problemas geométricos. Dominar esses conceitos facilita a passagem para tópicos seguintes (cônicas, transformações, vetores).

---

## Análise crítica

- A videoaula fornece uma apresentação clara e acessível dos conceitos fundamentais, com boa motivação geométrica; entretanto, recomenda-se:
  - Incluir mais exemplos numéricos completos (passo a passo) para reforçar técnicas algébricas de solução.
  - Mostrar casos degenerados (reta vertical) desde o início para evitar confusão com fórmulas de declive.
  - Apresentar uma aplicação prática (por exemplo: localização por coordenadas GPS aproximadas, transformações no plano) para conectar teoria e prática.

(Fonte primária: transcrição e conteúdo da videoaula disponibilizada na aba atual.)

---

## Sugestões de complementação

- Estender para estudo de cônicas (parábola, elipse, hipérbole) com derivação algébrica das equações.
- Introduzir vetores em \(\mathbb{R}^2\) e operações que simplificam cálculo de distâncias e projeções.
- Apresentar métodos numéricos básicos para encontrar interseções e soluções aproximadas quando não há fórmula fechada simples.

---

## Bibliografia (formato ABNT)

- UNIVESP. Geometria analítica e álgebra linear — O Plano Cartesiano [vídeo]. UNIVESP TV, YouTube. Transcrição consultada; conteúdo utilizado como base para esta aula. Acesso em 22 out. 2025.  
- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015. (Capítulos introdutórios sobre vetores e geometria em \(\mathbb{R}^2\)). Acesso em 22 out. 2025.  
- STEWART, J. Cálculo. São Paulo: Cengage; edições diversas. (Capítulos iniciais sobre coordenadas e aplicação do teorema de Pitágoras). Acesso em 2025.

---

## Materiais complementares

- Livro "Álgebra Linear", W. Keith Nicholson — capítulo sobre geometria euclidiana e transformações lineares.  
- Transcrição e vídeo "O Plano Cartesiano" na aba atual (UNIVESP) — base para a seleção dos tópicos e exemplos apresentados.  
- Recursos online de cursos universitários e notas de aula para aprofundamento em cônicas e transformações.

--- 

<!-- MathJax v3 for GitHub Pages (Edge-compatible) -->
<script>
  window.MathJax = {
    tex: {
      inlineMath: [['\\(','\\)'], ['$', '$']],
      displayMath: [['\\[','\\]'], ['$$','$$']]
    },
    options: {
      skipHtmlTags: ['script','noscript','style','textarea','pre','code']
    },
    svg: { fontCache: 'global' }
  };
</script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js"></script>