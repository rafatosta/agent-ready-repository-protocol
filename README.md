# Agent Ready Repository Protocol

O **Agent Ready Repository Protocol (ARRP)** é um protocolo para organizar repositórios de software de forma que agentes de IA consigam interpretar demandas, localizar apenas o contexto necessário, implementar mudanças e validar o resultado com menos repetição de instruções.

A ideia central é simples:

> O mantenedor descreve **o que deseja fazer**. O repositório ensina ao agente **como trabalhar naquele projeto**.

O protocolo não tenta substituir engenharia de software, testes, revisão humana ou documentação tradicional. Ele organiza essas informações para que agentes de IA não dependam de prompts extensos repetindo arquitetura, convenções, testes, commits e regras permanentes do projeto.

## Por que este protocolo existe?

Em projetos usados com agentes de IA, é comum que cada nova tarefa repita informações como:

- arquitetura e fronteiras do sistema;
- padrões de código;
- regras de domínio;
- testes obrigatórios;
- convenções de commit;
- procedimentos de documentação;
- restrições específicas do projeto.

Esse modelo tende a produzir prompts longos, difíceis de revisar e caros para processar. Também mistura duas coisas diferentes: **a intenção da tarefa** e **as regras permanentes do repositório**.

O ARRP separa essas responsabilidades.

Uma solicitação simples pode continuar simples:

```text
Junte os três itens do menu em uma única página e organize o conteúdo em três abas.
```

O agente deve obter do próprio repositório as informações necessárias sobre componentes, arquitetura, testes, documentação e commits.

## O que o protocolo organiza?

O protocolo define como um projeto pode documentar:

1. a porta de entrada do agente;
2. o contexto mínimo do projeto;
3. como interpretar uma tarefa;
4. como selecionar documentação sob demanda;
5. como decompor tarefas compostas;
6. como recomendar capacidade/modelo sem bloquear a execução;
7. como validar alterações proporcionalmente;
8. como criar commits locais por unidade lógica;
9. como atualizar documentação e changelog;
10. como separar documentação de IA, mantenedores e usuários.

## Três públicos diferentes

O protocolo trata a documentação conforme o público.

```text
REPOSITÓRIO
├── documentação para agentes de IA
├── documentação para mantenedores/desenvolvedores
└── documentação para usuários
```

### Agentes de IA

Precisam de instruções operacionais, diretas e estruturadas: regras permanentes, mapa de contexto, arquitetura, domínio, workflow e critérios de validação.

### Mantenedores e desenvolvedores

Precisam de contexto técnico, justificativas, decisões arquiteturais, processo de contribuição, releases e histórico do projeto.

### Usuários

Precisam entender o que o software faz, como instalar, usar e resolver problemas comuns.

O mesmo conhecimento não deve ser copiado integralmente em vários documentos. Quando necessário, um documento aponta para a fonte responsável.

## O README não é a porta de entrada do agente

Neste protocolo, o `README.md` é um documento para pessoas.

A porta de entrada do agente é:

```text
AGENTS.md
```

O `AGENTS.md` deve ser pequeno. Sua função principal é apresentar invariantes e **rotear o agente para a documentação necessária conforme a tarefa**.

Exemplo:

```text
UI/UX              → docs/ai/ux ou documentação equivalente
arquitetura        → docs/ai/architecture.md
domínio            → docs/ai/domain.md
persistência       → documentação de dados
regras normativas  → documentação normativa
testes             → docs/ai/testing.md
commit              → docs/ai/commit-convention.md
```

Nem todo projeto terá os mesmos documentos. O importante é tornar explícito onde cada tipo de informação está.

## Contexto mínimo suficiente

Um princípio fundamental do ARRP é:

> Ter documentação disponível não significa carregar toda a documentação.

O agente deve iniciar com pouco contexto, classificar a tarefa e ampliar a leitura apenas quando necessário.

Exemplo:

```text
Tarefa: alterar a disposição de três botões.

Contexto provável:
AGENTS.md
+ regras de tarefa
+ documentação de UI/UX
+ componentes afetados
+ testes relacionados
```

Não é necessário carregar inicialmente histórico do projeto, documentação de release, banco de dados ou regras de negócio sem relação com a mudança.

## Como uma tarefa é interpretada?

O protocolo não exige prompts rígidos.

O usuário pode escrever naturalmente:

```text
Melhore esta tela para funcionar melhor no celular.
```

O agente deve estruturar a demanda internamente, quando aplicável, em pontos como:

- objetivo;
- problema;
- escopo;
- restrições;
- dependências;
- critérios de conclusão.

Esses campos não precisam ser preenchidos manualmente pelo usuário. O agente deve obtê-los da solicitação, do repositório e da documentação vigente. Se uma decisão indispensável continuar ambígua, ela deve ser levada ao mantenedor.

## Tarefas simples e tarefas compostas

Tarefas pequenas podem ser executadas diretamente.

Tarefas maiores podem ser decompostas em unidades coerentes e verificáveis:

```text
[ ] 1. Reorganizar navegação
[ ] 2. Refatorar formulário
[ ] 3. Ajustar persistência
[ ] 4. Atualizar testes
[ ] 5. Atualizar documentação
```

A tarefa continua sendo uma única entrega. As subtarefas servem para organizar execução, validação e histórico.

Por padrão, uma etapa concluída e validada pode gerar um commit local. O agente continua até concluir a tarefa inteira, salvo impedimento real ou estratégia diferente definida pelo usuário.

## Política de modelos

O protocolo pode recomendar capacidades diferentes para etapas diferentes.

Exemplo:

```text
Alteração visual localizada    → modelo leve
Implementação funcional        → modelo intermediário
Mudança arquitetural complexa  → modelo avançado
```

Essa política é **consultiva, nunca bloqueante**.

Quando uma tarefa composta exigir capacidades diferentes, o agente deve informar isso no início. O usuário pode escolher entre:

- executar toda a tarefa com o modelo atual; ou
- permitir pausas em fronteiras seguras para troca de modelo.

Se o modelo atual for superior ao necessário, ele continua sendo válido, embora possa representar maior custo.

## Requisitos mínimos

O protocolo pode ser adotado em projetos novos ou existentes. Para uma migração, recomenda-se:

- repositório versionado com Git;
- código-fonte identificável;
- estrutura minimamente compreensível;
- forma conhecida de executar/buildar o projeto;
- testes, quando existentes;
- documentação existente, mesmo incompleta;
- mantenedor capaz de decidir ambiguidades relevantes.

O projeto não precisa possuir previamente `AGENTS.md`, documentação específica para IA ou arquitetura perfeitamente documentada.

## Como aplicar em um projeto existente?

O fluxo geral é:

```text
Projeto existente
      ↓
auditoria documental
      ↓
identificação de regras permanentes
      ↓
separação por público
      ↓
criação/ajuste do AGENTS.md
      ↓
criação da documentação para IA
      ↓
remoção de redundâncias
      ↓
separação entre estado atual e histórico
      ↓
validação de referências
      ↓
projeto preparado para agentes
```

A migração deve ser **documental**. O agente pode ler o código para verificar a realidade do projeto, mas não deve transformar a adoção do protocolo em uma refatoração funcional. Divergências encontradas entre documentação e implementação devem ser registradas para decisão do mantenedor.

## Estrutura deste repositório

```text
agent-ready-repository-protocol/
├── README.md
├── CHANGELOG.md
├── AGENTS.md
├── protocol/
│   ├── overview.md
│   ├── principles.md
│   ├── repository-structure.md
│   ├── task-lifecycle.md
│   ├── context-strategy.md
│   ├── model-policy.md
│   ├── commit-policy.md
│   └── documentation-policy.md
├── template/
│   ├── AGENTS.md
│   └── docs/
│       ├── ai/
│       ├── maintainers/
│       └── user/
├── migration/
│   ├── prerequisites.md
│   ├── audit-checklist.md
│   ├── migration-plan.md
│   └── migration-prompt.md
└── examples/
    ├── simple-task.md
    ├── composite-task.md
    ├── multi-model-task.md
    └── documentation-migration.md
```

## O que o protocolo não pretende fazer?

O ARRP não pretende:

- criar uma linguagem rígida de prompts;
- obrigar um modelo específico de IA;
- fazer o agente ler toda a documentação antes de cada tarefa;
- substituir testes ou revisão;
- eliminar decisões humanas em situações ambíguas;
- autorizar automaticamente push, merge, release ou deploy;
- impor a mesma quantidade de documentação a todos os projetos.

O protocolo deve ser proporcional ao projeto.

## Princípio central

O objetivo final é substituir este fluxo:

```text
prompt detalhado
→ explica arquitetura
→ explica convenções
→ explica testes
→ explica documentação
→ explica commits
→ explica a tarefa
→ agente executa
```

por:

```text
solicitação
→ agente interpreta
→ repositório orienta
→ contexto necessário é recuperado
→ agente implementa
→ valida
→ documenta
→ entrega
```

Quanto melhor o repositório descreve como o trabalho deve ser realizado, menor pode ser o prompt operacional.

## Status

O protocolo está em sua primeira versão de definição e será validado progressivamente em projetos reais.

Os principais pontos de observação serão:

- clareza das instruções;
- consumo de contexto;
- qualidade das implementações;
- capacidade de decomposição de tarefas;
- adequação das recomendações de modelo;
- qualidade dos commits;
- redução da necessidade de prompts extensos.
