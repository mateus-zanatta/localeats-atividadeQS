# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## 1. Identificação
- **Unidade Curricular:** Qualidade de Software
- **Projeto:** LocalEats
- **Integrante:** Mateus Zanatta Mariani

---

## Tarefa 1: Planejamento dos testes

### 1.1 Objetivo dos testes
Verificar se a interface móvel e a busca/exploração de restaurantes do LocalEats mantêm sua usabilidade, legibilidade e integridade visual durante a navegação, pesquisa e rolagem em diferentes viewports, garantindo que o usuário consiga localizar e visualizar estabelecimentos sem bloqueios de interface.

### 1.2 Escopo

| Integrante | Funcionalidade incluída | O que será verificado |
| :--- | :--- | :--- |
| Mateus Zanatta Mariani | Explorar e Pesquisar Restaurantes (Interface Mobile) | Responsividade do layout em tela de 390px, comportamento da barra de busca/botão e fixação do cabeçalho durante o scroll. |

| Funcionalidade não incluída | Justificativa |
| :--- | :--- |
| Finalização e pagamento de pedido (Checkout) | Foco desta iteração de testes concentrado na experiência de descoberta, usabilidade e busca no frontend mobile. |

### 1.3 Abordagem

| Item | Decisão da equipe | Justificativa |
| :--- | :--- | :--- |
| **Níveis de teste** | Teste de Sistema e Teste de Interface / Usabilidade | O fluxo de busca e navegação precisa ser testado de ponta a ponta pela interface gráfica em contexto real de uso. |
| **Tipos de teste** | Funcional e Não Funcional (Usabilidade e Responsividade) | O objetivo é assegurar tanto a execução da busca quanto a estabilidade estética e visual do layout. |
| **Perspectiva** | Caixa-preta | A validação avalia as entradas do usuário, interações táteis/clique e renderização visual na tela, sem acesso direto ao código interno da aplicação. |
| **Técnicas de teste** | Particionamento de Equivalência e Transição de Estados (Scroll/Visual) | Permitem testar categorias de busca válidas/inválidas e o comportamento dinâmico da interface antes e depois da rolagem de tela. |

### 1.4 Ambiente e responsabilidades

| Item | Definição |
| :--- | :--- |
| **Ambiente necessário** | URL: `https://local-eats-unisenac.vercel.app/`; Navegador Google Chrome / Firefox com DevTools emulado em dispositivo móvel (ex: iPhone 12 Pro - 390x844); Conexão estável com a internet; Usuário cadastrado/autenticado. |
| **Responsáveis pelo planejamento** | Mateus Zanatta Mariani |
| **Responsáveis pela especificação dos casos** | Mateus Zanatta Mariani |
| **Responsáveis pela futura execução** | Mateus Zanatta Mariani |

### 1.5 Critérios

| Critério | Definição da equipe |
| :--- | :--- |
| **Entrada** | Aplicação LocalEats acessível online, dados de restaurantes cadastrados na base e ferramentas de emulação de dispositivos móveis configuradas. |
| **Saída** | 100% dos casos de teste executados, anomalias visuais e funcionais registradas com evidências e relatório de conformidade preenchido. |
| **Suspensão** | Indisponibilidade total do servidor (erro 500/503), falha geral no deploy do Vercel ou impossibilidade de carregar a lista de restaurantes. |

---

## Tarefa 2: Riscos e técnicas de teste

### 2.1 Análise dos riscos

| ID | Integrante | Funcionalidade | Risco | Consequência | Probabilidade | Impacto | Prioridade | Justificativa |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **R01** | Mateus Zanatta Mariani | Explorar restaurantes / Navegação Mobile | O cabeçalho desconfigurar/quebrar e cobrir conteúdos ao rolar a página para baixo | Usuário não consegue clicar nos menus superiores ou o texto fica ilegível, gerando desistência do uso em smartphones | **Alta** | **Alto** | **Alta** | Dispositivos móveis representam a maior fatia de acessos para apps de delivery; quebra estrutural impede a navegação básica. |
| **R02** | Mateus Zanatta Mariani | Pesquisar restaurantes | O botão de busca ficar posicionado sobre a caixa de texto em telas menores | Impossibilidade de visualizar o termo digitado ou clicar no campo de texto de forma precisa | **Alta** | **Médio** | **Alta** | Prejudica diretamente a funcionalidade central de pesquisa de restaurantes por localização/culinária. |

### 2.2 Aplicação da técnica

**Integrante responsável:** Mateus Zanatta Mariani  
**Funcionalidade:** Explorar e Pesquisar Restaurantes no Mobile  
**Riscos relacionados:** R01 e R02  
**Técnica escolhida:** Particionamento de Equivalência e Teste de Transição de Estado Visual (Rolagem de Tela)

#### Por que a técnica foi escolhida?
O particionamento de equivalência permite avaliar classes de busca com termos válidos, vazios e inexistentes com o menor número de testes. O teste baseado em transição de estado de rolagem (topo vs. página rolada) valida se o CSS e a posição do cabeçalho/elementos móveis comportam-se de forma consistente em diferentes estados da viewport.

#### Aplicação da técnica

1. **Classes de Equivalência para Busca:**
   - **Classe Válida 1:** Termo existente (ex: "Japonesa" ou "Centro") -> Deve exibir restaurantes correspondentes com layout limpo e botão alinhado.
   - **Classe Válida 2 (Filtro por tag):** Clique direto no chip "Mexicana" / "Italiana" -> Deve filtrar a lista sem quebrar a posição dos elementos.
   - **Classe Inválida / Vazia:** Termo inexistente ou busca em branco -> Deve exibir mensagem adequada sem sobreposições na tela.

2. **Estados de Rolagem da Interface:**
   - **Estado 1 (Topo / Scroll = 0):** Cabeçalho e banner de destaque com espaçamento adequado em relação ao card de restaurante.
   - **Estado 2 (Rolagem ativa / Scroll > 100px):** Cabeçalho sticky/fixed deve permanecer compacto e legível sem colapsar ou cobrir o conteúdo central.

#### Casos derivados
- **CT01:** Validar layout do campo de busca e botão "Buscar" em resolução mobile (390x844).
- **CT02:** Validar fixação e integridade do cabeçalho durante a rolagem vertical de página.
- **CT03:** Validar espaçamento e alinhamento do bloco de imagem do restaurante com o cabeçalho.

---

## Tarefa 3: Casos de teste e rastreabilidade

### 3.1 Especificação dos casos de teste

#### CT01: Validar layout do campo de busca e botão "Buscar" em resolução mobile
- **Integrante responsável:** Mateus Zanatta Mariani
- **Funcionalidade:** Pesquisar restaurantes
- **Risco ou requisito relacionado:** R02
- **Técnica utilizada:** Particionamento de Equivalência / Teste de Responsividade

**Pré-condição:**  
Aplicação aberta no navegador em modo de emulação móvel (iPhone 12 Pro - 390x844) e na página inicial de restaurantes.

**Dados de entrada:**  
Texto digitado no input de busca: `"Italiana"`

**Passos:**
1. Acessar a página inicial do LocalEats na resolução de 390x844.
2. Localizar o campo de texto `"Buscar por culinária ou localização"`.
3. Observar a posição do botão `"Buscar"` em relação ao campo de texto.
4. Digitar o texto `"Italiana"` no campo.
5. Clicar no botão `"Buscar"`.

**Resultado esperado:**  
O campo de texto e o botão de busca devem estar perfeitamente alinhados (o botão deve ficar ao lado ou abaixo sem invadir a área de digitação), permitindo ler o texto completo digitado e realizar a busca sem impedimentos visuais.

---

#### CT02: Validar fixação e integridade do cabeçalho durante a rolagem vertical de página
- **Integrante responsável:** Mateus Zanatta Mariani
- **Funcionalidade:** Explorar restaurantes
- **Risco ou requisito relacionado:** R01
- **Técnica utilizada:** Teste de Transição de Estado Visual (Rolagem de Tela)

**Pré-condição:**  
Estar autenticado no LocalEats com o perfil "Olá, Mateus" e estar na visualização inicial da listagem em tela mobile (390x844).

**Dados de entrada:**  
Ação de rolagem vertical para baixo (scroll down de 300px a 600px).

**Passos:**
1. Acessar a aplicação no viewport mobile.
2. Observar a disposição inicial do cabeçalho contendo o logotipo "LocalEats", os links de menu e o avatar de usuário.
3. Efetuar a rolagem da página para baixo até ultrapassar a primeira seção de destaques.
4. Observar a renderização do cabeçalho e dos links ("Explorar", "Meus Favoritos", "Meus Pedidos").

**Resultado esperado:**  
Ao rolar a página, o cabeçalho deve permanecer fixado de forma limpa ou ocultar-se suavemente, sem quebrar linhas, sem amontoar links sobre o logotipo ou sobrepor indevidamente o card do restaurante.

---

#### CT03: Validar espaçamento e alinhamento do bloco de imagem do restaurante com o cabeçalho
- **Integrante responsável:** Mateus Zanatta Mariani
- **Funcionalidade:** Explorar restaurantes
- **Risco ou requisito relacionado:** R01 / Requisito de Estética e Usabilidade
- **Técnica utilizada:** Teste de Usabilidade e Layout

**Pré-condição:**  
Acessar a visualização de detalhes do restaurante ou card em destaque no catálogo inicial.

**Dados de entrada:**  
Navegação direta para a seção de catálogo do restaurante ("Restaurante Sabor 1").

**Passos:**
1. Acessar a tela inicial do LocalEats no dispositivo móvel.
2. Visualizar o card principal com a imagem do restaurante.
3. Verificar a margem superior (margin/padding) entre o card/imagem e a barra superior do cabeçalho.

**Resultado esperado:**  
Deve haver um espaçamento visual nítido e padronizado entre o bloco de imagem e o cabeçalho, evitando cortes visuais na imagem ou sensação de colagem direta entre componentes.

---

### 3.2 Matriz de rastreabilidade

| Integrante | Funcionalidade | Risco ou requisito | Técnica utilizada | Casos de teste |
| :--- | :--- | :--- | :--- | :--- |
| Mateus Zanatta Mariani | Pesquisar restaurantes | R02: Botão de busca sobreposto à caixa de entrada | Particionamento de Equivalência / Responsividade | CT01 |
| Mateus Zanatta Mariani | Explorar restaurantes | R01: Cabeçalho quebrado durante o scroll | Transição de Estado Visual (Scroll) | CT02 |
| Mateus Zanatta Mariani | Explorar restaurantes | R01 / Estética: Falta de espaçamento entre imagem e header | Teste de Usabilidade e Layout | CT03 |

---

## Uso de inteligência artificial

- **Ferramenta utilizada:** Perplexity AI
- **Como foi utilizada:** Apoio na elaboração e estruturação do plano de testes, categorização dos riscos (probabilidade/impacto), modelagem dos 3 casos de teste específicos e montagem da matriz de rastreabilidade.
- **Uma sugestão que precisou ser alterada ou rejeitada:** A sugestão inicial de focar os testes em validações de banco de dados e APIs backend foi substituída pelo foco nos problemas reais de layout mobile e usabilidade (viewport 390x844) evidenciados nos testes práticos.
- **Como as respostas foram verificadas:** Verificação manual passo a passo dos fluxos descritos em relação à interface real do LocalEats e às evidências registradas.
