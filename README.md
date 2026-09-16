## Iago Gonçalves

**Engenheiro DevOps/SRE** com +10 anos em TI, atualmente na **Shipay**. Atuo em
**sistemas de pagamentos via API** (Pix, cash-in/cash-out, boleto e BoletoPix) em
**alta escala — +3 milhões de requisições/dia**. Meu dia a dia é arquitetura de
**microserviços** e operação de **múltiplos clusters Kubernetes** — confiabilidade,
automação, IaC e CI/CD. Cada vez mais aplico **IA** na engenharia, e estou estudando
**LLMs** e **pipelines de ML (MLOps)**.

<div>
  <a href="https://www.linkedin.com/in/iago-goncalves-60524b107" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>
  <a href="mailto:contatoiagogfn@gmail.com"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
</div>

## No que trabalho

- **Pagamentos via API** — Pix, cash-in/cash-out, boleto e BoletoPix, em alta escala (**+3M requisições/dia**)
- **Microserviços** em produção — design, deploy e operação
- **Múltiplos clusters Kubernetes** — escala, confiabilidade e observabilidade
- **Infraestrutura como código** (Terraform), **CI/CD** e automação
- **IA aplicada à engenharia** — agentes e ferramentas no fluxo de trabalho

## Base em redes & infra

Fundamento forte em **redes e infraestrutura**: VoIP (**Asterisk**), servidores de
**e-mail (Zimbra)** e **DNS**, firewall e roteamento (**iptables**, **pfSense**,
**MikroTik**), switching e cabeamento — a base que sustenta operar serviços confiáveis
em produção.

## Estudando agora

- **LLMs** — fundamentos, prompting e avaliação
- **Pipelines de ML / MLOps** — treino, deploy e monitoramento de modelos
- **Segurança de IA (AI hardening)** — prompt injection, guard-rails e uso seguro de agentes
- **Loop engineering** — engenharia de loops de agentes autônomos (como no autosearch-hitl)

## Projetos em destaque

**[excalidraw-icons-mcp](https://github.com/iagogfe/excalidraw-icons-mcp)**: servidor
MCP pra agentes de IA desenharem diagramas de arquitetura no Excalidraw com **ícones
oficiais** de AWS, Azure, GCP, OCI e Kubernetes no lugar de retângulos genéricos.
Fork do [mcp_excalidraw](https://github.com/yctimlin/mcp_excalidraw), com busca e
inserção de ícones (31 tools), convenções por tipo de diagrama (C4, redes, cloud) e
criação em lote mais rápida. O agente desenha, tira screenshot do que fez e corrige.

[![release](https://img.shields.io/github/v/release/iagogfe/excalidraw-icons-mcp)](https://github.com/iagogfe/excalidraw-icons-mcp/releases/latest)
[![repo](https://img.shields.io/badge/GitHub-excalidraw--icons--mcp-181717?logo=github)](https://github.com/iagogfe/excalidraw-icons-mcp)

**[mcp-allquiet](https://github.com/iagogfe/mcp-allquiet)**: servidor MCP pro
[All Quiet](https://allquiet.app), que é gestão de incidentes e escala de plantão.
A API pública tem 136 operações, e uma tool pra cada uma encheria o contexto do
modelo antes da primeira pergunta. Então são 10 tools: 5 pro fluxo de incidente
(listar, ler, abrir, registrar ação, quem está de plantão) e 5 genéricas que leem
o spec OpenAPI embutido e alcançam o resto da API. Rodei a autosearch-hitl em
cima dele e o texto que o modelo lê caiu 48%, de 257 mil pra 135 mil caracteres,
com uma checagem que reprovava qualquer corte que perdesse nome de parâmetro,
campo obrigatório ou permissão exigida.

[![PyPI](https://img.shields.io/pypi/v/mcp-allquiet)](https://pypi.org/project/mcp-allquiet/)
[![repo](https://img.shields.io/badge/GitHub-mcp--allquiet-181717?logo=github)](https://github.com/iagogfe/mcp-allquiet)

**[autosearch-hitl](https://github.com/iagogfe/autosearch-hitl)** — uma *Agent Skill*
de **otimização autônoma com humano no centro (human-in-the-loop)**: você define o que
é "melhor" e ela itera sozinha — *muda → mede → mantém/descarta* — com segurança e bom
senso pra parar. Generaliza a ideia do
[`autoresearch`](https://github.com/karpathy/autoresearch) do Andrej Karpathy para
qualquer domínio com métrica objetiva.

[![skills.sh](https://img.shields.io/badge/skills.sh-autosearch--hitl-111111)](https://www.skills.sh/iagogfe/autosearch-hitl)
[![repo](https://img.shields.io/badge/GitHub-autosearch--hitl-181717?logo=github)](https://github.com/iagogfe/autosearch-hitl)

**[herdr-ai-memory](https://github.com/iagogfe/herdr-ai-memory)**: plugin pro
[herdr](https://herdr.dev) (multiplexador de agentes no terminal) que lança os
agentes dentro de um workstream do
[ai-memory](https://github.com/akitaonrails/ai-memory). Em vez de abrir o Claude
Code num pane solto, você escolhe o agente num menu e ele abre já com o histórico
do que os outros fizeram no projeto. Suporta 8 agentes, tem atalho de teclado e
oferece workstream paralelo quando já tem um agente rodando. Primeiro plugin de
memória entre agentes do marketplace do herdr.

[![repo](https://img.shields.io/badge/GitHub-herdr--ai--memory-181717?logo=github)](https://github.com/iagogfe/herdr-ai-memory)

## Contribuições

**[ai-memory](https://github.com/akitaonrails/ai-memory)**, memória de longo prazo
pra agentes de código: implementei o suporte a *managed workstreams* pro **Grok
Build CLI**. Na prática, dá pra sair do Claude Code no meio de uma tarefa, abrir o
Grok e continuar de onde parou, sem reexplicar nada.

O adapter gera a sessão nativa com `--session-id` e retoma com `--resume`, entrega
o contexto do workstream pelo `--rules` do Grok (o pacote só é confirmado depois que
o processo sobe, então uma falha na largada não perde a entrega) e importa o
transcript do `chat_history.jsonl` em modo leitura, sem escrever no store privado do
harness. O cursor de importação valida um hash do que já foi lido, então um rewind
que reescreve o arquivo não duplica histórico. Prompt de sistema, raciocínio
criptografado e os blocos que o Grok injeta ficam de fora do registro portátil.
Saiu na v1.19.0.

[![PR #237](https://img.shields.io/badge/PR-%23237%20merged-8250df?logo=github)](https://github.com/akitaonrails/ai-memory/pull/237)
[![v1.19.0](https://img.shields.io/badge/lan%C3%A7ado%20na-v1.19.0-brightgreen)](https://github.com/akitaonrails/ai-memory/releases/tag/v1.19.0)

## Tecnologias que uso no dia a dia

**Cloud & Infra**

![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge)
![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![Vault](https://img.shields.io/badge/Vault-000000?style=for-the-badge&logo=vault&logoColor=FFEC6E)

**Containers, orquestração & GitOps**

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)
![Argo CD](https://img.shields.io/badge/Argo_CD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)

**Observabilidade & on-call**

![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![PagerDuty](https://img.shields.io/badge/PagerDuty-06AC38?style=for-the-badge&logo=pagerduty&logoColor=white)

**Dados & mensageria**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)

**Linguagens & SO**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
