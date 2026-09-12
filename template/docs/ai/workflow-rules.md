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

## Reconciliação posterior de contribuições

Alterações podem chegar ao projeto sem seguir todo o fluxo documental, especialmente por contribuições humanas externas.

Quando o mantenedor solicitar reconciliação documental de um commit, intervalo, pull request ou diff:

- fixe a referência exata antes da análise;
- leia o diff e somente a documentação relacionada à área afetada;
- determine o impacto documental da alteração;
- atualize apenas documentos realmente afetados;
- aceite como resultado válido que nenhuma atualização documental seja necessária;
- não transforme detalhes locais de implementação em regras permanentes sem evidência suficiente;
- não altere código funcional durante a reconciliação;
- prefira um commit documental separado para preservar rastreabilidade.

## Ao concluir a tarefa

- execute validação final;
- confirme que todas as etapas do checklist foram concluídas;
- registre validações não executadas e motivo;
- informe commits criados;
- informe limitações reais restantes.

## Ações externas

Por padrão, commits locais podem ser autorizados pelo projeto. Push, merge, release e deploy exigem autorização explícita.
