# Atividade 1: Fundamentos e Características da Qualidade no LocalEats

## 1. Identificação

**Turma:** QS_Noite  
**Equipe:** Individual  
**Data:** 22/09/2026

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Mateus Zanatta Mariani | @mateus-zanatta |

**Elemento de Competência:** Compreender os fundamentos de qualidade de software e sua aplicação no desenvolvimento de sistemas.

**Aplicação:** <https://local-eats-unisenac.vercel.app/>

---

## 2. Tarefa 1: Fundamentos da qualidade

### 2.1 Necessidades explícitas e implícitas

| Tipo | Necessidade | Interessado | Consequência se não for atendida |
|---|---|---|---|
| Explícita | Permitir pesquisar e filtrar restaurantes por especialidade e localização | Usuário / Cliente | O usuário não encontra o restaurante desejado, gerando frustração e abandono da plataforma |
| Explícita | Permitir a autenticação de usuários (criar conta e entrar no sistema) | Usuário / Sistema | O usuário não consegue manter seus dados salvos, favoritos ou histórico de pedidos sincronizados |
| Implícita | Responsividade e estabilidade visual do layout em dispositivos móveis sem sobreposição de elementos | Usuário Mobile | Dificuldade ou impossibilidade de clicar em campos e botões essenciais, inviabilizando o uso em smartphones |
| Implícita | Feedback visual imediato e legibilidade de cabeçalhos/menus durante a rolagem (scroll) | Usuário / Cliente | Perda de contexto e navegação comprometida, causando sensação de sistema inacabado e baixa confiabilidade |

### 2.2 Questão sobre os fundamentos da qualidade

**Um sistema que implementa todas as funcionalidades explicitamente solicitadas pode, ainda assim, apresentar baixa qualidade? Justifiquem utilizando pelo menos uma necessidade implícita identificada pela equipe.**

Sim, um sistema que implementa todas as funcionalidades solicitadas pode apresentar baixa qualidade caso falhe nas necessidades implícitas. No LocalEats, por exemplo, mesmo que a busca por restaurantes funcione na regra de negócio, se o botão de busca ficar sobreposto à caixa de texto no mobile impedindo a digitação, ou se o cabeçalho quebrar ao rolar a página, a usabilidade é severamente comprometida. Isso demonstra que qualidade vai além de ter funcionalidades: exige atender às expectativas de uso e navegabilidade que nem sempre estão formalizadas em requisitos explícitos.

---

## 3. Tarefa 2: Exploração da aplicação

| Integrante | Funcionalidade | O que foi realizado | O que foi observado | Evidência |
|---|---|---|---|---|
| Mateus Zanatta Mariani | Explorar restaurantes / Navegação Mobile e Busca | Acessei a página inicial e a exploração de restaurantes via emulação mobile (iPhone 12 Pro / 390x844), realizando rolagem na tela e tentativa de preenchimento da busca | O cabeçalho quebrou e sobrepôs links ao rolar a página; o botão "Buscar" ficou sobreposto à caixa de texto de busca; e houve falta de espaçamento adequado entre o bloco de imagem do restaurante e o cabeçalho | [falta de espaço no cabeçalho](evidencias/falta-espaco-entre-os-blocos-de-imagem-e-cabecalho-4.jpg), [botão sobreposto à caixa de busca](evidencias/botao-buscar-em-cima-da-caixa-de-busca-5.jpg) e [cabeçalho quebrado ao scrollar](evidencias/Ao-scrollar-para-baixo-o-cabecalho-fica-quebrado-6.mp4) |

---

## 4. Tarefa 3: Requisitos e características de qualidade

| Integrante | Requisito de Qualidade | Característica ou subcaracterística | Justificativa | Como avaliar |
|---|---|---|---|---|
| Mateus Zanatta Mariani | A interface da aplicação deve manter a integridade visual e funcional dos elementos de navegação (header fixo, inputs e botões) em resoluções mobile (ex: 390x844) durante a rolagem e interação | Usabilidade (Estética da interface do usuário / Adaptabilidade) | Problemas de layout quebrado, sobreposição de botões em campos de texto e ausência de espaçamento adequado impedem o uso confortável e degradam a navegabilidade do LocalEats em smartphones | Testar a interface em diferentes resoluções de tela mobile (360px a 414px de largura), verificando visualmente se há sobreposição de componentes e se todos os botões e inputs permanecem 100% clicáveis e legíveis ao rolar a página |

---

## 5. Uso de inteligência artificial

**Ferramenta utilizada:**  
Perplexity AI

**Como foi utilizada:**  
Apoio na estruturação do documento conforme o padrão do template oficial da disciplina, formatação das tabelas e alinhamento do requisito de qualidade segundo a norma ISO/IEC 25010 com base nos problemas visuais e de layout mobile observados nos testes.

**Como as respostas foram verificadas:**  
Leitura crítica e conferência manual das evidências capturadas na interface móvel do LocalEats (prints e gravação de tela) para garantir que as descrições e classificações refletem estritamente o comportamento real da aplicação.
