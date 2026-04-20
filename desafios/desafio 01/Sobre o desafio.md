# 🐛 Desafio 01 — Caça ao Bug!

> **Mentoria QA | Heart Delas 💜**

Seja muito bem-vinda ao seu **primeiro desafio prático** da mentoria! Aqui você vai colocar a mão na massa e treinar três habilidades essenciais para qualquer QA:

🔍 **Observação** · 🔁 **Reprodução de bugs** · ✍️ **Escrita de reports claros e objetivos**

---

## 🎯 Objetivo

Você vai analisar um **vídeo com um bug real encontrado no LinkedIn** e, a partir dele, cumprir três missões:

| Missão | Descrição |
|---|---|
| 👀 **Observar** | Assistir ao vídeo com atenção e identificar **todos** os problemas visíveis (nem sempre o bug mais óbvio é o único!). |
| 🧪 **Reproduzir** | Tentar replicar o bug na sua conta do LinkedIn (web e/ou mobile). |
| 📝 **Reportar** | Documentar os bugs encontrados em um relatório profissional seguindo o template. |

---

## 📹 Material do Desafio

- **🎥 Vídeo do bug:** [Linkedin bug.mp4](https://github.com/He4rt-Delas/mentoria-qa/blob/desafio-01/desafios/desafio%2001/Linkedin%20bug.mp4)
- **🌐 Plataforma afetada:** LinkedIn
- **🖥️ Ambientes sugeridos para teste:**
  - **Desktop:** Chrome, Firefox, Safari ou Edge
  - **Mobile:** App LinkedIn no iOS e/ou Android
  - **Bônus:** teste em diferentes resoluções e navegação anônima 🚀

> 💡 **Dica:** quanto mais ambientes você testar, mais rica será sua análise!

---

## ✅ Pré-requisitos

Antes de começar, garanta que você tem:

- [ ] Uma conta ativa no LinkedIn
- [ ] Acesso a pelo menos **dois ambientes** de teste (ex: desktop + mobile)
- [ ] Ferramenta para capturar **prints e/ou vídeos** (ex: Lightshot, ShareX, Loom, gravador nativo do celular)
- [ ] Um editor de Markdown (VS Code, Notion, Obsidian, ou até o próprio GitHub)

---

## 📋 O que você deve entregar

### 1. Relatório de Bug(s)

Para **cada bug encontrado**, preencha o template abaixo. Lembre-se: **um bug = um report**.

```markdown
### 🐞 Bug #[número] — [Título curto e descritivo]

- **Severidade:** [Crítica / Alta / Média / Baixa]
- **Prioridade:** [Alta / Média / Baixa]
- **Ambiente:**
  - Dispositivo: [ex: Desktop / iPhone 14 / Galaxy S22]
  - Sistema Operacional: [ex: Windows 11 / macOS 14 / iOS 17]
  - Navegador/App: [ex: Chrome 120 / LinkedIn App v9.X]
  - Versão/Build: [se aplicável]

#### 📝 Descrição
[Explicação clara e objetiva do problema encontrado.]

#### 🔁 Passos para Reproduzir
1. [Passo 1]
2. [Passo 2]
3. [Passo 3]

#### ✅ Resultado Esperado
[O que deveria acontecer.]

#### ❌ Resultado Obtido
[O que está acontecendo de errado.]

#### 📎 Evidências
[Prints, GIFs, vídeos ou logs que comprovem o bug.]

#### 💡 Observações Adicionais
[Hipóteses, padrões identificados, workarounds, etc.]
```

### 2. Status de Reprodutibilidade

Indique claramente o resultado da sua tentativa de reprodução:

- [ ] ✅ **Consegui reproduzir o bug** — descreva o cenário exato.
- [ ] ❌ **Não consegui reproduzir** — descreva o que você tentou e o que observou de diferente.
- [ ] ⚠️ **Reproduzi parcialmente** — explique o que funcionou e o que não.

---

## 📚 Guia Rápido — Severidade x Prioridade

Uma confusão comum entre QAs iniciantes! Use esta referência:

| Severidade | Quando usar |
|---|---|
| 🔴 **Crítica** | Sistema fora do ar, perda de dados, falha de segurança. |
| 🟠 **Alta** | Funcionalidade principal quebrada, sem workaround. |
| 🟡 **Média** | Funcionalidade secundária quebrada ou com workaround. |
| 🟢 **Baixa** | Problemas visuais, typos, melhorias pontuais. |

| Prioridade | Quando usar |
|---|---|
| 🔥 **Alta** | Precisa ser corrigido imediatamente. |
| ⏳ **Média** | Corrigir na próxima sprint/release. |
| 🕰️ **Baixa** | Pode entrar no backlog. |

> 💡 **Lembre-se:** um bug pode ser de **alta severidade** mas **baixa prioridade** (e vice-versa)!

---

## 🧪 Dicas para um report de QA nota 10

- ✨ Seja **objetiva e clara** — evite ambiguidades e achismos.
- 🧠 Use **linguagem técnica neutra**, sem suposições pessoais (ex: "acho que", "parece que").
- 📸 **Sempre anexe evidências** — prints, vídeos, logs do console do navegador (F12 → Console).
- 🌐 Teste em **mais de um ambiente** e anote onde o bug aparece e onde não aparece.
- 🔄 Verifique se o bug é **consistente** (acontece sempre?) ou **intermitente**.
- 🔍 Preste atenção em detalhes: mensagens de erro, comportamento da UI, performance, responsividade.
- 🧩 Pense em **cenários alternativos**: e se eu estiver deslogada? E com internet lenta? E em outro idioma?
- 🗣️ Escreva os passos como se estivesse **ensinando alguém que nunca usou o produto**.

---

## 🚫 O que evitar no seu report

- ❌ Títulos vagos como "não funciona" ou "bug no LinkedIn".
- ❌ Passos incompletos ou que pulam etapas.
- ❌ Reports sem evidência.
- ❌ Opiniões pessoais ("isso está horrível", "o dev é ruim").
- ❌ Misturar múltiplos bugs em um único report.

---

## 📊 Critérios de Avaliação

| Critério | Peso |
|---|---|
| 🎯 Identificação correta dos bugs no vídeo | **25%** |
| ✍️ Qualidade e clareza do report | **25%** |
| 🔁 Capacidade de reproduzir o bug | **20%** |
| 📎 Evidências coletadas | **15%** |
| 💡 Observações técnicas e hipóteses | **15%** |

---

## 📤 Como entregar

1. 📁 Crie um arquivo `report.md` (ou use Jira / Trello / Notion — o que preferir).
2. 🐞 Inclua **todos os bugs identificados** seguindo o template.
3. 📸 Anexe suas evidências (prints, vídeos, logs).
4. 🚀 Envie para a mentora conforme combinado no grupo.

**📅 Prazo de entrega:** *(a definir)*

---

## 💡 Desafio Bônus (opcional)

Se quiser ir além, tente:

- 🔬 Inspecionar o **console do navegador** (F12) e capturar erros de JS ou requisições quebradas.
- 📱 Comparar o comportamento entre **web e mobile**.
- 🎨 Identificar possíveis problemas de **acessibilidade** (contraste, leitor de tela, navegação por teclado).
- 🧪 Sugerir **casos de teste** que poderiam ter pegado esse bug antes do deploy.

---

## ❓ Dúvidas?

Qualquer dúvida, **chama no grupo da mentoria** ou abre uma issue aqui no repositório! A mentora e as colegas estão aqui para te apoiar. 🤝

> **Importante:** não tenha medo de errar. Errar faz parte do processo e cada bug que você encontra é uma vitória! 💜

---

<p align="center">
  <strong>Boa sorte, QAs! 🕵️‍♀️🔍</strong><br>
  <em>Feito com 💜 pelo Heart Delas</em>
</p>
