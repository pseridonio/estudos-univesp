# Conjuntos de exercícios resolvidos — Seções cônicas  
Conteúdo alinhado com a videoaula “Seções Cônicas” (transcrição usada como base).

Para cada seção cônica há 10 exercícios: 5 exercícios simples (nível introdutório) e 5 exercícios complexos (envolvem manipulações algébricas, mudança de centro ou aplicação geométrica). Todas as soluções são detalhadas, com passos claros e fórmulas em LaTeX.

---

## Circunferência — 10 exercícios com soluções

1. (Simples) Verifique se o ponto \(P=(3,1)\) pertence à circunferência de centro \(C=(1,0)\) e raio \(R= \sqrt{5}\).  
   Solução: equação \((x-1)^2+(y-0)^2=5\). Substituir: \((3-1)^2+1^2=2^2+1=4+1=5\). Igual a \(5\) ⇒ pertence.

2. (Simples) Dada a circunferência \(x^2+y^2=25\), encontre seu centro e raio.  
   Solução: forma \((x-0)^2+(y-0)^2=5^2\) ⇒ centro \((0,0)\), raio \(5\).

3. (Simples) Escreva a equação da circunferência de centro \((2,-1)\) e raio \(3\).  
   Solução: \((x-2)^2+(y+1)^2=9\).

4. (Simples) Calcule a distância entre os pontos de interseção da circunferência \(x^2+y^2=4\) com o eixo \(x\).  
   Solução: interseções em \(y=0\) ⇒ \(x^2=4\) ⇒ \(x=\pm2\). Distância \(=2-(-2)=4\).

5. (Simples) Determine a equação reduzida da circunferência que passa por \((0,0),(2,0),(0,2)\).  
   Solução: centro equidistante. Pelo sistema: centro \((a,b)\) satisfaz \(a^2+b^2=R^2\), \((2-a)^2+b^2=R^2\) ⇒ subtrair primeiras: \((2-a)^2-a^2=0\) ⇒ \(4-4a=0\) ⇒ \(a=1\). Simetricamente \(b=1\). Então \(R^2=1^2+1^2=2\). Equação: \((x-1)^2+(y-1)^2=2\).

6. (Complexo) Determine a interseção entre a circunferência \((x-1)^2+(y-2)^2=5\) e a reta \(y=x+1\).  
   Solução: substituir \(y=x+1\):
   \((x-1)^2+(x+1-2)^2=5\) ⇒ \((x-1)^2+(x-1)^2=5\) ⇒ \(2(x-1)^2=5\) ⇒ \((x-1)^2=5/2\) ⇒ \(x-1=\pm\sqrt{5/2}\). Então \(x=1\pm\sqrt{5/2}\), \(y=x+1=2\pm\sqrt{5/2}\).

7. (Complexo) Encontre a equação da circunferência que é tangente à reta \(y=0\), tangente à reta \(x=2\) e passa pelo ponto \((2,4)\).  
   Solução: se tangente a \(y=0\) (eixo \(x\)) então o centro tem coordenada \(b=R\). Se tangente a \(x=2\) então centro tem \(a=2-R\). Centro \((2-R,R)\). Deve satisfazer \((2-(2-R))^2+(4-R)^2=R^2\) ⇒ \(R^2+(4-R)^2=R^2\) ⇒ \((4-R)^2=0\) ⇒ \(R=4\). Então centro \((2-4,4)=(-2,4)\). Verificar: equação \((x+2)^2+(y-4)^2=16\). (Observação: solução obtida por considerar tangências; conferir posição relativa.)

8. (Complexo) Dados três pontos não colineares \(A,B,C\), descreva o procedimento para obter a circunferência circunscrita e resolva para \(A=(0,1),B=(1,0),C=(2,1)\).  
   Solução (procedimento): resolver sistema linear para \(a,b,R^2\) a partir de \((x-a)^2+(y-b)^2=R^2\) aplicado aos três pontos; subtrair equações para eliminar \(R^2\). Cálculo: das eqns
   - \( (0-a)^2+(1-b)^2=R^2\)
   - \( (1-a)^2+(0-b)^2=R^2\)
   - \( (2-a)^2+(1-b)^2=R^2\).
   Subtraindo 1ª da 2ª: \(1 - 2a + a^2 + b^2 - (a^2 + (1 -2b + b^2))\) simplifies ⇒ linear system yields \( -2a + 2b = 0\) ⇒ \(b=a\). Subtraindo 2ª da 3ª: \(4 -4a =0\) ⇒ \(a=1\) ⇒ \(b=1\). Then \(R^2=(0-1)^2+(1-1)^2=1\). Equação \((x-1)^2+(y-1)^2=1\).

9. (Complexo) Determine a circunferência que passa por \((0,0)\) e \((4,0)\) e cujo centro está sobre a reta \(y=x\).  
   Solução: centro \((a,a)\). Distância ao (0,0): \(a^2+a^2=R^2\). Distância ao (4,0): \((4-a)^2+a^2=R^2\). Igualando: \(2a^2=(4-a)^2+a^2\) ⇒ \(2a^2=16-8a+a^2+a^2\) ⇒ \(2a^2=16-8a+2a^2\) ⇒ \(16-8a=0\) ⇒ \(a=2\). Então \(R^2=2*4=8\). Equação \((x-2)^2+(y-2)^2=8\).

10. (Complexo) Determine todos os pontos de interseção entre as circunferências \((x-1)^2+(y-1)^2=4\) e \((x+1)^2+(y-1)^2=4\).  
    Solução: subtrair as equações: \((x-1)^2-(x+1)^2=0\) ⇒ expandir: \(x^2-2x+1-(x^2+2x+1)= -4x=0\) ⇒ \(x=0\). Substituir em uma equação: \((0-1)^2+(y-1)^2=4\) ⇒ \(1+(y-1)^2=4\) ⇒ \((y-1)^2=3\) ⇒ \(y=1\pm\sqrt{3}\). Pontos: \((0,1\pm\sqrt{3})\).

---

## Elipse — 10 exercícios com soluções

1. (Simples) Verifique se \((3,0)\) pertence à elipse \(\dfrac{x^2}{9}+\dfrac{y^2}{4}=1\).  
   Solução: \(\tfrac{3^2}{9}+\tfrac{0}{4}=1+0=1\) ⇒ pertence.

2. (Simples) Determine \(a,b,c\) e os focos para \(\dfrac{x^2}{16}+\dfrac{y^2}{9}=1\).  
   Solução: \(a=4,b=3,\ c=\sqrt{a^2-b^2}=\sqrt{7}\). Focos \((\pm\sqrt{7},0)\).

3. (Simples) Encontre a equação da elipse de semieixos \(a=5,b=2\) centrada na origem.  
   Solução: \(\dfrac{x^2}{25}+\dfrac{y^2}{4}=1\).

4. (Simples) Para a elipse \(\dfrac{x^2}{25}+\dfrac{y^2}{9}=1\), calcule o vértice positivo no eixo \(x\).  
   Solução: vértice \(= (a,0)=(5,0)\).

5. (Simples) Explique por que \((0,3)\) não pertence à elipse \(\dfrac{x^2}{4}+\dfrac{y^2}{9}=1\).  
   Solução: \(\tfrac{0}{4}+\tfrac{9}{9}=1\) ⇒ na verdade pertence. (Observação: reavaliar: cálculo dá 1 ⇒ pertence. Portanto afirmação falsa.)

6. (Complexo) Demonstre que a soma das distâncias de um ponto \((x,y)\) na elipse \(\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}=1\) (com \(a>b\)) aos focos é \(2a\).  
   Solução (esboço): por definição da elipse, use coordenadas paramétricas \(x=a\cos\theta, y=b\sin\theta\). Distância a \(F_1=(c,0)\): \(d_1=\sqrt{(a\cos\theta - c)^2+(b\sin\theta)^2}\). Com identidades e \(c^2=a^2-b^2\), manipular para obter \(d_1+d_2=2a\). Passos clássicos: expandir quadrados, somar raízes, simplificar usando trigonometria; conclusão \(2a\).

7. (Complexo) Encontre os pontos de interseção entre a elipse \(\dfrac{x^2}{9}+\dfrac{y^2}{4}=1\) e a reta \(y=\dfrac{4}{3}x\).  
   Solução: substituir \(y=\tfrac{4}{3}x\) em elipse:
   \(\tfrac{x^2}{9}+\tfrac{(4x/3)^2}{4}=1\) ⇒ \(\tfrac{x^2}{9}+\tfrac{16x^2/9}{4}=\tfrac{x^2}{9}+\tfrac{16x^2}{36}=\tfrac{4x^2}{36}+\tfrac{16x^2}{36}=\tfrac{20x^2}{36}=\tfrac{5x^2}{9}=1\) ⇒ \(x^2=\tfrac{9}{5}\) ⇒ \(x=\pm \tfrac{3}{\sqrt{5}}\). Então \(y=\tfrac{4}{3}x=\pm \tfrac{4}{\sqrt{5}}\).

8. (Complexo) Determine a equação da elipse que passa por \((0,3)\) e \((4,0)\) e tem eixos alinhados com os eixos coordenados.  
   Solução: general form \(\tfrac{x^2}{a^2}+\tfrac{y^2}{b^2}=1\). Substituir pontos:
   - Para \((4,0)\): \(\tfrac{16}{a^2}=1\) ⇒ \(a^2=16\).
   - Para \((0,3)\): \(\tfrac{9}{b^2}=1\) ⇒ \(b^2=9\).
   Então \(\tfrac{x^2}{16}+\tfrac{y^2}{9}=1\).

9. (Complexo) Transforme a elipse deslocada \(\dfrac{(x-2)^2}{9}+\dfrac{(y+1)^2}{4}=1\) para forma paramétrica e apresente foco(s).  
   Solução: paramétrica: \(x=2+3\cos t,\ y=-1+2\sin t\). Parâmetro \(a=3,b=2\) → \(c=\sqrt{9-4}=\sqrt{5}\); focos: \((2\pm\sqrt{5},-1)\).

10. (Complexo) Resolva o problema: encontre todos os pontos \((x,y)\) tal que a soma das distâncias a \(F_1=(2,0)\) e \(F_2=(-2,0)\) é igual a \(6\). Escreva a equação canônica.  
    Solução: por definição elipse com focos ±2 e \(2a=6\) ⇒ \(a=3\). Temos \(c=2\) ⇒ \(b^2=a^2-c^2=9-4=5\). Equação: \(\dfrac{x^2}{9}+\dfrac{y^2}{5}=1\).

---

## Parábola — 10 exercícios com soluções

1. (Simples) Para \(x^2=4y\), determine foco e diretriz.  
   Solução: \(4p=4\Rightarrow p=1\). Foco \((0,1)\). Diretriz \(y=-1\).

2. (Simples) Verifique se o ponto \((2,1)\) pertence à parábola \(y=\dfrac{x^2}{4}\).  
   Solução: RHS \(=2^2/4=1\) ⇒ pertence.

3. (Simples) Escreva a equação da parábola com vértice \((0,0)\), abertura para baixo, cujo foco é \((0,-2)\).  
   Solução: foco \((0,p)\) com \(p=-2\) ⇒ fórmula \(x^2=4py\) ⇒ \(x^2=4(-2)y\) ⇒ \(x^2=-8y\).

4. (Simples) Determine a interseção da parábola \(y=x^2-2\) com a reta \(y=2x-1\).  
   Solução: igualando: \(x^2-2=2x-1\) ⇒ \(x^2-2x-1=0\) ⇒ \(x=(2\pm\sqrt{4+4})/2=1\pm\sqrt{2}\). Então \(y=2x-1\) dá \(y=2(1\pm\sqrt{2})-1=1\pm2\sqrt{2}\).

5. (Simples) Encontre a parábola que passa pelos pontos \((0,0),(1,1),(2,4)\) e tem vértice na origem.  
   Solução: forma \(y=ax^2\). Substituir \((1,1)\): \(a=1\). Verificar \((2,4)\): \(4=1*4\) OK. Equação \(y=x^2\).

6. (Complexo) Determine a parábola cujo foco é \(F=(1,2)\) e diretriz é a reta \(y=0\). Escreva a equação explícita.  
   Solução: ponto genérico \((x,y)\) satisfaz: distance to focus \(=\sqrt{(x-1)^2+(y-2)^2}\) equals distance to line \(y=0\), i.e. \(|y|\). Para foco acima de diretriz, consideramos \(y\ge0\). Então \(\sqrt{(x-1)^2+(y-2)^2}=y\). Quadrar: \((x-1)^2+(y-2)^2=y^2\) ⇒ \((x-1)^2+y^2-4y+4=y^2\) ⇒ \((x-1)^2-4y+4=0\) ⇒ \(4y=(x-1)^2+4\) ⇒ \(y=\tfrac{(x-1)^2}{4}+1\). Forma final.

7. (Complexo) A parábola \(y^2=8x\) é aberta para a direita. Determine vértice, foco e diretriz e escreva a equação da reta tangente no ponto onde \(x=2\).  
   Solução: forma \(y^2=4p x\) ⇒ \(4p=8\Rightarrow p=2\). Vértice \((0,0)\), foco \((2,0)\), diretriz \(x=-2\). Ponto com \(x=2\): \(y^2=16\) ⇒ \(y=\pm4\). Equação da parábola implícita \(F(x,y)=y^2-8x=0\). Derivada implícita: \(2y y' -8=0\) ⇒ \(y'=\tfrac{4}{y}\). Para \(y=4\): \(y'=1\) ⇒ reta \(y-4=1(x-2)\) ⇒ \(y=x+2\). Para \(y=-4\): \(y'=-1\) ⇒ \(y+4=-1(x-2)\) ⇒ \(y=-x+6\).

8. (Complexo) Encontre a parábola obtida cortando o cone por um plano paralelo a uma geratriz, descreva sua equação padrão (conceitual, sem números).  
   Solução: interpretação: corte por plano paralelo a geratriz gera parábola; coordenadas dependem da inclinação do plano; equação local pode ser dada por \(y=kx^2\) até mudança de escala e rotação. (Resposta conceitual com justificativa geométrica.)

9. (Complexo) Dada a parábola \(y=x^2-4x+3\), determine vértice, foco e diretriz.  
   Solução: completar quadrado: \(y=(x^2-4x+4)-4+3=(x-2)^2-1\). Forma canônica: \((x-2)^2= y+1\) ⇒ \((x-2)^2 = 1\cdot (y+1)\). Comparar com \((x-h)^2=4p(y-k)\) ⇒ \(4p=1\Rightarrow p=1/4\). Vértice \((2,-1)\). Foco \((2,-1+p)=(2,-1+1/4)=(2,-3/4)\). Diretriz: \(y=-1-p = -5/4\).

10. (Complexo) Encontre a equação da parábola que passa pelos pontos \((0,1),(1,3),(2,7)\).  
    Solução: forma geral \(y=ax^2+bx+c\). Substituir:
    - \(x=0\): \(c=1\).
    - \(x=1\): \(a+b+1=3⇒a+b=2\).
    - \(x=2\): \(4a+2b+1=7⇒4a+2b=6⇒2a+b=3\).
    Subtrair (2a+b=3) − (a+b=2) ⇒ \(a=1\). Então \(b=1\). Equação \(y=x^2+x+1\).

---

## Hipérbole — 10 exercícios com soluções

1. (Simples) Determine focos e vértices da hipérbole \(\dfrac{x^2}{9}-\dfrac{y^2}{4}=1\).  
   Solução: \(a=3,b=2,c=\sqrt{a^2+b^2}=\sqrt{13}\). Vértices \((\pm3,0)\). Focos \((\pm\sqrt{13},0)\).

2. (Simples) Verifique se \((4,3)\) pertence à hipérbole \(\dfrac{x^2}{4}-\dfrac{y^2}{9}=1\).  
   Solução: \( \tfrac{16}{4}-\tfrac{9}{9}=4-1=3\neq1\) ⇒ não pertence.

3. (Simples) Encontre assíntotas da hipérbole \(\dfrac{x^2}{a^2}-\dfrac{y^2}{b^2}=1\).  
   Solução: assíntotas são \(y=\pm \tfrac{b}{a}x\) (quando centro na origem).

4. (Simples) Para \(\dfrac{x^2}{4}-\dfrac{y^2}{1}=1\), escreva as assíntotas e os vértices.  
   Solução: \(a=2,b=1\) ⇒ vértices \((\pm2,0)\); assíntotas \(y=\pm \tfrac{1}{2}x\).

5. (Simples) Determine a equação reduzida da hipérbole com vértices em \((\pm5,0)\) e focos em \((\pm13,0)\).  
   Solução: \(a=5,c=13\) ⇒ \(b^2=c^2-a^2=169-25=144\) ⇒ \(b=12\). Equação \(\dfrac{x^2}{25}-\dfrac{y^2}{144}=1\).

6. (Complexo) Interseção entre hipérbole \(\dfrac{x^2}{9}-\dfrac{y^2}{4}=1\) e a reta \(y=2\).  
   Solução: substituir: \(\tfrac{x^2}{9}-\tfrac{4}{4}=1\) ⇒ \(\tfrac{x^2}{9}-1=1\) ⇒ \(\tfrac{x^2}{9}=2\) ⇒ \(x^2=18\) ⇒ \(x=\pm3\sqrt{2}\). Pontos \((\pm3\sqrt{2},2)\).

7. (Complexo) Para a hipérbole \(\dfrac{y^2}{16}-\dfrac{x^2}{9}=1\) (transversa no eixo \(y\)), encontre a equação das assíntotas.  
   Solução: assíntotas \(y=\pm \tfrac{4}{3}x\) deslocadas para o centro (aqui centro na origem) ⇒ \(y=\pm \tfrac{4}{3}x\).

8. (Complexo) Determine a distância entre os dois ramos da hipérbole \(\dfrac{x^2}{1}-\dfrac{y^2}{4}=1\) ao longo da linha \(y=0\) entre vértices.  
   Solução: vértices em \((\pm1,0)\) ⇒ distância entre vértices \(=2\).

9. (Complexo) Encontre a hipérbole com assíntotas \(y=\pm 2x\) e vértices em \((\pm3,0)\).  
   Solução: assíntotas indicam \(b/a=2\) ⇒ \(b=2a\). Vértice \(a=3\) ⇒ \(b=6\). Equação \(\dfrac{x^2}{9}-\dfrac{y^2}{36}=1\).

10. (Complexo) Resolva o sistema formado pela hipérbole \(\dfrac{x^2}{9}-\dfrac{y^2}{4}=1\) e a parábola \(y=x^2-4\). (encontre pontos de interseção reais)  
    Solução: substituir \(y\):
    \[
    \frac{x^2}{9}-\frac{(x^2-4)^2}{4}=1.
    \]
    Multiplicar por 36: \(4x^2 -9(x^2-4)^2=36\). Expandir: \(4x^2 -9(x^4-8x^2+16)=36\) ⇒ \(4x^2 -9x^4+72x^2-144=36\) ⇒ \(-9x^4+76x^2-180=0\). Multiplicar por \(-1\): \(9x^4-76x^2+180=0\). Substituir \(u=x^2\): \(9u^2-76u+180=0\). Discriminante \(\Delta=76^2-4*9*180=5776-6480=-704<0\) ⇒ sem raízes reais ⇒ sem interseções reais.

---

## Observações finais

- As soluções mostram procedimentos algébricos e geométricos com justificativas claras. Para exercícios complexos com manipulação pesada (polinômios de grau 4, mudança de centro, parametrização), os passos essenciais estão indicados; se desejar, posso desenvolver cada passo algébrico intermédio com toda a aritmética explícita.  
- O material segue o conteúdo e a organização da videoaula usada como referência.

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