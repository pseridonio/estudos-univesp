# Introdução ao Docker – Parte 2  
**Disciplina:** Plataforma de Ingestão e Análise de Dados  
**Professor:** Júlio Cezar Estrella  

---

## 1. Introdução

Nesta aula, o professor aprofunda os conceitos fundamentais do Docker, apresentando seus principais componentes, comandos básicos e o uso de **Dockerfile** para criar imagens customizadas. O foco é capacitar o aluno a operacionalizar imagens, personalizá-las e prepará-las para publicação em repositórios como o **Docker Hub**, com aplicação prática voltada a soluções IoT.

---

## 2. Componentes Principais do Docker

- **Docker Engine**:  
  Motor responsável por construir, enviar e executar contêineres. Gerencia imagens e fornece comandos para criação, execução e commit.

- **Docker Client**:  
  Interface de linha de comando que recebe instruções do usuário e as envia ao Docker Engine.

- **Registro de Imagens (Registry)**:  
  Repositório de imagens Docker. Pode ser:
  - **Público** (ex.: Docker Hub, padrão para novas imagens).
  - **Privado** (restrito à organização, com autenticação e controle de acesso).

- **Dockerfile**:  
  Arquivo de instruções que define como uma imagem será construída, incluindo:
  - Imagem base (FROM).
  - Comandos de instalação e configuração (RUN).
  - Cópia de arquivos para o contêiner (COPY).
  - Comando inicial ao executar o contêiner (ENTRYPOINT).

---

## 3. Primeiros Comandos

1. **Teste de instalação**:
   ```bash
   docker run hello-world
   ```
   - Baixa e executa a imagem de teste, exibindo mensagem de boas-vindas.
   - Qualquer erro indica problemas na instalação.

2. **Execução de um contêiner Ubuntu**:
   ```bash
   docker run -it --name aula06 --hostname teste ubuntu
   ```
   - Baixa a imagem `ubuntu:latest` do Docker Hub (se não existir localmente).
   - Abre um shell interativo como usuário root.

3. **Persistência de alterações**:
   - Alterações feitas dentro do contêiner (ex.: instalação de pacotes) são perdidas ao sair, a menos que se faça:
     ```bash
     docker commit <container_id> nome_imagem
     ```

---

## 4. Criando uma Imagem Customizada com Dockerfile

### Exemplo prático:

1. **Preparar script** (`entrada.sh`):
   ```bash
   #!/bin/bash
   toilet "Bem-vindo ao Contêiner"
   ```
   - Salvar na mesma pasta onde ficará o Dockerfile.

2. **Dockerfile**:
   ```dockerfile
   FROM ubuntu:latest
   RUN apt-get update && apt-get install -y toilet
   COPY entrada.sh /entrada.sh
   ENTRYPOINT ["bash", "/entrada.sh"]
   ```

3. **Construir a imagem**:
   ```bash
   docker build -t figura .
   ```

4. **Listar imagens**:
   ```bash
   docker images
   ```

5. **Executar a imagem**:
   ```bash
   docker run figura
   ```

---

## 5. Comandos Úteis

- `docker ps` – lista contêineres em execução.  
- `docker ps -a` – lista todos os contêineres.  
- `docker rm <id>` – remove contêiner.  
- `docker rmi <id>` – remove imagem.  
- `docker --help` – lista comandos disponíveis.

---

## 6. Boas Práticas e Observações

- Sempre manter o Docker atualizado.  
- Usar tags específicas em vez de `latest` para garantir reprodutibilidade.  
- Organizar scripts e Dockerfile em repositórios versionados (ex.: Git).  
- Em ambientes corporativos, avaliar uso de registries privados para segurança.

---

## 7. Análise Crítica

- O professor enfatiza o uso do **commit** para persistir alterações, mas em pipelines modernos recomenda-se **Dockerfile** para garantir reprodutibilidade e automação.  
- O exemplo com `toilet` é didático, mas poderia ser substituído por aplicações mais próximas do contexto IoT para maior relevância prática.  
- Não foi abordada a otimização de imagens (multi-stage builds, redução de camadas), importante para ambientes de produção.

---

## 8. Lista de Exercícios com Resolução

1. **Explique a função do Docker Engine.**  
   *Resposta:* É o serviço que constrói, executa e gerencia contêineres e imagens.

2. **Qual comando testa a instalação do Docker?**  
   *Resposta:* `docker run hello-world`.

3. **O que acontece se você sair de um contêiner sem dar commit?**  
   *Resposta:* Todas as alterações feitas serão perdidas.

4. **Escreva um Dockerfile que instale o pacote `curl` no Ubuntu.**  
   *Resposta:*  
   ```dockerfile
   FROM ubuntu:latest
   RUN apt-get update && apt-get install -y curl
   ```

5. **Como listar todas as imagens locais?**  
   *Resposta:* `docker images`.

6. **Explique a diferença entre `COPY` e `ADD` no Dockerfile.**  
   *Resposta:* `COPY` copia arquivos locais; `ADD` também pode extrair arquivos compactados e baixar de URLs.

7. **Qual comando remove uma imagem local?**  
   *Resposta:* `docker rmi <id>`.

8. **Como executar um contêiner interativo com bash?**  
   *Resposta:* `docker run -it ubuntu bash`.

9. **O que significa a flag `-t` no `docker build`?**  
   *Resposta:* Define o nome/tag da imagem.

10. **Como verificar ajuda sobre um comando específico do Docker?**  
    *Resposta:* `docker <comando> --help`.

11. **Explique o papel do Docker Hub.**  
    *Resposta:* É um repositório público de imagens Docker.

12. **Como criar um contêiner com nome e hostname personalizados?**  
    *Resposta:* `docker run -it --name nome --hostname host imagem`.

13. **O que é uma imagem base?**  
    *Resposta:* Imagem inicial sobre a qual outras são construídas.

14. **Como persistir alterações feitas em um contêiner?**  
    *Resposta:* `docker commit <container_id> nome_imagem`.

15. **Qual comando mostra apenas contêineres ativos?**  
    *Resposta:* `docker ps`.

16. **Explique a função do ENTRYPOINT.**  
    *Resposta:* Define o comando padrão executado ao iniciar o contêiner.

17. **Como copiar um arquivo local para dentro de um contêiner em execução?**  
    *Resposta:* `docker cp arquivo container_id:/caminho`.

18. **O que significa `ubuntu:latest`?**  
    *Resposta:* Última versão estável da imagem Ubuntu.

19. **Como remover todos os contêineres parados?**  
    *Resposta:* `docker container prune`.

20. **Explique a importância de usar tags específicas.**  
    *Resposta:* Evita mudanças inesperadas ao atualizar imagens.

21. **Como inspecionar detalhes de uma imagem?**  
    *Resposta:* `docker inspect imagem`.

22. **Qual comando exibe logs de um contêiner?**  
    *Resposta:* `docker logs container_id`.

23. **Como mapear uma porta do host para o contêiner?**  
    *Resposta:* `docker run -p host_port:container_port imagem`.

24. **Explique a diferença entre imagem e contêiner.**  
    *Resposta:* Imagem é o modelo; contêiner é a instância em execução.

25. **Como parar um contêiner ativo?**  
    *Resposta:* `docker stop container_id`.

26. **Qual comando atualiza a lista de pacotes no Ubuntu?**  
    *Resposta:* `apt-get update`.

27. **Como criar um volume no Docker?**  
    *Resposta:* `docker volume create nome_volume`.

28. **Explique a função do comando `RUN` no Dockerfile.**  
    *Resposta:* Executa comandos durante a construção da imagem.

29. **Como verificar o espaço ocupado por imagens e contêineres?**  
    *Resposta:* `docker system df`.

30. **Qual a vantagem de usar Docker em projetos IoT?**  
    *Resposta:* Facilita a portabilidade, isolamento e replicação de ambientes.

---

## 9. Bibliografia

- Estrella, J. C. *Plataforma de Ingestão e Análise de Dados – Introdução ao Docker – Parte 2 (LIBRAS)*. UNIVESP, YouTube, 24 jun. 2025.  
- [Docker Documentation – Get Started](https://docs.docker.com/get-started/)  
- Merkel, D. *Docker: Lightweight Linux Containers for Consistent Development and Deployment*. Linux Journal, 2014.  

---

Se quiser, posso também preparar **um quadro-resumo visual** com todos os comandos e funções apresentados nesta aula para facilitar a revisão. Quer que eu monte?