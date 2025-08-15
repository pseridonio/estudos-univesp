# Sistemas Embarcados – Sistemas Ciber-Físicos e Internet das Coisas (IoT)

## 1. Sistemas Ciber-Físicos (CPS)

Sistemas ciber-físicos são integrações de processos físicos com computação e redes de comunicação, responsáveis por monitorar e controlar fenômenos do mundo real em tempo quase real. Essas plataformas unem sensores que observam o ambiente, atuadores que interagem com ele e software embarcado que realiza cálculos e decisões de controle.  

Embora o vídeo aproxime CPS e Internet das Coisas, existe distinção: CPS enfatiza o laço de controle e resposta rápida entre o físico e o computacional; IoT foca na interconexão e troca de dados entre objetos via internet.

---

## 2. Internet das Coisas (IoT)

A Internet das Coisas refere-se à rede de objetos físicos embutidos com sensores, atuadores e conectividade, capazes de coletar, enviar e receber dados sem intervenção humana direta.  

Principais camadas de uma solução IoT:
- Camada de Percepção: sensores e atuadores.  
- Camada de Rede: protocolos (Wi-Fi, LoRaWAN, 5G) e gateways que transportam dados.  
- Camada de Aplicação: plataformas na nuvem, bancos de dados, dashboards e APIs para análise e visualização.

---

## 3. Hardware e Firmware em Sistemas Embarcados

### 3.1 Sensores e Atuadores

| Tipo de Sensor       | Princípio de Funcionamento              | Exemplo de Aplicação             |
|----------------------|-----------------------------------------|----------------------------------|
| Ultrassônico         | Emite/recebe ondas sonoras para medir distância | Medição de nível em silos        |
| Temperatura (RTD/Thermistor) | Variação de resistência elétrica com a temperatura | Controle de forno industrial     |
| Acelerômetro         | Detecta aceleração e vibração           | Monitoramento de máquinas rotativas |

Atuadores convertem sinais elétricos em movimento ou ação física, como relés, motores e válvulas.

### 3.2 Firmware vs. Software

Firmware é o software dedicado que roda diretamente no microcontrolador, com funções específicas e estreitas. Diferencia-se de software genérico por:
- Ser otimizado para recursos limitados (memória e energia).  
- Frequentemente implementado em C ou Assembly, visando determinismo.  
- Permitir resposta em tempo real a eventos do sensor ou comandos externos.

---

## 4. Plataforma Arduino e Ambiente de Desenvolvimento

O Arduino é uma plataforma open-source composta por placa de hardware (microcontrolador, memória, GPIOs) e IDE (Integrated Development Environment).  

Vantagens do IDE Arduino:
- Interface simples e gratuita.  
- Biblioteca extensa de exemplos e drivers para sensores/atuadores.  
- Compatibilidade com diversas placas (Uno, Mega, ESP32).  
- Comunidade ativa e vasto acervo de tutoriais online.

---

## 5. Exemplos de Aplicação

- Automação residencial: sensores de presença e atuadores para controle de iluminação.  
- Monitoramento agro: IoT no campo para medir umidade do solo e acionar bombas de irrigação.  
- Indústria 4.0: CPS em linhas de produção para ajustes automáticos de velocidade de esteiras.  

Em todos os casos, o firmware embarcado lê sensores, processa dados segundo algoritmo predefinido e comanda atuadores, reportando eventos críticos à nuvem.

---

## Exercícios

1. Defina sistema ciber-físico e explique, em até três frases, como ele difere de uma solução de IoT.  
   Resolução:  
   a. CPS integra controle físico e computação em um laço de realimentação.  
   b. Em CPS, decisões de controle ocorrem localmente, com baixa latência.  
   c. IoT prioriza conectividade e troca de dados, mas não necessariamente controle em tempo real.

2. Liste as três camadas de arquitetura de um sistema IoT e descreva a função de cada uma.  
   Resolução:  
   a. Percepção: coleta dados via sensores/atuadores.  
   b. Rede: transporta dados usando protocolos e gateways.  
   c. Aplicação: armazena, processa e apresenta informações a usuários ou sistemas.

3. Dê um exemplo de sensor ultrassônico em sistemas embarcados e explique, passo a passo, como ele mede distância.  
   Resolução:  
   a. Emite um pulso de som ultrassônico.  
   b. Usa receptor para capturar o eco refletido.  
   c. Calcula distância pelo tempo de ida e volta: distância = (velocidade do som × tempo)/2.

4. Qual a principal diferença entre firmware e software tradicional?  
   Resolução:  
   a. Firmware é dedicado e otimizado para hardware específico.  
   b. Opera em tempo real com recursos limitados.  
   c. Software tradicional roda em sistemas operacionais mais genéricos e flexíveis.

5. Desenhe mentalmente o fluxo de dados de um sistema embarcado que controla irrigação: sensor de umidade → microcontrolador → válvula. Liste cada etapa.  
   Resolução:  
   a. Leitura analógica do sensor de umidade.  
   b. Conversão AD e processamento do valor no firmware.  
   c. Saída digital para driver que aciona válvula de água.

6. Cite duas vantagens do IDE Arduino para prototipagem rápida de sistemas embarcados.  
   Resolução:  
   a. Biblioteca de exemplos pronta para uso.  
   b. Interface intuitiva e suporte a múltiplas placas.

7. Proponha um critério de threshold para alertar níveis críticos de umidade do solo em uma fazenda inteligente. Explique seu raciocínio.  
   Resolução:  
   a. Medir umidade em porcentagem pelo sensor.  
   b. Definir threshold em, por exemplo, 30 % (quando o solo está seco).  
   c. Firmware envia alerta via MQTT se valor < 30 %.

8. Em um projeto com ESP32 usando Arduino IDE, descreva como você incluiria uma biblioteca para sensor DHT11 e acessaria leituras de temperatura.  
   Resolução:  
   a. No IDE, vá em “Sketch → Incluir Biblioteca → Gerenciar Bibliotecas” e instale “DHT sensor library”.  
   b. No código, adicione `#include <DHT.h>` e inicialize: `DHT dht(pin, DHT11);`.  
   c. No loop, chame `dht.readTemperature()` para obter valor em °C.

9. Explique o papel do atuador em um CPS de linha de montagem e cite um exemplo prático.  
   Resolução:  
   a. Atuador executa ação física (mover, segurar, soldar).  
   b. Exemplo: pistão pneumático que desloca peças após inspeção de qualidade.

10. Crie um mini-plano de bibliotecas e sensores para um dispositivo de monitoramento de temperatura em freezer industrial.  
    Resolução:  
    a. Sensor: DS18B20 para faixa −55 °C a 125 °C.  
    b. Biblioteca: “OneWire” e “DallasTemperature”.  
    c. Comunicação: I2C para display local e MQTT para cloud.  
    d. Alerta: enviar notificação se temperatura > −18 °C.

---

## Bibliografia

- OLIVEIRA, Claudio Luís Vieira; ZANETTI, Humberto Augusto Piovesana. Arduino Descomplicado. Campinas: Editora Autêntica, 2019.  
- CARVALHO, André C. P. L. F. de; LORENA, Ana Carolina. Introdução à Computação: Hardware, Software e Dados. Rio de Janeiro: LTC, 2017.  
- THOMAZINI, Daniel; ALBUQUERQUE, Pedro Urbano Braga de. Sensores Industriais. 9. ed. Rio de Janeiro: Érica, 2020. E-book. ISBN 9788536533247. Disponível em: https://integrada.minhabiblioteca.com.br/reader/books/9788536533247/ (Acesso em 10 ago. 2025).  
- OLIVEIRA, André Schneider de; ANDRADE, Fernando Souza de. Sistemas Embarcados – Hardware e Firmware na Prática. 2. ed. Rio de Janeiro: Érica, 2010. E-book. ISBN 9788536520346. Disponível em: https://integrada.minhabiblioteca.com.br/reader/books/9788536520346/ (Acesso em 10 ago. 2025).  
- NIST. A Framework for Cyber-Physical Systems: Volume 1, Overview; 2017. Disponível em: https://www.nist.gov/publications/framework-cyber-physical-systems (Acesso em 10 ago. 2025).  
- IBM. What is the Internet of Things (IoT)? 2025. Disponível em: https://www.ibm.com/topics/internet-of-things (Acesso em 10 ago. 2025).  
- WIKIPÉDIA. Internet das Coisas. Disponível em: https://pt.wikipedia.org/wiki/Internet_das_coisas (Acesso em 10 ago. 2025).