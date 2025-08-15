# Aula 02 � Protocolos e Camadas  
**Disciplina:** COM310 � Infraestrutura para Sistemas Digitais  
**Semana:** 1  
**Fonte prim�ria:** V�deo Apoio 02 � Transcri��o integral da aula  

---

## 1. Objetivos da Aula

Esta aula tem como objetivos principais:
- Analisar as fontes de atraso e perda na rede.
- Entender a organiza��o dos protocolos em camadas.
- Introduzir os modelos OSI e TCP/IP.
- Compreender o conceito de encapsulamento.

---

## 2. Fontes de Atraso e Perda na Internet

Durante a comunica��o entre dispositivos, pacotes podem sofrer atrasos ou ser descartados. As principais causas s�o:

### a) Processamento nos n�s
- Tempo gasto para verificar erros e decidir o pr�ximo enlace de sa�da.

### b) Enfileiramento
- Filas se formam nos buffers dos roteadores quando a taxa de chegada excede a taxa de transmiss�o.

### c) Atraso de transmiss�o
- Tempo para empurrar o pacote inteiro para o enlace.
- Depende do tamanho do pacote (L) e da taxa de transmiss�o (R): `L / R`.

### d) Atraso de propaga��o
- Tempo necess�rio para o sinal percorrer o enlace f�sico.

> **Atraso total = Soma dos quatro tipos acima**.

---

## 3. Organiza��o em Camadas

### Por que usar camadas?
- Modulariza o sistema de redes.
- Facilita manuten��o, implementa��o e substitui��o de partes do sistema.
- Cada camada tem responsabilidades bem definidas.

### Analogia com correspond�ncia:
- Cada camada adiciona um "envelope" com informa��es (endere�o, controle, etc).
- Esse processo � chamado de **encapsulamento**.

---

## 4. Modelo OSI (ISO)

O **modelo OSI** (Open Systems Interconnection) possui 7 camadas:

| Camada             | Fun��o Principal                                          |
|--------------------|-----------------------------------------------------------|
| Aplica��o          | Intera��o com o usu�rio; e-mail, navegador, videoconf.    |
| Apresenta��o       | Formata��o, compress�o, criptografia                      |
| Sess�o             | Controle de sess�es, checkpoints em transfer�ncias        |
| Transporte         | Comunica��o fim-a-fim, confiabilidade (TCP)               |
| Rede               | Roteamento entre redes (IP)                               |
| Enlace             | Acesso ao meio f�sico, detec��o de erros                  |
| F�sica             | Transmiss�o de bits no meio f�sico                        |

> Modelo de refer�ncia � n�o possui implementa��o direta.

---

## 5. Modelo TCP/IP (Internet)

O modelo **TCP/IP** (modelo da internet) � uma implementa��o pr�tica com 4 camadas:

| Camada TCP/IP        | Camadas OSI correspondentes                |
|----------------------|--------------------------------------------|
| Aplica��o            | Aplica��o + Apresenta��o + Sess�o         |
| Transporte           | Transporte                                 |
| Rede                 | Rede                                       |
| Acesso ao meio       | Enlace + F�sica                            |

### Protocolos associados:
- **Transporte:** TCP (confi�vel), UDP (n�o confi�vel)
- **Rede:** IP
- **Acesso:** Ethernet, Wi-Fi, 802.15.4

> Roteadores operam at� a camada de rede. Hospedeiros implementam todas as camadas.

---

## 6. Encapsulamento

- Processo onde cada camada **envolve** os dados com seu cabe�alho espec�fico.
- O dado transmitido inclui os cabe�alhos das camadas superiores.
- Desencapsulamento ocorre no receptor, camada por camada.

---

## 7. An�lise Cr�tica

A aula apresenta de forma clara os fundamentos sobre atrasos, perdas e organiza��o em camadas. Alguns pontos que merecem aten��o cr�tica:

- A explica��o sobre as diferen�as entre **atraso de transmiss�o** e **atraso de propaga��o** � did�tica, mas pode confundir sem exemplos num�ricos.
- O conceito de **encapsulamento** foi bem apresentado por analogia, mas ainda pode ser melhor visualizado com esquemas gr�ficos.
- A transi��o entre o modelo OSI (te�rico) e TCP/IP (pr�tico) foi abordada corretamente, mas ainda de forma introdut�ria � aprofundamentos vir�o nas pr�ximas aulas.

---

## 8. Exerc�cios com Resolu��o

### Exerc�cios de Fixa��o � Aula 02

1. **Quais s�o os quatro principais tipos de atraso em redes?**
   - **Resposta:** Processamento, enfileiramento, transmiss�o e propaga��o.

2. **O que pode causar perda de pacotes em uma rede?**
   - **Resposta:** Quando a taxa de chegada de pacotes excede a capacidade de sa�da do roteador, os buffers se enchem e pacotes s�o descartados.

3. **Qual a f�rmula para o atraso de transmiss�o?**
   - **Resposta:** `L / R`, onde L � o tamanho do pacote e R � a taxa de transmiss�o.

4. **Explique a diferen�a entre atraso de transmiss�o e de propaga��o.**
   - **Resposta:** Transmiss�o � o tempo para empurrar o pacote para o link; propaga��o � o tempo que o sinal leva para cruzar o link f�sico.

5. **Para que serve a divis�o do software de rede em camadas?**
   - **Resposta:** Para modularizar, facilitar o desenvolvimento, manuten��o e substitui��o de partes espec�ficas.

6. **O que � encapsulamento?**
   - **Resposta:** Processo de adicionar informa��es de controle (cabe�alhos) em cada camada � medida que os dados descem pela pilha de protocolos.

7. **Quantas camadas tem o modelo OSI? Cite-as.**
   - **Resposta:** 7 camadas: Aplica��o, Apresenta��o, Sess�o, Transporte, Rede, Enlace, F�sica.

8. **Quantas camadas tem o modelo TCP/IP? Quais s�o elas?**
   - **Resposta:** 4 camadas: Aplica��o, Transporte, Rede, Acesso ao meio.

9. **Qual a principal fun��o da camada de transporte?**
   - **Resposta:** Garantir a comunica��o confi�vel fim-a-fim entre aplica��es.

10. **Cite dois protocolos da camada de transporte e suas caracter�sticas.**
    - **Resposta:** TCP (confi�vel, com verifica��o de ordem e entrega), UDP (r�pido, sem confiabilidade).

11. **O que a camada de enlace faz?**
    - **Resposta:** Define como os dados s�o acessados ao meio f�sico, incluindo detec��o de erros e controle de fluxo.

12. **Por que o modelo OSI � chamado de modelo de refer�ncia?**
    - **Resposta:** Porque n�o possui implementa��o pr�tica direta; serve para guiar o design de sistemas de rede.

13. **Onde est� localizada a maior complexidade na arquitetura da internet: n�cleo ou borda? Justifique.**
    - **Resposta:** Na borda, pois os hosts implementam todas as camadas e lidam com aplica��es, protocolos, sess�es e interfaces.

---

## 9. Bibliografia

### Fontes Diretas:
- **V�deo:** Aula 02 � Protocolos e Camadas. Prof. J� Ueyama. [YouTube � UNIVESP](https://www.youtube.com/watch?v=6-RzPthCSns)
- **Livro:** KUROSE, James F.; ROSS, Keith W. *Redes de Computadores e a Internet*. 6� ed. Pearson, 2018.

### Materiais Complementares:
- [Wikiversidade � Introdu��o �s Redes](https://pt.wikiversity.org/wiki/Introdu%C3%A7%C3%A3o_%C3%A0s_Redes_de_Computadores/Defini%C3%A7%C3%B5es_das_Redes_de_Computadores)
