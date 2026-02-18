# Introdução ao Docker – Parte 1

## 1. Introdução

Nesta aula apresentamos o Docker, uma plataforma de código aberto que empacota aplicações e suas dependências em unidades isoladas chamadas contêineres.  

Discutimos o papel dos contêineres no desenvolvimento de soluções de ingestão e análise de dados, especialmente em arquiteturas distribuídas, IoT e nuvem.  

Vamos entender como imagens, contêineres, o motor Docker, o registro e o Dockerfile se combinam para tornar aplicações portáveis, leves e reproduzíveis.

---

## 2. Docker no Contexto de Ingestão de Dados

- Contêineres garantem que pipelines de ingestão (ETL, streaming, microserviços) rodem de forma idêntica em qualquer ambiente: do desktop ao datacenter e à nuvem.  

- Essa portabilidade facilita a autonomia entre aplicação e dados, alinhada à independência de implementação exigida em arquiteturas de microsserviços.  

- Em IoT, microcontêineres podem ser executados diretamente em microcontroladores ou gateways na borda, sincronizando localmente e replicando para sistemas centrais na nuvem.

---

## 3. Conceitos Fundamentais

### 3.1 Contêiner vs Máquina Virtual

- Máquina Virtual  
  - Cada VM inclui um sistema operacional “guest” completo sobre um hipervisor.  
  - Overhead de memória e disco elevado; imagens volumosas.  

- Contêiner  
  - Compartilha o kernel do host, isolando processos por namespaces e cgroups.  
  - Inicialização rápida e footprint reduzido; imagens leves.

### 3.2 Imagem Docker

- Imagem: conjunto imutável de camadas (layers) contendo sistema de arquivos e metadados.  
- Camadas permitem reuso (cache) ao construir múltiplas versões, acelerando rebuilds.  

### 3.3 Docker Engine

- Composto por  
  - `dockerd`: daemon que gerencia contêineres e imagens.  
  - `docker` CLI: cliente para criar, executar e inspecionar contêineres.  

### 3.4 Docker Registry

- Registro: repositório de imagens (Docker Hub, GitHub Container Registry, Azure Container Registry).  
- Permite `docker pull`/`push` para distribuir imagens entre equipes e nuvens.  
- Segurança: escolha imagens oficiais e escaneie vulnerabilidades.

### 3.5 Dockerfile

- Arquivo de texto com instruções declarativas (`FROM`, `RUN`, `COPY`, `EXPOSE`, `CMD`) que definem como montar uma imagem.  
- Padroniza builds: versionamento em sistemas como Git e CI/CD.

---

## 4. História e Evolução

- 1979: `chroot` no Unix foi precursor do isolamento de processos.  
- 2013: Docker surge no projeto dotCloud, inicialmente usando LXC; evolui para libcontainer e containerd.  
- Rapidamente se tornou um dos projetos mais ativos no GitHub, a base de plataformas de orquestração como Kubernetes.

---

## 5. Vantagens e Limitações

Vantagens  
- Portabilidade entre ambientes; .  
- Agilidade em builds, testes e deploys; .  
- Suporte amplo em Linux e Windows; .  

Limitações  
- Isolamento de kernel — contêineres não substituem VMs em cargas que requerem multi-Kernel; .  
- Questões de segurança: privilégios podem ser abertos sem configurações adequadas; .  
- Gerenciamento de estado: contêineres são efêmeros, exigem volumes para dados persistentes.

---

## 6. Uso de Docker em IoT e Computação em Nuvem

- Borda (Edge): em gateways IoT, contêineres leves coletam e pré-processam dados, reduzindo tráfego upstream.  
- Núvem (Cloud): contêineres são tratadas como CaaS ou PaaS, executadas em instâncias IaaS ou orquestradas por Kubernetes e serviços gerenciados.  
- Em Smart Campuses, contêineres podem rodar no fog computing para análises regionais antes de replicar no data lake central.

---

## 7. Análise Crítica

- O vídeo enfatiza Docker Hub como registro padrão; hoje há registries privados e soluções de scanner de imagens (Clair, Trivy) para auditoria.  
- Foi mencionado que todo contêiner compartilha “tudo” do host; recomenda-se o uso de contêineres rootless e políticas de segurança (AppArmor, SELinux) para minimizar riscos.  
- A comparação com VM subestima projetos de ringan containers (CRI-O, containerd) e a adoção de padrões OCI que vão além do Docker.

---

## 8. Lista de Exercícios

1. **Explique o que é um contêiner Docker e como ele difere de uma VM.**  
   Resolução:  
   1. Contêiner isola processos usando namespaces e cgroups do kernel do host.  
   2. VM virtualiza hardware, cada nó roda um sistema operacional completo.  
   3. Contêineres iniciam em milissegundos, VMs em segundos e ocupam mais recursos.

2. **Descreva o papel do daemon `dockerd` e do cliente `docker`.**  
   Resolução:  
   1. `dockerd` é o serviço de fundo que executa e gerencia imagens e contêineres.  
   2. `docker` CLI interage com `dockerd` via API REST para comandos de run, build, pull, push.

3. **Liste cinco instruções comuns de um Dockerfile e explique cada uma.**  
   Resolução:  
   1. `FROM`: imagem base.  
   2. `RUN`: executa comando na construção da imagem.  
   3. `COPY`: copia arquivos do contexto de build para a imagem.  
   4. `EXPOSE`: indica portas abertas.  
   5. `CMD`: comando padrão ao iniciar o contêiner.

4. **Mostre passo a passo como criar e executar um contêiner NGINX.**  
   Resolução:  
   1. `docker pull nginx` → baixa imagem.  
   2. `docker images` → lista imagens locais.  
   3. `docker run -d --name web -p 8080:80 nginx` → inicia contêiner em background.  
   4. Acesse `http://localhost:8080` no navegador.  
   5. `docker ps` → verifica contêiner em execução.

5. **Explique a diferença entre `docker pull`, `docker run` e `docker build`.**  
   Resolução:  
   1. `docker pull`: baixa imagem do registro.  
   2. `docker build`: cria imagem a partir de Dockerfile.  
   3. `docker run`: instancia um contêiner a partir de uma imagem.

6. **Como inspeccionar logs de um contêiner em execução?**  
   Resolução:  
   1. `docker ps` → identifica ID ou nome do contêiner.  
   2. `docker logs <nome_ou_id>` → exibe saída padrão (stdout/stderr).  
   3. `docker logs -f <nome>` → segue logs em tempo real.

7. **Qual comando remove todas as imagens não referenciadas?**  
   Resolução:  
   1. `docker image prune -a` → remove imagens sem contêiner associado.  
   2. Confirme com `y` quando solicitado.

8. **Descreva como versionar e publicar uma imagem no Docker Hub.**  
   Resolução:  
   1. `docker tag local-image user/repo:tag` → cria alias.  
   2. `docker login` → autentica no Docker Hub.  
   3. `docker push user/repo:tag` → envia imagem.

9. **Escreva um Dockerfile mínimo para uma aplicação Node.js.**  
   Resolução:  
   ```dockerfile
   FROM node:18-alpine
   WORKDIR /app
   COPY package*.json ./
   RUN npm install --production
   COPY . .
   CMD ["node", "index.js"]
   ```  
   Passo a passo: define base, instala dependências e define comando de inicialização.

10. **Como compartilhar um diretório do host dentro de um contêiner?**  
    Resolução:  
    1. `docker run -v /caminho/host:/caminho/container nginx` → monta volume.  
    2. Alterações no host refletem no contêiner e vice-versa.

11. **Explique a relação entre camadas (layers) e o cache de builds.**  
    Resolução:  
    1. Cada instrução Dockerfile gera uma camada.  
    2. Se o comando e o contexto não mudam, o Docker reutiliza o cache, acelerando builds subsequentes.

12. **Mostre como listar todos os contêineres (executando ou não).**  
    Resolução:  
    1. `docker ps -a` → exibe todos os contêineres, incluindo parados.  
    2. Colunas: CONTAINER ID, IMAGE, STATUS, NAMES.

13. **Quando usar `--rm` ao executar um contêiner?**  
    Resolução:  
    1. `docker run --rm busybox echo "Olá"` → remove contêiner após parada.  
    2. Útil em tarefas one-off para não acumular contêineres parados.

14. **Qual a função do comando `docker inspect`?**  
    Resolução:  
    1. `docker inspect <id>` → retorna JSON com metadados do contêiner ou imagem.  
    2. Inclui configurações de rede, volumes, variáveis de ambiente.

15. **Descreva um cenário de uso de contêineres em um pipeline de CI/CD.**  
    Resolução:  
    1. Build de aplicação dentro de contêiner limpo.  
    2. Testes automatizados isolados.  
    3. Push da imagem aprovada para registro.  
    4. Deploy em cluster Kubernetes ou Docker Swarm.

16. **Como limitar recursos (CPU e memória) de um contêiner?**  
    Resolução:  
    1. `docker run -m 512m --cpus 1 nginx` → 512 MB RAM, 1 CPU.  
    2. Evita sobrecarga do host.

17. **O que acontece se executar `docker run hello-world` sem ter a imagem local?**  
    Resolução:  
    1. Docker procura localmente.  
    2. Se não existir, faz pull de `library/hello-world` do Docker Hub.  
    3. Instancia e executa o contêiner.

18. **Explique como renomear um contêiner em execução.**  
    Resolução:  
    1. `docker rename old_name new_name` → altera o nome, o ID permanece o mesmo.

19. **Por que é importante reduzir o tamanho de imagens?**  
    Resolução:  
    1. Reduz tempo de transferência.  
    2. Economiza armazenamento e acelera deploys.

20. **Como conectar-se a um shell interativo dentro de um contêiner em execução?**  
    Resolução:  
    1. `docker exec -it <nome> /bin/sh` ou `/bin/bash`.  
    2. Permite inspeção e debug em tempo real.

21. **Qual a diferença entre `COPY` e `ADD` em Dockerfile?**  
    Resolução:  
    1. `COPY`: copia arquivos do contexto de build.  
    2. `ADD`: além de copiar, pode descompactar arquivos tar e buscar URLs remotas.

22. **Como inspecionar o histórico de camadas de uma imagem?**  
    Resolução:  
    1. `docker history <image>` → mostra camadas, tamanho e instruções correspondentes.

23. **Explique o conceito de “build multi-stage” em Dockerfile.**  
    Resolução:  
    1. Cria imagens intermediárias para compilar ou testar.  
    2. Só copia artefatos finais para imagem de produção, reduzindo tamanho.

24. **Descreva como fazer rollback de um deploy baseado em contêineres.**  
    Resolução:  
    1. Mantenha tags versionadas no registry.  
    2. No orquestrador, altere versão do manifest para tag anterior.  
    3. Reinicie serviços ou atualize stacks.

25. **Como inspecionar a utilização de recursos de um contêiner?**  
    Resolução:  
    1. `docker stats` → exibe CPU, memória, rede e I/O em tempo real para todos os contêineres.

26. **Por que usar contêineres em gateways IoT?**  
    Resolução:  
    1. Isolamento de drivers e serviços de coleta.  
    2. Facilidade para atualizar lógica sem impactar o host.

27. **Mostre como criar um contêiner que roda em segundo plano e remove-se automaticamente.**  
    Resolução:  
    1. `docker run -d --rm nginx` → contêiner de fundo, removido após parada.

28. **Quais cuidados de segurança aplicar em imagens públicas?**  
    Resolução:  
    1. Escolher imagens oficiais ou assinadas.  
    2. Escanear vulnerabilidades (Trivy, Clair).  
    3. Rodar contêineres com usuário não-root.

29. **Descreva como definir variáveis de ambiente ao rodar um contêiner.**  
    Resolução:  
    1. `docker run -e VAR=value nginx` → passa `VAR` para o processo dentro do contêiner.

30. **Explique o fluxo de desenvolvimento de um microserviço em contêiner Docker.**  
    Resolução:  
    1. Definição do Dockerfile.  
    2. Build da imagem (`docker build`).  
    3. Testes locais (`docker run`, `docker exec`).  
    4. Push para registro.  
    5. Deploy automatizado pelo orquestrador.

---

## 9. Bibliografia

- Estrella, J. C., “Introdução ao Docker – Parte 1 (LIBRAS)”, Plataforma de Ingestão e Análise de Dados, UNIVESP, YouTube, 24 jun. 2025. Acesso em 19 ago. 2025.  
- Proença, M. H., “Arquitetura IoT para Aplicação em Smart Campus”, TCC, Universidade de São Paulo, 2020. Acesso em 19 ago. 2025.  
- Unicamp, “O que é computação em nuvem?”, suporte.nuvem.unicamp.br, 2025. Acesso em 19 ago. 2025.  
- Braga, A., “Cloud Computing”, 2ª ed., Editora Ciência Moderna, 2021. Acesso em 19 ago. 2025.  
- Sousa, F. R. C.; Carvalho, L. O., “Gerenciamento de Dados em Nuvem: Conceitos, Sistemas e Desafios”, Week 02 – Univesp, 2025. Acesso em 19 ago. 2025.  
- Merkel, D., “Docker: Lightweight Linux Containers for Consistent Development and Deployment”, Linux Journal, 2014. Acesso em 19 ago. 2025.