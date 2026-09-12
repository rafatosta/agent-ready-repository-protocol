# Ciclo de vida de uma tarefa

## 1. Receber

Preserve a solicitação do usuário como intenção principal. Não amplie o escopo apenas porque melhorias adicionais parecem úteis.

## 2. Interpretar

Extraia, quando aplicável:

- objetivo;
- problema atual;
- escopo;
- restrições explícitas;
- critérios de conclusão.

Não exija que o usuário preencha um formulário rígido.

## 3. Classificar

Determine se a tarefa é simples ou composta, quais áreas são afetadas e qual nível de capacidade é recomendado.

## 4. Decompor

Se houver unidades de trabalho coerentes e verificáveis, gere um checklist ordenado por dependência. Não crie etapas artificiais apenas para produzir mais commits.

## 5. Informar a estratégia no início

Para tarefas compostas, apresente o checklist antes da implementação. Se as etapas recomendarem capacidades/modelos diferentes, informe isso também no início.

Se o modelo atual puder executar todas as etapas, mesmo estando acima do necessário, a execução pode ser contínua.

Quando houver troca recomendada, o usuário pode escolher:

- **execução contínua:** concluir tudo com o modelo atual;
- **execução com pausas:** parar apenas nas fronteiras de etapa em que a troca foi previamente prevista.

A recomendação nunca é bloqueante por si só.

## 6. Selecionar contexto

Leia `AGENTS.md` e somente a documentação indicada para as áreas afetadas. Amplie o contexto quando uma dependência nova aparecer.

## 7. Implementar

Execute uma etapa por vez. Preserve escopo, trabalho existente e regras do projeto.

## 8. Validar

Use validações proporcionais durante a etapa. Antes de considerar uma etapa concluída, confirme seu critério de aceitação.

## 9. Registrar

Quando a política do projeto permitir, crie um commit local por etapa coerente concluída e validada. Atualize documentação e changelog conforme as regras do projeto.

## 10. Concluir

Ao final, valide a tarefa como um todo e informe:

- etapas concluídas;
- validações executadas;
- commits produzidos;
- limitações reais restantes;
- decisões que exigem mantenedor, se houver.
