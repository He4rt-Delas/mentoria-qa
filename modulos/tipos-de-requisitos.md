# Tipos de Requisitos de Software

## Introdução

Requisitos são a base de qualquer projeto de software. Eles descrevem **o que** o sistema deve fazer e **como** deve se comportar. Para um profissional de QA, entender profundamente os requisitos é fundamental — afinal, é impossível testar algo sem saber o que se espera que funcione.

---

## Por que um QA precisa entender sobre Requisitos?

Um QA que domina requisitos é capaz de:

- **Criar casos de teste mais precisos**, baseados no que realmente foi especificado
- **Identificar ambiguidades** antes do desenvolvimento, evitando retrabalho
- **Priorizar o que testar** de acordo com o impacto de cada requisito no negócio
- **Questionar funcionalidades** que não estão claras ou que parecem incompletas
- **Rastrear defeitos** diretamente ao requisito que foi violado
- **Participar ativamente** nas cerimônias de refinamento e planejamento

> Um QA que só testa "o que foi feito" sem entender "o que deveria ser feito" testa de forma incompleta. O requisito é o contrato entre o negócio e o time de desenvolvimento — e o QA é o guardião desse contrato.

---

## 1. Requisitos Funcionais

### O que são
Descrevem **o que o sistema deve fazer** — as funcionalidades, comportamentos e ações que o software precisa executar.

### Características
- Orientados a comportamento e ação
- Diretamente testáveis
- Respondem à pergunta: *"O sistema faz o quê?"*

### Importância para o QA
São a base principal dos casos de teste. Cada requisito funcional deve gerar ao menos um caso de teste positivo (caminho feliz) e um negativo (caminho alternativo ou de erro).

### Exemplos Práticos

**Exemplo 1 — Sistema de login:**
```
RF-01: O sistema deve permitir que o usuário faça login
       com e-mail e senha cadastrados.

RF-02: O sistema deve bloquear o acesso após 5 tentativas
       de login incorretas consecutivas.
```

**Casos de teste derivados do RF-02:**
```
CT-01: Realizar 5 tentativas com senha errada → conta deve ser bloqueada
CT-02: Realizar 4 tentativas erradas e 1 correta → login bem-sucedido, sem bloqueio
CT-03: Tentar login após bloqueio → mensagem de erro deve ser exibida
```

**Exemplo 2 — E-commerce:**
```
RF-10: O sistema deve calcular o frete com base no CEP
       informado pelo usuário.

RF-11: O frete grátis deve ser aplicado automaticamente
       para compras acima de R$150,00.
```

---

## 2. Requisitos Não Funcionais

### O que são
Descrevem **como o sistema deve se comportar** — qualidade, desempenho, segurança, disponibilidade e restrições técnicas.

### Características
- Orientados a qualidade e restrições
- Mais difíceis de testar, mas igualmente críticos
- Respondem à pergunta: *"Com que qualidade o sistema faz?"*

### Importância para o QA
São frequentemente negligenciados, mas são responsáveis por grande parte das falhas em produção. O QA deve garantir que requisitos de performance, segurança e disponibilidade sejam validados antes do go-live.

### Subtipos comuns

| Subtipo         | Descrição                                      |
|-----------------|------------------------------------------------|
| Performance     | Velocidade, tempo de resposta, throughput      |
| Disponibilidade | Uptime, tolerância a falhas                    |
| Segurança       | Autenticação, criptografia, controle de acesso |
| Usabilidade     | Facilidade de uso, acessibilidade              |
| Escalabilidade  | Capacidade de crescer com a demanda            |
| Manutenibilidade| Facilidade de manutenção e evolução            |

### Exemplos Práticos

```
RNF-01 (Performance): A página inicial deve carregar em menos de 3 segundos
                       para 95% dos acessos.

RNF-02 (Disponibilidade): O sistema deve ter disponibilidade de 99,9%
                           (máximo de ~8h de indisponibilidade por ano).

RNF-03 (Segurança): Todas as senhas devem ser armazenadas com hash
                    utilizando bcrypt com salt.

RNF-04 (Usabilidade): O sistema deve ser acessível conforme WCAG 2.1 nível AA.
```

**Teste derivado do RNF-01:**
```
Ferramenta: k6 / Lighthouse
Cenário: Simular 500 usuários simultâneos acessando a homepage
Critério de aceite: p95 do tempo de resposta ≤ 3000ms
```

---

## 3. Requisitos de Negócio

### O que são
Descrevem **os objetivos e necessidades estratégicas** da organização que motivam o desenvolvimento do sistema. São de alto nível e orientados ao resultado de negócio.

### Características
- Escritos do ponto de vista do negócio, não da tecnologia
- Servem como base para os requisitos funcionais
- Respondem à pergunta: *"Por que estamos construindo isso?"*

### Importância para o QA
Permitem ao QA entender o **impacto real** de um bug. Um defeito em uma funcionalidade crítica para o negócio tem prioridade máxima. Sem entender os requisitos de negócio, o QA pode gastar energia testando o que tem menos importância.

### Exemplos Práticos

```
RN-01: Aumentar em 20% a taxa de conversão de visitantes
       em compradores no próximo trimestre.

RN-02: Reduzir o tempo médio de atendimento ao cliente
       de 10 minutos para 5 minutos.

RN-03: Expandir as operações para o mercado europeu,
       garantindo conformidade com o GDPR.
```

**Como o QA usa isso:**
> O RN-01 sinaliza que o fluxo de checkout é crítico. Qualquer bug nesse fluxo tem impacto direto no objetivo de negócio — portanto, deve ser testado com maior profundidade e prioridade.

---

## 4. Requisitos de Usuário

### O que são
Descrevem **o que os usuários esperam conseguir** ao utilizar o sistema. Geralmente escritos em linguagem natural, do ponto de vista do usuário final.

### Características
- Escritos em linguagem simples, sem jargão técnico
- Frequentemente expressos como histórias de usuário (User Stories)
- Respondem à pergunta: *"O que o usuário quer fazer?"*

### Importância para o QA
Ajudam o QA a criar testes sob a perspectiva do usuário, garantindo que o sistema realmente resolve o problema de quem vai usá-lo — não apenas que ele "funciona tecnicamente".

### Exemplos Práticos

**Formato de User Story:**
```
Como [tipo de usuário]
Quero [ação/funcionalidade]
Para [benefício/objetivo]
```

```
US-01: Como cliente,
       quero salvar meus endereços de entrega
       para não precisar digitá-los a cada compra.

US-02: Como gestor,
       quero visualizar um relatório de vendas mensais
       para acompanhar o desempenho da equipe.

US-03: Como usuário,
       quero receber notificações sobre o status do meu pedido
       para saber quando ele será entregue.
```

**Critérios de aceite derivados do US-01:**
```
- O usuário pode adicionar até 5 endereços
- O usuário pode definir um endereço como padrão
- O usuário pode editar e excluir endereços salvos
- Os endereços aparecem como opção no checkout
```

---

## 5. Requisitos de Sistema

### O que são
Descrevem as **especificações técnicas detalhadas** do sistema, incluindo comportamentos, regras de negócio, integrações e restrições de implementação.

### Características
- Mais detalhados e técnicos que os requisitos de usuário
- Incluem restrições de tecnologia, integrações e ambientes
- Respondem à pergunta: *"Como o sistema deve funcionar internamente?"*

### Importância para o QA
São essenciais para criar testes de integração e garantir que as regras de negócio mais específicas foram implementadas corretamente.

### Exemplos Práticos

```
RS-01: O sistema deve integrar com a API dos Correios (v2)
       para calcular o prazo e o valor do frete.

RS-02: O banco de dados deve suportar PostgreSQL 14 ou superior.

RS-03: O sistema deve processar no máximo 1.000 transações
       por segundo sem degradação de performance.

RS-04: Logs de auditoria devem ser gerados para todas as
       operações de criação, edição e exclusão de registros.
```

---

## 6. Regras de Negócio

### O que são
São **políticas, condições ou restrições** que definem ou restringem algum aspecto do comportamento do sistema, derivadas de decisões do negócio.

### Características
- Definem condições específicas para ações do sistema
- Mudam conforme o negócio evolui
- São fontes frequentes de bugs quando não documentadas

### Importância para o QA
Regras de negócio mal interpretadas são uma das principais causas de defeitos. O QA deve garantir que todas as regras foram implementadas corretamente — especialmente as condicionais (se/então).

### Exemplos Práticos

```
RGN-01: Clientes com plano Premium têm 15% de desconto
        em todas as compras acima de R$200,00.

RGN-02: Pedidos realizados após as 18h são despachados
        apenas no próximo dia útil.

RGN-03: O CPF deve ser único por cadastro no sistema.

RGN-04: Menores de 18 anos não podem finalizar
        compras sem autorização de um responsável.
```

**Testes derivados do RGN-01:**
```
CT-01: Cliente Premium + compra de R$200,00 → desconto de 15% aplicado ✅
CT-02: Cliente Premium + compra de R$199,99 → desconto NÃO aplicado ✅
CT-03: Cliente Standard + compra de R$300,00 → desconto NÃO aplicado ✅
CT-04: Cliente Premium + compra de R$500,00 → desconto de 15% aplicado ✅
```

---

## Resumo: Tipos de Requisitos

| Tipo                    | Foco                            | Exemplo resumido                              |
|-------------------------|---------------------------------|-----------------------------------------------|
| Funcional               | O que o sistema faz             | "Permitir login com e-mail e senha"           |
| Não Funcional           | Como o sistema se comporta      | "Responder em menos de 3 segundos"            |
| De Negócio              | Por que estamos construindo     | "Aumentar conversão em 20%"                   |
| De Usuário              | O que o usuário quer fazer      | "Salvar endereços para reuso"                 |
| De Sistema              | Especificações técnicas         | "Integrar com API dos Correios v2"            |
| Regras de Negócio       | Condições e restrições          | "Desconto só acima de R$200 para Premium"     |

---

## Boas Práticas para o QA ao Lidar com Requisitos

1. **Leia os requisitos antes de qualquer teste** — não assuma o comportamento esperado
2. **Questione requisitos ambíguos** — "deve funcionar em mobile" não é um requisito testável
3. **Rastreie seus testes aos requisitos** — cada caso de teste deve ter uma origem
4. **Identifique requisitos ausentes** — o que não está documentado também pode causar bugs
5. **Participe do refinamento** — quanto mais cedo o QA entender o requisito, mais cedo pode encontrar problemas

> **Lembre-se:** Um bom QA não é apenas quem encontra bugs — é quem previne que eles cheguem à produção. E isso começa muito antes do código ser escrito: começa na leitura e compreensão dos requisitos.