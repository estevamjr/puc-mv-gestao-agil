# T-SONAIR // Command Multiplexer & Governance Platform

## 0. Destaques Acadêmicos
**Governança Ágil Automatizada & Engenharia de Requisitos**
A governança do ecossistema T-SONAIR foi desenhada para conectar as políticas de qualidade do produto (regras de engenharia) com o fluxo de trabalho diário do time (regras de processo). O funcionamento prático dessas camadas ocorreu da seguinte forma:
* 1. Definition of Ready (DoR) da Solução e Sua Aplicação na Execução
O DoR da solução consiste nas restrições de código que o software exige para funcionar de forma segura. No T-SONAIR, esse DoR foi codificado no backend por meio de esquemas estritos do Pydantic que barram dados malformados. Na execução do projeto, esse DoR se tornou um "LiveDoR": o desenvolvedor não cria tickets manualmente no Jira clicando em botões; em vez disso, a gestão do backlog é operada via chat integrado ao LLM. Para que o backend autorize a abertura de um ticket, o insumo humano enviado no chat precisa fornecer obrigatoriamente o contexto do Tech Lead e a estrutura de BDD contendo ao menos um cenário de sucesso (Happy Path) e um cenário de erro (Exceção). Se o desenvolvedor tentar abrir uma tarefa com comandos informais ou sem prever o cenário de erro, o middleware rejeita a requisição, barra a criação do card e exige mais informações no chat. O DoR da solução ditou, portanto, o comportamento da execução do backlog.  
* 2. Manifesto de Engenharia e a Variação do DoD Técnico
Os critérios de qualidade técnica mudam de acordo com o componente de software trabalhado. Essa lógica foi definida pelo papel de Tech Lead durante o rito de refinamento do backlog e centralizada sob o guarda-chuva do Épico Master de Fundações (SCRUM-5), que institui o Manifesto de Engenharia T-SONAIR. Por esse motivo, os critérios técnicos nas descrições dos cards variam de formato e volume conforme o risco de engenharia: tarefas críticas de API (como o gateway FastAPI no SCRUM-1 e SCRUM-37) possuem um DoD estrito exigindo cobertura de testes via PyTest superior a 80% e validação de schemas, enquanto tarefas de infraestrutura isolada (como o SCRUM-32) focam em critérios de conectividade SSH e persistência.  
* 3. AI Auditor e o DoD de Processo Universal
Enquanto o DoD técnico varia por tipo de tarefa, o DoD de processo (a execução das regras da Sprint) é universal e obrigatório para 100% dos tickets do board. Desenvolvemos um motor automatizado chamado AI Auditor, integrado via webhooks à API v3 do Jira Cloud. Na execução prática do projeto, sempre que um card tenta ser movido para concluído (Done), o robô intercepta a requisição. Se a descrição não contiver o link da documentação técnica oficial gerada no Confluence ou o PDF com o dossiê anexado, o AI Auditor barra o fechamento, executa um rollback automático do status do ticket para a coluna de auditoria e insere um log de violação de compliance nos comentários (como evidenciado nos históricos dos tickets SCRUM-38, SCRUM-37 e SCRUM-33).

## 🎯 1. Cenário de Negócio e Contexto Acadêmico (PUC-Rio)
O **T-SONAIR** é um middleware de governança e engenharia de requisitos automatizada, projetado para eliminar o gap operacional, a latência de processo e a fricção no fluxo de valor de equipes ágeis. 
* **A Dor Central:** O desperdício de tempo e overhead cognitivo do Product Owner (PO) no preenchimento mecânico, abertura e triagem manual de histórias de usuário e especificações técnicas. O sistema elimina essa fricção ao capturar a velocidade da ideação em linguagem natural e traduzi-la de forma determinística para sistemas de gestão (API v3 do Jira Cloud).
* **Contexto de Engenharia de Software:** Desenvolvido como parte do ecossistema de soluções da pós-graduação em Engenharia de Software da **Pontifícia Universidade Católica do Rio de Janeiro (PUC-Rio)**, o projeto aplica conceitos estritos de governança ativa, segurança de borda e arquitetura orientada a eventos.
* **Time Scrum Enxuto:** * 1 Product Owner (Ideação e Visão de Produto)
  * 1 Tech Lead / Lead Engineer (Arquitetura backend FastAPI e Integrações)
  * 1 Fullstack Engineer (Dashboard HITL em Next.js e Tailwind)

---

## 📈 2. Linha de Evolução Arquitetural e Maturidade do Ecossistema

Este repositório materializa uma estratégia de desenvolvimento incremental, contínuo e evolutivo dentro da pós-graduação, onde o ecossistema de software migrou de uma abordagem baseada em hardware/telemetria física industrial para englobar computação cognitiva de alto nível:


```

[FASE 1: FUNDAÇÃO IT/OT]                     ======> [FASE 2: EVOLUÇÃO T-SONAIR COGNITIVO]
Segurança Física / IoT Industrial                    Segurança Lógica / Engenharia de Requisitos
Convergência Hardware e Sensores                     Orquestração Avançada de LLMs (OpenRouter)
Algoritmo: SVM (Support Vector Machines)              Middleware Ativo: T-Bridge (FastAPI / Next.js)
Output: Sinalização Física (Painel Andon)             Output: Governança Ativa e Injeção via API v3

```

### 🏛️ Relatório Histórico: Fundação T-SONAIR (A Era Andon Industrial)
Nas versões de baseline V1.0 a V1.5, o projeto nasceu focado na convergência IT/OT (Tecnologia da Informação / Tecnologia Operacional) e na segurança física baseada em risco. Inspirado diretamente na **Filosofia Andon** do Sistema Toyota de Produção, o software atuava como uma camada de defesa de infraestrutura crítica em tempo real para salas de servidores. 

O ecossistema original consistia em uma bancada IoT com hardware dedicado: um **Módulo de Visão (ESP32-S3)** para reconhecimento facial na borda e um **Módulo de Interface (ESP32-C3)** operando como painel visual LCD de alertas. Através de uma **Fusão Sensorial Dinâmica**, o sistema cruzava telemetria física industrial de sensores de corrente elétrica (SCT-013), vibração (MPU6050) e magnéticos para gerar um *Risk Score (RS)* dinâmico. 

Regras estritas como o *Marcapasso (Watchdog Heartbeat)* e o *Dying Gasp* garantiam que o hardware travasse as portas em modo seguro (*Fail-Secure*) em caso de falha elétrica ou perda de comunicação com a central. Havendo um evento crítico de invasão, o microsserviço **ticket-andon-it** abria um chamado automático de segurança na Atlassian.

### 🧠 A Pivotagem para a Era Cognitiva: Eficiência de Valor na Alta Complexidade
Na fase atual, a disciplina atuou como o catalisador para **desacoplar as regras lógicas Andon dos sensores físicos**, aplicando-as diretamente para monitorar e auditar o fluxo de comportamento das próprias inteligências artificiais em ambiente corporativo. 

A evolução do ecossistema substituiu a leitura de hardware pela integração com Large Language Models (**LLMs** via OpenRouter). Embora o ciclo de desenvolvimento tenha exigido o mesmo tempo de entrega, o gain real não se deu em velocidade pura, mas sim em uma **eficiência drástica do valor entregue**. O escopo saltou de uma arquitetura estática de microsserviços IoT locais para uma infraestrutura orientada a eventos assíncronos em nuvem (FastAPI e Next.js), capaz de capturar intenções textuais livres, tratá-las de forma higienizada (Pydantic V2) e injetá-las de maneira consistente nas ferramentas oficiais de produção.

---

## 🔄 3. Espelhamento Metodológico: A Disciplina no Processo e no Produto
Este projeto adota o princípio do **espelhamento metodológico**: os conceitos de **Gestão de Projetos e Produtos Ágeis** foram aplicados tanto na governança do ciclo de desenvolvimento do time, quanto nas regras de negócio codificadas no software.

1. **A Disciplina no Processo (Gestão):** O MVP foi gerenciado sob o framework Scrum, pautado na queima de complexidade técnica (15 Story Points na Sprint 3). Desvios de percurso foram diagnosticados na *Sprint Retrospective* e imediatamente corrigidos para garantir a queima linear perfeita demonstrada no *Burndown Chart*.

![Sprint Retrospective](restrospectiveMeeting.png)

2. **A Disciplina no Produto (Software):** O sistema atua como uma camada ativa de governança que protege o fluxo contra indisciplina técnica através do **AI Compliance Gate**. O software automatiza e garante o cumprimento de regras de processo diretamente na esteira de código, agindo como um validador em tempo real da *Definition of Done (DoD)*.

---

## 🗺️ 4. O Workshop Lean Inception: Engenharia de Requisitos em 9 Passos
O alinhamento estratégico do produto e a concepção do MVP foram estruturados através das diretrizes do framework **Lean Inception** (Paulo Caroli), documentado integralmente no Board oficial do Miro através de 9 passos interdependentes:

* **Passo 1: Product Vision (Visão do Produto):** Definição das fronteiras do ecossistema, estabelecendo de forma clara as dores e o valor de engenharia da plataforma através do template clássico de direcionamento técnico.
* **Passo 2: IS - IS NOT - DOES - DOES NOT (É - Não É - Faz - Não Faz):** Alinhamento das fronteiras lógicas do escopo, delimitando de forma transparente a atuação do middleware contra soluções genéricas de chat nativo ou plug-ins de prateleira do Jira.
* **Passo 3: Product Goals (Metas do Ecossistema):** Estruturação e categorização dos objetivos em três pilares fundamentais de engenharia de software: Metas de Eficiência, Metas de Processo e Metas de Arquitetura.
* **Passo 4: Personas (Perfis do Ecossistema):** Mapeamento dos fatores humanos e atores do sistema, desdobrando perfis específicos (Gestor Acadêmico, Líder Técnico, Auditor de Processos e Engenheiro de Software) associados aos seus respectivos níveis de desconfiança com a IA e necessidades de controle.
* **Passo 5: Users' Journeys (Jornadas dos Usuários):** Cruzamento da arquitetura assíncrona do sistema (rotas FastAPI, estados `PENDING_APPROVAL` no Next.js) com os estágios analíticos, vigilantes e emocionais do operador ao longo do fluxo técnico.
* **Passo 6: Feature Brainstorming (Brainstorming de Funcionalidades):** Conexão dos pilares de valor do produto com o detalhamento de código, como esquemas estritos do Pydantic V2 atuando na porta 8443 via proxy Cloudflare para mitigar Prompt Injections.
* **Passo 7: Technical, Business and UX Review (Gráfico Semáforo):** Matriz de trade-offs de engenharia. Avaliação das funcionalidades através de pilares de Certeza Técnica e Complexidade, priorizando entregas de valor e isolando riscos lógicos das LLMs.
* **Passo 8: Sequencer (Sequenciador de Funcionalidades):** Planejamento físico de lançamentos dividido em 3 ondas lógicas de engenharia (Onda 1: Entrada e Interpretação; Onda 2: Conectividade e Segurança; Onda 3: Homologação e Persistência), garantindo um roadmap viável de arquitetura.
* **Passo 9: The MVP Canvas (O Canvas do MVP):** Consolidação estratégica do plano de entrega técnica, agrupando propostas de valor, jornadas impactadas, métricas de sucesso de infraestrutura e estimativas de custo e cronograma.

---

## 🏗️ 5. Dinâmica do Product Backlog & Validação do Fluxo de Homologação
O artefato `product-backlog.pdf` reflete fielmente o conceito real de **Backlog Emergente** preconizado pelas metodologias ágeis. A variação no nível de preenchimento dos tickets possui uma justificativa metodológica e experimental clara, atrelada ao ciclo de maturação da própria plataforma:

* **Tickets de Infraestrutura Core (Alta Complexidade Técnico):** Os itens focados na engenharia de base do ecossistema (como o Enclave de Segurança, o barramento de dados lógicos do T-Bridge e os validadores estritos do Pydantic V2) foram criados inicialmente com escopo focado na arquitetura. Como o processo de automação de requisitos do T-SONAIR ainda estava sendo consolidado e calibrado pelo time de desenvolvimento, essas frentes complexas de engenharia rodaram em paralelo para garantir a sustentação e a entrega da infraestrutura core do sistema.
* **Tickets de Gestão (Homologação e Validação do Fluxo Ativo):** Os tickets relacionados aos contextos de gestão e fluxos operacionais foram utilizados como o **cenário real de teste e homologação para a ativação das melhorias do T-SONAIR**. Por estarem mapeados no pipeline automatizado, esses itens foram gerados, refinados e documentados de forma nativa pela inteligência artificial direto no ecossistema (Jira Cloud API v3 e Confluence XHTML). Esse experimento prático validou a eficiência do produto em cenários de governança ágil, provando que a plataforma elimina a necessidade de digitação burocrática manual por parte do PO à medida que o pipeline entra em estado estável.

---

## 🛑 6. Absorção Incremental do ThoughtWorks Ground e Ação do AI Compliance Gate
* **ThoughtWorks Ground:** É importante ressaltar que as diretrizes de governança do *ThoughtWorks Ground* não estavam sendo aplicadas no estágio embrionário do projeto. A conformidade com esse framework de engenharia ocorreu de forma incremental e adaptativa, com as boas práticas sendo mapeadas, refinadas e absorvidas ao longo do bimestre durante a execução da própria disciplina.
* **AI Compliance Gate:** Como demonstrado no mapeamento de processos e nos relatórios de auditoria, a esteira conta com um mecanismo rígido de segurança e governança. Caso uma tarefa seja movida para o status de conclusão sem a devida conformidade documental, o *AI Compliance Gate* atua de forma imediata: a automação intercepta a chamada, reverte a transição do ticket para a coluna de Auditoria/Compliance Docs e emite alertas automatizados de violação. O arquivo consolidado do backlog registra explicitamente o tratamento de chamados e esses eventos de reversão de conformidade.

---

## 🔗 7. Links Oficiais do Ecossistema

* **Board de Engenharia (Miro):** [Acessar Mapeamento Interativo da Lean Inception](https://miro.com/app/board/uXjVHPIhqzU=/)
* **Protótipo de Interface (Figma):** [Acessar Workspace de Design do T-SONAIR](https://www.figma.com/design/95RlL4wEon5z49d2Yp5ky4/T-SONAiR-Prototype?node-id=0-1&t=l8K6IxAg117a73AB-1)
* **Demonstração em Vídeo (YouTube):** [Assista ao Showcase Técnico do T-SONAIR](https://youtu.be/xN829EZsen8?si=Cvh9seyb364ozTpF)

---

## 🗂️ 8. Estrutura de Arquivos do Repositório (Guia da Banca)
* **`/wireframe`**: Pasta contendo os registros visuais de layout obtidos diretamente da interface codificada.
* **`canvas-url.txt`**: Arquivo com o link público alternativo para o board do Miro.
* **`video-url.txt`**: Arquivo de texto contendo o link de acesso externo para a apresentação no YouTube.
* **`product-backlog.pdf`**: Documentação integral e exportada de todos os 31 tickets do projeto com seus históricos de automação.
* **`sprint-backlog.pdf`**: Relatório de fechamento da Sprint 3 com o gráfico de Burndown (Split Backlog).
* **`restrospectiveMeeting.png`**: Registro visual e analítico da dinâmica de Sprint Retrospective da Sprint 3, evidenciando o mapeamento de gargalos e melhorias contínuas.

```
