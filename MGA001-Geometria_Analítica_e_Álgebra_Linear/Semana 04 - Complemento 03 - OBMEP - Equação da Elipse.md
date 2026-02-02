# Equação da Elipse

### Introdução

A aula apresenta a dedução da equação da elipse a partir de sua definição como lugar geométrico: a soma das distâncias de um ponto a dois focos é constante. O desenvolvimento segue a derivação mostrada pelo professor Vander Martins na videoaula disponível no Portal da Matemática, incluindo o procedimento algébrico de eliminação dos radicais para obter a forma canônica quando o centro está na origem.

---

## Desenvolvimento

### Definição por lugar geométrico

A elipse é o conjunto dos pontos \(P=(x,y)\) tais que a soma das distâncias a dois pontos fixos (focos \(F_1\) e \(F_2\)) é constante e igual a \(2a\):
\[
\operatorname{dist}(P,F_1) + \operatorname{dist}(P,F_2) = 2a.
\]
Esta construção prática é ilustrada pelo “problema do jardineiro”, que traça a elipse com um barbante preso nos focos e esticado por um lápis enquanto se descreve a curva.

(afirmação baseada na transcrição da videoaula).

---

### Configuração do sistema e notação

Escolhemos coordenadas com o centro da elipse na origem e os focos sobre o eixo \(x\), em \((\pm c,0)\). Para um ponto genérico \(P=(x,y)\) temos:
\[
\sqrt{(x-c)^2 + y^2} + \sqrt{(x+c)^2 + y^2} = 2a.
\]
A equação acima é a expressão direta da definição e é a equação inicial usada para obter a forma algébrica canônica, conforme mostrado na demonstração do vídeo.

---

### Passo a passo algébrico para obter a forma canônica

1. **Isolar um radical**  
   Isolamos um dos radicais, por exemplo:
   \[
   \sqrt{(x+c)^2 + y^2} = 2a - \sqrt{(x-c)^2 + y^2}.
   \]

2. **Elevar ao quadrado para eliminar um radical**  
   Elevando ambos os lados ao quadrado e expandindo, obtemos termos quadráticos em \(x\), \(y\) e um radical remanescente; reorganizamos e isolamos novamente o radical restante para poder elevá‑lo ao quadrado pela segunda vez. Esse procedimento de “elevar duas vezes” é necessário para eliminar totalmente as raízes e obter uma relação polinomial entre \(x\) e \(y\).

3. **Usar a relação geométrica entre parâmetros**  
   Durante as manipulações aparece o termo \(a^2-c^2\), que, pela geometria da elipse, é igual a \(b^2\) (onde \(b\) é o semieixo menor), ou seja:
   \[
   b^2 = a^2 - c^2.
   \]
   Substituir \(a^2-c^2\) por \(b^2\) simplifica a expressão final e leva à forma canônica.

4. **Dividir pelos parâmetros para obter a forma padrão**  
   Após reorganizar e simplificar, dividimos convenientemente por \(a^2 b^2\) (ou por \(a^2\) quando apropriado) para chegar à forma canônica:
   \[
   \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1,
   \]
   com \(b^2=a^2-c^2\). O vídeo mostra exatamente essa sequência de isolamentos, quadraturas e simplificações algébricas até chegar à forma acima, partindo da igualdade das distâncias.

---

### Interpretação dos parâmetros

- **\(a\)**: semieixo maior; metade da soma constante das distâncias \(2a\).  
- **\(c\)**: distância do centro a cada foco; os focos ficam em \((\pm c,0)\).  
- **\(b\)**: semieixo menor, dado por \(b=\sqrt{a^2-c^2}\).  

A equação canônica expressa a relação entre as coordenadas dos pontos pertencentes à elipse quando os eixos da elipse são paralelos aos eixos coordenados e o centro está na origem.

---

## Exemplos resolvidos

### Exemplo 1 Determinar a equação canônica a partir de dados focais e soma das distâncias

Dados: \(F_1=(2,0)\), \(F_2=(-2,0)\), soma das distâncias \(=6\).
- Passo 1: \(2a=6\Rightarrow a=3\).
- Passo 2: \(c=2\) (distância do centro a cada foco).
- Passo 3: \(b^2=a^2-c^2=9-4=5\).
- Resultado: equação
  \[
  \frac{x^2}{9} + \frac{y^2}{5} = 1.
  \]

### Exemplo 2 Interseção com uma reta

Encontre interseções entre \(\dfrac{x^2}{9}+\dfrac{y^2}{4}=1\) e \(y=\dfrac{4}{3}x\).
- Substituir \(y\):
  \[
  \frac{x^2}{9} + \frac{(4x/3)^2}{4} = \frac{x^2}{9} + \frac{16x^2/9}{4} = \frac{x^2}{9} + \frac{16x^2}{36} = \frac{5x^2}{9} = 1.
  \]
- Resolver: \(x^2 = \dfrac{9}{5}\Rightarrow x=\pm \dfrac{3}{\sqrt{5}}\).
- Obter \(y\): \(y=\pm \dfrac{4}{\sqrt{5}}\).
- Solução: pontos \(\left(\pm\dfrac{3}{\sqrt{5}},\pm\dfrac{4}{\sqrt{5}}\right)\) (sinais correspondentes).

---

## Exercícios com resolução detalhada

### Exercício 1 Simples
Verifique se \(P=(3,0)\) pertence à elipse \(\dfrac{x^2}{9}+\dfrac{y^2}{4}=1\).  
Solução: substituir \(x=3,y=0\):
\[
\frac{3^2}{9} + \frac{0}{4} = \frac{9}{9}=1,
\]
logo \(P\) pertence à elipse.

### Exercício 2 Simples
Dado \(a=5\) e \(b=3\), calcule \(c\) e localize os focos.  
Solução: \(c=\sqrt{a^2-b^2}=\sqrt{25-9}=\sqrt{16}=4\). Focos: \((\pm4,0)\).

### Exercício 3 Intermediário
Encontre a equação da elipse cujo vértice está em \((4,0)\) e cujo foco correspondente é \((2,0)\).  
Solução:
- Vértice positivo dá \(a=4\).
- Foco positivo dá \(c=2\).
- \(b^2=a^2-c^2=16-4=12\).
- Equação: \(\dfrac{x^2}{16}+\dfrac{y^2}{12}=1\).

### Exercício 4 Intermediário
A elipse \(\dfrac{(x-2)^2}{9}+\dfrac{(y+1)^2}{4}=1\) tem quais focos?  
Solução:
- Forma deslocada com \(a=3,b=2\) e centro \(C=(2,-1)\).
- \(c=\sqrt{9-4}=\sqrt{5}\).
- Focos: \((2\pm\sqrt{5},\,-1)\).

### Exercício 5 Intermediário
Mostre que a soma das distâncias de um ponto \((x,y)\) parametrizado por \(x=a\cos t,\ y=b\sin t\) aos focos é \(2a\).  
Solução (esboço):
- Use expressão das distâncias \(d_1=\sqrt{(a\cos t - c)^2 + (b\sin t)^2}\) e \(d_2=\sqrt{(a\cos t + c)^2 + (b\sin t)^2}\).
- Somando \(d_1+d_2\), expandir quadrados, usar \(c^2=a^2-b^2\) e simplificar leva a \(2a\). (Manipulação algébrica clássica; expandir e reduzir termos quadráticos antes de usar identidades).

### Exercício 6 Avançado
Determine a interseção entre a elipse \(\dfrac{x^2}{25}+\dfrac{y^2}{9}=1\) e a reta \(y=2\).  
Solução:
- Substituir \(y=2\):
  \[
  \frac{x^2}{25} + \frac{4}{9} = 1 \Rightarrow \frac{x^2}{25} = \frac{5}{9} \Rightarrow x^2 = \frac{125}{9}.
  \]
- \(x = \pm \frac{5\sqrt{5}}{3}\). Pontos: \(\left(\pm \dfrac{5\sqrt{5}}{3},\,2\right)\).

### Exercício 7 Avançado
A elipse com focos em \((\pm 3,0)\) e semieixo maior \(a=5\) tem equação?  
Solução:
- Aqui \(c=3\), \(a=5\) ⇒ \(b^2=a^2-c^2=25-9=16\) ⇒ \(b=4\).
- Equação: \(\dfrac{x^2}{25}+\dfrac{y^2}{16}=1\).

### Exercício 8 Avançado
Dada a elipse \(\dfrac{x^2}{9}+\dfrac{y^2}{5}=1\), calcule a excentricidade \(e\).  
Solução:
- Excentricidade \(e=\dfrac{c}{a}\) com \(c=\sqrt{a^2-b^2}=\sqrt{9-5}=\sqrt{4}=2\) e \(a=3\).
- \(e=\dfrac{2}{3}\).

### Exercício 9 Avançado
Encontre a equação da elipse que passa por \((4,0)\) e \((0,3)\) com eixos alinhados.  
Solução:
- Se a elipse passa por \((4,0)\) então \(\dfrac{16}{a^2}+\dfrac{0}{b^2}=1\Rightarrow a^2=16\).
- Se passa por \((0,3)\) então \(\dfrac{0}{a^2}+\dfrac{9}{b^2}=1\Rightarrow b^2=9\).
- Equação: \(\dfrac{x^2}{16}+\dfrac{y^2}{9}=1\).

### Exercício 10 Avançado
Resolva para interseções entre a elipse \(\dfrac{(x-1)^2}{4}+\dfrac{(y-2)^2}{1}=1\) e a reta \(y=2\).  
Solução:
- Substituir \(y=2\) reduz a equação a \(\dfrac{(x-1)^2}{4}=1\Rightarrow (x-1)^2=4\Rightarrow x-1=\pm2\Rightarrow x=-1\) ou \(x=3\).
- Pontos: \((-1,2)\) e \((3,2)\).

---

## Conclusão

A derivação da equação da elipse a partir da definição por soma de distâncias exige manipulação algébrica cuidadosa (isolar radicais e elevar ao quadrado repetidamente) e o uso da relação geométrica \(b^2=a^2-c^2\) para simplificar o resultado. A forma canônica \(\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}=1\) expressa de modo direto a condição que define a curva quando o centro está na origem e os eixos estão alinhados com os eixos coordenados; essa dedução e os passos algébricos são explicitados na videoaula referenciada.

---

## Análise crítica

A apresentação do vídeo traz uma dedução clara e didática, enfatizando a construção prática (barbante) e os passos algébricos necessários para eliminar radicais. Pontos que merecem complemento em material didático escrito:
- Mostrar de forma explícita todas as manipulações algébricas intermédias ao elevar ao quadrado duas vezes, para estudantes que têm dificuldade com álgebra simbólica.  
- Incluir casos deslocados (centro não na origem) e indicar procedimento de translação de eixos para obter a forma canônica nesses casos.  
Essas complementações tornam a transição entre a intuição geométrica e a técnica algébrica mais acessível.

A demonstração e a explicação do método estão documentadas na transcrição do vídeo e serviram de base para esta aula.

---

## Sugestões de complementação

- Incluir uma sessão passo a passo que desenvolva por inteiro as duas elevações ao quadrado da igualdade inicial, exibindo todos os termos e cancelamentos.  
- Apresentar exercícios guiados sobre translação de centro e rotação (quando o termo misto \(xy\) aparece), com resolução completa.  
- Adicionar gráficos interativos (software GeoGebra) que mostrem a construção por barbante e a variação dos parâmetros \(a\), \(b\), \(c\).

---

## Bibliografia

- PORTAL DA MATEMÁTICA OBMEP. Equação da Elipse [vídeo]. Professor Vander Martins. Acesso em 22 out. 2025.  
- NICHOLSON, W. Keith. Álgebra Linear. 2. ed. São Paulo: AMGH Editora, 2015.  
- STEWART, J. Cálculo. Cengage Learning. Capítulos introdutórios de geometria analítica.

---

## Materiais complementares

- Portal da Matemática OBMEP playlist Cônicas — vídeo “Equação da Elipse” usado como referência para a dedução algébrica e construção geométrica.  
- Notas de curso sobre geometria analítica e propriedades métricas de elipses (livros e apostilas universitárias recomendadas na bibliografia).

---
