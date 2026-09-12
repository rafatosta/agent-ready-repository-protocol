# Estrutura documental recomendada

O protocolo não exige uma árvore idêntica em todos os projetos. A estrutura abaixo é uma referência.

```text
/
├── AGENTS.md
├── README.md
├── CONTRIBUTING.md
├── CHANGELOG.md
└── docs/
    ├── ai/
    │   ├── project-context.md
    │   ├── task-protocol.md
    │   ├── workflow-rules.md
    │   ├── model-policy.md
    │   ├── architecture.md
    │   ├── domain.md
    │   ├── coding-rules.md
    │   ├── testing.md
    │   ├── commit-convention.md
    │   ├── decision-policy.md
    │   └── documentation-map.md
    ├── maintainers/
    └── user/
```

## `AGENTS.md`

É a porta de entrada do agente. Deve ser curto e atuar como roteador. Contém invariantes essenciais e aponta para a fonte especializada conforme a tarefa.

## `docs/ai/`

Contém conhecimento operacional para agentes. Nem todos os arquivos devem ser lidos em toda tarefa.

## `docs/maintainers/`

Contém decisões, processo de release, histórico técnico e informações úteis a pessoas que mantêm o projeto.

## `docs/user/`

Contém instalação, uso, FAQ e troubleshooting quando o projeto exigir documentação de usuário.

## Arquivos opcionais

Um projeto pequeno pode combinar documentos. Um projeto regulado pode acrescentar documentação normativa. Um projeto sem interface não precisa de documentação de UX. A estrutura deve refletir necessidades reais.

## Regra de não duplicação

Quando uma regra possui uma fonte responsável, outros documentos devem referenciá-la em vez de copiar seu conteúdo integralmente.
