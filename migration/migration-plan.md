# Plano genérico de migração

## Etapa 1 — Auditoria

Inventarie a documentação e leia código apenas o suficiente para verificar o estado real. Classifique arquivos por público, atualidade e responsabilidade.

## Etapa 2 — Fonte responsável

Para cada regra importante, defina um único documento responsável. Elimine duplicação textual quando referências forem suficientes.

## Etapa 3 — Porta de entrada

Crie ou reduza `AGENTS.md` para conter invariantes essenciais e roteamento. Evite transformá-lo em enciclopédia.

## Etapa 4 — Documentação para IA

Crie somente os documentos necessários ao projeto. Use os arquivos em `template/docs/ai/` como base, removendo seções irrelevantes.

## Etapa 5 — Documentação humana

Preserve README, CONTRIBUTING e guias de usuário para pessoas. Mova decisões e históricos extensos para área de mantenedores quando apropriado.

## Etapa 6 — Estado atual x histórico

Arquive planos concluídos e documentação superada que ainda possua valor. Documentos operacionais devem refletir o estado vigente.

## Etapa 7 — Workflow

Defina política de tarefa, decomposição, validação, changelog, commits e ações externas.

## Etapa 8 — Validação

Confira links, caminhos, comandos e consistência. Registre divergências entre código e documentação.

## Etapa 9 — Commits

Faça commits documentais por unidade lógica. Não altere código funcional durante a migração.

## Resultado

Entregue relatório contendo:

- documentos criados;
- documentos movidos/arquivados;
- redundâncias removidas;
- regras consolidadas;
- divergências encontradas;
- pontos que exigem decisão do mantenedor.