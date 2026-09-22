# Atividade 2: Organização da Qualidade no LocalEats

## 1. Identificação
- **Unidade Curricular:** Qualidade de Software
- **Projeto:** LocalEats
- **Integrante:** Mateus Zanatta Mariani

---

## Tarefa 1: Diagnóstico da situação

### Problemas Organizacionais Identificados

| Problema identificado | Possível consequência para o produto ou para a equipe |
| :--- | :--- |
| **Falta de clareza nos critérios de pronto (Definition of Done - DoD)** | Funcionalidades com falhas visuais e de layout (como quebras em telas mobile) são enviadas para produção antes de serem devidamente validadas. |
| **Crença de que somente o QA deve testar** | Sobrecarga do analista de qualidade, gargalo nas entregas e falta de testes preliminares de responsividade/unidade pelos próprios desenvolvedores. |
| **Ausência de processo formal para aprovação de deploy e acompanhamento de defeitos** | Versões instáveis são disponibilizadas diretamente aos clientes, e bugs identificados são esquecidos ou acumulados sem priorização. |

### Justificativa

A qualidade do LocalEats **não** deve ser responsabilidade exclusiva do QA. A qualidade é uma responsabilidade compartilhada por todo o time: o Product Owner define critérios de aceitação claros, os desenvolvedores implementam com boas práticas de código e testes de componentes/responsividade, e o QA atua apoiando a estratégia, testes exploratórios e automação. Quando a qualidade é deixada apenas para a etapa final, o retrabalho e o custo de correção aumentam drasticamente.

---

## Tarefa 2: Papéis e competências

| Integrante | Papel analisado | Responsabilidades relacionadas à qualidade | Competências técnicas | Competências comportamentais |
| :--- | :--- | :--- | :--- | :--- |
| Mateus Zanatta Mariani | **Desenvolvedor Frontend / Full Stack** | Implementar interfaces responsivas seguindo os padrões de design; realizar testes de componentes e de layout em diferentes viewports (mobile/desktop); garantir que campos e cabeçalhos não quebrem com scroll; corrigir bugs reportados no backlog. | Domínio de HTML5/CSS3 moderno (Flexbox, Grid, media queries), frameworks JavaScript/TypeScript (React), testes unitários/componentes (Jest, Testing Library) e depuração via DevTools. | Atenção aos detalhes visuais, pensamento crítico sobre usabilidade e boa comunicação para alinhar requisitos com design e QA. |
| Mateus Zanatta Mariani | **QA / Analista de Qualidade** | Elaborar planos e casos de teste funcionais e de usabilidade/cross-device; realizar testes exploratórios em múltiplos dispositivos; registrar, classificar e acompanhar defeitos com evidências detalhadas (prints/vídeos). | Técnicas de teste de software (caixa-preta, particionamento de equivalência), ferramentas de emulação/responsividade, automação de testes (Cypress/Playwright) e gestão de defeitos (Jira/GitHub Issues). | Postura analítica, empatia com o usuário final, comunicação clara na descrição de bugs e proatividade. |
| Mateus Zanatta Mariani | **Product Owner (PO)** | Definir regras de negócio claras e critérios de aceitação (incluindo requisitos não funcionais de suporte a mobile); priorizar o backlog de correções de bugs em conjunto com novas features; aprovar a entrega final da versão. | Gestão de requisitos ágeis, modelagem de histórias de usuário, compreensão de métricas de produto e noções de UX/UI. | Visão de negócio, facilidade na tomada de decisão e habilidade para negociar prazos com base na qualidade. |
| Mateus Zanatta Mariani | **Liderança Técnica / Tech Lead** | Definir padrões de arquitetura e qualidade de código; conduzir revisões de código (Code Reviews); garantir práticas de integração contínua (CI/CD) com validações automáticas de build e linting antes do merge. | Arquitetura de software, automação de pipelines de CI/CD, revisão de código e boas práticas de engenharia de software (Clean Code). | Liderança colaborativa, mentoria da equipe e mediação de decisões técnicas com foco em estabilidade. |

---

## Tarefa 3: Matriz de responsabilidades (RACI)

| Atividade de qualidade | Product Owner (PO) | Desenvolvedor | QA / Analista de Qualidade | Tech Lead |
| :--- | :---: | :---: | :---: | :---: |
| Definir critérios de aceitação | **A** | C | C | I |
| Revisar requisitos | **A** | C | C | C |
| Implementar a funcionalidade | I | **R** | I | A |
| Revisar o código | I | C | I | **A / R** |
| Criar testes unitários e de componentes | I | **A / R** | C | C |
| Planejar e executar testes do sistema / responsividade | I | C | **A / R** | I |
| Registrar e acompanhar defeitos | I | C | **A / R** | I |
| Priorizar a correção dos defeitos | **A** | C | C | C |
| Aprovar a disponibilização da versão (Release / Deploy) | **A** | I | C | C |

*Legenda: **R** = Responsável (executa); **A** = Aprovador (decide/aprova); **C** = Consultado; **I** = Informado.*

### Lacuna ou conflito encontrado

**Conflito na disponibilização de versão sem critérios de aceite formais:** Historicamente, desenvolvedores colocavam alterações diretamente no ambiente de produção sem validação de testes do sistema e sem aprovação do PO. Ao centralizar a aprovação da versão no PO (com base no relatório de testes do QA) e o aceite técnico no Tech Lead, evita-se a publicação de código com layout quebrado em dispositivos móveis.

### Práticas recomendadas de QA

| Prática recomendada | Problema que ajuda a resolver | Papéis envolvidos |
| :--- | :--- | :--- |
| **Definition of Ready (DoR) e Definition of Done (DoD) claras** | Elimina a indefinição sobre o que torna uma história pronta para ser desenvolvida e entregue, exigindo que o layout seja testado em resoluções mobile antes de ser considerado "Pronto". | Product Owner, Desenvolvedor, QA e Tech Lead |
| **Testes exploratórios e cross-browser/cross-device no pipeline** | Evita que defeitos visuais (sobreposição de inputs e quebra de cabeçalho) passem despercebidos até chegarem ao cliente final. | Desenvolvedor e QA |

---

## Uso de inteligência artificial

- **Ferramenta utilizada:** Perplexity AI
- **Como foi utilizada:** Auxílio na estruturação da Matriz RACI, alinhamento dos papéis essenciais e formulação de práticas ágeis (DoD/DoR) adaptadas ao cenário de falhas de responsividade do LocalEats.
- **Como as respostas foram verificadas:** Revisão criteriosa para garantir que as regras da matriz (um único A por linha, pelo menos um R) foram rigorosamente respeitadas e que as competências descritas refletem a realidade do projeto.
