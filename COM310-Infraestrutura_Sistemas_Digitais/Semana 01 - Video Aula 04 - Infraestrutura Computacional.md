# Infraestrutura Computacional

## Objetivos e importância

Nesta aula, vamos:

- Entender o papel da infraestrutura computacional como base para execução de aplicações em nuvens públicas e privadas. [^2]
- Identificar como a percepção do usuário (latência, falhas de link, segurança) está relacionada a componentes invisíveis de rede e hardware. [^2]
- Reconhecer modelos de serviço como IaaS e como a infraestrutura é oferecida de forma transparente ao usuário. [^2]
- Classificar componentes de infraestrutura em granularidade grossa (macro) e fina (micro) para fins de projeto e operação. [^2]
- Conhecer exemplos práticos de ambientes de pesquisa e projetos de hardware aberto (Open Compute Project, Cerberus). [^2]

---

## Conteúdo principal

### O que é infraestrutura computacional

Infraestrutura computacional é o conjunto de recursos físicos e lógicos que sustenta a execução de software, redes e serviços em nuvem.  

Ela engloba desde data centers com centenas de milhares de servidores até pequenos clusters de pesquisa, garantindo conectividade, desempenho, segurança e disponibilidade dos serviços entregues aos usuários finais. [^2]

### Modelos de serviço

- IaaS (Infrastructure as a Service): provisionamento de servidores, armazenamento e rede como serviço gerenciado.  
- PaaS e SaaS: níveis superiores que utilizam IaaS como base, mas não detalhados nesta aula. [^2]

### Classificação por granularidade

A infraestrutura pode ser pensada em dois níveis de granularidade:

| Granularidade | Componentes principais                                                                                    |
|--------------:|-----------------------------------------------------------------------------------------------------------|
| Grossa        | Racks, servidores completos, roteadores, switches, nobreaks, geradores, sistemas de ar condicionado e segurança física. |
| Fina          | Placas-mãe, processadores, memória RAM, interfaces de rede, discos SSD/HDD, GPUs, fontes redundantes, baterias internas.    |

Tabela de comparação entre granularidades [^2]

#### Componentes de granularidade grossa

- Gabinetes e racks  
- Servidores completos (bare metal ou HCI)  
- Dispositivos de rede de núcleo (roteadores, switches)  
- Sistemas de energia e resfriamento (nobreaks, geradores, climatização)  
- Infraestrutura física de segurança e cabeamento estruturado [^2]

#### Componentes de granularidade fina

- Placas-mãe customizadas para data center  
- CPUs e unidades de processamento acelerado (GPUs, FPGAs)  
- Módulos de memória com perfil de data center  
- Controladores e interfaces de armazenamento (HDD, SSD)  
- Fontes de alimentação redundantes, baterias de back-up locais e sensores de umidade/temperatura [^2]

### Exemplo de infraestrutura de pesquisa

Em um laboratório acadêmico temos:

- Cerca de 60 servidores Intel e AMD organizados em racks.  
- Sistema operacional base Ubuntu e FreeBSD (FreeNAS) para armazenamento.  
- Serviços de autenticação via LDAP e virtualização majoritariamente com KVM/QEMU (algum Hyper-V).  
- Mais de 300 máquinas virtuais gerenciadas por virt-manager localmente e Kimchi remotamente.  
- Projetos de containers híbridos, middleware de nuvem (OpenNebula, OpenStack) e de passagens de mensagem (OpenMPI). [^2]

### Projetos de infraestrutura aberta

#### Open Compute Project

Comunidade global que publica designs de hardware de data center para reduzir custos, melhorar eficiência energética e promover interoperabilidade entre fornecedores. [^2]

#### Cerberus

Projeto que define um microcontrolador criptográfico para garantir a integridade do firmware no boot, protegendo a plataforma contra ataques que comprometam a camada de hardware antes do sistema operacional carregar. [^2]

---

## Análise crítica

Apesar de detalhar componentes físicos e projetos de hardware aberto, a aula não aborda:

- Ferramentas de monitoramento e automação (por exemplo, Prometheus, Ansible) para gestão em larga escala.  
- Orquestração de containers em produção (Docker Swarm, Kubernetes) e práticas de DevOps/SRE.  
- Políticas de governança de dados e compliance em ambientes multi-tenant.  

Esses tópicos são essenciais para um ambiente de produção moderno e podem complementar o entendimento apresentado. [^2]

---

## Exercícios

1. Defina infraestrutura computacional e explique sua importância para aplicações em nuvem.  
2. Compare IaaS, PaaS e SaaS, citando exemplos de cada modelo.  
3. Liste cinco componentes de granularidade grossa e cinco de granularidade fina.  
4. Desenhe um diagrama simplificado de um data center, incluindo sistemas de energia, resfriamento e rede.  
5. Descreva os passos para provisionar uma máquina virtual em um ambiente KVM usando virt-manager.  
6. Explique a lógica de redundância em fontes de alimentação e baterias de backup.  
7. Cite vantagens e desafios de manter uma infraestrutura heterogênea (Intel + AMD, HDD + SSD, CPU + GPU).  
8. Resuma o propósito do Open Compute Project e como ele beneficia provedores de serviços em nuvem.  
9. Explique o papel do Cerberus na segurança de firmware e os tipos de ataques que ele previne.  
10. Proponha uma arquitetura de alta disponibilidade para um pequeno cluster de pesquisa com 10 servidores.  

---

## Bibliografia

- [UNIVESP. Infraestrutura para Sistemas de Software – Infraestrutura Computacional. YouTube, 17 jun. 2025.](https://www.youtube.com/watch?v=EIRcxsVQlJM)  
- Open Compute Project. “OCP Overview,” 2025. https://www.opencompute.org  
- Project Cerberus. “Firmware Resilience and Security Specification,” 2024. https://github.com/opencomputeproject/Project-Cerberus  