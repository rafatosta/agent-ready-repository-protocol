# Regras de workflow

## Antes de alterar

- verifique estado do Git e mudanças existentes;
- identifique arquivos/camadas afetados;
- confirme o contexto mínimo necessário;
- preserve trabalho não relacionado.

## Durante

- implemente uma unidade lógica por vez;
- mantenha escopo da tarefa;
- execute validações proporcionais;
- amplie contexto somente quando surgir dependência real.

## Após cada etapa coesa

- confirme o critério de aceitação da etapa;
- atualize documentação aplicável;
- atualize `CHANGELOG.md` conforme política do projeto;
- revise o diff;
- crie commit local quando autorizado pela política do projeto.

## Ao concluir a tarefa

- execute validação final;
- confirme que todas as etapas do checklist foram concluídas;
- registre validações não executadas e motivo;
- informe commits criados;
- informe limitações reais restantes.

## Ações externas

Por padrão, commits locais podem ser autorizados pelo projeto. Push, merge, release e deploy exigem autorização explícita.