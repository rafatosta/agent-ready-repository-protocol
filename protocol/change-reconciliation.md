# Reconciliação documental pós-alteração

## Propósito

O ARRP deve continuar útil quando uma contribuição de código é válida, mas não atualiza a documentação exigida pelo projeto.

Esse cenário é comum em contribuições humanas rápidas: o autor corrige o problema, valida o comportamento e envia o código, mas não necessariamente conhece ou deseja executar todo o workflow documental do repositório.

A responsabilidade do protocolo é permitir que um agente reconcilie posteriormente essa alteração com a documentação vigente.

## Princípio

> Toda alteração pode ser analisada quanto a impacto documental, mas nem toda alteração exige mudança na documentação.

O agente deve partir de uma referência Git concreta e reconstruir apenas o contexto necessário para decidir o impacto documental.

## Escopo válido

A referência pode ser:

- um commit;
- um intervalo de commits;
- um pull request;
- um diff explicitamente fornecido.

A referência deve ser estável o suficiente para separar a alteração analisada de outras mudanças do repositório.

## Relação entre código e intenção

O diff é evidência forte do que foi implementado, mas nem sempre da intenção completa.

O agente pode afirmar com segurança o que mudou no comportamento quando isso estiver demonstrado pelo código e pelos testes. Ele não deve promover detalhes de implementação a políticas gerais sem respaldo documental, testes que expressem a regra, issue/PR associado ou outra evidência suficiente.

## Classificação

Ao analisar uma alteração, o agente deve decidir entre:

1. nenhuma atualização documental necessária;
2. documentação existente precisa ser corrigida;
3. documentação existente precisa ser complementada;
4. nova decisão permanente pode ser documentada com evidência suficiente;
5. intenção não pode ser inferida com segurança e exige decisão humana;
6. foi encontrada divergência entre implementação e intenção documentada.

## Limites

Durante essa operação o agente não deve:

- refatorar código funcional;
- ampliar o escopo da contribuição;
- corrigir bugs incidentais;
- inventar regras de UX, arquitetura, domínio ou convenções;
- reescrever documentação sem relação com o diff;
- tratar toda alteração de código como obrigação de produzir texto novo.

## Resultado esperado

O repositório deve terminar com documentação compatível com o estado implementado e com as decisões conhecidas, mantendo explícitas as lacunas que não possam ser determinadas com segurança.

A operação deve preferir um commit documental separado da alteração original, preservando a autoria e a rastreabilidade da contribuição de código.
