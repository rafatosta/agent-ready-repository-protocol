# Política de recomendação de modelos

A política de modelos é **consultiva**. Ela orienta custo e capacidade, mas não deve impedir uma tarefa solicitada pelo usuário quando o modelo atual consegue executá-la.

## Classes genéricas

### Nível A — localizado

Exemplos: texto, estilo, pequena alteração visual, renomeação, documentação pontual.

Recomendação: modelo leve e baixo esforço de raciocínio.

### Nível B — funcional comum

Exemplos: formulário, fluxo CRUD, pequena feature, correção que atravessa poucos arquivos.

Recomendação: modelo intermediário e esforço baixo/médio.

### Nível C — transversal

Exemplos: UI + domínio + persistência, migração de schema, refatoração envolvendo várias camadas.

Recomendação: modelo avançado e esforço médio.

### Nível D — arquitetural/ambíguo

Exemplos: redefinição estrutural, investigação difícil, grande refatoração, requisitos conflitantes.

Recomendação: modelo de maior capacidade e esforço médio/alto.

## Comportamento

- modelo adequado: continue;
- modelo superior ao necessário: continue e, se útil, informe o possível desperdício;
- modelo abaixo do recomendado: informe o risco, mas continue se tecnicamente possível;
- impossibilidade técnica real: explique o impedimento.

## Tarefas compostas

Classifique por etapa, não apenas pela tarefa global. No início, informe se o modelo atual atende todas as etapas e, quando houver recomendações diferentes, ofereça execução contínua ou pausas planejadas.

## Portabilidade

Não grave nomes de modelos específicos no protocolo genérico. Cada projeto ou ambiente pode mapear os níveis para modelos disponíveis naquele momento.
