# Política de commits

## Princípio

Commits devem representar **unidades lógicas concluídas e verificáveis**.

## Tarefas simples

Uma tarefa simples normalmente produz um único commit.

## Tarefas compostas

Uma tarefa composta pode produzir vários commits locais:

```text
etapa 1 → validar → commit
etapa 2 → validar → commit
etapa 3 → validar → commit
validação final da tarefa
```

O agente não precisa pedir confirmação entre commits no modo contínuo.

## Regras

- não agrupe alterações não relacionadas;
- preserve ordem de dependência entre etapas;
- cada commit deve deixar o repositório em estado válido quando tecnicamente possível;
- não use commit como substituto de validação;
- siga a convenção específica do projeto;
- documente no relatório final os commits produzidos.

## Ações externas

O protocolo distingue commit local de ações externas. Push, merge, release e deploy exigem autorização explícita, salvo política específica do projeto que diga o contrário.

## Reversão

Commits dependentes podem exigir reversão em ordem inversa. Isso é aceitável. O objetivo é coerência lógica, não independência artificial entre todos os commits.
