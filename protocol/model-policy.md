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

## Migração ARRP completa

A migração documental completa é, por padrão, uma tarefa **transversal (Nível C)**. Ela combina leitura e reconciliação de documentação, inspeção seletiva de código, testes e configuração, classificação de divergências, reorganização estrutural e produção de commits documentais coerentes.

Para ambientes OpenAI/Codex, o mapeamento prático recomendado em setembro de 2026 é:

```text
Migração ARRP completa
→ GPT-5.6 Sol
→ raciocínio Medium
```

Esse é o padrão recomendado por equilibrar capacidade e consumo de cota.

Use **GPT-6 Astra com raciocínio Medium** quando o repositório apresentar complexidade excepcional, por exemplo:

- documentação extensa e fortemente conflitante;
- arquitetura difícil de reconstruir;
- muitas camadas e fontes de verdade concorrentes;
- regras normativas complexas;
- grande volume de histórico misturado ao estado vigente;
- baixa clareza sobre a relação entre intenção documentada e implementação atual.

Não use raciocínio High por padrão. Ele deve ser reservado para trechos realmente ambíguos ou difíceis quando Medium não for suficiente.

Se o modelo atual for superior ao recomendado, a migração pode ser executada normalmente, embora com possível desperdício de cota. Se for inferior, o agente deve informar o risco, mas a política continua não bloqueante.

## Reconciliação documental posterior

Para documentar um commit, PR ou diff já implementado, a recomendação deve ser proporcional ao impacto:

```text
alteração simples/localizada
→ GPT-5.6 Terra / Medium

alteração funcional relevante
→ GPT-5.6 Sol / Medium

alteração arquitetural ou transversal
→ GPT-5.6 Sol / Medium
  ou GPT-6 Astra / Medium quando a ambiguidade justificar
```

## Portabilidade

As classes A–D são a parte estável do protocolo. Nomes específicos de modelos são apenas um **mapeamento operacional do ambiente atual** e podem ficar obsoletos.

Quando os modelos disponíveis mudarem, preserve as classes genéricas e atualize apenas o mapeamento correspondente.