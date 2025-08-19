# Aplicações IoT em Contêineres Docker  
**Disciplina:** Plataforma de Ingestão e Análise de Dados  
**Professor:** Júlio Cezar Estrella  

---

## 1. Introdução

Nesta aula, o professor apresenta como a tecnologia de **contêineres** pode ser aplicada ao desenvolvimento e operação de soluções de **Internet das Coisas (IoT)**. O foco está em entender **por que** e **como** usar contêineres nesse contexto, explorando vantagens, desafios, integração com **microsserviços**, otimização e segurança.

---

## 2. Por que usar contêineres em IoT

- **Portabilidade**: Executam em diferentes ambientes (nuvem, servidores locais, dispositivos embarcados) sem alterações no código.  
- **Eficiência**: Consomem menos recursos que máquinas virtuais, ideal para hardware limitado.  
- **Isolamento**: Cada serviço roda de forma independente, reduzindo impacto de falhas.  
- **Escalabilidade**: Fácil replicação e distribuição de instâncias.  
- **Atualização simplificada**: Possibilidade de atualizar software remotamente, sem intervenção física.  
- **Integração com nuvem**: Aproveita recursos de armazenamento, processamento e análise.

---

## 3. Contêineres e microsserviços

- **Arquitetura recomendada**: Separar funções em serviços independentes (ex.: coleta de dados, processamento, armazenamento).  
- **Vantagens**:
  - Disponibilidade e escalabilidade.
  - Facilidade de manutenção e resolução de problemas.
  - Modularidade: um serviço pode lidar com múltiplas tecnologias de comunicação (Zigbee, Wi-Fi, LoRa).  
- **Evitar monólitos**: Reduz acoplamento e aumenta flexibilidade.

---

## 4. Ciclo de desenvolvimento de aplicações IoT em contêineres

1. **Base**: Obter imagem existente de um registro (Docker Hub ou privado).  
2. **Customização**: Adicionar/remover pacotes, configurar serviços, incluir código da aplicação.  
3. **Testes**:  
   - Locais (debug, integração).  
   - Automatizados (ex.: Jenkins, GitHub Actions).  
4. **Publicação**: Enviar imagem ou Dockerfile para repositório.  
5. **Implantação**:  
   - Nuvem, servidor local ou dispositivo embarcado (ex.: System-on-Chip com Linux).  
6. **Monitoramento**: Acompanhar desempenho, comunicação entre serviços e integridade.  
7. **Atualização**: Distribuir novas versões de forma remota e controlada.

---

## 5. Otimização para IoT

- **Imagens leves**: Minimizar pacotes e bibliotecas.  
- **Compatibilidade**: Criar imagens para múltiplas arquiteturas (ARM, x86).  
- **Uso de microcontêineres**: Executar apenas o necessário, reduzindo consumo.  
- **Abstração de hardware**: Facilita desenvolvimento em linguagens de alto nível.  
- **Orquestração**: Planejar escalabilidade e distribuição.

---

## 6. Segurança

- **Princípio do mínimo necessário**: Executar apenas serviços essenciais.  
- **Verificação de vulnerabilidades**: Usar scanners de imagens (Docker Hub, Docker Cloud).  
- **Proteção de rede**: Firewalls, DMZ, honeypots.  
- **Isolamento de dados sensíveis**: Evitar exposição indevida.  
- **Atualizações seguras**: Garantir integridade antes do deploy.

---

## 7. Desafios

- **Monitoramento contínuo**: Necessário para detectar falhas e manter disponibilidade.  
- **Gerenciamento de atualizações**: Planejar frequência e impacto.  
- **Segurança em escala**: Quanto mais dispositivos, maior a superfície de ataque.  
- **Integração com hardware limitado**: Ajustar imagens e serviços para restrições de CPU, memória e armazenamento.

---

## 8. Análise crítica

- O uso de contêineres em IoT é altamente vantajoso, mas exige **planejamento de segurança** e **monitoramento robusto**.  
- A arquitetura de microsserviços é mais adequada que monólitos, mas aumenta a complexidade de orquestração.  
- A otimização de imagens e a compatibilidade com múltiplas arquiteturas são cruciais para viabilidade em campo.  
- O ciclo de desenvolvimento deve considerar desde o design até o “day after” — manutenção e evolução da solução.

---

## 9. Lista de Exercícios com Resolução

1. **Explique por que contêineres são adequados para IoT.**  
   *Resposta:* Portabilidade, eficiência, isolamento, escalabilidade e facilidade de atualização.

2. **Qual a principal vantagem de microsserviços sobre monólitos em IoT?**  
   *Resposta:* Modularidade e facilidade de manutenção.

3. **Descreva o ciclo básico de desenvolvimento de uma aplicação IoT em contêineres.**  
   *Resposta:* Base → Customização → Testes → Publicação → Implantação → Monitoramento → Atualização.

4. **Por que criar imagens para múltiplas arquiteturas?**  
   *Resposta:* Garantir execução em diferentes hardwares (ARM, x86).

5. **O que é um microcontêiner?**  
   *Resposta:* Imagem mínima que executa apenas o necessário para a aplicação.

6. **Como contêineres facilitam atualizações remotas?**  
   *Resposta:* Permitem substituir a imagem em execução por uma nova versão sem acesso físico.

7. **Qual a importância do monitoramento em IoT com contêineres?**  
   *Resposta:* Detectar falhas, garantir comunicação e disponibilidade.

8. **Cite três práticas de segurança para contêineres IoT.**  
   *Resposta:* Mínimo necessário, verificação de vulnerabilidades, proteção de rede.

9. **O que é abstração de hardware e por que é útil?**  
   *Resposta:* Permite desenvolver sem depender de detalhes físicos, facilitando portabilidade.

10. **Como evitar acoplamento excessivo em contêineres?**  
    *Resposta:* Usar arquitetura de microsserviços.

11. **Qual ferramenta pode automatizar testes e deploy?**  
    *Resposta:* Jenkins.

12. **Por que imagens leves são importantes em IoT?**  
    *Resposta:* Reduzem consumo de recursos e tempo de deploy.

13. **Como proteger dados sensíveis em contêineres?**  
    *Resposta:* Isolamento e criptografia.

14. **O que é DMZ e sua função?**  
    *Resposta:* Zona desmilitarizada; isola dispositivos da rede interna.

15. **Como lidar com múltiplas tecnologias de comunicação em IoT?**  
    *Resposta:* Criar microsserviço que suporte vários protocolos.

16. **Qual a relação entre contêineres e nuvem em IoT?**  
    *Resposta:* Contêineres aproveitam escalabilidade e recursos da nuvem.

17. **Por que evitar instalar pacotes desnecessários?**  
    *Resposta:* Reduz vulnerabilidades e tamanho da imagem.

18. **Como verificar vulnerabilidades em imagens?**  
    *Resposta:* Usar scanners de segurança do Docker Hub ou similares.

19. **O que é orquestração de contêineres?**  
    *Resposta:* Gerenciamento automatizado de múltiplos contêineres.

20. **Como planejar o “day after” em IoT?**  
    *Resposta:* Definir estratégias de atualização, monitoramento e coleta de dados.

21. **Qual a vantagem de usar linguagens de alto nível em microcontêineres?**  
    *Resposta:* Facilita desenvolvimento e manutenção.

22. **Como reduzir a superfície de ataque em IoT?**  
    *Resposta:* Executar apenas serviços essenciais e isolar redes.

23. **Por que a escalabilidade é crítica em IoT?**  
    *Resposta:* Permite atender aumento de dispositivos sem perda de desempenho.

24. **Como contêineres ajudam na modularidade?**  
    *Resposta:* Cada serviço roda isolado, podendo ser atualizado ou substituído.

25. **O que é um registro de contêineres?**  
    *Resposta:* Repositório para armazenar e distribuir imagens.

26. **Como integrar contêineres a dispositivos embarcados?**  
    *Resposta:* Usar imagens compatíveis com a arquitetura e recursos do hardware.

27. **Qual a importância de testes automatizados?**  
    *Resposta:* Garantem qualidade e reduzem erros antes do deploy.

28. **Como contêineres facilitam a replicação de soluções?**  
    *Resposta:* Imagens podem ser distribuídas e executadas em múltiplos ambientes.

29. **O que é controle de versão de software em contêineres?**  
    *Resposta:* Registro de mudanças e versões para rastreabilidade.

30. **Como a coleta de dados se integra ao desenvolvimento IoT?**  
    *Resposta:* Dados coletados alimentam análises para melhorar a solução.

---

## 10. ### Bibliografia atualizada

- **Título:** Plataforma de Ingestão e Análise de Dados – Aplicações IoT em Containers Docker (LIBRAS)  
  **Autor(es):** Júlio Cezar Estrella  
  **Tipo:** Vídeo (YouTube)  
  **Link:** https://www.youtube.com/watch?v=S8_DBzR169c  
  **Acesso:** 19 ago. 2025

- **Título:** Arquitetura IoT para Aplicação em Smart Campus  
  **Autor(es):** M. H. Proença  
  **Tipo:** TCC/PDF (Blackboard)  
  **Link:** disponibilizado na plataforma (Blackboard/Univesp)  
  **Acesso:** 19 ago. 2025

- **Título:** O que é computação em nuvem?  
  **Autor(es):** Unicamp (Serviço de TI)  
  **Tipo:** Artigo web institucional  
  **Link:** https://suporte.nuvem.unicamp.br/sobre/o_que_e.html  
  **Acesso:** 19 ago. 2025

- **Título:** Cloud Computing  
  **Autor(es):** André Braga  
  **Tipo:** Apostila/PDF (Blackboard)  
  **Link:** disponibilizado na plataforma (Blackboard/Univesp)  
  **Acesso:** 19 ago. 2025

- **Título:** Gerenciamento de Dados em Nuvem: Conceitos, Sistemas e Desafios  
  **Autor(es):** Flávio R. C. Sousa; Leonardo O. Carvalho  
  **Tipo:** Apostila/PDF (Blackboard)  
  **Link:** disponibilizado na plataforma (Blackboard/Univesp)  
  **Acesso:** 19 ago. 2025

- **Título:** O que é Docker – Um guia básico passo a passo para iniciantes  
  **Autor(es):** TipsCode  
  **Tipo:** Artigo web  
  **Link:** https://tipscode.com.br/o-que-e-docker-guia-basico-passo-a-passo  
  **Acesso:** 19 ago. 2025

- **Título:** Docker e Docker Compose – Um guia para iniciantes  
  **Autor(es):** Dev.to (Ingresse)  
  **Tipo:** Artigo web  
  **Link:** https://dev.to/ingresse/docker-e-docker-compose-um-guia-para-iniciantes-48k8  
  **Acesso:** 19 ago. 2025

- **Título:** Get started with Docker  
  **Autor(es):** Docker, Inc.  
  **Tipo:** Documentação oficial  
  **Link:** https://docs.docker.com/get-started/  
  **Acesso:** 19 ago. 2025

- **Título:** Docker: Lightweight Linux Containers for Consistent Development and Deployment  
  **Autor(es):** Dirk Merkel  
  **Tipo:** Artigo (Linux Journal)  
  **Link:** https://www.linuxjournal.com/content/docker-lightweight-linux-containers-consistent-development-and-deployment  
  **Acesso:** 19 ago. 2025