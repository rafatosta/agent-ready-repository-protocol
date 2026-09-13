# Executar migração ARRP

Este arquivo é a porta de entrada operacional do Agent Ready Repository Protocol (ARRP). O ARRP migra somente repositórios de software já existentes; não cria projetos novos, não é base de fork e não altera código funcional durante a migração.

## Modelo recomendado

Consulte `protocol/model-policy.md`. No ambiente OpenAI/Codex, a recomendação atual para a maioria das migrações é GPT-5.6 Sol com raciocínio Medium. Modelos de maior capacidade ficam reservados para casos excepcionalmente ambíguos ou complexos. A recomendação é consultiva.

## O que fornecer ao agente

O agente precisa ter acesso simultâneo ao projeto-alvo e ao repositório completo do ARRP. Todas as mudanças devem ocorrer no projeto-alvo.

Solicitação mínima:

```text
Execute a migração ARRP no projeto-alvo.
Comece por MIGRATION.md do repositório agent-ready-repository-protocol.
Não altere código funcional.
```

## Detecte se é primeira migração ou atualização

Antes de reorganizar documentos, leia `protocol/migration-update-policy.md` e classifique a execução como:

- **migração inicial** — o projeto ainda não possui estrutura compatível com o ARRP;
- **atualização incremental** — o projeto já foi migrado ou já possui responsabilidades equivalentes.

Quando for atualização incremental, preserve tudo que já estiver correto e aplique somente o delta necessário para o protocolo vigente. Não recrie estruturas, não mova arquivos adequados e não reescreva documentação por preferência estética. Se o projeto já estiver conforme, nenhuma alteração é um resultado válido.

## Fluxo obrigatório

1. Identifique o ARRP e o projeto-alvo.
2. Leia `protocol/migration-update-policy.md`.
3. Leia `migration/migration-prompt.md`.
4. Use `migration/audit-checklist.md` e `migration/migration-plan.md`.
5. Consulte `migration/prerequisites.md`.
6. Use `template/` apenas como referência documental, nunca como árvore obrigatória.
7. Consulte `protocol/` sob demanda para esclarecer contratos.
8. Verifique se o projeto possui as responsabilidades operacionais exigidas pelo ARRP, inclusive contexto sob demanda, interpretação de tarefas, recomendação consultiva de capacidade/modelo e reconciliação documental pós-alteração.
9. Garanta que `AGENTS.md` permaneça pequeno e composto principalmente por invariantes estáveis; estados transitórios devem ser roteados para documentação especializada.
10. Execute somente mudanças documentais necessárias.
11. Valide links, caminhos, comandos e consistência.
12. Produza relatório final e commits documentais quando permitidos.

## Idempotência

O ARRP deve ser idempotente no nível documental:

```text
primeira execução
→ pode produzir reorganização estrutural relevante

mesma versão executada novamente
→ nenhuma mudança relevante, salvo correções reais

versão mais nova executada sobre projeto já migrado
→ somente delta de conformidade
```

Uma evolução do ARRP não autoriza reestruturação geral do projeto-alvo. Mudança ampla só é apropriada quando a estrutura existente deixou de cumprir o comportamento exigido pelo protocolo.

## Limite de escopo

Durante a migração, não crie software novo, não altere APIs, schemas, dependências ou comportamento, não corrija bugs incidentais e não copie o repositório ARRP para dentro do projeto-alvo.

Depois da migração, o projeto deve operar de forma autônoma por meio de seu próprio `AGENTS.md` e documentação local. Uma execução futura do ARRP serve apenas para atualizar a conformidade documental quando o protocolo evoluir.