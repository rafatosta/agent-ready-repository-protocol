# Reconciliação documental de alterações

Este arquivo é a porta de entrada para documentar uma alteração de código que já foi realizada fora do fluxo documental do projeto.

Use este fluxo somente em um repositório que já tenha sido migrado para o ARRP ou que possua documentação equivalente suficiente para orientar a análise.

## Objetivo

Partir de uma alteração concreta — commit, intervalo de commits, pull request ou diff explícito — e verificar se a documentação do projeto continua coerente com o código.

O objetivo não é reimplementar a mudança nem ampliar seu escopo. É identificar o impacto documental da alteração e atualizar somente o que for necessário.

## Referência obrigatória

Antes de analisar, identifique exatamente qual alteração será usada como fonte:

- commit específico;
- intervalo de commits;
- pull request;
- diff fornecido explicitamente.

Evite usar expressões ambíguas como "alguma alteração recente" quando houver risco de misturar mudanças não relacionadas.

Quando o usuário disser "último commit", confirme o `HEAD` atual e use somente esse commit e seu pai como escopo.

## Processo

1. Leia o `AGENTS.md` e apenas a documentação necessária para entender a área afetada.
2. Inspecione o diff da referência informada.
3. Identifique o comportamento anterior e o comportamento resultante.
4. Identifique, quando houver evidência suficiente, qual problema a alteração resolve.
5. Classifique o impacto documental.
6. Localize os documentos responsáveis pelas regras, comportamento ou arquitetura afetados.
7. Atualize somente a documentação necessária.
8. Não transforme uma implementação localizada em regra geral sem evidência de que essa intenção existe.
9. Não altere código funcional como parte desta tarefa.
10. Revise a consistência final entre código, testes e documentação.
11. Gere um commit exclusivamente documental, quando a política do projeto permitir.

## Classificação do impacto

Toda alteração deve ser analisada, mas nem toda alteração exige mudança documental.

Classifique o resultado como uma ou mais destas situações:

- **documentação já compatível** — nenhuma alteração documental necessária;
- **documentação desatualizada** — atualizar para refletir comportamento já confirmado;
- **nova decisão documentável** — registrar somente quando houver evidência suficiente de que a mudança representa uma regra ou decisão permanente;
- **mudança localizada** — não promover a regra geral;
- **intenção não inferível** — registrar a lacuna ou solicitar decisão do mantenedor;
- **divergência relevante** — documentar a inconsistência sem corrigir código funcional nesta tarefa.

## Evidência e inferência

Diferencie sempre:

- **observado** — diretamente comprovado pelo diff, código, testes ou configuração;
- **inferido com alta confiança** — sustentado por evidências consistentes;
- **não definido** — depende de decisão humana.

Um valor alterado no código não cria automaticamente uma nova convenção do projeto.

Exemplo: alterar a margem de um botão de `8px` para `12px` prova a mudança local. Não prova, por si só, que todos os botões do sistema devem usar `12px`.

## Entrega

Ao concluir, informe:

- referência analisada;
- resumo factual da alteração;
- documentos consultados;
- documentos alterados;
- itens que não exigiram documentação;
- inferências relevantes e respectivas evidências;
- lacunas que exigem decisão do mantenedor;
- validações executadas;
- commit documental produzido, quando aplicável.

## Solicitação mínima

Exemplos:

```text
Analise o último commit de código e reconcilie a documentação do projeto com essa alteração. Não altere código funcional.
```

```text
Documente as alterações introduzidas pelo commit a1b2c3d. Use somente esse commit como escopo e não altere código funcional.
```

```text
Analise este pull request e atualize apenas a documentação necessária para refletir o comportamento introduzido.
```
