# 💻 Computação em Nuvem – Contextualização e Definições

## 1. Introdução  
A computação em nuvem (Cloud Computing) é a entrega de serviços de computação pela internet — englobando servidores, armazenamento, bancos de dados, redes, software, análise e inteligência artificial — de forma a oferecer:
- **Inovação rápida**
- **Recursos flexíveis**
- **Economia de escala**

A aula enfatiza que este modelo representa uma evolução significativa da infraestrutura de TI, alterando a maneira como empresas e usuários comuns consomem e operam recursos computacionais.

---

## 2. Contexto e origem
- Evolução da **computação distribuída** via internet.
- Serviços acessíveis por interfaces padronizadas.
- **Exemplo histórico**: serviços de e-mail migrando de servidores locais para data centers especializados (Gmail, Yahoo, Hotmail).
- Benefícios: simplificação de gestão, backup facilitado, eliminação da necessidade de manter servidores internos.

📌 **Análise crítica**: o professor ilustra bem as vantagens, mas não menciona explicitamente riscos como dependência de fornecedor (*vendor lock-in*) e requisitos de conformidade legal, que na prática são grandes fatores de decisão no uso de nuvem.

---

## 3. Evolução histórica
- **Anos 1970–1990**: *Remote Job Entry* (RJE) — execução de tarefas em computadores remotos.
- **2006**: Amazon lança a primeira nuvem pública de larga escala.
- Modelo de cobrança inspirado em serviços públicos (água, luz): paga-se pelo uso efetivo de recursos.

---

## 4. Conceito e vantagens
- Hospedagem e processamento em servidores remotos interligados.
- Uso de protocolos padronizados da web (WWW).
- Escalabilidade e disponibilidade para qualquer tipo de usuário.
- Redução de custos operacionais e de infraestrutura.

---

## 5. Comparação com Computação em Grade
- **Grid computing**: foco em processamento paralelo para grandes problemas científicos.
- **Cloud computing**: oferta de recursos como serviço sob demanda para usos amplos, inclusive comerciais.

---

## 6. Componentes principais
1. **Clientes**: dispositivos que acessam a nuvem (desktop, notebook, tablet, celular).
2. **Servidores distribuídos**: hardware (CPU, memória, discos) distribuído geograficamente.
3. **Data centers**: estruturas físicas que abrigam servidores, com forte consumo energético.

---

## 7. Modelos de serviço
- **SaaS (Software as a Service)**: software acessado via nuvem, sem gestão de infraestrutura pelo cliente (ex.: Gmail).
- **PaaS (Platform as a Service)**: plataforma para desenvolvimento/execução de aplicações sem gerenciar servidores (ex.: Google App Engine).
- **IaaS (Infrastructure as a Service)**: provê infraestrutura de rede, servidores e armazenamento virtualizado (ex.: AWS EC2).

📌 **Análise crítica**: a aula aborda bem a abstração entre camadas. Seria interessante destacar que o custo-benefício e a performance variam muito entre SaaS, PaaS e IaaS, exigindo análise estratégica.

---

## 8. Modelos de implantação
- **Nuvem pública**: infraestrutura compartilhada entre vários clientes.
- **Nuvem privada**: dedicada a uma única organização; maior controle e segurança.
- (Menção breve) **Nuvem híbrida**: combinação de pública e privada.

---

## 9. Acesso e integração
- Uso de APIs padronizadas para conexão entre aplicações e serviços na nuvem.
- Compatibilidade multi-plataforma (Windows, MacOS, Linux, dispositivos móveis).
- Forte ênfase em segurança, manutenção transparente ao usuário e desempenho.

---

## 10. Fatores que impulsionam a nuvem
- Processadores multicore.
- Virtualização.
- Armazenamento distribuído.
- Gerenciamento automatizado.
- Conexão de internet mais barata e veloz.
- Servidores mais acessíveis.

---

## 11. Aplicações típicas
- **SaaS**: e-mail, sistemas de gestão online, edição colaborativa.
- **PaaS**: plataformas de desenvolvimento web e mobile.
- **IaaS**: ambientes de testes, hospedagem de sites de alta demanda.

---

# 📚 Lista de Exercícios com Resolução Detalhada

1. **Defina computação em nuvem segundo o conceito apresentado.**  
   **Resolução:**  
   1. É o fornecimento de serviços de computação (servidores, armazenamento, rede, software, análise, IA) pela internet.  
   2. Objetiva inovação rápida, recursos flexíveis e economia de escala.  
   3. Acesso remoto e sob demanda.

2. **Cite três vantagens da computação em nuvem para empresas.**  
   **Resolução:**  
   - Redução de custos com hardware e manutenção.  
   - Maior agilidade para implantar soluções.  
   - Escalabilidade e flexibilidade de recursos.

3. **Explique o impacto da nuvem na transformação digital.**  
   **Resolução:**  
   1. Fornece recursos sob demanda.  
   2. Facilita experimentação rápida de novas soluções.  
   3. Suporta crescimento ou redução conforme a demanda.

4. **Descreva um exemplo histórico de serviço migrado para nuvem.**  
   **Resolução:**  
   - E-mails corporativos: antes locais, agora hospedados em data centers como Gmail ou Outlook.com, gerenciados por terceiros.

5. **Compare computação em nuvem e computação em grade.**  
   **Resolução:**  
   - **Grade:** foca em processar grandes problemas científicos com paralelismo.  
   - **Nuvem:** oferta ampla de recursos como serviço, para diversos usos.

6. **Liste os três componentes principais da nuvem.**  
   **Resolução:**  
   - Clientes (usuários/dispositivos).  
   - Servidores distribuídos.  
   - Data centers.

7. **Explique o papel dos servidores distribuídos.**  
   **Resolução:**  
   - Hospedar e processar dados/aplicações, distribuídos geograficamente para atender diferentes regiões e melhorar latência.

8. **O que caracteriza um data center?**  
   **Resolução:**  
   - Estrutura física especializada, com servidores, sistemas de energia, climatização, segurança e rede para hospedar recursos.

9. **Defina SaaS.**  
   **Resolução:**  
   - Software como serviço, acessível via nuvem, sem necessidade de instalação local ou gestão de infraestrutura pelo cliente.

10. **Dê um exemplo de SaaS.**  
    **Resolução:**  
    - Google Docs, Gmail, Trello.

11. **Defina PaaS.**  
    **Resolução:**  
    - Plataforma como serviço: ambiente que oferece ferramentas, linguagens e infraestrutura para desenvolvimento/execução de aplicações.

12. **Exemplo de PaaS.**  
    **Resolução:**  
    - Google App Engine, Heroku.

13. **Defina IaaS.**  
    **Resolução:**  
    - Infraestrutura como serviço: fornece recursos básicos de TI virtualizados — servidores, rede, armazenamento.

14. **Exemplo de IaaS.**  
    **Resolução:**  
    - Amazon EC2, Microsoft Azure VM.

15. **Explique a importância da virtualização para nuvem.**  
    **Resolução:**  
    - Permite criar instâncias isoladas de sistemas e serviços num mesmo hardware físico, otimizando uso e escalabilidade.

16. **O que é encapsulamento de complexidade na nuvem?**  
    **Resolução:**  
    - O usuário não precisa conhecer detalhes internos da infraestrutura; interage via interfaces e APIs simplificadas.

17. **Descreva uma nuvem pública.**  
    **Resolução:**  
    - Infraestrutura compartilhada, acessível pela internet a múltiplos clientes, com recursos provisionados sob demanda.

18. **Descreva uma nuvem privada.**  
    **Resolução:**  
    - Infraestrutura dedicada a uma organização, oferecendo maior controle e segurança sobre dados e recursos.

19. **Como as APIs são usadas na nuvem?**  
    **Resolução:**  
    - Fornecem interfaces padronizadas para que clientes e aplicações acessem e integrem serviços na nuvem.

20. **Benefício do acesso multiplataforma na nuvem.**  
    **Resolução:**  
    - Usuários podem acessar serviços de qualquer sistema operacional ou dispositivo compatível, ampliando mobilidade.

21. **Explique o conceito de “serviço sob demanda” na nuvem.**  
    **Resolução:**  
    - O cliente provisiona e paga apenas pelos recursos utilizados, podendo expandir ou reduzir conforme necessidade.

22. **Quais custos estão embutidos no preço de uma VM na nuvem?**  
    **Resolução:**  
    - Energia elétrica, refrigeração, manutenção, pessoal, espaço físico e margem de lucro do provedor.

23. **Cite dois fatores que impulsionaram a adoção da nuvem.**  
    **Resolução:**  
    - Processadores multicore.  
    - Armazenamento distribuído.

24. **Explique o papel da conectividade na popularização da nuvem.**  
    **Resolução:**  
    - Aumento da velocidade e redução do custo de internet tornaram viável o acesso constante a serviços remotos.

25. **Dê um exemplo de aplicação SaaS popular.**  
    **Resolução:**  
    - Microsoft 365 Online.

26. **Benefício de PaaS para desenvolvedores.**  
    **Resolução:**  
    - Permite focar no código sem se preocupar com a gestão de servidores e sistemas.

27. **Vantagem do IaaS para testes.**  
    **Resolução:**  
    - Provisionamento rápido de servidores temporários para validar soluções sem investimento em hardware físico.

28. **Quando pode ser necessário manter infraestrutura própria?**  
    **Resolução:**  
    - Por requisitos legais, de segurança, latência ou controle específico sobre recursos.

29. **O que significa escalabilidade na nuvem?**  
    **Resolução:**  
    - Capacidade de aumentar ou reduzir recursos automaticamente conforme a demanda.

30. **Como a nuvem facilita a composição de novas soluções?**  
    **Resolução:**  
    - Permite testar, ajustar e publicar aplicações rapidamente usando recursos já disponíveis via internet.


---

# 📖 Bibliografia

- ESTRELLA, Julio Cezar. **Infraestrutura para Sistemas de Software – Computação em Nuvem: Contextualização e Definições**. UNIVESP, 2025. Vídeo-aula no YouTube. Acesso em: 14 ago. 2025.
- ARMSTRONG, E.; REESE, G. *Cloud Computing – Concepts, Technology & Architecture*. Pearson, 2017.
- Amazon Web Services. [Modelos de Serviço em Nuvem](https://aws.amazon.com/pt/types-of-cloud-computing/). Acesso em: 14 ago. 2025.
- NEMETH, E.; SNYDER, G.; HEIN, T. R. *Manual completo do Linux: guia do administrador*. São Paulo: Pearson, 2005.
