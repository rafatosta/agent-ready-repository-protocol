# Como executar o Agent Ready Repository Protocol

O ARRP é aplicado por migração a repositórios de software já existentes. Ele não cria projetos novos, não deve ser usado como base de fork e não é um gerador de aplicações.

Existem três situações de uso:

1. **migração documental inicial** — prepara um repositório ainda não adaptado ao ARRP;
2. **atualização incremental** — reaplica uma versão atual do ARRP a um repositório já migrado;
3. **reconciliação documental posterior** — documenta uma alteração de código já realizada fora do workflow documental.

## Migração inicial

Disponibilize ao agente o projeto-alvo e o repositório completo `agent-ready-repository-protocol` e peça:

```text
Execute a migração ARRP no projeto-alvo.
Comece por MIGRATION.md do repositório agent-ready-repository-protocol.
Não altere código funcional.
```

O ARRP é somente especificação. Todas as mudanças devem ocorrer no projeto-alvo.

## Atualização incremental

O mesmo comando pode ser usado novamente quando o ARRP evoluir. O agente deve primeiro detectar que o projeto já foi migrado e então comparar o estado atual com o protocolo vigente.

O resultado esperado é:

```text
projeto já migrado
      ↓
detectar responsabilidades ARRP existentes
      ↓
comparar com protocolo atual
      ↓
identificar delta real
      ↓
alterar somente o necessário
```

Não é esperado recriar `docs/ai/`, mover novamente arquivos corretos, reformatar documentação apenas para coincidir com o template ou refazer toda a migração.

A regra é:

```text
mesma versão + projeto conforme
→ nenhuma mudança relevante

versão nova + projeto já migrado
→ somente delta necessário
```

Consulte `protocol/migration-update-policy.md` para a regra completa de idempotência e atualização.

## O que a migração verifica

A migração deve manter ou instalar, conforme a realidade do projeto, responsabilidades equivalentes para:

- `AGENTS.md` pequeno e roteador;
- contexto sob demanda;
- interpretação e decomposição de tarefas;
- recomendação consultiva de capacidade/modelo;
- decisões e divergências quando aplicável;
- workflow, testes, commits e autorizações;
- reconciliação documental pós-alteração;
- separação entre estado vigente e histórico;
- separação adequada entre agentes, mantenedores e usuários.

Nem toda responsabilidade precisa estar em um arquivo separado.

## Estabilidade do `AGENTS.md`

O bootstrap deve conter principalmente invariantes permanentes e informações necessárias em praticamente toda tarefa. Estados transitórios devem ficar em documentação especializada e ser alcançados pelo mapa de contexto.

Exceções só fazem sentido quando uma informação temporária precisa ser lida em toda tarefa para evitar erro grave.

## Projeto com muita documentação

Preserve conhecimento válido, identifique duplicações e ambiguidades, defina fontes responsáveis, separe documentação atual de histórico e confira afirmações relevantes contra código, testes e configuração.

## Projeto com pouca ou nenhuma documentação

Crie somente um baseline mínimo sustentado por evidências do repositório. Diferencie informações observadas, inferidas com alta confiança e não definidas. Não invente intenção, regra de domínio ou decisão arquitetural.

## Alteração de código feita fora do workflow documental

Uma contribuição humana pode corrigir corretamente o código sem atualizar toda a documentação. O mantenedor pode pedir depois uma reconciliação documental usando commit, intervalo, PR ou diff como referência exata.

Exemplo:

```text
Documente as alterações introduzidas pelo commit a1b2c3d.
Use somente esse commit como escopo e não altere código funcional.
```

Nenhuma atualização documental necessária é um resultado válido.

## Resumo

```text
MIGRAÇÃO INICIAL
projeto existente + ARRP completo
→ MIGRATION.md
→ projeto autônomo

ATUALIZAÇÃO DO ARRP
projeto já migrado + ARRP atual
→ detectar conformidade existente
→ aplicar somente o delta

RECONCILIAÇÃO POSTERIOR
commit/PR/diff existente
→ documentação local do projeto
→ atualizar somente impacto documental
```

O ARRP nunca é usado para criar um projeto novo.