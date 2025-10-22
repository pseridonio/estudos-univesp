# Seções cônicas — circunferência, elipse, parábola e hipérbole

## Introdução

Esta aula apresenta as seções cônicas: definições, equações canônicas, interpretações geométricas, relações entre parâmetros (raízes, focos, vértices) e exemplos resolvidos. O conteúdo segue a videoaula “Seções Cônicas” (UNIVESP) e usa a transcrição do vídeo como base para a organização dos tópicos e exemplos.

---

## Desenvolvimento

### 1. O que são seções cônicas

- Definição geométrica: as seções cônicas são as curvas resultantes da interseção de um plano com um cone duplo; dependendo da orientação do plano obtemos circunferência, elipse, parábola, hipérbole ou casos degenerados (reta, ponto).  
- Intuição geométrica: cortar o cone com planos horizontais produz circunferências; com planos inclinados adequadamente aparecem parábolas, elipses ou hipérboles conforme a inclinação relative ao eixo do cone.

Fonte do conceito e motivação visual: vídeo e transcrição da aula sobre seções cônicas.

---

### 2. Circunferência

- Definição: conjunto dos pontos à mesma distância (raio \(R\)) de um ponto fixo (centro \((a,b)\)).  
- Equação canônica (centro \((a,b)\), raio \(R\)):
  \[
  (x-a)^2 + (y-b)^2 = R^2.
  \]
- Interpretação das variáveis:
  - \(a,b\): coordenadas do centro.  
  - \(R\): raio (distância constante do centro a qualquer ponto da circunferência).  
- Exemplo resolvido:
  - Centro \((1,1)\), raio \(\sqrt{2}\):
    \[
    (x-1)^2 + (y-1)^2 = 2.
    \]
- Observação: a circunferência é caso particular de elipse quando os semi-eixos são iguais.

Use a equação para checar pertinência: um ponto \(P=(x_0,y_0)\) pertence à circunferência se substituindo nas coordenadas a igualdade é satisfeita.

---

### 3. Elipse

- Definição geométrica: conjunto dos pontos cuja soma das distâncias aos dois focos \(F_1, F_2\) é constante \(2a\).  
- Equação canônica (centro na origem, eixos alinhados):
  \[
  \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1,
  \]
  com \(a\) semieixo maior e \(b\) semieixo menor (\(a\ge b>0\)).  
- Relação entre parâmetros e focos:
  \[
  c^2^ = a^2^ - b^2^,
  \]
  onde \(c\) é a distância do centro até cada foco; os focos estão em \((\pm c, 0)\) (se elipse alongada no eixo \(x\)).  
- Exemplo numérico (extraído da aula): se \(a^2=25\) e \(b^2=9\), então
  \[
  c^2 = 25 - 9 = 16 \Rightarrow c = 4,
  \]
  logo os focos ficam em \((\pm 4, 0)\) e o semieixo maior vale \(a=5\), semieixo menor \(b=3\).
- Observação: quando \(a=b\) recuperamos a circunferência.

---

### 4. Parábola

- Definição geométrica: lugar geométrico dos pontos equidistantes de um foco \(F\) e de uma reta diretriz \(r\).  
- Equação canônica (vértice na origem, eixo \(y\)):
  \[
  x^2 = 4 p y,
  \]
  onde \(p\) é a distância do vértice ao foco (positivo se a parábola abre para cima).  
- Relação dos elementos:
  - Foco: \((0,p)\).  
  - Diretriz: \(y=-p\).  
- Exemplo: para \(x^2 - 4y = 0\) temos \(4p=4\Rightarrow p=1\); foco \((0,1)\) e diretriz \(y=-1\).
- Observação prática: variar \(p\) altera “abertura” da parábola; maior \(|p|\) ⇒ parábola mais “estreita” (em termos de curvatura relativa).

---

### 5. Hipérbole

- Definição geométrica: conjunto dos pontos cuja diferença (em valor absoluto) das distâncias a dois focos é constante \(2a\).  
- Equação canônica (hipérbole transversa no eixo \(x\)):
  \[
  \frac{x^2}{a^2} - \frac{y^2}{b^2} = 1.
  \]
- Relação entre parâmetros e focos:
  \[
  c^2 = a^2 + b^2,
  \]
  onde \(c\) é a distância do centro até cada foco; os focos estão em \((\pm c,0)\) para a forma acima.  
- Exemplo (da aula): se \(a=3\) e \(b=2\) então
  \[
  c^2 = 3^2 + 2^2 = 9 + 4 = 13 \Rightarrow c=\sqrt{13},
  \]
  focos em \((\pm\sqrt{13},0)\) e assim por diante.  
- Observação: inverter sinais na equação troca a orientação (hipérbole com transversa no eixo \(y\)).

---

### 6. Casos degenerados e aplicações

- Casos degenerados: interseções especiais podem produzir uma reta (quando o plano tangencia o cone), um ponto ou duas retas coincidentes.  
- Aplicações práticas (motivações apresentadas na aula):
  - Trajetórias balísticas aproximadas por parábolas.  
  - Propriedades ópticas (reflexão): focos de elipses e parábolas aparecem em sistemas ópticos e antenas.  
  - Imagem formada por lentes/câmeras corresponde a uma seção cônica do cone de raios visuais projetado pela lente.

---

## Procedimentos e exemplos resolvidos (passo a passo)

1. Dado o polinômio quadrático geral em \(x,y\),
   \[
   Ax^2 + Bxy + Cy^2 + Dx + Ey + F = 0,
   \]
   classifique a cônica pela forma e pelo discriminante \(\Delta = B^2 - 4AC\):
   - \(\Delta < 0\): elipse (circunferência se \(A=C\) e \(B=0\)).  
   - \(\Delta = 0\): parábola.  
   - \(\Delta > 0\): hipérbole.  
   (Procedimento padrão de classificação algébrica de cônicas.)

2. Exemplo de cálculo de focos para elipse: dado \(a^2\) e \(b^2\), calcule \(c=\sqrt{a^2-b^2}\) e posicione focos em \((\pm c,0)\) (ou permutados se elipse rotacionada). Exemplo numérico e dedução apresentada na aula.

3. Exemplo de parábola: a partir de \(x^2=4py\) determine foco e diretriz; para \(x^2-4y=0\) obtemos \(p=1\), foco \((0,1)\), diretriz \(y=-1\) (ver demonstração geométrica na transcrição do vídeo).

---

## Exercícios (com resolução detalhada)

1. Dada a cônica \(\dfrac{x^2}{9}+\dfrac{y^2}{4}=1\), determine \(a,b,c\) e os focos.  
   - Solução: \(a=3\), \(b=2\), \(c=\sqrt{9-4}=\sqrt{5}\). Focos: \((\pm\sqrt{5},0)\).

2. Para a parábola \(x^2=12y\) encontre foco e diretriz.  
   - Solução: \(4p=12\Rightarrow p=3\). Foco: \((0,3)\). Diretriz: \(y=-3\).

3. Classifique a cônica \(4x^2 - 9y^2 + 8x - 18 = 0\) e indique sua natureza.  
   - Solução: compare \(A=4\), \(B=0\), \(C=-9\) ⇒ \(\Delta = 0 - 4(4)(-9)=144>0\) ⇒ hipérbole.

4. Dada a elipse com \(a=5\) e \(b=3\), mostre que a soma das distâncias de um ponto genérico \((x,y)\) a \((c,0)\) e a \((-c,0)\) é \(2a=10\) quando \((x,y)\) satisfaz a equação canônica. (Resolver utilizando definição e manipulações algébricas; seguir procedimento mostrado na aula.)

5. Determine os focos da hipérbole \(\dfrac{x^2}{4}-\dfrac{y^2}{9}=1\).  
   - Solução: \(a^2=4\), \(b^2=9\) ⇒ \(c^2=4+9=13\) ⇒ \(c=\sqrt{13}\). Focos: \((\pm\sqrt{13},0)\).

(Se desejar, entrego as soluções completamente desenvolvidas passo a passo para cada exercício.)

---

## Conclusão

- As seções cônicas — circunferência, elipse, parábola e hipérbole — são curvas fundamentais com definições geométricas naturais (distâncias a pontos e retas) e equações algébricas canônicas que relacionam parâmetros (semieixos, focos, vértices). A videoaula fornece imagens e exemplos motivadores que ajudam a visualizar cada caso e entender aplicações como trajetórias e projeções óticas.

---

## Análise crítica

- O vídeo apresenta boa motivação geométrica e exemplos numéricos básicos; entretanto:
  - Recomenda-se explicitar a classificação algébrica via discriminante \(\Delta=B^2-4AC\) com exemplos de transformação de coordenadas (translação/rotação) para cônicas deslocadas/rotacionadas.  
  - Em alguns trechos a dedução do foco a partir dos parâmetros \(a,b\) foi feita de modo conciso; incluir a demonstração completa (usando Pitágoras e propriedades da elipse/hipérbole) melhora a compreensão.

Referência direta à transcrição do vídeo usada como base para estrutura e exemplos.

---

## Bibliografia (formato ABNT)

- UNIVESP. Geometria analítica e álgebra linear — Seções Cônicas [vídeo]. UNIVESP TV, YouTube. Transcrição consultada; conteúdo básico e exemplos extraídos da aula. Acesso em 22 out. 2025.  
- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015. Acesso em 22 out. 2025.

---

Se quiser, gero agora as soluções detalhadas de todos os exercícios passo a passo, ou crio um arquivo Markdown pronto para upload no GitHub com exemplos adicionais e figuras.