# Aula 01 – Introdução às Redes de Computadores  
**Disciplina:** COM310 – Infraestrutura para Sistemas Digitais  
**Semana:** 1  
**Fonte primária:** Vídeo Apoio 01 – Transcrição integral da aula  
**Link**: [Vídeo aula](https://www.youtube.com/watch?v=1csTmCZj-io&ab_channel=UNIVESP)

---

## 1. Objetivos da Aula

Esta primeira aula tem como propósito:

- Introduzir os conceitos fundamentais de redes de computadores.
- Apresentar a internet como um estudo de caso prático e real de implementação de uma rede.
- Discutir metodologias de ensino adotadas no curso.
- Conceituar protocolo, estrutura de rede e formas de roteamento.

---

## 2. O que é uma Rede de Computadores?

Uma **rede de computadores** é um sistema formado por hardware e software que permite a comunicação e o intercâmbio de dados entre dispositivos. Esses dispositivos podem ser computadores, smartphones, servidores, roteadores, entre outros.

### Componentes principais:
- **Hardware:** computadores, smartphones, switches, roteadores, servidores.
- **Software:** protocolos (como HTTP, TCP/IP), navegadores, e-mails.

### Objetivos:
- Compartilhamento de recursos (arquivos, internet, bancos de dados).
- Comunicação entre sistemas e usuários.

---

## 3. Conceito de Internet

A **internet** é uma implementação prática de uma rede de computadores em escala global.

> Analogia: se redes de computadores fossem uma “classe” de programação, a internet seria uma “instância” (objeto) dessa classe.

A internet conecta milhões de dispositivos por meio de enlaces físicos (cabos) e sem fio (Wi-Fi, redes móveis), com o suporte de roteadores e protocolos.

---

## 4. Metodologia do Curso

O curso adotará uma abordagem **top-down (de cima para baixo)**:
- Inicia-se pelos serviços e aplicações de rede (camadas superiores).
- Progressivamente se aprofunda até a camada física, onde ocorre a transmissão dos bits.

Essa estratégia facilita o entendimento prático desde o início, relacionando os conceitos com situações do cotidiano.

---

## 5. Protocolos de Comunicação

Um **protocolo** é um conjunto de regras e formatos que define como mensagens são enviadas, recebidas e interpretadas entre dispositivos.

### Exemplos:
- **HTTP:** usado para navegação web.
- **FTP:** para transferência de arquivos.
- **TCP/UDP:** protocolos de transporte.

> Analogamente, no mundo humano, um protocolo é como perguntar “Que horas são?” antes de esperar uma resposta adequada — ou seja, há um padrão para a interação.

---

## 6. Estrutura de uma Rede

A estrutura de uma rede é dividida em duas regiões:

### a) Borda da rede
- Onde estão os **dispositivos finais** (hosts), como smartphones e computadores.
- Pode usar serviços **com conexão** (ex: e-mail, web) ou **sem conexão** (ex: transmissão de vídeos).

### b) Núcleo da rede
- Composto por **roteadores** e enlaces de interconexão.
- Responsável pelo encaminhamento de pacotes entre diferentes redes.

---

## 7. Tipos de Serviços na Borda da Rede

| Tipo de Serviço       | Exemplo                  | Características                          |
|-----------------------|--------------------------|------------------------------------------|
| **Orientado à conexão** | Telefonema, e-mail        | Requer estabelecimento prévio da conexão |
| **Sem conexão**         | Streaming, vídeo, VoIP    | Dados enviados sem prévia negociação     |

---

## 8. Comutação e Roteamento

### a) Comutação de Circuitos
- Estabelece um **caminho fixo** antes da comunicação.
- Reserva recursos (ex: largura de banda).
- Usado tradicionalmente em telefonia.

### b) Comutação de Pacotes
- Dados divididos em **blocos discretos** (pacotes).
- Cada pacote pode seguir um **caminho diferente**.
- Mais eficiente para redes de dados (como a internet).

### Tipos de roteamento:
| Tipo                 | Descrição |
|----------------------|-----------|
| **Data Grama**       | Cada pacote toma sua própria rota. Roteamento dinâmico. |
| **Circuito Virtual** | Uma rota é pré-estabelecida para todos os pacotes. |

---

## 9. Análise Crítica

A aula apresenta os conceitos de forma introdutória e bem estruturada, sem aparentes equívocos técnicos. No entanto, alguns pontos poderiam ser melhor aprofundados:

- A explicação sobre protocolos mistura levemente conceitos de aplicação e transporte, o que pode gerar confusão (ex: FTP e TCP são de camadas diferentes).
- A analogia entre “classe” e “instância” (rede e internet) é didática, mas simplificada; é importante reforçar que existem outras “instâncias” além da internet (ex: intranets).
- A definição de enlace (“link”) poderia ser detalhada quanto aos tipos físicos (coaxial, fibra, etc) ou lógicos (VPN, túnel).

---

## 10. Exercícios com Resolução

### Exercícios de Fixação – Aula 01: Introdução às Redes de Computadores

---

1. **Defina o que é uma rede de computadores.**  
   **Resposta:**  
   Uma rede de computadores é um sistema composto por hardware e software que permite a comunicação e o compartilhamento de informações entre dois ou mais dispositivos. Ela pode conectar computadores, smartphones, servidores e outros periféricos, possibilitando o intercâmbio de dados.

---

2. **Quais são os dois principais componentes de uma rede de computadores?**  
   **Resposta:**  
   - **Hardware:** dispositivos físicos como computadores, roteadores, switches e servidores.  
   - **Software:** protocolos e aplicações (e-mail, navegadores) que organizam a comunicação.

---

3. **Explique a analogia entre "classe" e "instância" usada na aula para explicar a relação entre redes e a internet.**  
   **Resposta:**  
   A aula compara o conceito de redes de computadores com uma **classe** de programação, e a internet com uma **instância (objeto)** dessa classe. A internet seria uma aplicação prática do conceito de rede.

---

4. **O que é um protocolo de rede?**  
   **Resposta:**  
   É um conjunto de regras que define como os dados são formatados, transmitidos e interpretados entre os dispositivos de uma rede.

---

5. **Cite três exemplos de protocolos mencionados na aula.**  
   **Resposta:**  
   - HTTP  
   - FTP  
   - TCP/IP  

---

6. **Qual é a principal função dos roteadores no núcleo da rede?**  
   **Resposta:**  
   Encaminhar pacotes de dados entre diferentes redes, escolhendo os melhores caminhos disponíveis.

---

7. **Diferencie borda da rede e núcleo da rede.**  
   **Resposta:**  
   - **Borda:** onde estão os dispositivos finais (hosts).  
   - **Núcleo:** formado por roteadores e enlaces que interligam redes, responsável pelo encaminhamento de dados.

---

8. **Explique a abordagem metodológica top-down adotada no curso.**  
   **Resposta:**  
   É uma abordagem que começa pelas camadas superiores da rede (aplicação, transporte) e avança para as camadas mais baixas (enlace, física), facilitando o entendimento prático antes dos detalhes técnicos.

---

9. **O que caracteriza um serviço orientado à conexão?**  
   **Resposta:**  
   A necessidade de estabelecer uma conexão entre origem e destino antes de iniciar a comunicação. Ex: chamadas telefônicas ou e-mails.

---

10. **Dê um exemplo de serviço sem conexão.**  
    **Resposta:**  
    Streaming de vídeo ou telefonia IP (VoIP), que não exigem conexão formal antes da transmissão.

---

11. **Quais são os dois tipos de comutação de rede explicados na aula?**  
    **Resposta:**  
    - **Comutação de circuitos:** estabelece um canal fixo antes da transmissão.  
    - **Comutação de pacotes:** divide os dados em blocos (pacotes) que podem seguir rotas diferentes.

---

12. **Qual comutação é mais comum na internet atual? Justifique.**  
    **Resposta:**  
    A comutação de pacotes, pois é mais flexível, eficiente e permite compartilhamento dinâmico dos recursos da rede.

---

13. **Por que a comutação de circuitos pode gerar desperdício?**  
    **Resposta:**  
    Porque ela reserva um canal fixo, mesmo que não esteja em uso contínuo, desperdiçando capacidade de transmissão.

---

14. **Explique a diferença entre data gramas e circuitos virtuais.**  
    **Resposta:**  
    - **Data gramas:** cada pacote toma sua própria rota dinamicamente.  
    - **Circuitos virtuais:** todos os pacotes seguem uma rota pré-definida.

---

15. **Quais são os dois protocolos de transporte citados? Quais seus tipos de serviço?**  
    **Resposta:**  
    - **TCP:** orientado à conexão.  
    - **UDP:** sem conexão.

---

16. **O que é confiabilidade em redes de computadores?**  
    **Resposta:**  
    É a garantia de que os dados enviados chegarão corretamente ao destino. Protocolos como TCP incluem verificação e retransmissão para assegurar isso.

---

17. **Cite um exemplo prático de erro de transmissão e como a rede pode lidar com ele.**  
    **Resposta:**  
    Um pacote corrompido durante a transmissão pode ser detectado por técnicas de verificação de erros e retransmitido pelo remetente.

---

18. **Como a aula relaciona o funcionamento humano com o uso de protocolos?**  
    **Resposta:**  
    Compara uma conversa humana (por exemplo, pedir a hora) com a troca de mensagens entre máquinas. Ambas seguem um conjunto de regras (protocolo).

---

19. **Explique o papel dos enlaces na rede.**  
    **Resposta:**  
    São os meios físicos (cabos, Wi-Fi) ou lógicos que conectam os dispositivos, permitindo o transporte de dados.

---

20. **Qual é a principal vantagem da comutação por pacotes em relação à de circuitos?**  
    **Resposta:**  
    Maior eficiência e uso compartilhado dos recursos, além da possibilidade de roteamento dinâmico.

---

21. **Como o conceito de “roteamento” é explicado na aula?**  
    **Resposta:**  
    Como o processo de determinar o caminho que um pacote deve seguir da origem até o destino, podendo ter várias alternativas.

---

22. **Por que a internet é considerada um estudo de caso de rede?**  
    **Resposta:**  
    Porque ela exemplifica na prática todos os conceitos de redes: protocolos, roteamento, comutação, hardware e software funcionando em conjunto.

---

23. **Quais tecnologias modernas também são consideradas parte de redes?**  
    **Resposta:**  
    Smartphones, veículos conectados, redes institucionais e regionais (como da USP ou da TV Cultura).

---

24. **O que a aula diz sobre protocolos humanos e de máquina?**  
    **Resposta:**  
    Ambos seguem regras para comunicação, mas protocolos de rede são implementados em software e governam a troca de dados entre máquinas.

---

25. **Quais são os critérios para escolher a rota de um pacote?**  
    **Resposta:**  
    Menor congestionamento, menor tempo, número de saltos, etc.

---

26. **O que é um enlace sem fio, segundo o vídeo?**  
    **Resposta:**  
    É um meio de transmissão onde os dados são enviados via sinais de rádio, como Wi-Fi ou redes móveis.

---

27. **Como a rede lida com bifurcações durante o envio de pacotes?**  
    **Resposta:**  
    Utiliza roteadores para avaliar o melhor caminho no momento, baseado em congestionamento ou rotas disponíveis.

---

28. **Quais serviços foram citados como exemplos de uso da rede com conexão?**  
    **Resposta:**  
    Web (navegação), transferência de arquivos e e-mail.

---

29. **E quais foram citados como sem conexão?**  
    **Resposta:**  
    Videoconferência, streaming de vídeo, telefonia IP.

---

30. **Qual será o próximo tema do curso, conforme anunciado?**  
    **Resposta:**  
    O conceito de **camadas** e a **organização dos protocolos** nessa estrutura.

---



## 11. Bibliografia

### Fontes Diretas:
- **Vídeo:** Aula 01 – Introdução às Redes de Computadores. Professor não identificado. Transcrição integral.
- **Livro:** KUROSE, James F.; ROSS, Keith W. *Redes de Computadores e a Internet*. 6ª ed. Pearson, 2018.

### Materiais Complementares (citados para leitura posterior):
- [Wikiversidade – Introdução às Redes de Computadores](https://pt.wikiversity.org/wiki/Introdu%C3%A7%C3%A3o_%C3%A0s_Redes_de_Computadores/Defini%C3%A7%C3%B5es_das_Redes_de_Computadores)
- [Introdução ao Endereçamento IP (PDF)](https://learn-us-east-1-prod-fleet02-xythos.content.blackboardcdn.com/...)

---


## 12. Detalhes da Aula

### Link: 

https://www.youtube.com/watch?v=1csTmCZj-io&ab_channel=UNIVESP

### Transcrição do vídeo
```text
alunos sejam bem vindos à aula número um
é nessa aula a gente vai introduzir o
conceito de redes de computadores
a gente também vai falar sobre a
estrutura de redes que existem é no
mundo nesse universo aí de redes de
computadores inicialmente vai conceituar
pra da base é para os da base para os
próximos capítulos que a gente vai
abordar durante essa disciplina
botam pra iniciar a qual o objetivo
dessa disciplina que a gente vai
aprender com essa disciplina
a gente vai inicialmente aprender os
conceitos de redes
a gente vai aprender também uma
implementação estudo de caso desses
conceitos que existe que é a internet
repetindo que vai aprender os conceitos
e aplicação desses conceitos que seria a
internet
resumindo que a gente vai fazer é
apresentar os modelos de de redes
os modelos a isi ozzy modelo da internet
assim como conceito a esse mundo de
redes que que a gente tem
há na literatura a começar pelo conceito
de protocolos que é largamente
utilizados os princípios nem os
princípios por exemplo de confiabilidade
e segurança que são aspectos bastante
importantes pro mundo aí de redes com de
computadores então confiabilidade só
exemplificando seria a garantia de que
uma informação que saiu de um ponto vai
chegar um outro ponto
então essa confiabilidade é crucial
nesse mundo aí de redes de computadores
assim com as técnicas né existem
diversas técnicas que são exploradas
nesse mundo de redes de computadores
as técnicas por exemplo de verificação
de erros
eu tenho que verificar se o pacote
chegou integrou no seu destinatário ou
não há então existem várias técnicas pra
gente fazer essa verificação verificação
de erros e até eventualmente
há o conceito desses erros a retificação
desses erros né
então esse é o que a gente vai ver e
essencialmente o que a gente tem que ser
capaz de responder no final
é dessa disciplina bem claramente né
são seus fundamentos episódio como é que
funciona a rede de computadores como
funciona a rede de computadores em
termos de conceito
assim como a sua aplicação desses
conceitos na internet que a rede que a
gente tem mais ao que a gente utiliza no
nosso dia a dia
bom como é que com a metodologia que a
gente vai levar nesse curso
primeiramente existem várias duas
metodologias básicas na metodologia que
a gente chama de é top down de cima para
baixo e abandonar a gente nossa nesse
curso que a gente vai administrando a
gente vai abordar a utilizar o explorar
a abordagem top down também vai começar
com a camada de cima vou explicar para
vocês nessa inclusive já nessas aulas o
que seria se as camadas então vou
começar a partir de cima até chegar na
camada física que a camada onde os dados
os bits são transportados então só pra
mim é já de esclarecer para vocês
a metodologia que a gente vai utilizar
desse curso vai entender esses conceitos
básicos de redes de computadores e
essencialmente que eu quero dizer aqui a
gente vai estudar
primeiramente os conceitos básicos e
depois a gente vai pegar cada um dos
conceitos e aprofunda em cada um desses
conceitos nas próximas aulas vai
promover uma maior profundidade detalhes
então ao longo do deste curso de redes
de computadores e aula de hoje né gente
vai falar na aula de hoje disse pra
vocês na aula de hoje são 14 álbuns
então na hora de hoje a gente vai falar
sobre a conceituação de redes
o definiu que é uma rede de computadores
vou definir também o quê
se esses protocolos nos protocolos são
os softwares que define as regras de
envio de mensagens né
assim com as ações que elas devem tomar
durante o envio e finalmente nessa aula
a gente também vai ver o que a gente vai
ver a estrutura da rede
como é que a rede ela é estrutural
a rede estruturada basicamente no núcleo
da rede em dois componentes é os
componentes do núcleo da rede
os componentes da borda da rede a
estrutura é bem simples a estrutura do
núcleo ea estrutura da borda da rede
cada uma dessas regiões da rede
o núcleo ea extremidade ou a borda da
rede ela possui seus componentes tanto
de hardware como de sol
então a gente vai conceitual e fazer
porque fazer a definição de cada uma
delas
sim com o finalmente vai falar sobre
esse tipo de roteamento quais são as
maneiras que a gente pode rotear ou seja
enviar é um pacote de um ponto para
outro ela pode tomar vários caminhos
eu cheguei a de são carlos até são paulo
agora podia eu poderia tomar várias
rotas para chegar até esse ponto
obviamente eu peguei a rota mais simples
e menos congestionado
assim também acontece com o mundo tá
sempre é isso que a gente vai ver as
formas de roteadores de várias é a
taxonomia definir duas formas de
roteamento que a gente vai ver
nessa aula depois a gente vai expandir
então para os próximos conceitos
inicialmente que são redes de
computadores né
é uma rede de computadores seria o que
seria se aglomerado é de software e
hardware tac permite essa comunicação de
diversos computadores
hoje em dia a gente tem um suporte fones
roteadores que permitem o que permite
esse intercâmbio transmissão de dados
está e compartilhamento de dados entre
esses componentes
a gente tem aqui o exemplo uma rede
móvel onde é composto por smartphones
aos veículos também hoje
dia podem através de peças podem
transmitir mensagens assim como receber
mensagens
a gente tem as provedoras tanto globais
como as provedores regionais as
provedoras nacionais né é que fazem
parte o que fazem parte do mundo de
redes de computadores se como agente
possui a rede institucional à rede da
usp e da unicamp
a rede da tv cultura a rede da sua
instituição
então tudo isso é o que tudo isso é
interligado é de forma o que de forma
que eu possa intercambiar os dados
informações nela entre os diversos
componentes pode definir o que é uma
rede então puxei uma definição a id do
dicionário então uma rede de
computadores como já tinha falado pra
vocês é um sistema constituído que liga
é dois ou mais componentes nesse caso
aqui os computadores e seus periféricos
com o objetivo de que com o objetivo de
comunicar interligar assim como dica é
de fazer o compartilhamento de recursos
recursos esses que podem ser um arquivo
pode ser dados pode ser um banco de
dados e assim por diante
os componentes vão voltar aqui para os
componentes de uma rede de computadores
e falou sobre a gente falou sobre o que
é uma rede justamente essa
infraestrutura que permite o
compartilhamento e interligação de
computadores e seus periféricos
computadores não necessariamente os
desktops podem ser também hoje em dia os
smartphones com o que vocês têm aí é no
bolso de vocês né
assim como é a gente define as redes
a gente vai definir aqui né vai mostrar
aqui pra vocês o componente então está
ali
nesse momento a gente tá conceito único
é uma rede de computadores uma rede de
computadores
ela possui basicamente dois componentes
o componente aqui que seria de rádio
composto de computadores smartphones
roteadores switchs servidores e assim
por diante
assim como a gente tem os componentes de
que o componente de software
os componentes de software são compostos
basicamente porque basicamente pelos
protocolos os é o software de e mail
software de browsers que permitem o que
permitem você navegar numa página aí da
internet então essencialmente uma rede
de computadores
sempre digo que é o que é um conjunto de
software hardware e software hardware e
software os protocolos e as aplicações
que permitem o intercâmbio de dados numa
rede de computadores hardware computador
smartphone com roteadores switchs
servidores então rede de computadores é
justamente essa junção esse conjunto de
hardware software que permite o que
permite esse intercâmbio de dados e
informações que a internet tanto que
conceituou aqui o que é uma rede na rede
como se fosse assim uma programação a
gente pode fazer uma analogia como se
fosse uma classe ea internet que a gente
vai ver aqui é como se fosse um objeto
de uma classe que seria a conceituação
ele também tem porque a gente também tem
aí o objeto que servem então pra ver o
que parece serve para dizer à instância
a ação de uma coça então a internet é
uma instância uma implementação de uma
classe que seria redes de computadores
então no caso da internet aqui que é uma
rede que a gente vai estudar de forma
extensiva né é uma implementação de uma
rede existem elementos de computação aí
interligados em lá se sair de
comunicação então vocês estão vendo aqui
um i love que seria o que é um laço sem
fio
você pode ter um enlace aqui né
o inla tanto de por exemplo um cabo a id
é de patram sado que conecta os
computadores e conectar dos roteadores e
switches roteadores sakineh que permite
o que permitem que esses roteadores
possam se comunicar
a gente tem
glass que seriam que seriam os meios de
comunicação entre os hospedeiros e
computadores
assim como roteador entre os entre os
próprios roteadores 5 em las aqui sem
fio que são em lances onde estados não
são dirigidas
bom agora a gente conceituou né
falamos de redes falamos a id da
internet que seria uma uma implementação
de uma rede um exemplo de mim com a
implantação de uma rede
agora a gente vai falar rapidamente
conceito há um aspecto um conceito que
seria protocolo este protocolo vai ser
largamente utilizados nas próximas aulas
então eu queria que vocês entendessem o
que é um protocolo porque a gente vai se
dar extensivamente perceber um protocolo
ip um protocolo http um protocolo ftp um
protocolo e assim por diante então
existem várias siglas que vocês precisam
memorizar e que na idade essas siglas
nada mais são do que o protocolo assim
portanto a importância de entender o que
é um protocolo não vão votar aqui pra
parte dos humanos para você entender que
seria um protocolo protocolos humanos
você perguntar uma hora você não vai
pega no braço uma pessoa e vê a hora não
é uma coisa que vai fazer perguntar que
horas são
vou dizer eu tenho uma pergunta fazer
uma apresentação e as depois disso fazer
o que é pedir a informação da hora
então é essa a gente na realidade
utiliza protocolo está com vocês vão ver
né
dentro do aspecto aí de protocolos de
redes que seria essa protocolo de rede
então em vez de aqui de seres humanos a
gente tem o que a gente tem computadores
máquinas em vez de computadores e toda a
actividade da na internet é governada
através de um protocolo
então o que seria esse protocolo
protocolo é o que é um conjunto de
regras
o formatos né que define o que que
define os formatos a ordem das mensagens
assim com as ações que serão tomadas a
partir do momento em que uma mensagem
ela chega no hospedeiro
há que assumir eu devo tomar o a
mensagem chegou corretamente ou não é
todo esse tipo de assim é por esse tipo
de procedimento é definido através de um
software chamado protocolo só que a
gente tem 11 anos e aqui a gente tem o
que a gente tem essa implementação do
protocolo e nos seres humanos e aqui a
gente tem uma implementação de um
protocolo no ambiente da internet
então como ao hospedeiro solicita um
esforço assim o hospedeiro falam um alô
para o servidor o servidor responde com
a lo
posso conversar com você e eu posso e
assim que o esse desktop ele faz ele
então pede informação olha eu queria o
arquivo o arquivo de redes de
computadores que talvez você tenha e aí
o arquivo então é transmitido a partir
desse ponto pro o desktop então vocês
estão vendo aqui que tem o que é um alô
um outro lo para responder a conexão ea
partir desse ponto ele pode conversar
ele vai continuar a sua conversa com bom
conceito mas aqui é um protocolo com o
conceito rapidamente aqui definir como é
que é estruturada a internet então
internet ou a rede de computadores que é
o internet mas como falei pra vocês a
implementação da rede ela tem dois vão
ser duas regiões estão nessa região aqui
que seria a região é do do núcleo
e tem outra região aqui que seria a
região da bota da rede
entre essas duas regiões elas possuem o
que elas possuem opus possui estruturas
e funções que governo cada uma dessas
regiões
a gente vai ver então existem softwares
para essa parte aqui pra parte da borda
assim com o software e hardware para a
parte central ou seja para o núcleo da
rede de computadores também assim como a
falando aqui na borda da rede existem
tipos de
é tipo de serviço né são dois tipos de
serviços que são o primeiro orientada a
conexão e sem a conexão então orientada
a conexão a gente tem um exemplo que
seria um telefonema orientada a conexão
ela estabelece formalmente uma conexão
para que a comunicação possa ser
realizado
então telefonemas seria o que eu do
pergunte para a pessoa se eu posso
conversar com uma pessoa antes de eu é
emitir comandos ou emitir a minha
mensagem é somente essa mensagem de
forma que a comunicação então possa ser
realizado sem conexão eu não preciso
ligar para uma pessoa pra saber se eu
posso enviar uma carta uma
correspondência então esse espectro aí ô
ô ô tio serviço é um serviço sem conexão
voltando aqui primeiro orientado a
conexão um telefonema exemplo de uma
orientação a conexão correspondência é
uma um serviço que não existe orientação
e aí existem o que existem também no
mundo da internet dois protocolos o
primeiro protocolo com conexão tcp o
segundo protocolo sem conexão que seria
o protocolo o dp bom é quanto à borda da
rede continua aqui na borda da rede tem
o que a gente tem aplicações usando o
serviço com conexão
assim como a gente tem aplicações usando
serviços sem conexão
então a gente é exemplo aqui o web a
transferência de um arquivo o e mail que
vocês acessam diariamente são serviços
que usam que são baseados com conexão e
as aplicações que não usam conexão são
um filme de vídeos na teleconferência
telefonia ip que normalmente é
normalmente não usam a conexão antes de
estabelecer essa comunicação ea parte do
núcleo então a parte do núcleo como
falei pra vocês sejam terceiro esses
roteadores aqui
esses roteadores aí são são estruturas
de software mais simples que a gente vai
ver e que servem pra que servem pra
conectar um ponto ao outro né uma vamos
assim uma rede aqui a gente tem uma rede
local uma rede talvez residencial e aqui
a gente tem o que a gente tem uma rede
corporativa então quem vai fazer essa
comunicação não é que vai fazer essa
comunicação e justamente os componentes
do núcleo da rede
o núcleo da rede são múltiplos e
roteadores que são interconectados
existem duas formas de a transferir
dados nessa dessa região da loja da rede
no primeiro seria utilizando a comutação
de circuitos ea segunda seria utilizando
a computação aí de pacotes na comutação
de circuitos
ela utiliza o que ela utiliza um canal
dedicado não é como se tivesse um tubo
de cone comunicação ao é de 1 do
destinatário do remetente até o
destinatário a tela nu troca de que ela
não vai trocar a derrota durante o que
durante a sua comunicação diferente da
comutação aqui de kehl divergente da
comutação de pacotes né comutação de
pacotes os dados são enviados em blocos
discretos sendo que esses blocos
elas podem tomar rotas diferentes como a
gente já vai ver inclusive nessa aula
então comutação de circuitos
ela segue o que antes disse a uma
comunicação um intercâmbio de dados a
primeira coisa que ela vai fazer é
verificar qual a rota menos
congestionado
se fosse no google maps ela já definir a
rota já e reserva que reserva uma faixa
na rodovia até chegar no seu
destinatário
é isso que a comutação de circuitos ela
faz é a comutação de circuitos ela
possui várias implementações uma das
implementações e usando que é usando a
freqüência
a divisão através da frequência ea outra
seria fazer a divisão do canal
usando o que usando o tempo aos lotes de
tempo
ok então na parte de freqüência seria
essencialmente assim um rádio fm
ela utiliza ou se fosse um fpm ela tem
uma freqüência específica onde os dados
da os estados de áudio são transferidos
né
são transmitidos usando essa faixa de
freqüência enquanto que no no temporal o
que existe existe aqui uma faixa de
tempo pra cada uma neta cada um dos
componentes que são dos dos comunicantes
né que estão usando essa rede
então a gente tem quatro comunicantes
cada uma delas utiliza o que utilizam um
determinado lote de tempo
como vocês podem então é ver através
dessa licitação
bom aí existem como falei pra vocês na
comutação de pacotes é onde os pacotes
elas seguem através dos blocos discretos
elas podem diferentemente da comutação
de circuitos
a gente viu aqui elas podem até podem
tomar rotas alternativas
é como se fosse assim se fosse no google
de novo na no trânsito é cada pacote ela
vai tomar uma rota menos congestionado
então à medida que ela chega numa
bifurcação ela vai verificar qual a rota
menos congestionado e assim utilizar
essa rota
a rota que existe menos congestionamento
bom dentro desse conceito aqui de
comutação de pacotes e com rotação de
circuitos que a gente viu a gente tem
dois tipos de roteamento nascem dois
tipos de roteamento que são o resultado
da organização na organização dessa
dessa rede
então a primeira o primeiro loteamento é
o roteamento que a gente chama de redes
da grama onde como falei pra vocês um
endereço de destino e ele vai ver o que
ele vai indicá né e indicar o próximo
salto o próximo o próximo de si o
próximo mês essa rota que ele deve então
seguir rock como falei pra vocês
as rotas elas podem mudar de uma sessão
para outra
então a analogia que a gente tem seria
sempre dirigir perguntando o caminho
menos congestionado
então esse seria as redes de data grama
e as redes e curto virtuais
utilizo que utilizam os circuitos
virtuais
então ele segue o que recebe as rotas
baseados no circuito que foi criado
inicialmente antes de dodô pacote sair
de um é remetente para o destinatário
ele definir a rota específica que ele
vai seguir
depois disso então depois que a rota é
vamos assim a faixa da rodovia reservada
para um casal então o carro ela se
dirige até o destinatário
existem vantagens vantagens nesse tipo
de rede circuitos virtuais
existe o que existe um certo desperdício
pode assistir desperdício de que
desperdício de canal
ora se uma freqüência é reservada para o
modo de terno um determinado emissora de
fm cio é só a emissora não utiliza o
canal esse canal é desperdiçam diferente
então das redes de data grama não existe
o que se tem é vantagens vantagens
relacionados a essas duas dois tipos de
roteamento ou estão concluindo essa aula
a gente introduziu o conceito de rede de
computadores e eu queria dizer que estes
estão a gestão baseado na biografia do
livro de rede de computadores à internet
do cruze a sexta edição e nas próximas
aulas na próxima aula em particular a
gente vai falar sobre a os protocolos e
o conceito de camadas que vai aprofundar
então nessa parte da conceituação e dos
protocolos em particular que vai mostrar
pra vocês como é que esses protocolos
eles são organizados
é é uma estrutura de camadas
agradeço então a atenção de vocês espero
vocês então na aula de número 2
obrigado
```

