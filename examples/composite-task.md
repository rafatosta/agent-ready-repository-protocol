# Exemplo — tarefa composta

## Solicitação

```text
Reorganize o cadastro para que o usuário informe os dados uma única vez e as telas seguintes derivem essas informações.
```

## Plano possível

```text
[ ] 1. Mapear fluxo e contratos afetados
[ ] 2. Ajustar modelo/estado compartilhado
[ ] 3. Refatorar formulários
[ ] 4. Atualizar navegação e feedback
[ ] 5. Atualizar testes e documentação
```

## Execução padrão

Cada etapa é implementada e validada. Ao final de uma unidade lógica, cria-se um commit local conforme a política do projeto. O agente continua sem pedir confirmação entre etapas até concluir a tarefa completa.

```text
etapa 1 → commit
etapa 2 → commit
etapa 3 → commit
etapa 4 → commit
etapa 5 → commit
→ validação final
```

As etapas não devem ser criadas artificialmente: cada uma precisa representar uma fronteira real de trabalho.