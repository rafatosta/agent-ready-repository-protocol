# Protocolo de interpretação de tarefas

## Objetivo

Permitir que solicitações em linguagem natural sejam convertidas em um plano operacional sem exigir prompts rígidos do mantenedor.

## Fluxo

1. Preserve a intenção original do usuário.
2. Extraia objetivo, escopo, restrições e critérios de conclusão quando estiverem disponíveis.
3. Classifique a tarefa como simples ou composta.
4. Identifique áreas e dependências prováveis.
5. Consulte `model-policy.md` para recomendação de capacidade.
6. Se composta, crie checklist de etapas coerentes e ordenadas.
7. Informe o plano no início quando houver decomposição relevante ou escolha de estratégia de modelo.
8. Consulte apenas o contexto necessário via `documentation-map.md`.
9. Implemente até concluir a tarefa inteira, salvo impedimento real ou modo com pausas escolhido pelo usuário.

## Tarefa simples

Execute diretamente quando o escopo for localizado e não houver benefício real em decompor.

## Tarefa composta

Divida quando houver unidades verificáveis com dependências claras. A tarefa continua sendo uma única entrega.

## Reconciliação documental de alteração existente

Quando o usuário solicitar documentação posterior de uma alteração já realizada, trate a referência Git como escopo da tarefa.

A referência pode ser um commit, intervalo de commits, pull request ou diff explícito. Identifique primeiro o que mudou, depois consulte apenas a documentação necessária para avaliar impacto.

O objetivo é sincronizar documentação e implementação, não refazer a alteração. Uma análise pode concluir legitimamente que nenhuma mudança documental é necessária.

Não infira intenção permanente apenas porque um detalhe apareceu no diff. Diferencie fato observado, inferência sustentada e informação não definida.

## Ambiguidade

Não pergunte por informação que possa ser determinada com segurança pela solicitação, código ou documentação vigente. Pergunte quando uma decisão necessária tiver alternativas materialmente diferentes e nenhuma fonte autoritativa resolver a dúvida.

## Escopo auxiliar

Sugestões úteis, melhorias opcionais e problemas encontrados incidentalmente não viram requisitos automaticamente. Registre-os separadamente quando forem relevantes.
