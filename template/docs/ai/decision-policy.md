# Política de decisões

Nem toda escolha de implementação merece documentação histórica.

## Registrar permanentemente quando

- altera fronteira arquitetural;
- cria dependência significativa;
- muda contrato público ou persistente;
- resolve ambiguidade importante;
- define política de segurança, privacidade ou compatibilidade;
- rejeita alternativa plausível por trade-off relevante.

## Não registrar como decisão arquitetural quando

- é detalhe local facilmente inferível do código;
- é mera formatação;
- é implementação mecânica sem impacto futuro relevante.

## Formato

O projeto pode usar ADRs, log de decisões ou documento equivalente. Este arquivo deve apontar para o mecanismo escolhido.

## Decisões pendentes

Quando faltar autoridade para decidir, registre a pendência sem inventar uma conclusão.