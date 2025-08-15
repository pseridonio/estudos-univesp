# Sistemas Embarcados – Sistemas Ciber-Físicos e Internet das Coisas (IoT)

## Conteúdo da Aula

### 1. Contextualização e Definição de Internet das Coisas

Nesta aula, exploramos o conceito de Internet das Coisas (IoT) como a interconexão de objetos do dia a dia à internet, permitindo coleta e troca de dados de forma autônoma e remota.  

O termo IoT surgiu nos anos 1980 e 1990, mas só se tornou viável com a popularização de microcontroladores acessíveis no início dos anos 2000, oferecendo baixo custo e versatilidade para embarcar conectividade em dispositivos físicos.  

IoT faz parte de um ecossistema maior de sistemas ciber-físicos (CPS), que unem componentes de software, hardware e redes para monitorar e controlar processos no mundo real.

---

### 2. Tecnologias Habilitadoras e Linha do Tempo

- Anos 1980–1990: primeiras ideias de conectar dispositivos domésticos à internet, porém infraestrutura insuficiente.  
- Anos 2000: microcontroladores baratos (ex.: AVR, PIC, ARM Cortex) e módulos de comunicação (Wi-Fi, GSM, LoRa) viabilizam protótipos de IoT.  
- Convergência com Inteligência Artificial (AI): algoritmos de aprendizado de máquina interpretam dados e extraem insights em tempo real.  
- Avanço para 5G: baixíssima latência e alta largura de banda abrem caminho para aplicações IoT críticas e em larga escala.

---

### 3. Impacto do 5G na Agroindústria

O 5G oferece conexões de até 10 Gbps, latência abaixo de 1 ms e densidade massiva de dispositivos, requisitos ideais para sistemas embarcados em fazendas inteligentes.  

Com redes 5G, sensores, atuadores e câmeras em ambientes rurais podem transmitir vídeo e telemetria em alta definição sem falhas, garantindo monitoramento 24/7 e tomada de decisão remota instantânea.  

No setor agropecuário, isso se traduz em maior precisão na irrigação, segurança de rebanhos, detecção precoce de pragas e otimização de insumos.

---

### 4. Caso de Uso: Monitoramento de Vacas Leiteiras

Neste projeto, câmeras e acelerômetros instalados em cercados capturam movimento e comportamento das vacas.  

Os dados são enviados via rede móvel (2G/3G/4G ou 5G) para a nuvem, onde algoritmos de visão computacional detectam janelas de cio, alertando o produtor por aplicativo móvel.  

Resultados iniciais indicam aumento de até 30 % na taxa de detecção de cio, liberando veterinários para outras tarefas e reduzindo perdas por falhas de inseminação artificial.

---

### 5. Caso de Uso: Telemetria de Bombas Hidráulicas

Para enfrentar secas em regiões agrícolas, desenvolveu-se um sensor ultrassônico não invasivo que mede o fluxo de água em tubulações de bomba.  

O dispositivo embarca microcontrolador, módulo GPRS/3G/4G e antena satelital, permitindo transmissão de dados em áreas remotas.  

O sistema web service processa as medições em tempo real, auxiliando na gestão de recursos hídricos e evitando colapso de irrigação, premiado pela Agência Nacional de Águas (ANA) em 2024.

---

### 6. Desafios e Oportunidades no Agronegócio

Principais desafios:

- Garantir conectividade confiável em áreas isoladas.  
- Dimensionar energia e autonomia para sensores remotos.  
- Proteger dados e privacidade dos produtores.  

Principais oportunidades:

- Aumento de produtividade e redução de desperdícios.  
- Novos modelos de negócio baseados em serviços de monitoramento.  
- Formação de profissionais multidisciplinares em engenharia, agronomia e dados.

---

### 7. Exemplos de Projetos Multidisciplinares

- Plataforma de monitoramento ambiental em bacias hidrográficas, usando sensores de qualidade da água e IoT para prevenir crises hídricas.  
- Rede de estações meteorológicas autônomas para apoiar pequenas propriedades na tomada de decisão sobre plantio e colheita.  
- Sistemas de vagões ferroviários inteligentes, integrando IoT e AI para otimizar logística de grãos.

---

---

## Exercícios

1. Descreva, em suas próprias palavras, o conceito de Internet das Coisas e destaque duas diferenças entre IoT e sistemas tradicionais de automação industrial.  

   Resposta passo a passo:  
   a. Defina IoT como rede de dispositivos inteligentes.  
   b. Compare com automação convencional (centralizada vs distribuída).  
   c. Cite exemplos práticos de cada abordagem.

2. Explique como a popularização dos microcontroladores no início dos anos 2000 viabilizou projetos de IoT.  

   Resposta passo a passo:  
   a. Liste características de microcontroladores (baixo custo, consumo reduzido).  
   b. Mostre como módulos de comunicação se integraram (Wi-Fi, GSM).  
   c. Conecte essa evolução à escalabilidade de protótipos.

3. Calcule a redução de latência proporcionada pelo 5G se comparado ao 4G, sabendo que o 4G tem latência média de 50 ms e o 5G de 1 ms.  

   Resposta passo a passo:  
   a. Subtraia latências: 50 ms – 1 ms = 49 ms.  
   b. Divida pela latência 4G: 49/50 = 0,98.  
   c. Multiplique por 100 para obter percentual: 98 % de redução.

4. Em um fazenda com 120 vacas, o sistema IoT detecta cio em 42 animais por mês. Qual é a taxa de detecção percentual?  

   Resposta passo a passo:  
   a. Relação animais detectados / total: 42/120 = 0,35.  
   b. Multiplique por 100: 35 % de taxa de detecção.

5. Proponha um diagrama de blocos para um sensor ultrassônico de fluxo de água com telemetria via rede móvel.  

   Resposta passo a passo:  
   a. Identifique blocos: sensor ultrassônico, microcontrolador, módulo de comunicação.  
   b. Conecte o fluxo de dados: sensor → MCU → rede móvel → nuvem.  
   c. Inclua alimentação e gerenciamento de energia.

6. Discuta três principais desafios de segurança em aplicações IoT no campo e sugira contramedidas.  

   Resposta passo a passo:  
   a. Liste ameaças (interceptação de dados, firmware malicioso, acesso não autorizado).  
   b. Para cada ameaça, indique solução (criptografia, assinaturas digitais, autenticação de múltiplos fatores).  
   c. Conecte com impacto agrícola.

7. Pesquise um caso real de uso de IoT no agronegócio brasileiro que não foi apresentado em aula e compare-o aos exemplos vistos.  

   Resposta passo a passo:  
   a. Escolha um caso (ex.: monitoramento de solo via sensores de umidade).  
   b. Descreva semelhanças e diferenças técnicas.  
   c. Avalie impactos e resultados obtidos.

8. Modele uma rotina de coleta de dados para um sistema de monitoramento de temperatura em silos utilizando IoT.  

   Resposta passo a passo:  
   a. Defina frequência de leitura de temperatura.  
   b. Especifique protocolo de comunicação (MQTT, HTTP).  
   c. Descreva armazenamento e análise na nuvem.

9. Explique como algoritmos de visão computacional podem diferenciar comportamentos normais de vacas e identificar ciclos de cio.  

   Resposta passo a passo:  
   a. Cite técnicas (deteção de movimento, reconhecimento de postura).  
   b. Explique etapas de pré-processamento (filtragem, segmentação).  
   c. Descreva classificação por rede neural.

10. Elabore um breve plano de projeto para implantação de IoT em uma cultura de soja, incluindo sensores, rede, nuvem e interface de usuário.  

    Resposta passo a passo:  
    a. Liste sensores necessários (umidade do solo, temperatura, luminosidade).  
    b. Escolha tecnologias de conectividade (LoRaWAN, 4G).  
    c. Defina plataforma de nuvem e dashboard de visualização.

---

## Bibliografia

- UNIVESP. Sistemas Embarcados – Sistemas Ciber-Físicos e Internet das Coisas. Professor Marcelo Assunção e Humberto Xavier. YouTube, 23 mar. 2022. Disponível em: https://www.youtube.com/watch?v=kO1vb2uKWBU. Acesso em 10 ago. 2025.
- OLIVEIRA, Claudio Luís Vieira; ZANETTI, Humberto Augusto Piovesana. Arduino Descomplicado. Campinas: Editora Autêntica, 2019.  
- CARVALHO, André C. P. L. F. de; LORENA, Ana Carolina. Introdução à Computação: Hardware, Software e Dados. Rio de Janeiro: LTC, 2017.  
- THOMAZINI, Daniel; ALBUQUERQUE, Pedro Urbano Braga de. Sensores Industriais. 9. ed. Rio de Janeiro: Érica, 2020. E-book. ISBN 9788536533247. Acesso em 10 ago. 2025.  
- OLIVEIRA, André Schneider de; ANDRADE, Fernando Souza de. Sistemas Embarcados – Hardware e Firmware na Prática. 2. ed. Rio de Janeiro: Érica, 2010. E-book. ISBN 9788536520346. Acesso em 10 ago. 2025.  