# Contrato do agente

Este arquivo é a porta de entrada do agente para o projeto.

## Antes de alterar código

1. Preserve a solicitação do usuário como objetivo principal.
2. Leia `docs/ai/task-protocol.md`.
3. Identifique as áreas afetadas.
4. Consulte apenas a documentação indicada em `docs/ai/documentation-map.md` para essas áreas.
5. Inspecione o estado atual do repositório e mudanças não commitadas antes de editar.

## Invariantes do projeto

> Substitua esta seção pelas regras permanentes que nunca devem ser violadas sem decisão explícita do mantenedor.

- [INVARIANTE 1]
- [INVARIANTE 2]
- [INVARIANTE 3]

## Regras gerais

- Não amplie escopo sem necessidade para cumprir a tarefa.
- Não invente regra de negócio ausente.
- Preserve trabalho existente não relacionado.
- Use validação proporcional durante a implementação e validação final conforme `docs/ai/testing.md`.
- Siga `docs/ai/workflow-rules.md` ao concluir etapas.
- Use `docs/ai/commit-convention.md` para commits.

## Contexto

- visão do projeto: `docs/ai/project-context.md`
- interpretação de tarefas: `docs/ai/task-protocol.md`
- workflow: `docs/ai/workflow-rules.md`
- capacidade/modelo: `docs/ai/model-policy.md`
- arquitetura: `docs/ai/architecture.md`
- domínio: `docs/ai/domain.md`
- código: `docs/ai/coding-rules.md`
- testes: `docs/ai/testing.md`
- decisões: `docs/ai/decision-policy.md`
- mapa completo: `docs/ai/documentation-map.md`

Não leia todos esses documentos por padrão. Use o mapa para selecionar o contexto necessário.