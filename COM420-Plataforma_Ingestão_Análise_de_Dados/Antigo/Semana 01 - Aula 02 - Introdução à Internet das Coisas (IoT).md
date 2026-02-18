# Aula 2: Introdução à Internet das Coisas (IoT)

## 1. Origem e Evolução do Conceito

- O termo “Internet das Coisas” foi introduzido por Kevin Ashton em 1999, em um projeto na P&G.  
- Ganhou notoriedade mundial por volta de 2008, com publicações em veículos como *The Guardian*, *Boston Globe* e *Scientific American*.  
- No Brasil, em 2019, surgiu o Plano Nacional de Internet das Coisas, articulando diretrizes para aplicação em setores estratégicos.

---

## 2. Relação entre IoT e Computação em Nuvem

- IoT gera grandes volumes de dados em alta frequência.  
- Computação em nuvem fornece infraestrutura escalável para armazenamento e análise desses dados.  
- A integração permite análise distribuída e resposta em tempo real, com suporte para inteligência artificial e automação.

---

## 3. Arquitetura e Componentes da IoT

| Componente       | Função Principal                                  | Exemplos                       |
|------------------|---------------------------------------------------|--------------------------------|
| Dispositivos     | Coleta de dados do ambiente via sensores          | ESP32, câmeras, termostatos    |
| Conectividade    | Transmissão dos dados coletados                   | Wi-Fi, LoRa, Zigbee, Bluetooth |
| Processamento    | Análise, filtragem e transformação dos dados      | Gateways, cloud platforms      |
| Interface Usuário| Visualização e decisão baseada em dados           | Dashboards, apps móveis        |

- Dispositivos IoT operam com sensores acoplados e conectividade local/remota.  
- Dados são propagados para plataformas via brokers ou VPN, permitindo visualização em tempo real.

---

## 4. Plataformas Middleware para IoT

- **Home Assistant**: permite controlar dispositivos domésticos e visualizar métricas como pacotes de dados transmitidos.  
- **OpenHAB e OpenRemote**: oferecem suporte para ambientes heterogêneos e automação inteligente.  
- Esses sistemas geralmente requerem implantação local, mas podem ser acessados remotamente via VPN.

---

## 5. Tecnologias de Comunicação

| Tecnologia | Alcance  | Vazão       | Custo     | Observação                  |
|------------|----------|-------------|-----------|-----------------------------|
| LoRa       | Alto     | Baixa       | Baixo     | Ideal para sensores distantes|
| Wi-Fi      | Médio    | Alta        | Médio     | Padrões variados: A/B/G/N/AX |
| Bluetooth  | Curto    | Baixa       | Baixo     | Baixo consumo de energia     |
| Zigbee     | Curto    | Moderada    | Baixo     | Protocolo de malha           |
| Satélite   | Muito Alto| Baixa       | Alto      | Abrangência global           |

- A escolha da tecnologia impacta diretamente no consumo, transmissão e análise posterior dos dados coletados.

---

## 6. Aplicações e Exemplos Práticos

- Reconhecimento facial para abertura de portões.  
- Ajuste automático de iluminação e temperatura com base em sensores e preferências do usuário.  
- Motores de aeronaves monitorados por milhares de sensores que garantem operação eficiente.  
- Sistemas de vigilância com câmeras conectadas a DVR/NVR e visualização via celular.

---

## 7. Desafios da IoT

- **Segurança**: dispositivos conectados são vulneráveis a invasões.  
- **Atualização de software embarcado**: requer manutenção constante.  
- **Complexidade**: envolve múltiplos softwares e etapas de processamento.  
- **Energia**: necessidade de fonte constante, uso de baterias e energia solar.  
- **Padronização**: dados frequentemente desestruturados exigem tratamento prévio.  

---

## Lista de Exercícios com Resolução

1. Quem cunhou o termo IoT e em que contexto surgiu?  
   Resolução: Kevin Ashton, projeto na P&G (1999).  

2. Relacione IoT e computação em nuvem com foco na gestão de dados.  
   Resolução: IoT coleta e envia dados para nuvem, que os armazena e analisa.  

3. Cite e descreva os principais componentes do ecossistema IoT.  

4. Quais tecnologias de conectividade são mais usadas em ambientes domésticos de IoT?  

5. Justifique o uso de plataformas como Home Assistant para automação residencial.  

6. Explique por que LoRa é adequada para ambientes com sensores distantes.  

7. Discuta o papel dos sensores na coleta de dados ambientais.  

8. Monte uma topologia simples para coleta e envio de dados de sensores.  

9. Quais os riscos associados ao controle remoto de dispositivos residenciais via VPN?  

10. Projete um sistema de segurança residencial utilizando IoT.  

11. Compare as características do Wi-Fi AX com Zigbee para aplicações em IoT.  

12. Quais fatores influenciam a escolha da tecnologia de transmissão de dados?  

13. Explique como dispositivos IoT podem operar com mínimo de intervenção humana.  

14. Cite três formas de interface entre usuário e sistemas IoT.  

15. Avalie os impactos da rede 5G na evolução das aplicações IoT.  

16. Quais problemas podem surgir da falta de padronização na estrutura dos dados?  

17. Como funciona a identificação de usuários por características de caminhada?  

18. Descreva os tipos de software envolvidos no funcionamento completo de uma plataforma IoT.  

19. Proponha um modelo de análise de dados gerados por sensores térmicos.  

20. Quais são os benefícios de interfaces gráficas para tomada de decisão?  

21. Compare o processo de coleta entre sensores de temperatura e câmeras térmicas.  

22. Discuta o uso de microcontroladores como ESP8266 e ESP32 em IoT.  

23. Faça um estudo de caso sobre a coleta e análise de dados em ambientes industriais.  

24. Que fatores devem ser considerados ao implantar sensores em larga escala?  

25. Quais são os desafios de armazenamento e filtragem de dados em IoT?  

26. Crie um plano de atualização para softwares embarcados em dispositivos residenciais.  

27. Como a IoT se aplica ao controle de iluminação em ambientes comerciais?  

28. Explique a função dos brokers na arquitetura IoT.  

29. Modele um sistema de alerta baseado em sensores termográficos para emergências.  

30. Liste as tecnologias de transmissão citadas na aula e suas principais características.

---

## Bibliografia

- [Plataforma de Ingestão e Análise de Dados – Vídeo “Introdução à Internet das Coisas” (Prof. Júlio Cezar Estrella, UNIVESP), YouTube, acesso em 05/08/2025](https://www.youtube.com/watch?v=0s3HATVC6qs&ab_channel=UNIVESP)  
- Arquitetura IoT para Aplicação em Smart Campus (Proença, TCC Soro, UNIVESP), PDF, acesso em 05/08/2025  
- Braga, André. *Cloud Computing*, UNIVESP, acesso em 05/08/2025  
- “O que é computação em nuvem?”, suporte Nuvem Unicamp, acesso em 05/08/2025

---