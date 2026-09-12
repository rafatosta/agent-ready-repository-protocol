# Visão geral do protocolo

O Agent Ready Repository Protocol organiza a relação entre três elementos: **demanda humana**, **agente de IA** e **repositório**.

A demanda descreve principalmente o resultado desejado. O repositório mantém as regras permanentes. O agente interpreta a demanda, recupera somente o contexto necessário, implementa e valida.

## Objetivos

- reduzir prompts operacionais extensos;
- tornar regras permanentes verificáveis no próprio repositório;
- reduzir leitura inicial desnecessária;
- preservar a intenção do mantenedor sem transformar sugestões automáticas em requisitos;
- decompor tarefas grandes em unidades verificáveis;
- criar histórico Git coerente;
- manter recomendação de modelo como informação consultiva;
- separar documentação por público.

## Unidade principal

A unidade principal continua sendo a **tarefa solicitada pelo usuário**. Subtarefas são um recurso de execução e não alteram o compromisso de entregar a tarefa completa.

## Fonte de verdade

Cada projeto que adota o protocolo deve declarar suas próprias fontes de verdade. O protocolo não determina regras de domínio específicas. Ele determina onde essas regras devem ser documentadas e como o agente deve localizá-las.

## Resultado esperado

Um repositório preparado deve aceitar solicitações relativamente curtas e permitir que o agente descubra de forma controlada:

- quais regras se aplicam;
- quais arquivos e documentos consultar;
- como validar;
- como registrar a alteração.
