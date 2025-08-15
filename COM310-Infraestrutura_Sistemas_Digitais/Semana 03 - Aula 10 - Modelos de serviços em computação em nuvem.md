# Material da aula — Modelos de serviços em computação em nuvem

Você quer que sua turma entenda, não decore. A nuvem muda como pensamos sobre controle, risco e velocidade. Vamos usar o vídeo para montar um percurso claro e aplicável.

---

## Objetivos de aprendizagem

- **Conceitos:** Diferenciar IaaS, PaaS, SaaS e ambiente on‑premise, incluindo o papel de serviços gerenciados.   
- **Arquitetura:** Reconhecer camadas e responsabilidades em cada modelo (aplicação, dados, runtime, middleware, SO, virtualização, servidores, rede, storage).   
- **Estratégia:** Identificar quando optar por on‑premise, nuvem pública, privada ou híbrida.   
- **Mercado:** Citar provedores relevantes e o contexto de adoção no setor público e privado. 

---

## Resumo e pontos‑chave do vídeo

- **Panorama dos modelos:** A aula aprofunda como surgiram e maturaram IaaS, PaaS e SaaS, destacando fronteiras de responsabilidade e a noção de “serviços gerenciados”.   
- **Comparação com on‑premise:** Mostra diagramas evolutivos que contrastam controle total local com terceirização progressiva na nuvem, e ressalta que on‑premise segue pertinente em cenários específicos e híbridos.   
- **IaaS:** Entrega infraestrutura de TI elástica (compute, rede, armazenamento) com cobrança por uso e granularidade de preços; abstrai o hardware físico do cliente.   
- **PaaS:** Fornece plataforma para desenvolver, hospedar e escalar aplicações, abstraindo configuração de servidores, segurança e middleware.   
- **SaaS:** Software completo entregue via web; quase tudo é gerenciado pelo provedor.   
- **Mercado e provedores:** Destaque histórico para a liderança da Amazon em IaaS, seguida por Microsoft e Google; políticas públicas brasileiras favorecem arranjos multiforncedor e ambientes híbridos. 

---

## Estrutura sugerida de slides

1. **Abertura e objetivos**
   - **Propósito:** O que você será capaz de decidir ao final.
   - **Mapa:** On‑premise vs IaaS vs PaaS vs SaaS. 

2. **De onde viemos: on‑premise**
   - **Pilha completa:** O que a TI gerencia localmente.
   - **Quando faz sentido:** Requisitos legais, latência, legado. 

3. **IaaS — Infraestrutura como serviço**
   - **O que inclui:** VMs, redes, volumes, segurança básica.
   - **Custo:** Paga pelo que usa; elasticidade. 

4. **PaaS — Plataforma como serviço**
   - **Para quem:** Devs e times de produto.
   - **Abstrações:** Runtime, autoscaling, devops simplificado. 

5. **SaaS — Software como serviço**
   - **Exemplos:** Suites de produtividade, colaboração.
   - **Trade‑off:** Menos controle, mais velocidade. 

6. **Diagrama de responsabilidades**
   - **Camadas por modelo:** Quem gerencia o quê (visual didático).
   - **Serviços gerenciados:** Onde eles se encaixam. 

7. **Analogias de mobilidade**
   - **Carro próprio (on‑premise), aluguel (IaaS), transporte público (PaaS).** 

8. **Cenários de adoção**
   - **Puras e híbridas:** Decidindo pela carga de trabalho.
   - **Setor público no Brasil:** Contratações conjuntas e híbridas. 

9. **Provedores e ecossistema**
   - **Panorama:** AWS, Azure, Google Cloud e plataformas PaaS. 

10. **Encerramento**
    - **Checklist de decisão:** Requisitos, risco, custo, time‑to‑value.

---

## Modelos de serviço em comparação

| Aspecto | On‑premise | IaaS | PaaS | SaaS |
|---|---|---|---|---|
| Controle | Máximo | Alto (infra virtual) | Médio (código e dados) | Baixo |
| Velocidade de entrega | Baixa | Média | Alta | Altíssima |
| Custo inicial | Alto | Baixo | Baixo | Baixo |
| Operação | Equipe interna | Cliente + provedor | Majoritariamente provedor | Provedor |
| Casos típicos | Legado/Compliance | Ambientes flexíveis | Desenvolvimento ágil | Uso final de apps |

> Sources: 

---

## Exemplos, analogias e cenários

- **Analogias para fixar:**
  - **On‑premise (carro próprio):** Controle total, manutenção por sua conta.  
  - **IaaS (carro alugado):** Liberdade com limites; manutenção incluída no serviço.  
  - **PaaS (transporte público):** Rotas predefinidas, facilidade e escala por demanda. 

- **Cenários práticos:**
  - **Migração de portal institucional:** Início em IaaS para lift‑and‑shift; evolução para PaaS com autoscaling.   
  - **Sistemas acadêmicos e governamentais:** Híbrido para equilibrar compliance com escala e custo em nuvem pública/privada. 

---

## Atividades, avaliação e recursos

### Atividades em aula
- **Mapa de responsabilidades:**  
  - **Tarefa:** Dado um serviço (ex.: app web com banco relacional), liste quem gerencia cada camada em on‑premise, IaaS, PaaS e SaaS. 
- **Debate estruturado:**  
  - **Pergunta‑guia:** Em quais requisitos on‑premise ainda supera a nuvem? Traga exemplos do seu contexto. 

### Exercícios rápidos
- **Classificação:**  
  - **Desafio:** Classifique 8 descrições reais (ex.: “hospedar containers sem gerenciar VMs”) como IaaS, PaaS ou SaaS, justificando.   
- **Arquitetura mínima viável:**  
  - **Desafio:** Proponha arquitetura IaaS e PaaS para o mesmo produto e compare custo/tempo/risco em 5 linhas. 

### Mini‑quiz (5 itens)
1. **O que PaaS abstrai que IaaS não?**  
2. **Por que “serviço gerenciado” reduz carga operacional?**  
3. **Quando SaaS é inadequado? Dê um exemplo.**  
4. **Um requisito de latência extrema tende a favorecer qual modelo? Por quê?**  
5. **Defina “pagamento por uso” em IaaS, com um exemplo de métrica.** 

### Tarefa pós‑aula
- **Estudo de caso (1–2 páginas):**  
  - **Briefing:** Empresa legada de e‑commerce quer reduzir custos em 6 meses. Compare três caminhos (IaaS lift‑and‑shift, PaaS replatform, SaaS para subsistemas como e‑mail e analytics). Conclua com recomendação defendida por critérios de risco, custo, velocidade e equipe. 

### Materiais de apoio
- **Vídeo base UNIVESP (Modelos de Serviços):** referências e diagramas conceituais.   
- **Contexto Brasil — Governo Digital:** diretrizes de contratação e adoção de nuvem (híbrida, multiforncedor). 

