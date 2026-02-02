# Introdução à Elipse

## Introdução

Esta aula apresenta a elipse como lugar geométrico, seus elementos (focos, centro, vértices, semieixos), a relação entre os parâmetros \(a\), \(b\) e \(c\), e um procedimento prático para construção e análise da curva, com base na transcrição da videoaula “Introdução à Elipse” do Portal da Matemática (OBMEP).

---

## Desenvolvimento

### 1. Definição por lugar geométrico

A elipse é o lugar geométrico dos pontos do plano cuja soma das distâncias a dois pontos fixos, chamados focos \(F_1\) e \(F_2\), é constante e igual a \(2a\).

### 2. Elementos principais e notação

- Focos: \(F_1\) e \(F_2\) (pontos fixos).  
- Distância focal: \(2c\), distância entre \(F_1\) e \(F_2\).  
- Centro: ponto médio entre \(F_1\) e \(F_2\).  
- Eixo maior: segmento de comprimento \(2a\) que contém os vértices \(A_1\) e \(A_2\).  
- Eixo menor: segmento de comprimento \(2b\) contendo os vértices \(B_1\) e \(B_2\).  
- Semieixos: \(a\) (semieixo maior) e \(b\) (semieixo menor).

Todas essas designações e a figura de referência foram apresentadas na transcrição da aula e são usadas para formular propriedades e problemas envolvendo a elipse.

### 3. Relação entre \(a\), \(b\) e \(c\)

Ao tomar o ponto \(P\) que coincide com um extremo do eixo menor e construir o triângulo retângulo formado pelas distâncias relevantes, aplica-se o Teorema de Pitágoras e obtém-se a relação
\[
a^2 = b^2 + c^2,
\]
onde \(c\) é a distância do centro a cada foco, isto é, \(c^2 = a^2 - b^2\).

### 4. Equação canônica (eixos alinhados, centro na origem)

Para a elipse cujo eixo maior está alinhado ao eixo \(x\) e com centro na origem, a equação canônica é
\[
\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1,
\]
com \(a\ge b>0\). Os focos ficam em \((\pm c,0)\) com \(c=\sqrt{a^2-b^2}\) e os vértices do eixo maior em \((\pm a,0)\) e do eixo menor em \((0,\pm b)\).

### 5. Construção mecânica (problema do jardineiro)

Um método prático para traçar elipses (mencionado na aula) é o “problema do jardineiro”: fixam-se as extremidades de um segmento de comprimento \(2a\) nos focos e, com uma linha esticada e um lápis, varre-se a posição do lápis mantendo a soma das distâncias igual a \(2a\); o locus descrito é a elipse. Esse método evidencia diretamente a definição por soma de distâncias e é útil para construir a curva sem cálculo algébrico.

### 6. Uso em problemas e observações

- Para qualquer ponto \(P\) da elipse vale \(\operatorname{dist}(P,F_1)+\operatorname{dist}(P,F_2)=2a\); essa propriedade é fundamental para resolver problemas de determinação de equações e interseções.  
- Conhecer \(a\) e \(b\) permite determinar \(c\) e localizar os focos; vice‑versa, conhecer os focos e \(2a\) permite obter \(b\).  
- A transcrição recomenda atenção aos nomes e à geometria associada para facilitar a leitura de enunciados e a aplicação de relações métricas da elipse.

---

## Exemplos resolvidos (passo a passo)

1. Dado \(a=5\) e \(b=3\). Calcular \(c\) e os focos.  
   - \(c=\sqrt{a^2-b^2}=\sqrt{25-9}=\sqrt{16}=4\).  
   - Focos: \((\pm4,0)\).

2. Construção prática: se os focos são \(F_1=(2,0)\), \(F_2=(-2,0)\) e a soma das distâncias é \(2a=6\), então \(a=3\), \(c=2\) e
   \[
   b^2 = a^2 - c^2 = 9 - 4 = 5,
   \]
   o que dá a equação
   \[
   \frac{x^2}{9} + \frac{y^2}{5} = 1.
   \]

3. Interseção reta–elipse: substituir a expressão da reta \(y=mx+k\) na equação canônica e resolver o quadrático resultante em \(x\). A existência e quantidade de soluções dependem do discriminante dessa equação reduzida; o procedimento algébrico é padrão para curvas do segundo grau e foi indicado na aula como técnica de resolução.

---

## Conclusão

A elipse é apresentada como um lugar geométrico com propriedades métricas diretas que conduzem a relações algébricas úteis (\(a^2=b^2+c^2\)) e a uma equação canônica quando eixos e centro estão alinhados. O método de construção manual (problema do jardineiro) conecta a definição abstrata à prática geométrica, facilitando a compreensão e a resolução de problemas envolvendo a elipse.

---

## Referência usada

Conteúdo e transcrição da videoaula “Introdução à Elipse” — Portal da Matemática (OBMEP).