# Executar migração ARRP

Este arquivo é a **porta de entrada operacional** do Agent Ready Repository Protocol (ARRP).

O ARRP existe exclusivamente para **migrar repositórios de software já existentes** para uma estrutura documental preparada para agentes de IA. Ele não é um template para iniciar projetos, não deve ser usado como base de fork e não cria aplicações novas.

## O que fornecer ao agente

O agente precisa ter acesso simultâneo a dois conjuntos de arquivos:

1. **o repositório-alvo**, que será migrado;
2. **o repositório completo do ARRP**, usado somente como especificação da migração.

A forma mais simples é fornecer os dois repositórios como pastas ou arquivos ZIP no mesmo contexto de trabalho.

Exemplo conceitual:

```text
/contexto
├── projeto-alvo/
│   └── ...
└── agent-ready-repository-protocol/
    ├── MIGRATION.md
    ├── protocol/
    ├── template/
    ├── migration/
    └── examples/
```

O ARRP é somente referência. **Todas as alterações da migração devem ocorrer no repositório-alvo.**

## Comando de entrada

Depois de disponibilizar os dois repositórios ao agente, a instrução pode ser curta:

```text
Execute a migração ARRP no projeto-alvo.
Comece por MIGRATION.md do repositório agent-ready-repository-protocol.
Não altere código funcional.
```

## Fluxo obrigatório

Ao receber essa instrução, o agente deve:

1. identificar inequivocamente qual pasta/repositório é o ARRP e qual é o projeto-alvo;
2. tratar este arquivo como ponto inicial da migração;
3. ler `migration/migration-prompt.md`;
4. usar `migration/audit-checklist.md` durante a auditoria;
5. seguir `migration/migration-plan.md` para ordenar a execução;
6. consultar `migration/prerequisites.md` para verificar se o repositório pode ser migrado;
7. usar `template/` como referência para os documentos que poderão ser criados ou reorganizados no projeto-alvo;
8. consultar `protocol/` somente quando precisar esclarecer contratos, princípios ou decisões do ARRP;
9. consultar `examples/` apenas quando um exemplo ajudar a resolver uma situação equivalente;
10. executar a migração documental no projeto-alvo;
11. não modificar código funcional durante a migração;
12. criar commits documentais por unidade lógica, quando permitido pela política do projeto-alvo;
13. apresentar o relatório final definido pelo plano de migração.

## Leitura sob demanda

O repositório completo do ARRP deve estar disponível ao agente, mas isso **não significa ler todos os arquivos antecipadamente**.

A ordem esperada é:

```text
MIGRATION.md
   ↓
migration/migration-prompt.md
   ↓
migration/audit-checklist.md + migration/migration-plan.md
   ↓
template/ conforme a necessidade
   ↓
protocol/ para esclarecer regras específicas
   ↓
examples/ quando útil
```

Isso preserva o princípio de contexto mínimo suficiente do próprio protocolo.

## Papel de cada área

```text
MIGRATION.md
→ ponto de entrada e orquestração

migration/
→ processo de auditoria e migração

template/
→ referência da estrutura documental que poderá ser adaptada ao projeto-alvo

protocol/
→ contratos, princípios e comportamento esperado do protocolo

examples/
→ exemplos auxiliares; não são regras obrigatórias
```

## Limite de escopo

O ARRP é um protocolo de **migração documental de repositórios existentes**.

Portanto, durante sua aplicação:

- não crie um novo projeto de software;
- não use este repositório como template de aplicação;
- não faça fork do ARRP para iniciar um produto;
- não refatore código funcional como parte da migração;
- não altere APIs, schemas ou dependências para adequar o software ao protocolo;
- não force todos os arquivos de `template/` a existirem no projeto-alvo;
- não copie o próprio repositório ARRP para dentro do projeto migrado.

O resultado esperado é que o **repositório existente** passe a possuir documentação, contratos e roteamento de contexto suficientes para trabalhar com agentes de IA segundo o ARRP.

## Depois da migração

O projeto migrado deve se tornar autônomo. O uso cotidiano passa a ocorrer por meio do `AGENTS.md` e da documentação local criada ou reorganizada durante a migração.

O repositório ARRP não precisa permanecer anexado ao projeto depois que a migração terminar.

Se uma versão futura do protocolo precisar ser aplicada, uma nova migração poderá ser executada usando novamente o repositório ARRP completo.