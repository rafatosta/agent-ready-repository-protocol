# Changelog

Todas as mudanças relevantes do protocolo serão registradas neste arquivo.

## [Unreleased]

### Adicionado

- estrutura inicial do Agent Ready Repository Protocol;
- princípios de contexto mínimo suficiente;
- ciclo de vida de tarefas simples e compostas;
- política consultiva de modelos;
- política de commits locais por etapa;
- separação documental por público;
- templates documentais de destino da migração;
- plano de migração para repositórios existentes;
- guia prático `USAGE.md`;
- `MIGRATION.md` como porta de entrada operacional para executar o protocolo;
- `DOCUMENT-CHANGE.md` como referência para reconciliação documental de alterações já implementadas;
- contrato `protocol/change-reconciliation.md` para tratar commits, PRs e diffs que chegaram sem atualização documental;
- exemplo de reconciliação documental de contribuição externa;
- recomendação operacional de modelo para migrações ARRP e reconciliação documental no ambiente OpenAI/Codex.

### Alterado

- o escopo do ARRP foi definido como exclusivamente migratório;
- o protocolo não deve ser usado para criar projetos novos nem como base de fork;
- o fluxo recomendado fornece ao agente o projeto-alvo e o repositório ARRP completo, consultado sob demanda durante a migração;
- `template/` é referência documental da migração, não template de aplicação;
- os templates de `task-protocol.md` e `workflow-rules.md` agora incluem reconciliação documental posterior;
- a migração deve instalar no projeto-alvo capacidade para analisar contribuições de código feitas fora do workflow documental sem exigir alteração funcional;
- `protocol/model-policy.md` agora mantém classes genéricas estáveis e um mapeamento operacional atualizável para modelos específicos;
- `MIGRATION.md` recomenda GPT-5.6 Sol com raciocínio Medium como padrão atual e GPT-6 Astra Medium apenas para migrações de complexidade excepcional.
