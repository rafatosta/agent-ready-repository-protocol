# Exemplo — reconciliação documental de contribuição externa

## Situação

Um contribuidor corrige um botão desalinhado e envia um pull request funcional. O código está correto, mas a documentação do projeto não foi revisada.

## Solicitação

```text
Analise este pull request e reconcilie a documentação necessária com a alteração realizada. Não altere código funcional.
```

## Possíveis resultados

### Caso 1 — nenhuma documentação necessária

O diff apenas corrige uma violação de uma regra de UX que já estava documentada.

Resultado:

```text
Código corrigido.
Documentação existente já descreve o comportamento esperado.
Nenhuma alteração documental necessária.
```

### Caso 2 — documentação desatualizada

A alteração confirma um comportamento novo que já aparece em outros componentes e testes.

Resultado:

```text
Atualizar documentação de UX para refletir o comportamento vigente.
Criar commit documental separado.
```

### Caso 3 — intenção insuficiente

O diff troca um valor visual localizado, mas não existe evidência de que isso represente uma regra geral.

Resultado:

```text
Mudança local observada.
Não promover para convenção global.
Nenhuma regra permanente criada.
```

O objetivo é restaurar coerência documental sem exigir que todo contribuidor domine previamente todo o contrato documental do projeto.
