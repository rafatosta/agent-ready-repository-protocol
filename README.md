# Agent Ready Repository Protocol

O **Agent Ready Repository Protocol (ARRP)** é um protocolo de **migração documental para repositórios de software já existentes**. Seu objetivo é reorganizar a documentação e as instruções do projeto para que agentes de IA consigam interpretar demandas, localizar apenas o contexto necessário, implementar mudanças e validar resultados com menos repetição de instruções.

A ideia central é simples:

> O mantenedor descreve **o que deseja fazer**. O repositório migrado ensina ao agente **como trabalhar naquele projeto**.

## Escopo

O ARRP é aplicado **somente por migração**.

Ele não:

- cria novos projetos;
- funciona como gerador de aplicações;
- deve ser usado como base de fork para iniciar um produto;
- substitui um template de projeto;
- obriga um software existente a adotar uma arquitetura nova.

O protocolo parte de um repositório que já possui código e o adapta documentalmente para o trabalho com agentes.

A pasta `template/` deste repositório contém **modelos documentais usados durante a migração**. Ela não é um template de aplicação.

## Como executar

Para aplicar o ARRP, o agente deve ter acesso simultâneo ao:

1. repositório existente que será migrado;
2. repositório completo do ARRP, usado apenas como especificação.

A porta de entrada é:

```text
MIGRATION.md
```

Uma forma simples de execução é disponibilizar os dois repositórios como pastas ou ZIPs no mesmo contexto e solicitar:

```text
Execute a migração ARRP no projeto-alvo.
Comece por MIGRATION.md do repositório agent-ready-repository-protocol.
Não altere código funcional.
```

`MIGRATION.md` orienta o agente a consultar `migration/`, `template/`, `protocol/` e `examples/` conforme a necessidade. O repositório completo fica disponível, mas não deve ser lido integralmente por padrão.

Consulte [USAGE.md](USAGE.md) para o fluxo completo.

## Por que este protocolo existe?

Em projetos usados com agentes de IA, cada nova tarefa pode acabar repetindo informações como:

- arquitetura e fronteiras do sistema;
- padrões de código;
- regras de domínio;
- testes obrigatórios;
- convenções de commit;
- procedimentos de documentação;
- restrições específicas do projeto.

Esse modelo tende a produzir prompts longos, difíceis de revisar e caros para processar. Também mistura duas coisas diferentes: **a intenção da tarefa** e **as regras permanentes do repositório**.

O ARRP separa essas responsabilidades.

Depois da migração, uma solicitação pode continuar simples:

```text
Junte os três itens do menu em uma única página e organize o conteúdo em três abas.
```

O agente deve obter do próprio repositório migrado as informações necessárias sobre componentes, arquitetura, testes, documentação e commits.

## O que a migração organiza?

O protocolo define como um repositório existente pode passar a documentar:

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

O protocolo trata a documentação conforme o público:

```text
REPOSITÓRIO MIGRADO
├── documentação para agentes de IA
├── documentação para mantenedores/desenvolvedores
└── documentação para usuários
```

A documentação para agentes deve ser operacional e estruturada. A documentação para mantenedores pode registrar decisões, justificativas e histórico. A documentação para usuários deve permanecer orientada a instalação, uso e resolução de problemas.

O mesmo conhecimento não deve ser copiado integralmente em vários documentos. Quando necessário, um documento aponta para a fonte responsável.

## O `AGENTS.md` como porta de entrada

No projeto migrado, o `README.md` continua sendo voltado a pessoas.

A porta de entrada do agente passa a ser:

```text
AGENTS.md
```

O `AGENTS.md` deve ser pequeno. Sua função principal é apresentar invariantes essenciais e **rotear o agente para a documentação necessária conforme a tarefa**.

Exemplo:

```text
UI/UX              → documentação de interface
arquitetura        → documentação arquitetural
domínio            → regras e conceitos do domínio
persistência       → documentação de dados
regras normativas  → fonte normativa do projeto
testes             → estratégia de testes
commit             → convenção de commits
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
+ regras da tarefa
+ documentação de UI/UX
+ componentes afetados
+ testes relacionados
```

Não é necessário carregar inicialmente histórico do projeto, documentação de release, banco de dados ou regras de negócio sem relação com a mudança.

## Tarefas simples e compostas

Tarefas pequenas podem ser executadas diretamente. Tarefas maiores podem ser decompostas em unidades coerentes e verificáveis:

```text
[ ] 1. Reorganizar navegação
[ ] 2. Refatorar formulário
[ ] 3. Ajustar persistência
[ ] 4. Atualizar testes
[ ] 5. Atualizar documentação
```

A tarefa continua sendo uma única entrega. As subtarefas organizam execução, validação e histórico.

Uma etapa concluída e validada pode gerar um commit local. O agente continua até concluir a tarefa inteira, salvo estratégia diferente definida pelo usuário ou impedimento real.

## Política de modelos

O protocolo pode recomendar capacidades diferentes para etapas diferentes:

```text
Alteração visual localizada    → modelo leve
Implementação funcional        → modelo intermediário
Mudança arquitetural complexa  → modelo avançado
```

Essa política é **consultiva, nunca bloqueante**.

Quando uma tarefa composta exigir capacidades diferentes, o agente deve informar isso no início. O usuário pode escolher executar toda a tarefa com o modelo atual ou permitir pausas em fronteiras seguras para troca de modelo.

## Projetos com documentação em diferentes estados

A migração pode encontrar três cenários principais:

```text
documentação suficiente
→ reorganizar, deduplicar e validar

documentação parcial ou desatualizada
→ preservar, reconciliar, complementar e registrar divergências

pouca ou nenhuma documentação
→ gerar somente um baseline mínimo baseado no estado observável do repositório
```

Quando a documentação for insuficiente, o agente pode usar estrutura de diretórios, código, configuração, dependências, scripts, testes, CI/CD, rotas, schemas e relações entre módulos como evidência.

O agente deve distinguir informações **observadas**, **inferidas com alta confiança** e **não definidas**. O protocolo não deve inventar intenção, regra de domínio, convenção ou decisão arquitetural sem evidência suficiente.

## Relação entre documentação e código

Durante a migração:

- a documentação pode representar intenção, regras e histórico;
- código, testes e configuração representam o estado implementado;
- nenhum dos dois é automaticamente considerado correto quando houver conflito.

Divergências devem ser registradas e classificadas. A migração pode atualizar documentação obsoleta, mas não deve refatorar código funcional para resolver inconsistências.

## Requisitos mínimos

O ARRP pressupõe um projeto existente. Para uma migração assistida, recomenda-se:

- repositório versionado com Git;
- código-fonte identificável;
- estrutura minimamente compreensível;
- forma conhecida de executar, buildar ou validar o projeto;
- testes, quando existirem;
- documentação existente, mesmo incompleta, quando houver;
- mantenedor capaz de decidir ambiguidades relevantes.

O projeto não precisa possuir previamente `AGENTS.md`, documentação específica para IA ou arquitetura formal.

## Estrutura deste repositório

```text
agent-ready-repository-protocol/
├── README.md
├── USAGE.md
├── MIGRATION.md
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

O papel dessas áreas é diferente:

```text
MIGRATION.md → ponto de entrada
migration/   → processo de migração
template/    → modelos documentais de destino
protocol/    → contratos e princípios
examples/    → exemplos auxiliares
```

## Depois da migração

Quando a migração termina, o projeto deve se tornar autônomo. O trabalho cotidiano passa a usar o `AGENTS.md` e a documentação local do próprio repositório migrado.

O ARRP não precisa permanecer anexado às tarefas futuras. Ele volta a ser necessário apenas se o mantenedor decidir executar uma nova migração para incorporar uma evolução do protocolo.

## Princípio central

O objetivo final é substituir:

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
→ repositório migrado orienta
→ contexto necessário é recuperado
→ agente implementa
→ valida
→ documenta
→ entrega
```

Quanto melhor o repositório descreve como o trabalho deve ser realizado, menor pode ser o prompt operacional.

## Status

O protocolo está em sua primeira versão de definição e será validado por migrações em projetos reais.

Os principais pontos de observação serão:

- clareza das instruções;
- consumo de contexto;
- qualidade das implementações posteriores;
- capacidade de decomposição de tarefas;
- adequação das recomendações de modelo;
- qualidade dos commits;
- redução da necessidade de prompts extensos.