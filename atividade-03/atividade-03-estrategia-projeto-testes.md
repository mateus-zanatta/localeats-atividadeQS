# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## 1. Identificação

**Turma:** QS_Noite  
**Equipe:** Individual  
**Data:** 22/09/2026

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Mateus Zanatta Mariani | @mateus-zanatta |

**Elemento de Competência:** Planejar e projetar testes selecionando técnicas adequadas.

**Aplicação:** <https://local-eats-unisenac.vercel.app/>

---

## 2. Tarefa 1: Planejamento dos testes

### 2.1 Objetivo dos testes

Verificar se a interface de busca e exploração de restaurantes do LocalEats mantém sua integridade visual, usabilidade e funcionalidade durante a navegação, pesquisa e rolagem em dispositivos móveis, garantindo que o usuário consiga localizar estabelecimentos sem bloqueios de layout ou sobreposição de componentes.

### 2.2 Escopo

#### Funcionalidades incluídas

| Integrante | Funcionalidade incluída | O que será verificado |
|---|---|---|
| Mateus Zanatta Mariani | Explorar e pesquisar restaurantes por especialidade ou localização | Se a interface móvel renderiza a caixa de busca, botões e cabeçalho fixo corretamente sem quebras ou sobreposições durante a rolagem de tela |

#### Funcionalidade não incluída

| Funcionalidade não incluída | Justificativa |
|---|---|
| Fazer pedido (Checkout) | O foco da análise prévia concentrou-se nos problemas de usabilidade, busca e layout responsivo na tela inicial; fluxos transacionais exigem cenários adicionais fora do escopo desta entrega individual |

### 2.3 Abordagem

| Item | Decisão da equipe | Justificativa |
|---|---|---|
| Níveis de teste | Teste de sistema | A busca e a navegação serão avaliadas de forma integrada através da interface do usuário em viewport mobile |
| Tipos de teste | Teste funcional e de usabilidade | O objetivo é validar tanto a resposta funcional da pesquisa quanto a conformidade visual e usabilidade do layout |
| Perspectiva caixa-preta ou caixa-branca | Caixa-preta | Avaliação com base nas entradas, cliques, rolagem de tela e respostas visuais observadas, sem acesso ao código-fonte |
| Técnicas de teste | Particionamento de equivalência | Permite organizar as entradas de busca em classes representativas e avaliar o comportamento da interface em diferentes cenários de pesquisa e visualização |

### 2.4 Ambiente e responsabilidades

| Item | Definição |
|---|---|
| Ambiente necessário | Navegador (Google Chrome / DevTools), emulação de tela mobile (iPhone 12 Pro - 390x844), acesso à aplicação LocalEats em produção e conta de usuário autenticada |
| Responsáveis pelo planejamento | Mateus Zanatta Mariani |
| Responsáveis pela especificação dos casos | Mateus Zanatta Mariani |
| Responsáveis pela futura execução | Mateus Zanatta Mariani |

### 2.5 Critérios

| Critério | Definição da equipe |
|---|---|
| Entrada | Aplicação online e acessível, listagem de restaurantes cadastrados carregada e ferramentas de emulação configuradas |
| Saída | Os três casos de teste planejados executados e seus resultados e evidências devidamente registrados |
| Suspensão | Indisponibilidade total do servidor da aplicação ou falha crítica que impeça a renderização inicial dos restaurantes |

---

## 3. Tarefa 2: Riscos e técnicas de teste

### 3.1 Análise dos riscos

| ID | Integrante | Funcionalidade | Risco | Consequência | Probabilidade | Impacto | Prioridade | Justificativa |
|---|---|---|---|:---:|:---:|:---:|:---:|---|
| R01 | Mateus Zanatta Mariani | Explorar restaurantes | O cabeçalho quebrar e sobrepor elementos durante a rolagem da página | O usuário perde acesso aos menus superiores e o layout fica ilegível em smartphones | Alta | Alto | Alta | Problema já evidenciado na gravação de tela da Atividade 1; afeta diretamente a usabilidade no dispositivo mais comum de uso |
| R02 | Mateus Zanatta Mariani | Pesquisar restaurantes | O botão \"Buscar\" ficar sobreposto à caixa de texto em telas menores | O usuário não consegue visualizar o texto digitado nem interagir com o campo de forma confortável | Alta | Alto | Alta | Problema comprovado em print da Atividade 1; inviabiliza a usabilidade da funcionalidade essencial de busca na plataforma |

### 3.2 Aplicação das técnicas

#### Análise do integrante 1

**Integrante:** Mateus Zanatta Mariani  
**Funcionalidade:** Explorar e pesquisar restaurantes por especialidade ou localização  
**Risco relacionado:** R01 e R02  
**Técnica escolhida:** Particionamento de equivalência

**Por que a técnica foi escolhida:**  
A funcionalidade de busca e a interface de visualização recebem entradas e interações do usuário que podem ser categorizadas em classes representativas (busca por categoria válida, busca por termo inexistente e interação direta de layout/rolagem no mobile), permitindo validar o comportamento funcional e responsivo sem necessidade de testes exaustivos para cada restaurante da base.

**Aplicação da técnica:**

| Classe de equivalência | Exemplo de entrada | Resultado esperado |
|---|---|---|
| Categoria existente com layout responsivo | \"Italiana\" | Exibir os restaurantes da categoria com o botão de busca alinhado e o campo de texto 100% visível |
| Termo sem correspondência no sistema | \"restaurante_inexistente_123\" | Exibir \"Nenhum restaurante encontrado\" de forma centralizada e sem quebrar os elementos da tela |
| Interação visual de rolagem vertical (Scroll > 100px) | Ação de rolar a página para baixo | Cabeçalho fixar-se ou comportar-se suavemente sem sobrepor o conteúdo central nem quebrar linhas |

**Casos derivados:** CT01, CT02 e CT03

---

## 4. Tarefa 3: Casos de teste e rastreabilidade

### 4.1 Casos de teste

### CT01: Validar busca por categoria e alinhamento do botão em layout mobile

**Integrante responsável:** Mateus Zanatta Mariani  
**Funcionalidade:** Pesquisar restaurantes por especialidade ou localização  
**Risco ou requisito relacionado:** R02  
**Técnica utilizada:** Particionamento de equivalência (classe: categoria existente com layout responsivo)

**Pré-condição:**  
Aplicação carregada na tela inicial em viewport mobile (390x844), com restaurantes cadastrados na categoria \"Italiana\".

**Dados de entrada:**  
\"Italiana\"

**Passos:**

1. Acessar a tela inicial do LocalEats no navegador emulado para mobile.
2. Localizar o campo de pesquisa \"Buscar por culinária ou localização\".
3. Digitar \"Italiana\" no campo de texto.
4. Clicar no botão \"Buscar\".

**Resultado esperado:**  
A listagem exibe os restaurantes de culinária italiana, e o botão \"Buscar\" permanece alinhado corretamente ao lado/abaixo do campo, sem cobrir a digitação do usuário.

---

### CT02: Validar estabilidade do cabeçalho durante a rolagem de página no mobile

**Integrante responsável:** Mateus Zanatta Mariani  
**Funcionalidade:** Explorar restaurantes  
**Risco ou requisito relacionado:** R01  
**Técnica utilizada:** Particionamento de equivalência (classe: interação visual de rolagem vertical)

**Pré-condição:**  
Aplicação aberta na tela inicial no dispositivo móvel com múltiplos restaurantes listados.

**Dados de entrada:**  
Ação de rolagem vertical (scroll down de 300px).

**Passos:**

1. Acessar a tela inicial do LocalEats.
2. Observar a disposição inicial do logotipo e dos menus superiores.
3. Rolar a página verticalmente para baixo até ultrapassar o primeiro card de destaque.

**Resultado esperado:**  
O cabeçalho superior mantém sua formatação estruturada sem quebrar links em várias linhas ou cobrir o conteúdo dos restaurantes abaixo.

---

### CT03: Validar busca por termo inexistente e integridade dos cards

**Integrante responsável:** Mateus Zanatta Mariani  
**Funcionalidade:** Pesquisar restaurantes por especialidade ou localização  
**Risco ou requisito relacionado:** Requisito de qualidade (Estética e usabilidade da interface)  
**Técnica utilizada:** Particionamento de equivalência (classe: termo sem correspondência)

**Pré-condição:**  
Aplicação carregada na tela inicial em resolução mobile.

**Dados de entrada:**  
\"restaurante_inexistente_123\"

**Passos:**

1. Acessar a tela inicial do LocalEats.
2. Digitar \"restaurante_inexistente_123\" no campo de busca.
3. Clicar no botão \"Buscar\".

**Resultado esperado:**  
O sistema apresenta a mensagem amigável de que nenhum restaurante foi encontrado, mantendo o espaçamento adequado entre blocos e o alinhamento de todos os componentes da tela.

---

### 4.2 Matriz de rastreabilidade

| Integrante | Funcionalidade | Risco ou requisito | Técnica utilizada | Casos de teste |
|---|---|---|---|---|
| Mateus Zanatta Mariani | Pesquisar restaurantes por especialidade ou localização | R02 | Particionamento de equivalência | CT01 |
| Mateus Zanatta Mariani | Explorar restaurantes | R01 | Particionamento de equivalência | CT02 |
| Mateus Zanatta Mariani | Pesquisar restaurantes por especialidade ou localização | Requisito de qualidade (Atividade 1) | Particionamento de equivalência | CT03 |

---

## 5. Uso de inteligência artificial

**Ferramenta utilizada:**  
Perplexity AI

**Como foi utilizada:**  
Apoio no planejamento dos testes, definição dos riscos com foco nas falhas mobile, aplicação do particionamento de equivalência e elaboração detalhada dos 3 casos de teste seguindo o template do repositório da disciplina.

**Uma sugestão que precisou ser alterada ou rejeitada:**  
A sugestão inicial de utilizar testes de carga e desempenho foi descartada, ajustando o foco para testes funcionais de sistema e usabilidade mobile, que refletem os problemas reais encontrados na exploração prática da Atividade 1.

**Como as respostas foram verificadas:**  
Conferência contra o modelo padrão de entrega, validação de cada caso de teste em relação às evidências registradas no ambiente móvel (390x844) e conferência da matriz de rastreabilidade.
