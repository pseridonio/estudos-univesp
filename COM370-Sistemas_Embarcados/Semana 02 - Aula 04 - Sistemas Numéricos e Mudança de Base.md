# 📚 Sistemas Numéricos e Mudança de Base

## 1. Introdução
Sistemas numéricos são conjuntos de símbolos e regras usados para representar quantidades. Em **sistemas embarcados**, compreender diferentes bases numéricas é essencial, pois a forma como números são representados e manipulados impacta diretamente no funcionamento de hardware e software.

---

## 2. Breve histórico da quantificação
- **Antiguidade**: Egípcios, babilônios, romanos, chineses e hindus já utilizavam sistemas próprios de contagem, muitas vezes baseados em símbolos gráficos.
- **Sistema decimal**: Desenvolvido pelos hindus e difundido pelos árabes (numeração indo-arábica). Popularizado na Europa durante a Revolução Francesa, facilitando o comércio internacional.
- **Sistema binário**: Concebido por Gottfried Wilhelm Leibniz no século XVII, com apenas dois símbolos (0 e 1). Posteriormente, George Boole desenvolveu a álgebra booleana, permitindo aplicações lógicas e matemáticas que fundamentam a computação moderna.

---

## 3. Principais bases numéricas
| Base | Nome         | Algarismos possíveis | Uso principal |
|------|--------------|----------------------|---------------|
| 10   | Decimal      | 0–9                  | Cotidiano, cálculos humanos |
| 2    | Binário      | 0–1                  | Processamento interno de computadores |
| 8    | Octal        | 0–7                  | Representação compacta de binário |
| 16   | Hexadecimal  | 0–9, A–F              | Representação compacta de grandes números binários |

---

## 4. Conversões entre bases

### 4.1 Decimal → Binário (método das divisões sucessivas)
1. Divida o número decimal por 2.
2. Anote o resto (0 ou 1) — este será o bit menos significativo.
3. Continue dividindo o quociente por 2 até chegar a zero.
4. O binário é formado pela leitura dos restos de baixo para cima.

**Exemplo:**  
45₁₀ → binário  
45 ÷ 2 = 22 resto 1  
22 ÷ 2 = 11 resto 0  
11 ÷ 2 = 5 resto 1  
5 ÷ 2 = 2 resto 1  
2 ÷ 2 = 1 resto 0  
1 ÷ 2 = 0 resto 1  
**Resultado:** 101101₂

---

### 4.2 Binário → Decimal (método da soma ponderada)
1. Escreva os pesos das potências de 2 (da direita para a esquerda: 2⁰, 2¹, 2²…).
2. Multiplique cada bit pelo seu peso.
3. Some os resultados.

**Exemplo:**  
11011₂ = (1×2⁴) + (1×2³) + (0×2²) + (1×2¹) + (1×2⁰)  
= 16 + 8 + 0 + 2 + 1 = **27₁₀**

---

### 4.3 Decimal → Hexadecimal
- Divida o número por 16.
- Anote o resto (0–9 ou A–F).
- Continue até o quociente ser zero.
- Leia os restos de baixo para cima.

**Exemplo:**  
423₁₀ → hexadecimal  
423 ÷ 16 = 26 resto 7  
26 ÷ 16 = 1 resto 10 (A)  
1 ÷ 16 = 0 resto 1  
**Resultado:** 1A7₁₆

---

## 5. Unidades de medida em bits
- **Bit**: menor unidade de informação (0 ou 1).
- **Nibble**: 4 bits.
- **Byte**: 8 bits.
- **Word (palavra)**: depende da arquitetura (ex.: 32 bits ou 64 bits).

---

## 6. Aplicações em sistemas embarcados
- Representação de dados em sensores e atuadores.
- Endereçamento de memória.
- Protocolos de comunicação.
- Conversão de sinais (ADC/DAC).

---

# 📝 Lista de Exercícios Resolvidos

### Exercício 1 – Decimal para Binário
**Enunciado:** Converta 58₁₀ para binário.  
**Resolução:**  
58 ÷ 2 = 29 resto 0  
29 ÷ 2 = 14 resto 1  
14 ÷ 2 = 7 resto 0  
7 ÷ 2 = 3 resto 1  
3 ÷ 2 = 1 resto 1  
1 ÷ 2 = 0 resto 1  
**Resposta:** 111010₂

---

### Exercício 2 – Binário para Decimal
**Enunciado:** Converta 101011₂ para decimal.  
**Resolução:**  
(1×2⁵) + (0×2⁴) + (1×2³) + (0×2²) + (1×2¹) + (1×2⁰)  
= 32 + 0 + 8 + 0 + 2 + 1 = **43₁₀**

---

### Exercício 3 – Decimal para Hexadecimal
**Enunciado:** Converta 255₁₀ para hexadecimal.  
**Resolução:**  
255 ÷ 16 = 15 resto 15 (F)  
15 ÷ 16 = 0 resto 15 (F)  
**Resposta:** FF₁₆

---

### Exercício 4 – Hexadecimal para Decimal
**Enunciado:** Converta 3B₁₆ para decimal.  
**Resolução:**  
(3×16¹) + (11×16⁰) = 48 + 11 = **59₁₀**

---

### Exercício 5 – Aplicação prática
Um microcontrolador de 8 bits pode representar valores de 0 até qual número em decimal?  
**Resolução:**  
2⁸ = 256 combinações → valores de 0 a 255.  
**Resposta:** **255₁₀**

---

# 📖 Bibliografia

- OLIVEIRA, Claudio Luís Vieira; ZANETTI, Humberto Augusto Piovesana. *Arduino Descomplicado*. Campinas: Editora Autêntica, 2019.  
- CARVALHO, André C. P. L. F. de; LORENA, Ana Carolina. *Introdução à Computação: Hardware, Software e Dados*. Rio de Janeiro: LTC, 2017.  
- TOCCI, R. J.; WIDMER, N. S.; MOSS, G. L. *Sistemas digitais: princípios e aplicações*. 11. ed. São Paulo: Pearson, 2011.  
- OLIVEIRA, André Schneider de; ANDRADE, Fernando Souza de. *Sistemas Embarcados - Hardware e Firmware na Prática*. 2. ed. Rio de Janeiro: Érica, 2010.  
- UNIVESP. *Sistemas Embarcados – Sistemas numéricos e mudança de base*. Disponível em: [YouTube](https://www.youtube.com/watch?v=j0pfcgxVxCA&ab_channel=UNIVESP). Acesso em: 30 ago. 2025.  