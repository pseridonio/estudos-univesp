# Física do Movimento  
## Cinemática – Aceleração e Tópicos Avançados

Este material reúne os principais conceitos abordados nas aulas sobre aceleração e cinemática e complementa as informações dos capítulos 2 e 3 do livro, acrescentando temas avançados, como análise vetorial em dois ou mais eixos, movimento parabólico e circular, além de aplicações práticas.

### Sumário
1. [Introdução](#introdução)  
2. [Aceleração Média](#aceleração-média)  
3. [Aceleração Instantânea](#aceleração-instantânea)  
4. [Representação Gráfica](#representação-gráfica)  
5. [Complementos dos Capítulos 2 e 3 do Livro](#complementos-dos-capítulos-2-e-3-do-livro)  
6. [Aprofundamentos Adicionais](#aprofundamentos-adicionais)  
7. [Considerações Finais e Aplicações Práticas](#considerações-finais-e-aplicações-práticas)  
8. [Bibliografia](#bibliografia)  
9. [Exercícios](#exercícios)  
10. [Resolução dos Exercícios](#resolução-dos-exercícios)  

---

## Introdução

Neste documento, exploramos os conceitos clássicos e avançados da cinemática, enfatizando a aceleração média e instantânea, as equações do MRUV _(movimento retilínio uniformememnte variado)_ e as representações gráficas dos movimentos. São abordadas também aplicações em movimentos vetoriais, parabólicos e circulares, possibilitando uma compreensão aprofundada dos fenômenos do movimento.

---

## Aceleração Média

A aceleração média é definida como a razão entre a variação da velocidade e o intervalo de tempo em que essa variação ocorre:

```
a_média = (v_final – v_inicial) / (t_final – t_inicial)
```

*Exemplo:* Se um objeto aumenta sua velocidade de 60,5 m/s para 64,5 m/s em 2 s, temos:  
- Δv = 4 m/s  
- a_média = 4 m/s ÷ 2 s = 2 m/s²

---

## Aceleração Instantânea

A aceleração instantânea corresponde à taxa exata de variação da velocidade em um dado instante e é obtida pela derivada da função velocidade em relação ao tempo:

```
a(t) = dv/dt
```

*Exemplo:* Para a função de velocidade de um carro de Fórmula 1:  
```
VX(T) = 60 + 0.5 * T²
```
- A derivada é: d(VX)/dT = T, de onde se conclui que:
  - Em T = 1 s, a(1) = 1 m/s²  
  - Em T = 3 s, a(3) = 3 m/s²

---

## Representação Gráfica

### Velocidade vs. Tempo

- A inclinação da reta **tangente** à curva de velocidade em um ponto corresponde à aceleração instantânea naquele instante.
- A reta **secante** entre dois pontos fornece a aceleração média no intervalo.

*Exemplo (Representação ASCII):*

```
    v (m/s)
     70 |          *
     65 |         /  
     60 |   *----/       <- Tangente: aceleração instantânea
     55 |  /  
     50 | *
        +---------------- t
          0   1   2   3
```

### Aceleração vs. Tempo

- Para MRUV (aceleração constante), o gráfico é uma linha horizontal.
- Em situações com aceleração variável, a área sob a curva representa a variação da velocidade.

*Exemplo (Representação ASCII):*

```
    a (m/s²)
      3 |   -------------
      2 |   -------------   <- Aceleração constante
      1 |   -------------
      0 |___________________ t
         0   1   2   3
```

---

## Complementos dos Capítulos 2 e 3 do Livro

### Movimento Uniformemente Variado (MRUV)

- **Equações Básicas:**
  - Posição:  
    `x(t) = x₀ + v₀ * t + (1/2) * a * t²`
  - Velocidade:  
    `v(t) = v₀ + a * t`
  - **Equação de Torricelli:**  
    `v² = v₀² + 2a(x – x₀)`

- A derivação por cálculo diferencial mostra como obter a velocidade e a aceleração a partir da função posição.

### Análise Gráfica Avançada

- A curva de posição vs. tempo no MRUV é parabólica (curvatura associada à aceleração).
- A curva de velocidade vs. tempo é linear para aceleração constante e pode apresentar pontos de inflexão em movimentos variáveis.
- O gráfico de aceleração evidencia, pelo método da área, a variação da velocidade.

---

## Aprofundamentos Adicionais

### Cinemática Vetorial e Movimento em Duas Dimensões

- Em movimentos em dois ou mais eixos, as grandezas posição, velocidade e aceleração são vetoriais.
- Por exemplo, a posição em plano pode ser representada por:
  ```
  r(t) = x(t) î + y(t) ĵ
  ```
- Velocidade e aceleração são obtidas pelas derivadas de cada componente.

### Movimento Parabólico

- O movimento parabólico ocorre em lançamentos oblíquos, onde:
  - Componente horizontal (MRU):  
    `x(t) = v₀ * cos(θ) * t`
  - Componente vertical (MRUV):  
    `y(t) = v₀ * sin(θ) * t – (1/2) * g * t²`

### Movimento Circular

- **Movimento Circular Uniforme (MCU):**  
  A aceleração centrípeta é dada por:  
  `a_c = v² / r`
- **Movimento Circular Não Uniforme:**  
  Reúne aceleração tangencial (variação do módulo de v) e centrípeta (para mudança de direção).

---

## Considerações Finais e Aplicações Práticas

O domínio dos conceitos de aceleração média e instantânea, aliado à compreensão das equações do MRUV e às representações gráficas, é essencial para a resolução de problemas em diversas áreas da física e engenharia. A abordagem vetorial e o estudo de movimentos não retilíneos ampliam o leque de aplicações, permitindo analisar desde movimentos simples até lançamentos de projéteis e trajetórias circulares.

---

## Bibliografia

- **Vídeo Aula:**  
  *Física do Movimento - Conceitos de Cinemática - Parte 2*  
  UNIVESP / Professor Cleber Amorim  
  [Assista no YouTube](https://www.youtube.com/watch?v=XKZQotDgj64)

- **Livro:**  
  **Curso de Física Básica 1** – Herch Moysés Nussenzveig, Editora Edgard Blücher, 2005, 3ª edição.
  (Contém, nos capítulos 2 e 3, complementos sobre MRUV, análise gráfica e aplicações dos conceitos cinemáticos.)

- **Referência Adicional:**  
  *Halliday, D., Resnick, R. & Walker, J. – "Fundamentals of Physics"*  
  (Uma referência clássica para aprofundamento dos conceitos da cinemática.)

---

## Exercícios

1. **Exercício 1:**  
   Calcule a aceleração média de um objeto que aumenta sua velocidade de 20 m/s para 30 m/s em 4 s.

2. **Exercício 2:**  
   Um objeto move-se segundo a função:  
   `x(t) = 3t² + 2t + 1`.  
   Determine a velocidade instantânea em t = 2 s.

3. **Exercício 3:**  
   Para o movimento descrito por  
   `x(t) = 5 + 4t – t²`,  
   calcule a aceleração instantânea em t = 3 s.

4. **Exercício 4:**  
   Um carro parte do repouso e acelera a 2 m/s². Qual a velocidade e a distância percorrida em 5 s?

5. **Exercício 5:**  
   Utilizando a equação de Torricelli, determine a velocidade final de um objeto que parte do repouso, percorrendo 50 m com aceleração constante de 3 m/s².

6. **Exercício 6:**  
   Um objeto é lançado verticalmente para cima com velocidade inicial de 20 m/s. Determine (a) o tempo para atingir a altura máxima e (b) a altura máxima alcançada (g = 9,8 m/s²).

7. **Exercício 7:**  
   Para um movimento circular uniforme com raio de 10 m e velocidade de 5 m/s, calcule a aceleração centrípeta.

8. **Exercício 8:**  
   Em um movimento circular não uniforme, um objeto apresenta aceleração tangencial de 2 m/s² e centrípeta de 3 m/s². Determine a aceleração total.

9. **Exercício 9:**  
   Num lançamento de projétil com ângulo de 45° e velocidade inicial de 20 m/s, calcule o alcance horizontal (despreze a resistência do ar).

10. **Exercício 10:**  
    Um projétil é lançado com 30 m/s formando um ângulo de 30° com a horizontal. Determine o tempo total de voo.

11. **Exercício 11:**  
    Dada a função de posição `x(t) = 2t³ – 5t² + t`, determine as funções de velocidade `v(t)` e aceleração `a(t)`.

12. **Exercício 12:**  
    Considere o movimento descrito por `x(t) = t² – 4t + 7`. Determine o instante em que o objeto atinge a velocidade mínima (considere a velocidade em módulo, ou seja, questione o instante em que v(t) = 0).

13. **Exercício 13:**  
    Um objeto move-se segundo `x(t) = 10 + 3t – t²`. Calcule a velocidade média no intervalo de 1 s ≤ t ≤ 4 s.

14. **Exercício 14:**  
    Dada a função de velocidade `v(t) = 6t – 4`, calcule (a) a aceleração instantânea e (b) a velocidade no instante t = 3 s.

15. **Exercício 15:**  
    Um objeto é lançado horizontalmente de uma altura de 80 m com velocidade de 15 m/s. Determine (a) o tempo de queda e (b) a distância horizontal percorrida.

16. **Exercício 16:**  
    Num movimento uniformemente variado, um carro reduz sua velocidade de 30 m/s para 10 m/s em 8 s. Calcule a desaceleração média.

17. **Exercício 17:**  
    Dada a função de posição `x(t) = 4t² + 2t`, determine a velocidade instantânea em t = 5 s.

18. **Exercício 18:**  
    Um objeto move-se com aceleração variável dada por `a(t) = 4 – t`. Se v(0) = 3 m/s, determine a velocidade em t = 4 s.

19. **Exercício 19:**  
    Considere o lançamento vertical de um projétil cuja altura é dada por  
    `y(t) = 20t – 4.9t²`.  
    Determine o tempo para atingir a altura máxima.

20. **Exercício 20:**  
    Um atleta percorre uma pista retilínea com velocidade dada por `v(t) = 5 + 0.5t`. Calcule a distância percorrida nos primeiros 10 s.

21. **Exercício 21:**  
    Um objeto apresenta as seguintes posições: 0 m em t = 0, 15 m em t = 3 s e 35 m em t = 6 s. Determine as velocidades médias nos intervalos 0–3 s e 3–6 s.

22. **Exercício 22:**  
    Um projétil é lançado verticalmente para cima com 25 m/s. Determine a velocidade imediatamente antes de atingir o solo.

23. **Exercício 23:**  
    Para a função de velocidade `v(t) = 9t² – 4t`, determine a aceleração instantânea em t = 2 s.

24. **Exercício 24:**  
    Num movimento circular, considerando um período de revolução de 4 s e um raio de 8 m, determine (a) a velocidade linear e (b) a aceleração centrípeta.

25. **Exercício 25:**  
    Um carro de Fórmula acelera de 40 m/s para 80 m/s em 5 s. Determine a aceleração média.

26. **Exercício 26:**  
    Dada a função de posição `x(t) = 5t – t²`, encontre os instantes em que o objeto está em repouso.

27. **Exercício 27:**  
    Um projétil é lançado com velocidade inicial de 25 m/s formando um ângulo de 60°. Determine a altura máxima atingida.

28. **Exercício 28:**  
    Considere a posição vetorial de um objeto dada por  
    `r(t) = (2t²)î + (3t)ĵ`.  
    Determine (a) a função velocidade vetorial e (b) o módulo da aceleração instantânea em t = 2 s.

29. **Exercício 29:**  
    Se a aceleração varia com o tempo segundo `a(t) = 3t – 2` e v(1) = 5 m/s, determine a variação da velocidade no intervalo de t = 1 s a t = 4 s.

30. **Exercício 30:**  
    Um objeto move-se segundo a função `x(t) = t³ – 6t² + 9t`. (a) Calcule a velocidade média no intervalo de 0 ≤ t ≤ 3 s; (b) Determine o instante em que a aceleração instantânea é zero.

---

## Resolução dos Exercícios

1. **Exercício 1:**  
   Aceleração média:  
   ```
   a_média = (30 – 20) / 4 = 10/4 = 2,5 m/s².
   ```

2. **Exercício 2:**  
   Para `x(t) = 3t² + 2t + 1`:  
   - Velocidade: `v(t) = dx/dt = 6t + 2`.  
   - Em t = 2 s: `v(2) = 6×2 + 2 = 12 + 2 = 14 m/s`.

3. **Exercício 3:**  
   Para `x(t) = 5 + 4t – t²`:  
   - Velocidade: `v(t) = 4 – 2t`.  
   - Aceleração: `a(t) = dv/dt = –2` (constante).  
   - Em t = 3 s: `a(3) = –2 m/s²`.

4. **Exercício 4:**  
   Partindo do repouso com a = 2 m/s²:  
   - Velocidade final: `v = 0 + 2×5 = 10 m/s`.  
   - Distância percorrida: `s = (1/2)×2×(5)² = 0.5×2×25 = 25 m`.

5. **Exercício 5:**  
   Utilizando `v² = v₀² + 2aΔx`, com v₀ = 0, a = 3 m/s², Δx = 50:  
   ```
   v² = 0 + 2×3×50 = 300  →  v = √300 ≈ 17,32 m/s.
   ```

6. **Exercício 6:**  
   Lançamento vertical para cima com v₀ = 20 m/s:  
   - Tempo para altura máxima: `t = v₀ / g = 20/9,8 ≈ 2,04 s`.  
   - Altura máxima: `h = v₀² / (2g) = 400 / 19,6 ≈ 20,41 m`.

7. **Exercício 7:**  
   Em MCU, `a_c = v²/r` com v = 5 m/s e r = 10 m:  
   ```
   a_c = (5)² / 10 = 25/10 = 2,5 m/s².
   ```

8. **Exercício 8:**  
   Aceleração total é a soma vetorial das componentes tangencial e centrípeta:  
   ```
   a_total = √(a_t² + a_c²) = √(2² + 3²) = √(4 + 9) = √13 ≈ 3,61 m/s².
   ```

9. **Exercício 9:**  
   Para projétil com v₀ = 20 m/s e ângulo de 45°:  
   - Alcance: `R = (v₀² × sin(90°)) / g = (400×1)/9,8 ≈ 40,82 m`.

10. **Exercício 10:**  
    Para v₀ = 30 m/s e ângulo de 30°:  
    - Tempo de voo: `T = (2 v₀ sinθ) / g = (2×30×0,5)/9,8 = (30)/9,8 ≈ 3,06 s`.

11. **Exercício 11:**  
    Dada `x(t) = 2t³ – 5t² + t`:  
    - Velocidade: `v(t) = 6t² – 10t + 1`.  
    - Aceleração: `a(t) = dv/dt = 12t – 10`.

12. **Exercício 12:**  
    Para `x(t) = t² – 4t + 7`:  
    - Velocidade: `v(t) = 2t – 4`.  
    - A velocidade em módulo atinge o valor mínimo quando v(t) = 0:  
      `2t – 4 = 0  →  t = 2 s`.

13. **Exercício 13:**  
    Para `x(t) = 10 + 3t – t²`:  
    - Calcule:  
      `x(1) = 10 + 3×1 – 1 = 12 m`  
      `x(4) = 10 + 3×4 – 16 = 10 + 12 – 16 = 6 m`  
    - Velocidade média:  
      `v_média = (6 – 12)/(4 – 1) = (–6)/3 = –2 m/s`.

14. **Exercício 14:**  
    Dada `v(t) = 6t – 4`:  
    - Aceleração: `a(t) = 6 m/s²` (constante).  
    - Em t = 3 s: `v(3) = 6×3 – 4 = 18 – 4 = 14 m/s`.

15. **Exercício 15:**  
    Para lançamento horizontal a partir de 80 m com v₀ = 15 m/s:  
    - Tempo de queda:  
      `h = (1/2) g t²  →  t = √((2×80)/9,8) ≈ √(16,33) ≈ 4,04 s`.  
    - Distância horizontal:  
      `d = 15 × 4,04 ≈ 60,6 m`.

16. **Exercício 16:**  
    A desaceleração média:  
    ```
    a_média = (10 – 30) / 8 = (–20)/8 = –2,5 m/s².
    ```

17. **Exercício 17:**  
    Para `x(t) = 4t² + 2t`,  
    - Velocidade: `v(t) = 8t + 2`.  
    - Em t = 5 s: `v(5) = 8×5 + 2 = 40 + 2 = 42 m/s`.

18. **Exercício 18:**  
    Dada `a(t) = 4 – t`:  
    - Integre para obter v(t):  
      `v(t) = ∫ (4 – t) dt = 4t – (1/2)t² + C`.  
    - Usando a condição v(0) = 3, obtemos C = 3.  
    - Em t = 4 s:  
      `v(4) = 4×4 – 0.5×(16) + 3 = 16 – 8 + 3 = 11 m/s`.

19. **Exercício 19:**  
    Para `y(t) = 20t – 4.9t²`, o tempo para atingir a altura máxima ocorre quando:  
    `dy/dt = 20 – 9.8t = 0  →  t = 20/9.8 ≈ 2,04 s`.

20. **Exercício 20:**  
    Para `v(t) = 5 + 0.5t`:  
    - A distância é dada pela integral:  
      `s = ∫₀¹⁰ (5 + 0.5t) dt = [5t + 0.25t²]₀¹⁰ = (50 + 25) = 75 m`.

21. **Exercício 21:**  
    Dados:  
    - t = 0: x = 0;  
    - t = 3: x = 15 m → v₁ = 15/3 = 5 m/s;  
    - t = 6: x = 35 m → v₂ = (35 – 15)/(6 – 3) = 20/3 ≈ 6,67 m/s.

22. **Exercício 22:**  
    Para lançamento vertical com v₀ = 25 m/s, desconsiderando perdas de energia, o objeto atinge na descida a mesma velocidade do lançamento:  
    **v ≈ 25 m/s** (direção para baixo).

23. **Exercício 23:**  
    Dada `v(t) = 9t² – 4t`,  
    - Aceleração: `a(t) = d(9t² – 4t)/dt = 18t – 4`.  
    - Em t = 2 s: `a(2) = 18×2 – 4 = 36 – 4 = 32 m/s²`.

24. **Exercício 24:**  
    Para um movimento circular com T = 4 s e r = 8 m:  
    - Velocidade linear:  
      `v = (2πr) / T = (16π)/4 = 4π ≈ 12,57 m/s`.  
    - Aceleração centrípeta:  
      `a_c = v² / r = (12,57²)/8 ≈ 158/8 ≈ 19,75 m/s²`.

25. **Exercício 25:**  
    Aceleração média para um carro que acelera de 40 m/s para 80 m/s em 5 s:  
    ```
    a_média = (80 – 40) / 5 = 40/5 = 8 m/s².
    ```

26. **Exercício 26:**  
    Para `x(t) = 5t – t²`:  
    - Velocidade: `v(t) = 5 – 2t`.  
    - Igualando a zero: `5 – 2t = 0  →  t = 2,5 s`.

27. **Exercício 27:**  
    Para lançamento com v₀ = 25 m/s e ângulo de 60°:  
    - Altura máxima:  
      `h = (v₀² sin²θ)/(2g) = (625 × (0.75))/(19,6) ≈ 468,75/19,6 ≈ 23,93 m`.

28. **Exercício 28:**  
    Dada a posição vetorial `r(t) = (2t²)î + (3t)ĵ`:  
    - Velocidade: `v(t) = d/dt [2t²]î + d/dt [3t]ĵ = (4t)î + (3)ĵ`.  
    - Em t = 2 s: `v(2) = (8)î + 3ĵ`.  
      Módulo: `|v(2)| = √(8² + 3²) = √(64 + 9) = √73 ≈ 8,54 m/s`.  
    - Aceleração: `a(t) = d/dt (4t)î + 0ĵ = 4î`.  
      Módulo: 4 m/s².

29. **Exercício 29:**  
    Com `a(t) = 3t – 2`, a variação da velocidade de t = 1 s a t = 4 s é:  
    ```
    Δv = ∫₁⁴ (3t – 2) dt = [ (3/2)t² – 2t ]₁⁴.
    ```
    - Em t = 4:  
      `(3/2)×16 – 8 = 24 – 8 = 16`.
    - Em t = 1:  
      `(3/2)×1 – 2 = 1,5 – 2 = –0,5`.
    - Portanto, Δv = 16 – (–0,5) = 16,5 m/s.  
    Se v(1) = 5 m/s, então v(4) = 5 + 16,5 = 21,5 m/s.

30. **Exercício 30:**  
    Para `x(t) = t³ – 6t² + 9t`:  
    - Velocidade: `v(t) = 3t² – 12t + 9`.  
    - Velocidade média no intervalo de 0 a 3 s:  
      Calcule `x(3) = 27 – 54 + 27 = 0` e `x(0) = 0`,  
      então `v_média = [x(3) – x(0)]/3 = 0/3 = 0 m/s`.  
    - Aceleração: `a(t) = d/dt [v(t)] = 6t – 12`.  
      Igualando a zero: `6t – 12 = 0  →  t = 2 s`.

---

### Dicas Extras para os Estudos

- **Pratique com Diversos Cenários:** Resolva os exercícios variando os parâmetros para fixar os conceitos de aceleração, MRUV, movimentos vetoriais e projeções.
- **Visualize os Gráficos:** Esboce os gráficos de posição, velocidade e aceleração para relacionar as derivadas e integrais com o comportamento dos movimentos.
- **Compare Abordagens:** Note as diferenças entre os métodos de cálculo por média e por derivada.