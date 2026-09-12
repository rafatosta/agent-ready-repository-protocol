# Exemplo — tarefa com capacidades diferentes

## Plano

```text
[ ] 1. Definir nova fronteira arquitetural — capacidade avançada
[ ] 2. Implementar componentes e casos de uso — capacidade intermediária
[ ] 3. Atualizar documentação e ajustes mecânicos — capacidade leve/intermediária
```

## Informação inicial

O agente deve informar no início se o modelo atual é adequado para todas as etapas.

Se o modelo atual for avançado, pode executar tudo de forma contínua, ainda que algumas etapas estejam superdimensionadas.

Se o modelo atual for intermediário, o agente pode informar que a primeira etapa se beneficiaria de capacidade maior e oferecer duas estratégias:

1. executar toda a tarefa com o modelo atual;
2. pausar antes da etapa que recomenda troca.

A escolha é feita no início. A recomendação não bloqueia a execução por si só.