# Instalação do Docker no Windows 10

## 1. Introdução

Nesta aula, o professor Júlio Cezar Estrella apresenta um passo a passo para instalar e configurar o **Docker Desktop** no **Windows 10**, preparando o ambiente para uso de contêineres em atividades práticas da disciplina, como a execução do **Home Assistant** e de frameworks de IoT.  

O foco é garantir que o ambiente esteja pronto para criar imagens, instalar pacotes e executar aplicações em contêineres, usando o **Hyper-V** como backend.

---

## 2. Pré-requisitos

Antes de iniciar a instalação:

- **Suporte à virtualização**:  
  - Verifique se o hardware (notebook, desktop ou servidor) suporta virtualização.  
  - Habilite a virtualização na BIOS/UEFI.  
  - Sem isso, o Docker Desktop não funcionará.

- **Hyper-V habilitado**:  
  - No Windows, abra o **Painel de Controle** → **Programas** → **Ativar ou desativar recursos do Windows**.  
  - Marque **Hyper-V** e confirme.  
  - Reinicie o computador.

> 💡 Alternativa: o Docker Desktop também pode usar **WSL 2** como backend, mas nesta aula o foco é o Hyper-V.

---

## 3. Download e Instalação

1. **Baixar o instalador** no site oficial: [docs.docker.com](https://docs.docker.com).  
2. Após reiniciar o PC e habilitar o Hyper-V, execute o instalador **como administrador** (botão direito → “Executar como administrador”).  
3. Durante a instalação:
   - Mantenha a opção **Enable Hyper-V Windows Features** marcada.  
   - Opcional: criar atalho na área de trabalho.  
4. Aguarde o desempacotamento e instalação dos arquivos.  
5. Ao final, clique em **Close**.

---

## 4. Configuração Inicial

1. Abra o Docker Desktop pelo atalho criado.  
2. Aceite os termos de uso.  
3. Na tela de backend, **desabilite o WSL 2** e mantenha apenas o Hyper-V.  
4. Aplique as alterações e reinicie o Docker Desktop.  
5. Verifique o ícone verde na barra de tarefas — indica que o Docker está ativo.

---

## 5. Testando a Instalação

- Abra o **PowerShell** ou **Prompt de Comando**.
- Execute:
  ```powershell
  docker -v
  ```
  → Exibe a versão instalada.  
- Teste com:
  ```powershell
  docker run hello-world
  ```
  → Baixa a imagem “hello-world” e exibe mensagem de boas-vindas.

---

## 6. Observações e Boas Práticas

- Sempre use a **versão mais recente** do Docker Desktop.  
- Caso seu computador não suporte virtualização, utilize os **polos da UNIVESP** para realizar as atividades.  
- Mantenha o Docker atualizado para corrigir vulnerabilidades.  
- Em ambientes corporativos, verifique políticas de uso e permissões de administrador.

---

## 7. Análise Crítica

- O vídeo foca no Hyper-V, mas o **WSL 2** pode oferecer melhor desempenho em alguns cenários; vale avaliar conforme o hardware.  
- A recomendação de executar como administrador é correta, mas em ambientes de segurança restrita, é importante revisar permissões e políticas de execução.  
- Não foi abordada a configuração de **recursos de CPU e memória** no Docker Desktop, que pode ser relevante para workloads mais pesados.  
- A instalação no Windows 10 Home requer WSL 2, pois o Hyper-V não está disponível nessa edição — ponto não mencionado no vídeo.

---

## 8. Lista de Exercícios

1. **Verifique se seu hardware suporta virtualização e descreva o procedimento para habilitá-la na BIOS.**  
   *Resposta:* Entrar na BIOS/UEFI durante a inicialização (teclas como F2, Del ou Esc), localizar a opção “Intel VT-x” ou “AMD-V” e habilitar.

2. **Explique a função do Hyper-V no contexto do Docker Desktop.**  
   *Resposta:* É o hipervisor nativo do Windows que cria máquinas virtuais leves para hospedar contêineres.

3. **Qual a diferença entre usar Hyper-V e WSL 2 como backend do Docker?**  
   *Resposta:* Hyper-V cria VMs dedicadas; WSL 2 usa subsistema Linux integrado ao Windows, com desempenho de I/O geralmente superior.

4. **Liste os passos para habilitar o Hyper-V no Windows 10 Pro.**  
   *Resposta:* Painel de Controle → Programas → Ativar/Desativar Recursos → Marcar Hyper-V → OK → Reiniciar.

5. **Por que é necessário executar o instalador como administrador?**  
   *Resposta:* Para permitir alterações no sistema, como instalação de drivers e serviços.

6. **Mostre o comando para verificar a versão do Docker instalada.**  
   *Resposta:* `docker -v`.

7. **Explique o que acontece ao executar `docker run hello-world`.**  
   *Resposta:* O Docker baixa a imagem “hello-world” do Docker Hub e a executa, exibindo mensagem de teste.

8. **Como confirmar que o Docker Desktop está ativo após a instalação?**  
   *Resposta:* Ícone verde na barra de tarefas e resposta positiva aos comandos `docker`.

9. **Quais são as implicações de manter o WSL 2 habilitado junto com o Hyper-V?**  
   *Resposta:* Pode haver sobreposição de recursos e consumo extra de memória.

10. **Descreva um cenário em que o WSL 2 seria preferível ao Hyper-V.**  
    *Resposta:* Em Windows 10 Home ou quando se deseja integração mais direta com ferramentas Linux.

11. **Como acessar as configurações do Docker Desktop?**  
    *Resposta:* Clicar no ícone do Docker na bandeja do sistema → engrenagem (Settings).

12. **Explique a importância de manter o Docker Desktop atualizado.**  
    *Resposta:* Corrige falhas de segurança e melhora desempenho.

13. **Qual comando lista todas as imagens disponíveis localmente?**  
    *Resposta:* `docker images`.

14. **Como remover uma imagem local que não está mais em uso?**  
    *Resposta:* `docker rmi <image_id>`.

15. **Explique o conceito de contêiner efêmero.**  
    *Resposta:* Contêiner que é criado para uma tarefa temporária e removido após execução.

16. **Qual a função do Docker Hub?**  
    *Resposta:* Repositório público de imagens Docker.

17. **Como criar um atalho do Docker Desktop na área de trabalho?**  
    *Resposta:* Marcar a opção durante a instalação ou criar manualmente via menu iniciar.

18. **Explique a diferença entre imagem e contêiner.**  
    *Resposta:* Imagem é o modelo imutável; contêiner é a instância em execução.

19. **Qual comando exibe todos os contêineres, inclusive os parados?**  
    *Resposta:* `docker ps -a`.

20. **Como parar um contêiner em execução?**  
    *Resposta:* `docker stop <container_id>`.

21. **Explique o impacto de não habilitar a virtualização na BIOS.**  
    *Resposta:* O Docker Desktop não conseguirá criar o ambiente de execução.

22. **Como verificar se o Hyper-V está ativo no Windows?**  
    *Resposta:* `systeminfo` no CMD e procurar “Hyper-V Requirements”.

23. **Qual comando remove todos os contêineres parados?**  
    *Resposta:* `docker container prune`.

24. **Explique o que é backend no contexto do Docker Desktop.**  
    *Resposta:* Tecnologia usada para hospedar e gerenciar contêineres (Hyper-V ou WSL 2).

25. **Como alterar o backend do Docker Desktop após a instalação?**  
    *Resposta:* Configurações → General → selecionar/desmarcar WSL 2.

26. **Qual comando exibe logs de um contêiner?**  
    *Resposta:* `docker logs <container_id>`.

27. **Explique a importância de testar a instalação com `hello-world`.**  
    *Resposta:* Confirma conectividade com o Docker Hub e funcionamento do runtime.

28. **Como atualizar o Docker Desktop manualmente?**  
    *Resposta:* Baixar nova versão no site oficial e instalar sobre a existente.

29. **Quais cuidados tomar ao instalar o Docker em ambiente corporativo?**  
    *Resposta:* Verificar políticas de TI, permissões e compatibilidade com sistemas internos.

30. **Explique como o Docker se integra a frameworks de IoT.**  
    *Resposta:* Permite empacotar e executar aplicações IoT em contêineres portáveis, facilitando deploy e atualização.

---

## 9. Bibliografia

- Estrella, J. C. *Plataforma de Ingestão e Análise de Dados – Docker no Windows 10 (LIBRAS)*. UNIVESP, YouTube, 24 jun. 2025. Acesso em 19 ago. 2025.  
- [O que é computação em nuvem? – Unicamp](https://suporte.nuvem.unicamp.br/sobre/o_que_e.html). Acesso em 19 ago. 

