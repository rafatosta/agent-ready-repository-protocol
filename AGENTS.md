# Instruções para agentes

Este repositório documenta o Agent Ready Repository Protocol (ARRP). Trate `protocol/` como a especificação vigente e `template/` como material reutilizável para outros projetos.

## Leitura inicial mínima

1. Leia `protocol/overview.md`.
2. Leia apenas os documentos de `protocol/` necessários para a tarefa.
3. Não leia toda a árvore por padrão.

## Regras

- Preserve a separação entre documentação para IA, mantenedores e usuários.
- Não transforme exemplos em requisitos universais sem registrar a decisão no protocolo.
- Evite duplicar a mesma regra em documentos diferentes; prefira referência à fonte responsável.
- Mudanças no comportamento do protocolo devem atualizar `CHANGELOG.md`.
- Mantenha linguagem direta e operacional nos arquivos voltados a agentes.
- Commits devem ser coesos e usar Conventional Commits em português.
- Não faça push, merge, release ou publicação como efeito colateral de uma alteração documental.

## Roteamento

- princípios gerais: `protocol/principles.md`
- estrutura documental: `protocol/repository-structure.md`
- ciclo de tarefas: `protocol/task-lifecycle.md`
- orçamento de contexto: `protocol/context-strategy.md`
- recomendação de modelos: `protocol/model-policy.md`
- commits: `protocol/commit-policy.md`
- públicos e linguagem: `protocol/documentation-policy.md`
- migração de repositórios: `migration/`

Ao concluir, revise links, consistência entre documentos e escopo da alteração.