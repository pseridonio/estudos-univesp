# Seções Cônicas — Circunferência, Elipse, Parábola e Hipérbole

## Introdução

Este material apresenta, com base na videoaula "Introdução às Cônicas" (Portal da Matemática OBMEP) e em referências didáticas, os conceitos geométricos e analíticos das seções cônicas: definição por corte de um plano em um cone, classificação das cônicas, formas canônicas das equações, relações entre parâmetros (semieixos, focos, vértices, diretriz, parâmetro focal) e exemplos resolvidos. O objetivo é fornecer um recurso didático para estudantes iniciando Geometria Analítica, com explicações passo a passo e exercícios resolvidos.

---

## Desenvolvimento

### Definição geométrica das cônicas

- Uma superfície gerada pela rotação de uma reta (geratriz) em torno de um eixo forma um cone.  
- As seções cônicas são as curvas obtidas quando um plano corta essa superfície cônica. A natureza da curva depende do ângulo entre o plano de corte e o eixo/geratriz do cone:
  - Plano paralelo à geratriz → parábola.  
  - Plano que corta com ângulo menor que o da geratriz → hipérbole.  
  - Plano que corta com ângulo maior que o da geratriz → elipse.  
  - Plano perpendicular ao eixo (caso particular) → circunferência.  

Observação: existem casos degenerados (reta, par de retas, ponto) quando o plano tangencia ou coincide em posições especiais.

---

### Circunferência

- Definição: conjunto de pontos com mesma distância \(R\) a um ponto fixo \(C=(a,b)\).  
- Equação canônica:
  \[
  (x-a)^2 + (y-b)^2 = R^2.
  \]
- Interpretação:
  - \(a,b\) — coordenadas do centro;  
  - \(R>0\) — raio.  
- Verificação de pertença: substituir o ponto na equação; igualdade significa que o ponto pertence à circunferência.

Exemplo resolvido:
- Centro \(C=(1,1)\), \(R=\sqrt{2}\).  
  Equação: \((x-1)^2+(y-1)^2=2\).

---

### Elipse

- Definição geométrica: conjunto dos pontos cuja soma das distâncias a dois pontos fixos (focos \(F_1,F_2\)) é constante \(2a\).  
- Equação canônica (centro na origem, eixos alinhados):
  \[
  \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1,\qquad a\ge b>0.
  \]
- Parâmetros e relações:
  - \(a\) — semieixo maior; \(b\) — semieixo menor;  
  - \(c\) — distância do centro a cada foco, com \(c^2 = a^2 - b^2\).  
  - Focos (se eixo maior é \(x\)): \((\pm c,0)\).  
- Interpretação: por definição, para qualquer ponto \((x,y)\) na elipse: \(\operatorname{dist}((x,y),F_1)+\operatorname{dist}((x,y),F_2)=2a\).

Exemplo resolvido:
- Se \(a^2=25\) e \(b^2=9\): \(a=5\), \(b=3\), \(c=\sqrt{25-9}=4\). Focos: \((\pm4,0)\).

---

### Parábola

- Definição geométrica: conjunto dos pontos equidistantes de um foco \(F\) e de uma reta diretriz \(r\).  
- Equação canônica (vértice na origem, eixo \(y\)):
  \[
  x^2 = 4p\,y,
  \]
  onde \(p\) é a distância do vértice ao foco.  
- Elementos:
  - Foco: \((0,p)\).  
  - Diretriz: \(y=-p\).  
- Observação: parábolas podem ser orientadas em qualquer direção via rotação/translação.

Exemplo resolvido:
- \(x^2 - 4y = 0 \Rightarrow 4p=4 \Rightarrow p=1\). Foco: \((0,1)\). Diretriz: \(y=-1\).

---

### Hipérbole

- Definição geométrica: conjunto dos pontos cuja diferença absoluta das distâncias a dois focos é constante \(2a\).  
- Equação canônica (transversa no eixo \(x\), centro na origem):
  \[
  \frac{x^2}{a^2} - \frac{y^2}{b^2} = 1.
  \]
- Parâmetros e relações:
  - \(a\) — semi-eixo transverso; \(b\) — semi-eixo conjugado;  
  - \(c\) — distância center–focus com \(c^2 = a^2 + b^2\).  
  - Focos: \((\pm c,0)\) (no caso acima).  
  - Assíntotas (centro na origem): \(y=\pm \dfrac{b}{a}x\).  

Exemplo resolvido:
- \(a=3\), \(b=2\) ⇒ \(c=\sqrt{9+4}=\sqrt{13}\). Assíntotas: \(y=\pm \tfrac{2}{3}x\).

---

### Classificação algébrica

- Forma geral da cônica:
  \[
  A x^2 + Bxy + C y^2 + D x + E y + F = 0.
  \]
- Discriminante:
  \[
  \Delta = B^2 - 4AC.
  \]
  - \(\Delta < 0\) → elipse (circunferência se \(A=C\) e \(B=0\)).  
  - \(\Delta = 0\) → parábola.  
  - \(\Delta > 0\) → hipérbole.
- Procedimento: para reduzir uma cônica geral à forma canônica pode ser necessário:
  - Translação de eixos (completar quadrado) para remover termos lineares \(Dx, Ey\).  
  - Rotação de eixos quando \(B\neq0\) para eliminar o termo misto \(Bxy\).  

---

## Exemplos resolvidos (passo a passo)

1. Interseção entre circunferência e reta  
   - Circunferência: \((x-1)^2+(y-2)^2=5\)  
   - Reta: \(y=x+1\)  
   Substituindo:
   \[
   (x-1)^2 + (x-1)^2 = 5 \quad\Rightarrow\quad 2(x-1)^2 = 5 \quad\Rightarrow\quad (x-1)^2=\tfrac{5}{2}
   \]
   Assim
   \[
   x = 1\pm\sqrt{\tfrac{5}{2}},\qquad y = 2\pm\sqrt{\tfrac{5}{2}}.
   \]

2. Focos de elipse deslocada  
   - \(\dfrac{(x-2)^2}{9} + \dfrac{(y+1)^2}{4} = 1\).  
   Aqui \(a=3\), \(b=2\), \(c=\sqrt{9-4}=\sqrt{5}\).  
   Focos: \((2\pm\sqrt{5},-1)\).

3. Tangente à parábola por derivada implícita  
   - \(y^2 = 8x\) ⇒ derivando: \(2y\,y' = 8\) ⇒ \(y'=\dfrac{4}{y}\).  
   Se \(x=2\) então \(y^2=16\Rightarrow y=\pm4\). Para \(y=4\): \(y'=1\) ⇒ tangente \(y-4 = 1(x-2)\). Para \(y=-4\): \(y'=-1\) ⇒ \(y+4 = -1(x-2)\).

---

## Exercícios (lista representativa com resolução detalhada)

Apresento 10 exercícios selecionados (diversos níveis) com solução completa; se desejar a lista completa por cônica (40 exercícios), eu a forneço em seguida.

1. (Circunferência — simples) Verifique se \(P=(3,1)\) pertence à circunferência com centro \(C=(1,0)\) e raio \(R=\sqrt{5}\).  
   Resolução: substituir em \((x-1)^2+y^2=5\): \( (3-1)^2 + 1^2 = 4+1=5\). Pertence.

2. (Elipse — simples) Para \(\dfrac{x^2}{16}+\dfrac{y^2}{9}=1\), determine \(a,b,c\) e os focos.  
   Resolução: \(a=4\), \(b=3\), \(c=\sqrt{16-9}=\sqrt{7}\). Focos: \((\pm\sqrt{7},0)\).

3. (Parábola — simples) Determine foco e diretriz de \(x^2=4y\).  
   Resolução: \(4p=4\Rightarrow p=1\). Foco \((0,1)\). Diretriz \(y=-1\).

4. (Hipérbole — simples) Quais são as assíntotas de \(\dfrac{x^2}{9}-\dfrac{y^2}{4}=1\)?  
   Resolução: \(a=3,b=2\) ⇒ assíntotas \(y=\pm \tfrac{2}{3}x\).

5. (Interseção — intermediário) Encontre as interseções entre \(\dfrac{x^2}{9}+\dfrac{y^2}{4}=1\) e \(y=\tfrac{4}{3}x\).  
   Resolução: substituir e simplificar:
   \[
   \frac{x^2}{9} + \frac{(4x/3)^2}{4} = \frac{x^2}{9} + \frac{16x^2}{36} = \frac{5x^2}{9} = 1 \Rightarrow x^2 = \frac{9}{5}.
   \]
   Logo \(x=\pm \tfrac{3}{\sqrt{5}}\), \(y=\pm \tfrac{4}{\sqrt{5}}\).

6. (Tangente — intermediário) Determine a reta tangente à parábola \(y=x^2-4x+3\) no vértice.  
   Resolução: completar quadrado → \(y=(x-2)^2-1\). Vértice \((2,-1)\). Derivada \(y'=2x-4\); em \(x=2\), \(y'=0\). Tangente horizontal: \(y=-1\).

7. (Elipse deslocada — avançado) Parametrize \(\dfrac{(x-2)^2}{9}+\dfrac{(y+1)^2}{4}=1\) e encontre os focos.  
   Resolução: paramétrica \(x=2+3\cos t,\ y=-1+2\sin t\). \(a=3,b=2\Rightarrow c=\sqrt{5}\). Focos em \((2\pm\sqrt{5},-1)\).

8. (Sistema — avançado) Verifique se há interseção real entre \(\dfrac{x^2}{9}-\dfrac{y^2}{4}=1\) e \(y=x^2-4\).  
   Resolução completa foi feita: substituindo e reduzindo obtém-se polinomial em \(x^2\) com discriminante negativo (\(-704\)), portanto sem interseção real.

9. (Construção — avançado) Determine a circunferência que passa por \((0,0)\) e \((4,0)\) com centro sobre \(y=x\).  
   Resolução: centro \((a,a)\). Igualando distâncias e resolvendo obtém \(a=2\) e \(R^2=8\). Equação \((x-2)^2+(y-2)^2=8\).

10. (Problema aplicado — avançado) Focos \(F_1=(2,0),F_2=(-2,0)\), soma das distâncias \(=6\). Obtenha a equação canônica da elipse.  
    Resolução: \(2a=6\Rightarrow a=3\). \(c=2\). \(b^2=a^2-c^2=9-4=5\). Equação \(\dfrac{x^2}{9}+\dfrac{y^2}{5}=1\).

---

## Conclusão

- As cônicas têm definições geométricas naturais (distâncias a pontos/retas) e expressões algébricas canônicas que permitem extração de parâmetros geométricos.  
- A classificação algébrica via \(\Delta=B^2-4AC\) e as ferramentas de translação/rotação de eixos são essenciais para reduzir cônicas gerais à forma canônica.  
- Aplicações práticas incluem óptica (propriedades focais), trajetórias físicas (parábolas) e modelos geométricos em engenharia.

---

## Análise crítica

- A videoaula do Portal da Matemática OBMEP fornece motivação geométrica clara e ilustra os cortes no cone; complementar com exemplos algébricos de redução (translação e rotação de eixos) e com demonstrações completas da relação entre \(a,b,c\) enriquece a compreensão.

---

## Bibliografia (ABNT)

- PORTAL DA MATEMÁTICA OBMEP. Introdução às Cônicas [vídeo]. YouTube. Transcrição consultada; conceitos geométricos e classificação usados como referência. Acesso em 22 out. 2025.  
- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015.  
- STEWART, J. Cálculo. Cengage Learning. (capítulos introdutórios sobre geometria em \(\mathbb{R}^2\)).

---

## Materiais complementares

- Portal da Matemática (OBMEP) — playlist sobre cônicas (vídeos e transcrições).  
- Nicholson, W. Keith — capítulos sobre geometria euclidiana e transformações lineares.  
- Notas de cursos universitários sobre cônicas e transformações (translação/rotação de eixos).

---