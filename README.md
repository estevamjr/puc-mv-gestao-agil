# T-SONAIR // Command Multiplexer & Governance Platform

## 🎯 1. Cenário de Negócio e Stakeholders
O **T-SONAIR** é um middleware de governança projetado para eliminar o gap operacional e a fricção no fluxo de valor de equipes ágeis.
* **A Dor Central:** O tempo desperdiçado pelo Product Owner (PO) na abertura, preenchimento e triagem manual de solicitações e tickets. O ecossistema elimina essa fricção ao capturar a velocidade da ideação em linguagem natural e traduzi-la automaticamente para sistemas de gestão (Jira Cloud API v3).
* **Stakeholders e Usuários:** Pesquisadores de PhD, Product Owners, Compliance Officers e Tech Leads.
* **Time Scrum Enxuto:** 
  * 1 Product Owner (Ideação e Visão de Produto)
  * 1 Tech Lead / Lead Engineer (Arquitetura backend FastAPI e Integrações)
  * 1 Fullstack Engineer (Dashboard HITL em Next.js e Tailwind)

---

## 🔄 2. Espelhamento Metodológico: A Disciplina no Processo e no Produto
Este projeto adota um modelo de **espelhamento metodológico**: os conceitos de **Gestão de Projetos e Produtos Ágeis** foram utilizados tanto no gerenciamento do ciclo de desenvolvimento, quanto no core da própria solução de software criada.

1. **A Disciplina no Processo (Gestão):** O MVP foi gerenciado sob o framework Scrum, pautado na queima de complexidade técnica (15 Story Points na Sprint 3). Desvios de percurso foram diagnosticados na Sprint Retrospective e corrigidos para garantir a queima linear perfeita demonstrada no Burndown Chart.
2. **A Disciplina no Produto (Software):** O sistema atua como uma camada ativa de governança que protege o fluxo contra indiscipina técnica através do **AI Compliance Gate**, automatizando e garantindo o cumprimento de regras de processo diretamente na esteira de código.

---

## 🏗️ 3. Dinâmica do Product Backlog & Engenharia Automática de Requisitos
O artefato `product-backlog.pdf` reflete fielmente o conceito real de **Backlog Emergente** preconizado pelas metodologias ágeis, apresentando variações estruturais intencionais de preenchimento que espelham a maturidade do ecossistema:

* **Frentes Prontas com DoD, US e AC Individuais (Itens Históricos):** Os tickets consolidados das frentes de valor da Sprint e do Enclave (como T-Bridge, HITL e Guardrails) foram refinados com User Stories, Critérios de Aceitação (AC) e Definition of Done (DoD) individuais. 
* **Tasks com Descrições Técnicas Diretas (Frentes de Infraestrutura):** Itens focados estritamente em engenharia de base (como as tarefas de telemetria via Wi-Fi ou gerenciamento via Bitwarden) contam com descrições objetivas de escopo técnico, pois não demandavam a fragmentação em histórias de usuário tradicionais neste estágio do MVP.
* **Tickets Recentes Sem Informações Manuais (Automação Nativa via T-SONAIR):** Os itens de escopo mais recentes não possuem descrições ou critérios preenchidos manualmente pelo PO. Isto ocorre porque o próprio fluxo do T-SONAIR cria de forma automatizada as páginas correspondentes no Confluence com os resumos técnicos discutidos e refinados via LLM. O ecossistema atualiza esses dados de forma síncrona no final do processo, imediatamente antes da etapa de integração, eliminando completamente o trabalho de digitação e triagem humana.

---

## 🛑 4. Ressalva Técnica: Ação do AI Compliance Gate
Como demonstrado no mapeamento de processos e nos relatórios de auditoria, a esteira conta com um mecanismo rígido de segurança e governança. Caso uma tarefa seja movida para o status de conclusão sem a devida conformidade documental, o *AI Compliance Gate* atua de forma imediata: a automação intercepta a chamada, reverte a transição do ticket para a coluna de Auditoria/Compliance Docs e emite alertas automáticos de violação. O arquivo consolidado do backlog registra explicitamente o tratamento de chamados e esses eventos de reversão de conformidade.

---

## 🔗 5. Links Oficiais do Ecossistema

* **Board de Engenharia (Miro):** [Acessar Mapeamento Interativo da Lean Inception](https://miro.com/app/board/uXjVHPIhqzU=/)
* **Protótipo de Interface (Figma):** [Acessar Workspace de Design do T-SONAIR](https://www.figma.com/design/95RlL4wEon5z49d2Yp5ky4/T-SONAiR-Prototype?node-id=0-1&t=l8K6IxAg117a73AB-1)
* **Demonstração em Vídeo (YouTube):** [Link do vídeo de Showcase Técnico será inserido aqui]

---

## 🗂️ 6. Estrutura de Arquivos do Repositório (Guia da Banca)
* **`/wireframe`**: Pasta contendo os registros visuais de layout obtidos diretamente da interface codificada.
* **`canvas-url.txt`**: Arquivo com o link público alternativo para o board do Miro.
* **`video-url.txt`**: Arquivo de texto contendo o link de acesso externo para a apresentação no YouTube.
* **`product-backlog.pdf`**: Documentação integral e exportada de todos os 31 tickets do projeto com seus históricos de automação.
* **`sprint-backlog.pdf`**: Relatório de fechamento da Sprint 3 com o gráfico de Burndown.