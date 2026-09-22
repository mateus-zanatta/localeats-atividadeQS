# Atividade 2: Organização da Qualidade no LocalEats

## 1. Identificação

**Turma:** QS_Noite  
**Equipe:** Individual  
**Data:** 22/09/2026

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Mateus Zanatta Mariani | @mateus-zanatta |

**Elemento de Competência:** Identificar papéis, responsabilidades e competências relacionadas às atividades de qualidade e testes.

---

## 2. Tarefa 1: Diagnóstico da situação

### 2.1 Problemas organizacionais

| Problema identificado | Possível consequência para o produto ou para a equipe |
|---|---|
| Os critérios para considerar uma funcionalidade pronta não estão claros (falta de DoD) | Funcionalidades com falhas de layout e responsividade chegam aos usuários em produção antes de serem devidamente validadas |
| Alguns integrantes acreditam que somente o QA deve testar | Desenvolvedores não testam o próprio código nem a responsividade básica, sobrecarregando o QA e gerando gargalos nas entregas |
| Não está claro quem pode aprovar a disponibilização de uma nova versão | Versões instáveis podem ser publicadas sem validação formal, ou o lançamento pode atrasar por falta de um responsável definido para o deploy |

### 2.2 Responsabilidade pela qualidade

**A qualidade do LocalEats deve ser responsabilidade exclusiva do profissional de QA? Justifiquem.**

Não. A qualidade resulta de decisões tomadas ao longo de todo o ciclo de desenvolvimento: quem define requisitos estabelece a clareza do que é esperado, quem desenvolve precisa garantir código limpo e testes unitários/responsivos, e quem lidera valida padrões técnicos. Se apenas o QA fosse responsável, os testes ocorreriam tardiamente, elevando o custo de correção e desresponsabilizando o restante da equipe pela prevenção de falhas. A qualidade deve ser construída colaborativamente por todo o time.

---

## 3. Tarefa 2: Papéis e competências

| Integrante | Papel analisado | Responsabilidades relacionadas à qualidade | Competências técnicas | Competências comportamentais |
|---|---|---|---|---|
| Mateus Zanatta Mariani | Desenvolvedor | Implementar funcionalidades seguindo requisitos e padrões visuais responsivos; testar componentes e layout no mobile antes da entrega; corrigir defeitos de sua área | Domínio de HTML5/CSS3 moderno (Flexbox, Grid), JavaScript/TypeScript (React), noções de testes unitários e depuração via DevTools | Atenção aos detalhes visuais; disposição para testar a própria interface; boa comunicação para alinhar requisitos técnicos |
| Mateus Zanatta Mariani | QA / Analista de Qualidade | Planejar e executar testes de sistema e usabilidade cross-device; registrar e acompanhar defeitos com evidências detalhadas; apoiar na definição de critérios de aceitação | Conhecimento de técnicas de teste de software (caixa-preta, particionamento de equivalência); uso de ferramentas de emulação e rastreamento de bugs | Pensamento crítico; postura analítica e investigativa; comunicação empática ao reportar problemas sem gerar atritos |
| Mateus Zanatta Mariani | Líder técnico | Revisar código (Code Review) antes do merge; definir arquitetura e padrões técnicos de qualidade; apoiar na priorização de correções críticas | Ampla experiência em arquitetura de software; capacidade de revisar código de terceiros; domínio de pipelines de CI/CD | Capacidade de oferecer feedback construtivo; liderança técnica colaborativa; mediação de decisões sob pressão |
| Mateus Zanatta Mariani | Responsável pelo produto | Definir requisitos e critérios de aceitação claros (incluindo suporte a múltiplos dispositivos); priorizar o backlog de correções; aprovar a versão final | Entendimento do domínio de negócio de delivery; capacidade de modelar histórias de usuário e critérios de pronto | Visão estratégica de produto; facilidade na tomada de decisão; comunicação clara com usuários e equipe |

---

## 4. Tarefa 3: Matriz de responsabilidades

Utilizem:

- **R:** responsável por executar a atividade;
- **A:** aprovador ou responsável final;
- **C:** consultado antes da execução ou decisão;
- **I:** informado sobre o resultado.

| Atividade de qualidade | Desenvolvedor | QA | Líder técnico | Responsável pelo produto |
|---|:---:|:---:|:---:|:---:|
| Definir critérios de aceitação | I | C | C | R/A |
| Revisar requisitos | I | C | R | A |
| Implementar a funcionalidade | R/A | I | C | I |
| Revisar o código | C | I | R/A |  |
| Criar testes unitários | R/A | C | I |  |
| Planejar e executar testes do sistema | C | R/A | I | I |
| Registrar e acompanhar defeitos | C | R/A | I | I |
| Priorizar a correção dos defeitos | C | C | R | A |
| Aprovar a disponibilização da versão | I | C | R | A |

### 4.1 Lacuna ou conflito encontrado

**Lacuna ou conflito:**  
Na atividade "Implementar a funcionalidade", o próprio Desenvolvedor atua como R e A ao mesmo tempo, sem uma validação inicial cruzada de layout/responsividade antes de submeter o código.

**Consequência:**  
Isso se conecta diretamente ao problema de funcionalidades chegarem aos usuários com layout quebrado em dispositivos móveis, pois a implementação é considerada concluída sem que uma segunda perspectiva avalie a interface em viewports menores.

### 4.2 Práticas de QA recomendadas

| Prática recomendada | Problema que ajuda a resolver | Papéis envolvidos |
|---|---|---|
| Definição explícita de Definition of Ready (DoR) e Definition of Done (DoD) com testes de responsividade | Elimina a falta de clareza sobre quando uma tarefa está pronta para entrega, garantindo validação visual mobile antes do deploy | Responsável pelo produto, Desenvolvedor, QA e Líder técnico |
| Revisão de código obrigatória e testes exploratórios em múltiplos dispositivos antes do merge | Evita que sobreposições de layout e quebras de cabeçalho passem despercebidas para o ambiente de produção | Desenvolvedor, QA, Líder técnico |

---

## 5. Uso de inteligência artificial

**Ferramenta utilizada:**  
Perplexity AI

**Como foi utilizada:**  
Apoio na estruturação das seções da atividade, alinhamento dos 4 papéis com competências técnicas/comportamentais e organização da Matriz RACI seguindo a padronização oficial do repositório da disciplina.

**Como as respostas foram verificadas:**  
Revisão individual das responsabilidades e verificação das regras da matriz RACI (presença de pelo menos um R e um único A por linha) para garantir coerência com o contexto de desenvolvimento e testes do LocalEats.
