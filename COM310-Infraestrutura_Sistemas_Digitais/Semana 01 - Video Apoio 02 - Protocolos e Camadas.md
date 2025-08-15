# Aula 02 – Protocolos e Camadas  
**Disciplina:** COM310 – Infraestrutura para Sistemas Digitais  
**Semana:** 1  
**Fonte primária:** Vídeo Apoio 02 – Transcrição integral da aula  

---

## 1. Objetivos da Aula

Esta aula tem como objetivos principais:
- Analisar as fontes de atraso e perda na rede.
- Entender a organização dos protocolos em camadas.
- Introduzir os modelos OSI e TCP/IP.
- Compreender o conceito de encapsulamento.

---

## 2. Fontes de Atraso e Perda na Internet

Durante a comunicação entre dispositivos, pacotes podem sofrer atrasos ou ser descartados. As principais causas são:

### a) Processamento nos nós
- Tempo gasto para verificar erros e decidir o próximo enlace de saída.

### b) Enfileiramento
- Filas se formam nos buffers dos roteadores quando a taxa de chegada excede a taxa de transmissão.

### c) Atraso de transmissão
- Tempo para empurrar o pacote inteiro para o enlace.
- Depende do tamanho do pacote (L) e da taxa de transmissão (R): `L / R`.

### d) Atraso de propagação
- Tempo necessário para o sinal percorrer o enlace físico.

> **Atraso total = Soma dos quatro tipos acima**.

---

## 3. Organização em Camadas

### Por que usar camadas?
- Modulariza o sistema de redes.
- Facilita manutenção, implementação e substituição de partes do sistema.
- Cada camada tem responsabilidades bem definidas.

### Analogia com correspondência:
- Cada camada adiciona um "envelope" com informações (endereço, controle, etc).
- Esse processo é chamado de **encapsulamento**.

---

## 4. Modelo OSI (ISO)

O **modelo OSI** (Open Systems Interconnection) possui 7 camadas:

| Camada             | Função Principal                                          |
|--------------------|-----------------------------------------------------------|
| Aplicação          | Interação com o usuário; e-mail, navegador, videoconf.    |
| Apresentação       | Formatação, compressão, criptografia                      |
| Sessão             | Controle de sessões, checkpoints em transferências        |
| Transporte         | Comunicação fim-a-fim, confiabilidade (TCP)               |
| Rede               | Roteamento entre redes (IP)                               |
| Enlace             | Acesso ao meio físico, detecção de erros                  |
| Física             | Transmissão de bits no meio físico                        |

> Modelo de referência – não possui implementação direta.

---

## 5. Modelo TCP/IP (Internet)

O modelo **TCP/IP** (modelo da internet) é uma implementação prática com 4 camadas:

| Camada TCP/IP        | Camadas OSI correspondentes                |
|----------------------|--------------------------------------------|
| Aplicação            | Aplicação + Apresentação + Sessão         |
| Transporte           | Transporte                                 |
| Rede                 | Rede                                       |
| Acesso ao meio       | Enlace + Física                            |

### Protocolos associados:
- **Transporte:** TCP (confiável), UDP (não confiável)
- **Rede:** IP
- **Acesso:** Ethernet, Wi-Fi, 802.15.4

> Roteadores operam até a camada de rede. Hospedeiros implementam todas as camadas.

---

## 6. Encapsulamento

- Processo onde cada camada **envolve** os dados com seu cabeçalho específico.
- O dado transmitido inclui os cabeçalhos das camadas superiores.
- Desencapsulamento ocorre no receptor, camada por camada.

---

## 7. Análise Crítica

A aula apresenta de forma clara os fundamentos sobre atrasos, perdas e organização em camadas. Alguns pontos que merecem atenção crítica:

- A explicação sobre as diferenças entre **atraso de transmissão** e **atraso de propagação** é didática, mas pode confundir sem exemplos numéricos.
- O conceito de **encapsulamento** foi bem apresentado por analogia, mas ainda pode ser melhor visualizado com esquemas gráficos.
- A transição entre o modelo OSI (teórico) e TCP/IP (prático) foi abordada corretamente, mas ainda de forma introdutória — aprofundamentos virão nas próximas aulas.

---

## 8. Exercícios com Resolução

### Exercícios de Fixação – Aula 02

1. **Quais são os quatro principais tipos de atraso em redes?**
   - **Resposta:** Processamento, enfileiramento, transmissão e propagação.

2. **O que pode causar perda de pacotes em uma rede?**
   - **Resposta:** Quando a taxa de chegada de pacotes excede a capacidade de saída do roteador, os buffers se enchem e pacotes são descartados.

3. **Qual a fórmula para o atraso de transmissão?**
   - **Resposta:** `L / R`, onde L é o tamanho do pacote e R é a taxa de transmissão.

4. **Explique a diferença entre atraso de transmissão e de propagação.**
   - **Resposta:** Transmissão é o tempo para empurrar o pacote para o link; propagação é o tempo que o sinal leva para cruzar o link físico.

5. **Para que serve a divisão do software de rede em camadas?**
   - **Resposta:** Para modularizar, facilitar o desenvolvimento, manutenção e substituição de partes específicas.

6. **O que é encapsulamento?**
   - **Resposta:** Processo de adicionar informações de controle (cabeçalhos) em cada camada à medida que os dados descem pela pilha de protocolos.

7. **Quantas camadas tem o modelo OSI? Cite-as.**
   - **Resposta:** 7 camadas: Aplicação, Apresentação, Sessão, Transporte, Rede, Enlace, Física.

8. **Quantas camadas tem o modelo TCP/IP? Quais são elas?**
   - **Resposta:** 4 camadas: Aplicação, Transporte, Rede, Acesso ao meio.

9. **Qual a principal função da camada de transporte?**
   - **Resposta:** Garantir a comunicação confiável fim-a-fim entre aplicações.

10. **Cite dois protocolos da camada de transporte e suas características.**
    - **Resposta:** TCP (confiável, com verificação de ordem e entrega), UDP (rápido, sem confiabilidade).

11. **O que a camada de enlace faz?**
    - **Resposta:** Define como os dados são acessados ao meio físico, incluindo detecção de erros e controle de fluxo.

12. **Por que o modelo OSI é chamado de modelo de referência?**
    - **Resposta:** Porque não possui implementação prática direta; serve para guiar o design de sistemas de rede.

13. **Onde está localizada a maior complexidade na arquitetura da internet: núcleo ou borda? Justifique.**
    - **Resposta:** Na borda, pois os hosts implementam todas as camadas e lidam com aplicações, protocolos, sessões e interfaces.

---

## 9. Bibliografia

### Fontes Diretas:
- **Vídeo:** Aula 02 – Protocolos e Camadas. Prof. Jó Ueyama. [YouTube – UNIVESP](https://www.youtube.com/watch?v=6-RzPthCSns)
- **Livro:** KUROSE, James F.; ROSS, Keith W. *Redes de Computadores e a Internet*. 6ª ed. Pearson, 2018.

### Materiais Complementares:
- [Wikiversidade – Introdução às Redes](https://pt.wikiversity.org/wiki/Introdu%C3%A7%C3%A3o_%C3%A0s_Redes_de_Computadores/Defini%C3%A7%C3%B5es_das_Redes_de_Computadores)
