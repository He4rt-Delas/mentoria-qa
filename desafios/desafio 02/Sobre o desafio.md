# 🏗️ Desafio 02 — Plano de Qualidade para Reestruturação de Sistema Legado
> **Mentoria QA | Heart Delas 💜**

> 🎯 **Nível:** Intermediário–Avançado · Recomendado para quem já tem contato com tipos de teste, CI/CD e conceitos de qualidade de software.

Seja muito bem-vinda a mais um desafio prático da mentoria! Aqui você vai exercitar uma das habilidades mais estratégicas de uma QA: **pensar qualidade do início ao fim de um projeto**, antes mesmo da primeira linha de código ser reescrita.

🧠 **Pensamento estratégico** · 🗺️ **Planejamento de testes** · ⚙️ **Visão de CI/CD**

---

## 🎯 Objetivo

Você foi alocado como QA em um projeto **legado** com **muitas features em produção** que vai passar por uma **reestruturação completa**. O sistema é **full stack** (front-end e back-end), e a empresa **não pode perder funcionalidades** nem comprometer a experiência do usuário durante a transição.

Sua missão é elaborar o **plano de qualidade** que vai guiar essa reestruturação.

| Missão | Descrição |
|---|---|
| 🗺️ **Planejar** | Definir como garantir que o sistema reestruturado tenha as **mesmas funcionalidades** do legado. |
| 🧪 **Testar** | Definir **quais tipos de testes** serão realizados e em quais momentos. |
| 🤖 **Automatizar** | Decidir se haverá **automação** e, em caso positivo, **desenhar o esquema de CI/CD**. |

---

## 📹 Material do Desafio

- **🏛️ Cenário:** Sistema legado full stack em reestruturação completa
- **🖥️ Camadas envolvidas:**
  - **Front-end:** interface do usuário (web e/ou mobile)
  - **Back-end:** APIs, regras de negócio, banco de dados, integrações
- **🎯 Restrições do projeto:**
  - Nenhuma funcionalidade pode ser perdida
  - A experiência do usuário não pode ser comprometida
  - Bugs e regressões em produção não são aceitáveis

> 💡 **Dica:** quanto mais você considerar o contexto real (riscos, custo, prazo, time), mais robusto será seu plano!

---

## 🏢 Contexto Fictício — Sistema VidaPlus

Para tornar o desafio mais concreto, use o cenário abaixo como referência ao construir seu plano. Você pode (e deve!) adaptar suas decisões ao contexto desta empresa.

> **VidaPlus** é uma plataforma de gestão de planos de saúde com cerca de **80 mil usuários ativos** entre beneficiários, médicos e operadoras conveniadas. O sistema existe há **9 anos** e passou por várias equipes, com pouca documentação formal.
>
> **Stack atual (legado):**
> - Front-end: jQuery + templates server-side em PHP
> - Back-end: monolito PHP (Laravel 6), banco MySQL, algumas integrações via SOAP com operadoras de saúde
> - Infraestrutura: servidores on-premise, deploy manual via FTP
>
> **Stack novo (reestruturação em andamento):**
> - Front-end: React 18 + TypeScript
> - Back-end: Node.js com NestJS, banco PostgreSQL, integrações migradas para REST/GraphQL
> - Infraestrutura: AWS (ECS + RDS), CI/CD ainda a ser definido
>
> **Contexto de negócio:**
> - Funcionalidades críticas: autorização de procedimentos, emissão de guias médicas, portal do beneficiário, faturamento para operadoras
> - O sistema não pode ficar indisponível em horário comercial (8h–18h, seg–sex)
> - A migração será feita em fases, com legado e novo sistema coexistindo por até **12 meses**
> - Time: 4 devs, 1 tech lead, 1 designer, **1 QA (você)**, sem QA automatizado hoje
> - Prazo para primeira fase em produção: **6 meses**

---

## ✅ Pré-requisitos

Antes de começar, garanta que você tem:

- [ ] Conhecimento básico sobre **tipos de teste** (unitário, integração, E2E, etc.)
- [ ] Noção sobre **CI/CD** e pipelines de deploy
- [ ] Familiaridade com **ferramentas de QA** (Cypress, Playwright, Postman, etc.)
- [ ] Um editor de Markdown (VS Code, Notion, Obsidian, ou o próprio GitHub)
- [ ] Ferramenta para criar diagramas (Draw.io, Excalidraw, Miro, Lucidchart)

---

## 📋 O que você deve entregar

Você vai construir um **plano de qualidade escrito**, justificando todas as suas escolhas. Não existe uma única resposta certa — o que importa é a **clareza do raciocínio** e a **coerência com o contexto**.

### Entregáveis obrigatórios

1. 📄 **Plano de qualidade escrito**, com justificativas para cada decisão.
2. 🗺️ **Diagrama do pipeline de CI/CD** proposto.
3. 🧪 **Estratégia de testes** (o que será testado, como e em que momento).
4. 🤖 **Estratégia de automação** (o que automatizar, com quais ferramentas).
5. 📊 **Métricas e critérios** que você usará para considerar o trabalho concluído com qualidade.

---

## ❓ Perguntas-Guia para Construir Seu Plano

Use as perguntas abaixo como roteiro. Você não precisa respondê-las em ordem nem todas — elas existem para te provocar a pensar nos pontos críticos da reestruturação.

### 🔍 Sobre o entendimento do legado

- Como você vai **descobrir e mapear** todas as funcionalidades existentes hoje?
- Existe documentação confiável? Se não, com quem você vai conversar e o que vai investigar?
- Como identificar **regras de negócio implícitas** (aquelas que ninguém documentou, mas estão no código)?
- Quais funcionalidades são **mais críticas** para o negócio? Como priorizar?
- O que serve como **referência (baseline)** para dizer que o novo sistema "se comporta igual" ao antigo?

### 🧪 Sobre os tipos de teste

- Quais **níveis de teste** fazem sentido (unitário, integração, contrato, E2E, etc.)?
- Como balancear **velocidade vs. cobertura**? Onde investir mais esforço?
- Como você vai testar a **comunicação entre front-end e back-end**?
- E os **testes não-funcionais** — performance, segurança, acessibilidade, usabilidade — entram no plano?
- Vai haver **testes exploratórios e manuais**? Em que momento?
- Como tratar a **migração de dados**, se houver?

### 🤖 Sobre automação

- Você vai automatizar? **O que** vale a pena automatizar e **o que não vale**?
- Quais **ferramentas** você escolheria para cada tipo de teste? Por quê?
- Como lidar com **testes instáveis (flaky tests)**?
- Quem é responsável por **escrever e manter** os testes automatizados?
- Qual a **cobertura mínima** aceitável? Faz sentido definir um número?

### ⚙️ Sobre CI/CD

- Como seria o **fluxo de um commit até produção**?
- Quais **estágios (gates)** o pipeline precisa ter? O que cada um valida?
- O que **bloqueia um deploy**? O que apenas **alerta**?
- Como garantir **deploys seguros** (blue-green, canary, feature flags, rollback)?
- Como o pipeline trata os **diferentes ambientes** (dev, homologação, produção)?
- Que **monitoramento e observabilidade** entram em ação após o deploy?

### 🔄 Sobre estratégia de migração

- O legado e o novo sistema vão **coexistir** durante a transição? Como?
- Faz sentido migrar **tudo de uma vez** ou **por partes**? Por quê?
- Como **comparar** o comportamento do legado com o do novo sistema em tempo real?
- Qual o plano de **rollback** se algo der errado?

### 👥 Sobre processo e time

- Como o QA vai se **integrar ao time de desenvolvimento** durante a reestruturação?
- Em que momento o QA é envolvido — só no final ou desde o refinamento das histórias?
- Como definir o **"pronto" (Definition of Done)** de uma feature reestruturada?
- Quais **métricas de qualidade** você vai acompanhar para mostrar progresso e saúde do projeto?
- Quais são os **principais riscos** da reestruturação e como mitigá-los?

---

## 📚 Guia Rápido — Pirâmide de Testes

Uma referência clássica para te ajudar a balancear sua estratégia:

| Nível | Característica | Quantidade ideal |
|---|---|---|
| 🔺 **E2E** | Lentos, caros, validam fluxos completos | Poucos |
| 🔶 **Integração** | Médios, validam comunicação entre módulos | Moderados |
| 🟩 **Unitários** | Rápidos, baratos, validam unidades isoladas | Muitos |

> 💡 **Lembre-se:** a pirâmide é um guia, não uma regra. Adapte ao contexto do seu projeto!

---

## 🧠 Dicas para um plano de qualidade nota 10

- ✨ Seja **claro e objetivo** — um plano bem fundamentado vale mais do que uma lista enorme sem contexto.
- 🎯 Pense em **trade-offs**: tempo, custo, complexidade e risco.
- 📊 Use **diagramas, tabelas e fluxos** sempre que ajudarem a comunicar a ideia.
- 🧩 **Justifique cada decisão** — por que essa ferramenta? Por que esse tipo de teste? Por que essa ordem?
- 🛡️ Lembre-se: o plano serve para **reduzir riscos e dar confiança ao time** de que a reestruturação não vai quebrar o que já funciona.
- 🔄 Pense no **ciclo completo**: do commit até o monitoramento em produção.
- 🗣️ Escreva como se estivesse **apresentando para liderança técnica e de produto**.
---

## 🚫 O que evitar no seu plano

- ❌ Listar ferramentas sem justificar a escolha.
- ❌ Querer automatizar 100% de tudo (nem sempre é viável ou inteligente).
- ❌ Ignorar testes manuais e exploratórios.
- ❌ Esquecer dos **testes não-funcionais** (performance, segurança, acessibilidade).
- ❌ Plano genérico que serviria para qualquer projeto — adapte ao contexto!
- ❌ Não considerar **estratégia de migração e rollback**.




## 📤 Como entregar

1. 📁 Crie um arquivo `plano-de-qualidade.md` (ou use Notion, Confluence, Google Docs — o que preferir).
2. 🗺️ Inclua o **diagrama do pipeline de CI/CD** (pode ser imagem, link do Draw.io, Excalidraw, etc.).
3. 🧠 **Justifique** todas as decisões importantes do plano.
4. 🚀 Envie para a mentora conforme combinado no grupo.

**📅 Prazo de entrega:** *(a definir)*

---

## 💡 Desafio Bônus (opcional)

Se quiser ir além, tente:

- 🔬 Definir **métricas DORA** (deployment frequency, lead time, change failure rate, MTTR) para o projeto.
- 🐦 Pesquisar e aplicar padrões como **Strangler Fig**, **Shadow Testing** ou **Feature Flags** na sua estratégia de migração.
- ♿ Incluir uma seção dedicada à **acessibilidade** (WCAG 2.1) no plano.
- 🔐 Detalhar como **testes de segurança** (SAST, DAST, SCA) entram no pipeline.
- 📋 Criar uma **matriz de riscos** com mitigações específicas.
- 🧪 Sugerir **casos de teste** específicos para validar a paridade entre legado e novo sistema.

---

## ❓ Dúvidas?

Qualquer dúvida, **chama no grupo da mentoria** ou abre uma issue aqui no repositório! A mentora e as colegas estão aqui para te apoiar. 🤝

> **Importante:** não existe plano perfeito. O importante é **pensar criticamente** sobre o contexto e justificar suas escolhas. Cada decisão que você toma é uma oportunidade de aprendizado! 💜

---

<p align="center">
  <strong>Bora planejar qualidade, QAs! 🏗️🧪</strong><br>
  <em>Feito com 💜 pelo Heart Delas</em>
</p>