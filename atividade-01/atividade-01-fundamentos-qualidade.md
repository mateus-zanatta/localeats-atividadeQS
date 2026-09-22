# Atividade 1: Fundamentos e Características da Qualidade no LocalEats

## 1. Identificação
- **Unidade Curricular:** Qualidade de Software
- **Projeto:** LocalEats
- **Integrante:** Mateus Zanatta Mariani

---

## Tarefa 1: Fundamentos da qualidade

### Tabela de Necessidades Explícitas e Implícitas

| Tipo | Necessidade | Interessado | Consequência se não for atendida |
| :--- | :--- | :--- | :--- |
| **Explícita** | Permitir pesquisar e filtrar restaurantes por especialidade e localização | Usuário / Cliente | O usuário não encontra o restaurante desejado, gerando frustração e abandono da plataforma. |
| **Explícita** | Permitir a autenticação de usuários (criar conta e entrar no sistema) | Usuário / Sistema | O usuário não consegue manter seus dados salvos, favoritos ou histórico de pedidos sincronizados. |
| **Implícita** | Responsividade e estabilidade visual do layout em dispositivos móveis sem sobreposição de elementos | Usuário Mobile | Dificuldade ou impossibilidade de clicar em campos e botões essenciais, inviabilizando o uso em smartphones. |
| **Implícita** | Feedback visual imediato e legibilidade de cabeçalhos/menus durante a rolagem (scroll) | Usuário / Cliente | Perda de contexto e navegação comprometida, causando sensação de sistema inacabado e baixa confiabilidade. |

### Justificativa

Um sistema que implementa todas as funcionalidades solicitadas pode, sim, apresentar baixa qualidade caso falhe nas necessidades implícitas. Por exemplo, se a busca por restaurante existe e funciona na regra de negócio, mas o botão de busca fica sobreposto ao campo de texto no mobile impedindo a digitação ou o clique, a usabilidade e a experiência do usuário são severamente comprometidas, tornando o software ineficiente e frustrante.

---

## Tarefa 2: Exploração da aplicação

### Registro da Exploração

| Integrante | Funcionalidade | O que foi realizado | O que foi observado | Evidência |
| :--- | :--- | :--- | :--- | :--- |
| Mateus Zanatta Mariani | Explorar restaurantes / Navegação Mobile e Busca | Acessou a página inicial e a exploração de restaurantes via emulação mobile (iPhone 12 Pro / 390x844), realizando rolagem na tela e tentativa de preenchimento da busca. | O cabeçalho quebrou e sobrepôs links ao rolar a página; o botão "Buscar" sobrepôs a caixa de texto de busca; e houve falta de espaçamento adequado entre o bloco de imagem do restaurante e o cabeçalho. | `evidencias/ao-scrollar-cabecalho-quebrado.mp4`, `evidencias/botao-buscar-sobreposto.jpg`, `evidencias/falta-espaco-bloco-imagem.jpg` |

---

## Tarefa 3: Requisitos e características de qualidade

| Integrante | Requisito de Qualidade | Característica ou subcaracterística (ISO/IEC 25010) | Justificativa | Como avaliar |
| :--- | :--- | :--- | :--- | :--- |
| Mateus Zanatta Mariani | A interface da aplicação deve manter a integridade visual dos elementos de navegação (header fixo, inputs e botões) em resoluções mobile (ex: 390x844) durante a rolagem e interação. | **Usabilidade** / **Estética da interface do usuário** (*User interface aesthetics*) e **Adaptabilidade** (*Portability / Adaptability*) | Problemas de layout quebrado, sobreposição de botões em campos de texto e ausência de espaçamento adequado impedem o uso confortável e degradam a navegabilidade do LocalEats em smartphones. | Testar a interface em diferentes resoluções de tela e dispositivos móveis (360px a 414px de largura), verificando visualmente se há sobreposição de componentes (`z-index` / `position: sticky/fixed`) e se todos os botões e inputs permanecem 100% clicáveis e legíveis ao rolar a página. |

---

## Uso de inteligência artificial

- **Ferramenta utilizada:** Perplexity AI
- **Como foi utilizada:** Apoio na estruturação do documento conforme o padrão do guia, formatação das tabelas e alinhamento do requisito de qualidade segundo a norma ISO/IEC 25010 com base nos problemas visuais observados nos testes.
- **Como as respostas foram verificadas:** Leitura crítica e conferência manual das evidências capturadas na interface móvel do LocalEats para garantir que as descrições refletem estritamente o comportamento real da aplicação.
