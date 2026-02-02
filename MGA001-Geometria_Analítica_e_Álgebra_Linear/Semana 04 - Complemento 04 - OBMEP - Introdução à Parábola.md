# Introdução à Parábola

### Introdução

A parábola é a seção cônica obtida quando um plano corta um cone em direção paralela a uma geratriz; alternativamente, é o lugar geométrico dos pontos cuja distância a um ponto fixo (foco) é igual à distância a uma reta fixa (diretriz). Esta aula deriva a equação da parábola, explica elementos geométricos (vértice, foco, diretriz, parâmetro focal), apresenta exemplos e fornece uma lista de exercícios com soluções detalhadas, seguindo a transcrição da videoaula “Introdução à Parábola” (Portal da Matemática OBMEP).

---

## Desenvolvimento

### Definição geométrica e construção

- Definição por lugar geométrico: a parábola é o conjunto de pontos \(P\) tais que
  \[
  \operatorname{dist}(P,F)=\operatorname{dist}(P,r),
  \]
  onde \(F\) é o foco (ponto fixo) e \(r\) é a diretriz (reta fixa).

- Construção prática (método usado na aula): fixam‑se o foco \(F\) e a diretriz \(r\); tomando pontos com distância igual ao foco e à diretriz obtêm‑se pontos da parábola; a reunião desses pontos forma a curva familiar à função quadrática (forma em “U”).

(Informação e figura baseadas na transcrição do vídeo da aula).

---

### Configuração cartesiana e elementos

- Coloca‑se o sistema de coordenadas de modo conveniente para simplificar deduções; escolha padrão: vértice na origem, eixo de simetria coincidindo com o eixo \(y\), foco em \((0,p)\) e diretriz \(y=-p\), com \(p>0\) como parâmetro focal (distância vértice–foco).

- Elementos:
  - Vértice: \(V=(0,0)\).
  - Foco: \(F=(0,p)\).
  - Diretriz: \(y=-p\).
  - Parâmetro focal: \(p\) (positivo quando a parábola abre para cima).

---

### Dedução algébrica da equação canônica

1. Tome ponto genérico \(P=(x,y)\) na parábola. Pela definição:
   \[
   \sqrt{(x-0)^2 + (y-p)^2} = |y + p|.
   \]
   Considerando a parábola que abre para cima (região onde \(y\ge -p\)), a expressão à direita é \(y+p\).

2. Eleve ambos os lados ao quadrado:
   \[
   x^2 + (y-p)^2 = (y+p)^2.
   \]

3. Expanda e simplifique:
   \[
   x^2 + y^2 - 2py + p^2 = y^2 + 2py + p^2 \quad\Rightarrow\quad x^2 - 2py = 2py.
   \]

4. Reorganize para isolar \(y\):
   \[
   x^2 = 4py \quad\Rightarrow\quad y = \frac{1}{4p}x^2.
   \]

5. Interpretação: escrevendo \(4p\) explicitamente, a forma canônica da parábola com vértice na origem e foco em \((0,p)\) é
   \[
   x^2 = 4py,
   \]
   com \(p>0\) determinando a “abertura” da parábola.

---

### Casos e orientações práticas

- Parábola que abre para baixo: escolha \(p<0\) e diretriz \(y=-p\) acima do vértice; a mesma dedução leva a \(x^2 = 4py\) com \(p<0\).

- Parábola com eixo horizontal: permute \(x\) e \(y\) na dedução; a forma canônica passa a ser
  \[
  y^2 = 4px,
  \]
  com foco \((p,0)\) e diretriz \(x=-p\).

- Observação sobre translações: para vértice em \((h,k)\), a forma é
  \[
  (x-h)^2 = 4p(y-k) \quad\text{ou}\quad (y-k)^2 = 4p(x-h)
  \]
  conforme a orientação do eixo.

---

## Exemplos resolvidos (passo a passo)

1. Determinar foco e diretriz de \(x^2 = 4y\).
   - Comparar com \(x^2 = 4py\) ⇒ \(4p = 4\) ⇒ \(p = 1\).
   - Foco: \((0,1)\). Diretriz: \(y = -1\).

2. Retas tangentes em pontos de \(y^2 = 8x\).
   - Identificar parâmetro: \(y^2 = 4px\) ⇒ \(4p = 8\) ⇒ \(p = 2\). Foco \((2,0)\), diretriz \(x=-2\).
   - Para ponto com coordenada \(x=2\): \(y^2 = 8\cdot2 = 16\) ⇒ \(y = \pm 4\).
   - Derivada implícita: \(2y\,y' = 8 \Rightarrow y' = \dfrac{4}{y}\).
     - Em \((2,4)\): \(y' = 1\) ⇒ reta tangente: \(y - 4 = 1(x - 2)\).
     - Em \((2,-4)\): \(y' = -1\) ⇒ reta tangente: \(y + 4 = -1(x - 2)\).

3. Parábola deslocada: ache foco e diretriz de \((x-2)^2 = 12(y+1)\).
   - Comparar com \((x-h)^2 = 4p(y-k)\) ⇒ \(4p = 12 \Rightarrow p = 3\). Vértice \((2,-1)\).
   - Foco: \((2, -1 + 3) = (2,2)\). Diretriz: \(y = -1 - 3 = -4\).

---

## Lista de exercícios com resoluções detalhadas

Observação: os exercícios seguem níveis: 5 simples introdutórios e 5 complexos/avançados. Todas as soluções incluem passos algébricos.

Circunferência de referência não usada — foco apenas em parábolas.

Exercício 1 (Simples)  
Enunciado: Verifique se \(P=(2,1)\) pertence à parábola \(y=\dfrac{x^2}{4}\).  
Solução: Substituir \(x=2\) em \(y=\dfrac{x^2}{4}\): \(y=\dfrac{4}{4}=1\). Como \(P\) tem \(y=1\), pertence.

Exercício 2 (Simples)  
Enunciado: Determine foco e diretriz de \(y = \dfrac{1}{4}x^2\).  
Solução: Escrever como \(x^2 = 4py\). Aqui \(4p = 4\cdot \tfrac{1}{4}^{-1}\) — mais direto: rearrange \(x^2 = 4y\cdot (\tfrac{1}{4})^{-1}\); de forma prática, multiplique ambos os lados por 4: \(4y = x^2\) ⇒ \(x^2 = 4y\). Logo \(p=1\). Foco \((0,1)\). Diretriz \(y=-1\).

Exercício 3 (Simples)  
Enunciado: Escreva a equação da parábola com vértice em \((1,2)\), foco em \((1,5)\).  
Solução:
- Parâmetro \(p\) = distância foco–vértice = \(5-2=3\).
- Fórmula com vértice \((h,k)=(1,2)\) e abertura vertical: \((x-h)^2 = 4p(y-k)\).
- Substituir \(p=3\): \((x-1)^2 = 12(y-2)\).

Exercício 4 (Simples)  
Enunciado: Determine a equação da diretriz e o foco para a parábola \(y = -\dfrac{1}{8}x^2\).  
Solução:
- Escreva na forma \(x^2 = 4py\): multiplicar por \(-1\): \(-x^2 = \dfrac{1}{8} \cdot (-8) x^2\) — mais simples: \(y = -\tfrac{1}{8}x^2\) ⇒ \(x^2 = -8y\) ⇒ \(4p = -8\) ⇒ \(p = -2\).
- Foco: \((0,-2)\). Diretriz: \(y = 2\).

Exercício 5 (Simples)  
Enunciado: Para \(y^2 = 20x\), determine vértice, foco e diretriz.  
Solução:
- Forma \(y^2 = 4px\) ⇒ \(4p = 20\) ⇒ \(p = 5\).
- Vértice: \((0,0)\). Foco: \((5,0)\). Diretriz: \(x=-5\).

Exercício 6 (Complexo)  
Enunciado: Ache as interseções entre a parábola \(y = x^2 - 4x + 3\) e a reta \(y = 2x -1\).  
Solução:
1. Igualar: \(x^2 - 4x + 3 = 2x -1\).
2. Reunir termos: \(x^2 - 6x + 4 = 0\).
3. Aplicar fórmula quadrática: \(x = \dfrac{6 \pm \sqrt{36 - 16}}{2} = \dfrac{6 \pm \sqrt{20}}{2} = 3 \pm \sqrt{5}\).
4. Calcular \(y\): para \(x = 3 + \sqrt{5}\), \(y = 2x -1 = 5 + 2\sqrt{5}\); para \(x = 3 - \sqrt{5}\), \(y = 5 - 2\sqrt{5}\).
5. Soluções: \(\bigl(3\pm\sqrt{5},\:5\pm2\sqrt{5}\bigr)\) (sinais correspondentes).

Exercício 7 (Complexo)  
Enunciado: Determine a equação da parábola com foco \(F=(2,3)\) e diretriz \(y=1\).  
Solução:
1. Vértice \(V\) está no ponto médio entre foco e sua projeção na diretriz; aqui projeção vertical do foco na diretriz é \((2,1)\), então vértice está em \((2,\: \tfrac{3+1}{2})=(2,2)\).
2. Parâmetro \(p\) = distância vértice–foco = \(3-2=1\).
3. Com vértice \((h,k)=(2,2)\) e foco acima do vértice, a parábola abre para cima: \((x-2)^2 = 4\cdot1\cdot(y-2)\).
4. Equação: \((x-2)^2 = 4(y-2)\).

Exercício 8 (Complexo)  
Enunciado: A parábola \(x^2 = 12y\) é traduzida de modo que seu vértice vá para \((3,-1)\). Escreva a nova equação.  
Solução:
1. Forma original: \(x^2 = 4py\) com \(4p = 12 \Rightarrow p=3\).
2. Translação: substituir \(x\) por \(x-h\) e \(y\) por \(y-k\) com \((h,k)=(3,-1)\).
3. Nova equação: \((x-3)^2 = 12(y+1)\).

Exercício 9 (Complexo)  
Enunciado: Ache a equação da reta tangente à parábola \(y = \dfrac{x^2}{4}\) no ponto onde \(x = 4\).  
Solução:
1. Derivada: \(y' = \dfrac{d}{dx}\bigl(\tfrac{x^2}{4}\bigr) = \dfrac{x}{2}\).
2. Em \(x=4\): \(y' = 2\).
3. Coordenada \(y\): \(y(4) = \dfrac{16}{4} = 4\). Ponto: \((4,4)\).
4. Equação da reta tangente (ponto‑declive): \(y - 4 = 2(x - 4)\) ⇒ \(y = 2x -4\).

Exercício 10 (Complexo)  
Enunciado: Determine todos os pontos de interseção entre \(y^2 = 8x\) e a circunferência \(x^2 + y^2 = 16\).  
Solução:
1. Da parábola: \(x = \dfrac{y^2}{8}\).
2. Substituir na circunferência:
   \[
   \left(\frac{y^2}{8}\right)^2 + y^2 = 16 \quad\Rightarrow\quad \frac{y^4}{64} + y^2 - 16 = 0.
   \]
3. Multiplicar por 64: \(y^4 + 64y^2 - 1024 = 0\). Seja \(u = y^2\):
   \[
   u^2 + 64u - 1024 = 0.
   \]
4. Resolver quadrática em \(u\): discriminante \(\Delta = 64^2 + 4\cdot1024 = 4096 + 4096 = 8192\).
   \[
   u = \frac{-64 \pm \sqrt{8192}}{2} = -32 \pm \sqrt{2048}.
   \]
   Como \(u=y^2\ge0\), escolha a solução positiva:
   \[
   u = -32 + \sqrt{2048} = -32 + 32\sqrt{2} = 32(\sqrt{2}-1).
   \]
5. Então \(y = \pm \sqrt{32(\sqrt{2}-1)}\). Calcule \(x = \dfrac{u}{8} = \dfrac{32(\sqrt{2}-1)}{8} = 4(\sqrt{2}-1)\).
6. Pontos de interseção:
   \[
   \left(4(\sqrt{2}-1),\ \pm\sqrt{32(\sqrt{2}-1)}\right).
   \]

---

## Conclusão

A parábola é caracterizada geometricamente pelo equilíbrio entre distâncias a um foco e a uma diretriz; a dedução algébrica leva à forma canônica \(x^2 = 4py\) (ou sua variante horizontal) que torna explícito o parâmetro focal \(p\) e relaciona vértice, foco e diretriz. Dominar translações e derivadas facilita o cálculo de tangentes, interseções e construções geométricas.

---

## Análise crítica

A videoaula oferece uma boa motivação geométrica e uma dedução clara da equação canônica por isolamento de radicais e quadraturas consecutivas. Pontos que merecem complemento em material escrito: explicitar totalmente as manipulações algébricas ao elevar ao quadrado, mostrar cuidado com sinais ao tratar diretriz (valor absoluto) e exemplificar translações e rotações para casos com vértice deslocado ou eixo não alinhado.

---

## Sugestões de complementação

- Incluir uma seção detalhada que execute passo a passo as duas quadraturas necessárias ao deduzir a equação partindo da igualdade de distâncias, com atenção aos termos cancelados.  
- Adicionar exercícios guiados sobre translação de vértice e rotação de eixos (quando aparece termo misto \(xy\)).  
- Incluir gráficos interativos (GeoGebra) que mostrem a construção por barbante e a variação do parâmetro \(p\).

---

## Bibliografia (formato ABNT)

- PORTAL DA MATEMÁTICA OBMEP. Introdução à Parábola [vídeo]. YouTube. Transcrição consultada; conteúdos e dedução algébrica usados como referência. Acesso em 22 out. 2025.  
- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015. Acesso em 22 out. 2025.  
- STEWART, J. Cálculo. Cengage Learning. Capítulos introdutórios sobre derivadas e aplicações geométricas. Acesso em 22 out. 2025.

---

## Materiais complementares

- Livro "Álgebra Linear", W. Keith Nicholson — capítulos sobre transformações lineares e translações de eixos.  
- Documento "Geometria Analítica" (material didático listado nas diretivas) — para referência sobre translação/rotação de eixos e classificação de cônicas.  
- Vídeo “Introdução à Parábola” — transcrição usada como fonte principal nesta aula.

---