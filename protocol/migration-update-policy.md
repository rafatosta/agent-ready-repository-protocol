# Política de atualização de migração

O ARRP pode ser executado mais de uma vez sobre o mesmo repositório. Uma nova execução não deve presumir que o projeto está no estado pré-migração.

## Modos de migração

Antes de reorganizar qualquer documento, classifique a execução como:

1. **migração inicial** — o repositório ainda não possui estrutura documental compatível com o ARRP;
2. **atualização incremental** — o repositório já foi migrado anteriormente ou já possui estrutura equivalente suficiente.

Sinais de migração anterior podem incluir `AGENTS.md` funcionando como roteador, `docs/ai/`, mapa documental, protocolo de tarefas, relatório histórico de migração ou outras responsabilidades equivalentes. Não dependa de um único nome de arquivo para reconhecer conformidade.

## Regra de idempotência

A migração deve ser idempotente no nível documental:

- executar novamente a mesma versão do protocolo sobre um projeto já conforme deve produzir nenhuma mudança relevante ou somente correções objetivamente necessárias;
- executar uma versão mais nova do protocolo deve aplicar somente o delta necessário;
- documentos, caminhos e responsabilidades já corretos devem ser preservados;
- não mova, renomeie, reescreva ou reformate arquivos apenas para aproximá-los literalmente do `template/`;
- nenhuma alteração é um resultado válido quando o repositório já satisfaz o protocolo vigente.

O objetivo é conformidade funcional da documentação, não igualdade estrutural com este repositório.

## Atualização incremental

Quando uma migração anterior for detectada:

1. audite o estado documental atual;
2. identifique quais responsabilidades do ARRP já estão satisfeitas;
3. compare o estado atual com o protocolo vigente;
4. produza uma lista de diferenças reais;
5. altere somente os documentos necessários para fechar essas diferenças;
6. preserve decisões e adaptações específicas do projeto que continuem válidas;
7. valide referências e registre o resultado da atualização.

Uma mudança no ARRP não autoriza reestruturação geral do projeto-alvo. Reorganização ampla só é adequada quando a estrutura existente se tornou incompatível, redundante, obsoleta ou impede o comportamento exigido pelo protocolo atual.

## Responsabilidades que devem ser verificadas

A auditoria incremental deve confirmar, quando aplicáveis ao projeto:

- `AGENTS.md` pequeno, com invariantes estáveis e roteamento;
- leitura de contexto sob demanda;
- protocolo de interpretação e decomposição de tarefas;
- política consultiva de capacidade/modelo ou responsabilidade equivalente;
- política de decisões, divergências e lacunas quando necessária;
- workflow, validação, commits e autorizações claramente roteados;
- reconciliação documental pós-alteração;
- separação entre estado vigente e histórico;
- separação adequada entre documentação para agentes, mantenedores e usuários.

Não crie arquivos vazios ou responsabilidades artificiais. Uma responsabilidade pode estar integrada a outro documento quando isso for mais simples e inequívoco.

## Estabilidade do bootstrap

O `AGENTS.md` deve privilegiar informações permanentes, não inferíveis e necessárias em praticamente todas as tarefas.

Estados transitórios — por exemplo, uma migração em andamento, um catálogo temporariamente pendente, uma versão corrente de uma feature ou uma limitação operacional que pode mudar com frequência — devem ficar em documentação especializada e ser alcançados pelo roteamento.

Uma informação transitória só deve permanecer no `AGENTS.md` quando sua leitura em toda tarefa for necessária para evitar erro grave e não houver mecanismo mais seguro de roteamento.

## Relatório de atualização

Ao concluir uma atualização incremental, informe:

- que uma migração anterior foi detectada;
- responsabilidades já conformes e preservadas;
- diferenças encontradas em relação ao protocolo vigente;
- arquivos realmente alterados;
- itens deliberadamente não alterados e motivo;
- validações realizadas;
- se a execução resultou em nenhuma mudança documental;
- commits produzidos, quando houver.
