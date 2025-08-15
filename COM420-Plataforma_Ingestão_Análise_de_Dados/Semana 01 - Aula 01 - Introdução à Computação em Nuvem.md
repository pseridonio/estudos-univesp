# Aula 1: Introdução à Computação em Nuvem

## 1. História da Computação em Nuvem

A ideia de oferecer processamento como serviço remonta aos primeiros datacenters dos anos 1940, quando grandes mainframes ficavam concentrados em salas climatizadas e eram acessados por terminais burros [2].  

Na década de 1960 surgiram empresas de processamento de dados, evoluindo para clusters interligados por redes nos anos 1980 e grades computacionais nos anos 1990.  

Embora o vídeo mencione o auge da “computação como serviço” a partir de 2012, o lançamento do Amazon EC2 em 2006 antecipou em vários anos essa era [2].  

---

## 2. O que é Computação em Nuvem?

Computação em nuvem é um modelo de disponibilização de recursos de TI (processamento, armazenamento, redes, software) sob demanda via Internet, com escalabilidade e elasticidade automáticas [4].  

A Nuvem se baseia em cinco características essenciais:  
- Autoatendimento sob demanda  
- Amplo acesso à rede  
- Agrupamento de recursos  
- Elasticidade rápida  
- Serviço medido  

---

## 3. Modelos de Implantação

| Modelo            | Descrição                                                          | Propriedade             | Exemplo                |
|-------------------|--------------------------------------------------------------------|-------------------------|------------------------|
| Nuvem Pública     | Infraestrutura gerenciada por provedor, acesso aberto via Internet | Terceirizado            | AWS, Azure, Google     |
| Nuvem Privada     | Infraestrutura dedicada a uma única organização                   | Local ou terceirizado   | Datacenter bancário    |
| Nuvem Comunitária | Compartilhada por organizações com interesses comuns               | Colaboração entre pares | Consórcios governamentais |
| Nuvem Híbrida     | Combinação de pública e privada para flexibilidade                  | Misto                   | Integração AWS + CPD    |

A nuvem comunitária surge como variante para setores regulados ou com governança colaborativa [5].  

---

## 4. Modelos de Serviço

1. Infraestrutura como Serviço (IaaS)  
   - Provisão de recursos virtuais (CPU, memória, disco, rede)  
   - Exemplos: Amazon EC2, Google Compute Engine, OpenStack [2]

2. Plataforma como Serviço (PaaS)  
   - Ambiente completo para desenvolvimento, teste e deployment  
   - Exemplos: Google App Engine, Azure App Service [2]

3. Software como Serviço (SaaS)  
   - Aplicações prontas acessadas via navegador ou API  
   - Exemplos: Google Workspace, Salesforce, Office 365 [2]

---

## 5. Características Atuais da Nuvem

A computação em nuvem atual oferece:  
- Escala praticamente ilimitada, invisível ao usuário final [2].  
- Transparência quanto à localização física dos dados [2].  
- Autosserviço e faturamento pay-per-use conforme ciclos de processamento e armazenamento [2].  
- Diversas formas de distribuição geográfica, permitindo baixa latência e alta disponibilidade [2].  
- Suporte a workloads massivos de dados (terabytes a petabytes), com bancos NoSQL e ferramentas de análise em larga escala [2].

---

## 6. Topologia de Data Centers

Um datacenter de nuvem típica é composto por racks (“hacks”) cheios de servidores em U-units, interligados por switches e roteadores de alta capacidade.  

```text

+---------+      +-----------+     +-------------+  
| Clientes| ←→   | Front-End | ←→  | Switch Core |  
+---------+      +-----------+     +-------------+  
                       ↓                  ↓  
                 +------------+   +---------------+  
                 | Servidores |   | Armazenamento |
                 +------------+   +---------------+
```

O front-end faz autenticação e firewall, enquanto o back-end processa e armazena os dados [2].  

---

## 7. Modelagem

Para representar conceitualmente uma nuvem, utilizamos modelos de componentes (serviço, infraestrutura, rede, segurança) e fluxos de dados, destacando nós de computação, módulos de balanceamento e camadas de persistência.  

---

## Lista de Exercícios

1. Defina computação em nuvem e aponte suas cinco características essenciais.  
   Resolução: Explique a definição “modelo de oferta de recursos via Internet sob demanda” e descreva autoatendimento sob demanda, amplo acesso à rede, agrupamento de recursos, elasticidade e serviço medido.  

2. Descreva brevemente a evolução histórica da computação em nuvem desde os anos 1940 até hoje.  
   Resolução: Cite datacenters originais, clusters, grades e surgimento das grandes nuvens do mercado.  

3. Compare nuvem pública e privada em termos de propriedade, acesso e custos.  
   Resolução: Use tabela para evidenciar diferenças de gestão e modelo financeiro.  

4. Explique o que é IaaS e cite dois exemplos comerciais.  
   Resolução: Definição de Infraestrutura como Serviço e exemplos EC2, Compute Engine.  

5. Em que situações PaaS é mais vantajoso que IaaS?  
   Resolução: Ambiente gerenciado reduz esforço de configuração; foco no desenvolvimento.  

6. Dê dois exemplos de SaaS e explique um caso de uso empresarial para cada um.  

7. Interprete rapidamente a topologia de um datacenter de nuvem e identifique seus principais componentes.  

8. Qual a vantagem de ter datacenters distribuídos geograficamente?  

9. Discuta riscos e mitigações relacionados à transparência da localização de dados.  

10. Calcule o custo mensal aproximado para um servidor EC2 com 2 vCPUs e 8 GB RAM, custando US\$0,04 por vCPU-hora e US\$0,01 por GB-hora de RAM, em 30 dias corridos (24 h/dia).  
    Resolução: vCPU: 2 × 24 × 30 × 0,04 = US\$57,6; RAM: 8 × 24 × 30 × 0,01 = US\$57,6; total = US\$115,2.  

11. Explique por que a adoção de NoSQL aumentou com a nuvem.  

12. Descreva a função de um front-end em um datacenter.  

13. Compare balanceamento de carga e failover em nuvens públicas.  

14. Dialogue sobre como “pague conforme o uso” impacta o orçamento de startups.  

15. Projete um mini-datacenter privado para uma empresa de 50 funcionários, indicando hardware básico.  

16. Quais são as tecnologias de virtualização mais comuns em IaaS?  

17. Proponha um método de monitoramento de performance para VMs em nuvem.  

18. Discuta a diferença entre elasticidade e escalabilidade.  

19. Elabore um diagrama simplificado de fluxo de dados cliente-nuvem.  

20. Investigue o que são SLAs de nuvem e cite métricas comuns.  

21. Analise vantagens e desvantagens de migration para nuvem híbrida.  

22. Identifique três serviços básicos do AWS S3 e descreva cada um.  

23. Demonstre como autenticar um usuário via front-end antes de acessar recursos de cloud.  

24. Explique o conceito de resource pooling em datacenters.  

25. Cite dois casos de uso de community cloud na área de saúde.  

26. Discuta como a nuvem pode acelerar projetos de ingestão de dados em Smart Campus [3].  

27. Descreva o papel de contêineres Docker em PaaS.  

28. Avalie os impactos de latência ao acessar IaaS em outra região geográfica.  

29. Apresente um plano de backup e recuperação em nuvem.  

30. Pesquise e documente quatro ferramentas open-source usadas em nuvem [5].  

---

## Bibliografia

- [Plataforma de Ingestão e Análise de Dados – Vídeo “Introdução à Computação em Nuvem” (Professor Júlio Cezar Estrella, UNIVESP), YouTube, acesso em 05/08/2025 [2].](https://www.youtube.com/watch?v=w0thcaHLOAI&ab_channel=UNIVESP)  
- Arquitetura IoT para Aplicação em Smart Campus (Proença, TCC Soro, UNIVESP), PDF, acesso em 05/08/2025 [3].  
- “O que é computação em nuvem?”, suporte Nuvem Unicamp, acesso em 05/08/2025, https://suporte.nuvem.unicamp.br/sobre/o_que_e.html [4].  
- Braga, André. Cloud Computing. PDF, UNIVESP, acesso em 05/08/2025 [5].