# 🤖 Desafio 03 — Automação de Testes: Decisão, Qualidade e Rastreabilidade
> **Mentoria QA | Heart Delas 💜**

> 🎯 **Nível:** Intermediário · Recomendado para quem já tem noção de testes manuais e quer dar o primeiro passo (ou melhorar) em automação de forma estratégica.

Seja muito bem-vinda a mais um desafio prático da mentoria! Desta vez você vai colocar a mão no código — mas o principal objetivo **não é sair automatizando tudo**. É aprender a **pensar antes de escrever**, tomar boas decisões de automação e construir uma suíte que seja confiável, legível e útil de verdade.

🧠 **Tomada de decisão** · 🧹 **Boas práticas de código** · ⚡ **Performance dos testes** · 📊 **Relatório de resultados**

---

## 🎯 Objetivo

Você vai trabalhar com a aplicação **Sauce Demo** — um e-commerce de demonstração criado especialmente para prática de QA:

> 🌐 **https://www.saucedemo.com/**

Sua missão é construir uma **suíte de testes automatizados** para essa aplicação, tomando decisões conscientes sobre o que automatizar, como estruturar o código e como comunicar os resultados.

| Missão | Descrição |
|---|---|
| 🗺️ **Decidir** | Analisar a aplicação e justificar **o que vale automatizar** e o que não vale. |
| 🧹 **Implementar** | Escrever os testes com **boas práticas** de código e organização. |
| ⚡ **Otimizar** | Pensar em **performance da suíte**: velocidade, estabilidade e manutenibilidade. |
| 📊 **Reportar** | Configurar um **relatório de testes** claro e útil para o time. |

---

## 🧪 Sobre a Aplicação

O **Sauce Demo** simula um e-commerce com fluxo completo de compra. Explore a aplicação antes de começar a automatizar.

### Funcionalidades disponíveis

| Área | O que existe |
|---|---|
| 🔐 **Login** | Tela de autenticação com múltiplos tipos de usuário |
| 🛍️ **Catálogo** | Listagem de produtos com ordenação e filtros |
| 📦 **Produto** | Página de detalhes de cada item |
| 🛒 **Carrinho** | Adicionar, remover e visualizar itens |
| 💳 **Checkout** | Fluxo de 3 etapas: dados, resumo e confirmação |
| 🔓 **Logout** | Encerramento de sessão |

### Usuários disponíveis para teste

A aplicação oferece diferentes usuários, cada um com um comportamento específico:

| Usuário | Senha | Comportamento |
|---|---|---|
| `standard_user` | `secret_sauce` | Fluxo normal e funcional |
| `locked_out_user` | `secret_sauce` | Bloqueado — não consegue fazer login |
| `problem_user` | `secret_sauce` | Apresenta bugs visuais e de comportamento |
| `performance_glitch_user` | `secret_sauce` | Simula lentidão no carregamento |
| `error_user` | `secret_sauce` | Apresenta erros em interações específicas |
| `visual_user` | `secret_sauce` | Apresenta problemas visuais na interface |

> 💡 Esses usuários são um convite para você pensar: **qual deles automatizar e por quê?**

---

## 🛠️ Tecnologia

Você tem **liberdade total de escolha do framework**. O que importa é a **qualidade do raciocínio e do código**, não a ferramenta.

Algumas opções populares:

| Framework | Linguagem | Bom para |
|---|---|---|
| **Playwright** | TypeScript / Python / Java | E2E moderno, robusto, nativo para CI |
| **Cypress** | JavaScript / TypeScript | DX ágil, ótima experiência local |
| **Selenium + JUnit/TestNG** | Java | Contextos enterprise |
| **Robot Framework** | Python | Legibilidade, equipes mistas |
| **WebdriverIO** | JavaScript / TypeScript | Flexibilidade e integração com Appium |

> ⚠️ **Qualquer que seja sua escolha, justifique-a.** A justificativa vale tanto quanto o código.

---

## 📋 O que você deve entregar

### Entregável 1 — Análise de Automação (documento escrito)

Antes de escrever uma linha de código, produza uma análise respondendo:

- **O que você decidiu automatizar?** Liste os cenários escolhidos.
- **Por que esses cenários?** Justifique com base em risco, frequência de uso, estabilidade, etc.
- **O que você decidiu NÃO automatizar?** E por quê? Essa parte é tão importante quanto a anterior.
- **Qual framework você escolheu?** E por que ele faz sentido para esse contexto?

> 📝 Pode ser um arquivo `analise.md`, uma seção no README, ou qualquer formato de texto.

---

### Entregável 2 — Suíte de Testes Automatizados

Implemente os testes seguindo as práticas listadas na seção de critérios de avaliação. No mínimo, sua suíte deve cobrir:

#### Cenários obrigatórios

- [ ] Login com credenciais válidas (`standard_user`)
- [ ] Login com usuário bloqueado (`locked_out_user`) — deve validar a mensagem de erro
- [ ] Adicionar produto ao carrinho e verificar o item no carrinho
- [ ] Fluxo completo de checkout (do login até a tela de confirmação)
- [ ] Logout

#### Cenários opcionais (bônus)

- [ ] Ordenação de produtos (ex: por preço)
- [ ] Remover item do carrinho
- [ ] Verificar que o `problem_user` apresenta comportamento inconsistente
- [ ] Validação de campos obrigatórios no checkout

---

### Entregável 3 — Relatório de Testes

Configure sua suíte para **gerar um relatório** ao final da execução. O relatório deve deixar claro:

- Quantos testes passaram e quantos falharam
- Qual foi o tempo total de execução
- Em caso de falha: qual foi o erro e em qual teste ocorreu

> 💡 Exemplos de ferramentas: **Allure Report**, **HTML Reporter nativo do Playwright/Cypress**, **Extent Reports**, **Mochawesome**, etc. Escolha uma e configure.

---

## ✅ Critérios de Avaliação

Esta seção é o coração do desafio. Cada item representa uma prática real de mercado.

### 🧠 Tomada de Decisão (o que automatizar)

- [ ] A análise justifica os cenários escolhidos com base em risco e valor de negócio.
- [ ] Há uma explicação honesta sobre o que foi deixado de fora e por quê.
- [ ] A escolha do framework é justificada (não apenas "porque eu já conhecia").

### 🧹 Boas Práticas de Código

- [ ] Uso de **Page Object Model (POM)** ou padrão equivalente de abstração de UI.
- [ ] Nomes de testes e métodos **claros e descritivos** (quem lê sabe o que o teste valida).
- [ ] Sem seletores frágeis: preferência por `data-testid`, `aria-label`, `role` em vez de XPaths longos ou classes CSS voláteis.
- [ ] Sem dados hardcoded espalhados: credenciais, URLs e textos esperados centralizados (arquivo de config, constantes, fixtures).
- [ ] Ausência de duplicação: lógica repetida está abstraída em helpers ou métodos reutilizáveis.
- [ ] Estrutura de pastas organizada e coerente.

### ⚡ Performance e Estabilidade dos Testes

- [ ] Sem `sleep` ou `wait` fixos desnecessários — uso de waits inteligentes (espera por elemento, por estado, por rede).
- [ ] Cada teste é **independente**: não depende de outro teste ter executado antes.
- [ ] Estado limpo a cada teste: login e setup feitos no próprio teste ou em hooks (`beforeEach`/`afterEach`).
- [ ] Se o framework suportar, testes configurados para **rodar em paralelo** (pelo menos comentado/documentado como fazer).

### 📊 Relatório de Testes

- [ ] Relatório configurado e gerado com a execução dos testes.
- [ ] O relatório mostra resultado por teste (passou/falhou), tempo de execução e mensagem de erro quando aplicável.
- [ ] Instruções no README de como gerar o relatório localmente.

---

## ❓ Perguntas-Guia para sua Análise

Use essas perguntas para pensar antes de codar:

### 🔍 Sobre o que automatizar

- Quais funcionalidades têm **maior risco** se pararem de funcionar?
- Quais fluxos um usuário real **executa com mais frequência**?
- Quais testes seriam **chatos ou lentos de executar manualmente** toda vez?
- Há cenários que são **instáveis ou difíceis de reproduzir** automaticamente? Vale a pena tentar?
- O que é mais **eficaz testar manualmente** do que automatizar?

### 🧹 Sobre boas práticas

- Se outro QA precisasse **manter esse código amanhã**, ele entenderia sem explicação?
- Os seletores que você usou **quebrariam com uma mudança de CSS**? Existe uma alternativa mais estável?
- Você consegue **rodar qualquer teste isoladamente** sem que ele falhe por depender de outro?

### ⚡ Sobre performance

- Sua suíte demora mais do que o necessário por causa de **esperas desnecessárias**?
- Os testes são **independentes** o suficiente para rodar em paralelo?
- Se um teste falha no meio, o **próximo começa limpo** ou herda um estado indesejado?

### 📊 Sobre o relatório

- Quem vai **consumir esse relatório**? Um dev? Um gestor? O próprio QA?
- Em caso de falha, o relatório dá **informação suficiente para investigar** sem precisar reexecutar?

---

## 🚫 O que evitar

- ❌ Automatizar **tudo** sem critério — cobertura não é qualidade.
- ❌ Testes que **dependem de outros** para funcionar (ordem de execução frágil).
- ❌ `sleep(3000)` em vez de **waits inteligentes**.
- ❌ Seletores frágeis como `/html/body/div[2]/div/form/input[1]`.
- ❌ Credenciais e URLs escritas diretamente nos testes sem centralização.
- ❌ Relatório inexistente ou sem informação útil em caso de falha.
- ❌ README sem instruções de como **instalar e executar** os testes.

---

## 📁 Estrutura sugerida de entrega

```
meu-projeto-automacao/
├── README.md               ← Como instalar, rodar e gerar o relatório
├── analise.md              ← Sua análise: o que automatizar e por quê
├── package.json / pom.xml  ← Dependências do projeto
├── playwright.config.ts    ← (ou equivalente do seu framework)
├── tests/
│   ├── login.spec.ts
│   ├── cart.spec.ts
│   └── checkout.spec.ts
├── pages/                  ← Page Objects
│   ├── LoginPage.ts
│   ├── InventoryPage.ts
│   └── CheckoutPage.ts
├── fixtures/ ou data/      ← Dados de teste centralizados
└── reports/                ← Relatórios gerados (pode estar no .gitignore)
```

> 💡 Adapte a estrutura ao seu framework — o que importa é que esteja **organizada e com sentido**.

---

## 📤 Como entregar

1. 📁 Suba o projeto em um repositório público no **GitHub**.
2. 📄 Inclua um **README.md** com:
   - Como instalar as dependências
   - Como executar os testes
   - Como gerar o relatório
3. 📝 Inclua o arquivo de **análise** (o que automatizar e por quê).
4. 🚀 Envie o link do repositório para a mentora conforme combinado no grupo.

**📅 Prazo de entrega:** *(a definir)*

---

## 💡 Desafio Bônus (opcional)

Se quiser ir além:

- 🔄 Configure os testes para rodar em um pipeline de **CI/CD** (GitHub Actions, por exemplo).
- 📸 Configure **screenshots automáticos em caso de falha**.
- 🎥 Configure **gravação de vídeo** dos testes (Playwright e Cypress suportam nativamente).
- 🔁 Implemente **retry automático** para testes instáveis e documente o porquê.
- ♿ Adicione uma verificação básica de **acessibilidade** (ex: com `axe-core`).
- 🧹 Configure um **linter** (ESLint, Checkstyle) e **formatador** (Prettier) no projeto.

---

## ❓ Dúvidas?

Qualquer dúvida, **chama no grupo da mentoria** ou abre uma issue aqui no repositório! A mentora e as colegas estão aqui para te apoiar. 🤝

> **Lembre-se:** o objetivo deste desafio não é escrever o maior número de testes. É escrever os **testes certos, da forma certa, com resultado visível**. Uma suíte pequena e bem feita vale mais do que cem testes frágeis. 💜

---

<p align="center">
  <strong>Bora automatizar com intenção, QAs! 🤖🧪</strong><br>
  <em>Feito com 💜 pelo Heart Delas</em>
</p>
