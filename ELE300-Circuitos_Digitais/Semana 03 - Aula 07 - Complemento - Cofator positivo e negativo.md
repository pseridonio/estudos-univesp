### Cofator positivo e cofator negativo na Expansão de Shannon — explicação completa

### Definição intuitiva
- Cofator positivo de uma função F em relação a uma variável x (denotado F_\{x=1\} ou F|_\{x=1\}) é a **subfunção resultante** quando assumimos que x vale 1 em F, mantendo as demais variáveis livres; ou seja, é F com x fixado em 1.  
- Cofator negativo de F em relação a x (denotado F_\{x=0\} ou F|_\{x=0\}) é a **subfunção** obtida ao fixar x = 0 em F, mantendo as demais variáveis livres; ou seja, F com x substituído por 0.

Esses cofatores são os blocos básicos da expansão de Shannon: F = x·F_\{x=1\} + x'·F_\{x=0\}, onde x' é a negação de x.

---

### O que exatamente significa “substituir x por 1 (ou 0)”
- Substituir x por 1 em F significa: em todas as ocorrências de x na expressão booleana, trocar x por 1, então simplificar a expressão resultante com álgebra Booleana; o resultado dependerá somente das variáveis restantes. Ex.: se F = x·y + x'·z, então F_\{x=1\} = 1·y + 0·z = y.  
- Substituir x por 0 em F significa trocar x por 0 e simplificar: no exemplo anterior, F_\{x=0\} = 0·y + 1·z = z.

Cada cofator é, portanto, uma função booleana com um grau de liberdade a menos (uma variável a menos), e pode ser representado por sua própria tabela-verdade sobre as variáveis remanescentes.

---

### Interpretação em tabela-verdade
- Dada a tabela-verdade de F(x, a, b, ...), o cofator positivo F_\{x=1\} é a **restrição** da tabela às linhas onde x = 1; o cofator negativo F_\{x=0\} é a restrição às linhas onde x = 0. Assim, cada cofator corresponde a metade (ou fração) das linhas da tabela-verdade original.  
- Exemplo: se F tem 3 variáveis (x,a,b), a tabela tem 8 linhas. F_\{x=0\} é a tabela reduzida com as 4 linhas que têm x=0, indexadas apenas por a e b; F_\{x=1\} são as 4 linhas com x=1.

---

### Propriedades algébricas importantes
1. Linearidade em termos de substituição: computar cofatores respeita OR e AND quando aplicado componente a componente:  
   - (G + H)_{x=1} = G_{x=1} + H_{x=1}  
   - (G · H)_{x=1} = G_{x=1} · H_{x=1}  
   e análogo para x=0.  
2. Cofator de uma constante: 0_{x=0}=0, 1_{x=1}=1.  
3. Repetir cofatores recursivamente: é possível tomar cofator de cofator (por exemplo, (F_\{x=1\})_{y=0} = F_{x=1,y=0}), o que dá base para expansão recursiva e geração de mintermos.

Cada propriedade facilita simplificações e implementações (por exemplo, ao distribuir a substituição por 1 ou 0 sobre somas e produtos).

---

### Como calcular cofatores passo a passo (procedimento)
1. Escolha a variável x sobre a qual calcular o cofator.  
2. Na expressão booleana de F, substitua todas as ocorrências de x por 1 (para cofator positivo) ou por 0 (para cofator negativo).  
3. Simplifique a expressão resultante usando identidades booleanas básicas (0·A = 0, 1·A = A, A + 0 = A, A + 1 = 1, A·A = A, A + A = A, etc.).  
4. O resultado é F_\{x=1\} (ou F_\{x=0\}), função das variáveis restantes.  
5. Opcional: confirme construindo a tabela-verdade restrita (linhas com x fixo) e verificando correspondência.

---

### Exemplo numérico detalhado (3 variáveis) — passo a passo

Considere F(A,B,C) = A·B'·C + A'·B·C + A·B·C'  (três termos quaisquer).

1. Cofator positivo em A (A = 1): substitua A por 1:
   - Primeiro termo: (1)·B'·C = B'·C  
   - Segundo termo: (0)·B·C = 0  
   - Terceiro termo: (1)·B·C' = B·C'  
   Soma simplificada: F_{A=1} = B'·C + B·C' (isto é, B xor C)  
2. Cofator negativo em A (A = 0): substitua A por 0:
   - Primeiro termo: 0·B'·C = 0  
   - Segundo termo: 1·B·C = B·C  
   - Terceiro termo: 0·B·C' = 0  
   Soma simplificada: F_{A=0} = B·C  
3. Verificação pela tabela-verdade: as linhas com A=1 produzem a função B'·C + B·C'; as linhas com A=0 produzem B·C. Portanto, Shannon dá:
   F = A·F_{A=1} + A'·F_{A=0} = A·(B'·C + B·C') + A'·(B·C).

Observação: os cofatores aqui são concretos e já podem ser usados para implementação por MUX (A como seletor, entrada0 = F_{A=0} = B·C, entrada1 = F_{A=1} = B'·C + B·C').

---

### Exemplo com expressão não-canônica (termos faltando variáveis)
Considere G(x,y,z) = x·y + z. Calcule cofatores em x:
- G_{x=1} = 1·y + z = y + z (não depende de x)  
- G_{x=0} = 0·y + z = z

Observe que G_{x=1} e G_{x=0} são funções menores; a expansão de Shannon em x: G = x·(y + z) + x'·(z). Se quiser, simplifique: G = x·y + z·(x + x') = x·y + z.

Esse exemplo também mostra que a expansão de Shannon é identicamente verdadeira e que, ao recompor, podemos recuperar a expressão original, mas a decomposição pode evidenciar subfunções úteis para síntese modular.

---

### Cofatores e mintermos / SoP canônica
- Expandir por Shannon recursivamente em todas as variáveis produz essencialmente a SoP canônica: cada caminho da expansão (sequência de escolhas xi = 0/1) que resulta em 1 corresponde a um mintermo; o cofator em cada nível contém informação sobre quais combinações produzem 1.  
- Assim, cofatores são blocos intermediários que, quando reduzidos a constantes, identificam diretamente mintermos.

---

### Uso prático dos cofatores
- Síntese com multiplexadores: escolha uma variável x como seletora; conecte F_\{x=0\} à entrada 0 e F_\{x=1\} à entrada 1 do MUX — a saída do MUX é F. Isso implementa F com um MUX e lógica para gerar as entradas, frequentemente reduzindo componentes em relação à implementação direta da SoP canônica.  
- Simplificação estratégica: escolher a variável de expansão que torna cofatores simples (constantes, literais simples ou funções fáceis) reduz custo de implementação; por isso, ao aplicar Shannon, avalie cofatores antes de expandir recursivamente.  
- Testes e verificação: cofatores representam restrições da função e podem ser usados para verificar propriedades locais (por exemplo, monotonicidade em uma variável) ou para detectar redundâncias.

---

### Resumo prático — checklist para calcular cofatores
1. Identifique variável x para cofator.  
2. Substitua x por 1 → calcule e simplifique → obtém F_\{x=1\}.  
3. Substitua x por 0 → calcule e simplifique → obtém F_\{x=0\}.  
4. Use F = x·F_\{x=1\} + x'·F_\{x=0\} para decompor, implementar ou analisar.  
5. Se necessário, repita recursivamente para outras variáveis ou construa a SoP canônica a partir dos cofatores reduzidos a constantes.

---

### Leitura recomendada e referência da aula base
- Explicação e uso do Teorema de Expansão de Shannon e da ideia de cofatores na implementação por multiplexadores aparecem de forma didática na videoaula usada como base nesta disciplina.

---

Referências consultadas:
- UNIVESP. Circuitos Digitais - Circuitos Combinacionais. Professor André Ricardo Fioravanti. YouTube. Acesso em: 10 out. 2025.