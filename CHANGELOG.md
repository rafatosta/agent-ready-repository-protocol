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
- `MIGRATION.md` como porta de entrada operacional para executar o protocolo.

### Alterado

- o escopo do ARRP foi definido como exclusivamente migratório;
- o protocolo não deve ser usado para criar projetos novos nem como base de fork;
- o fluxo recomendado agora fornece ao agente o projeto-alvo e o repositório ARRP completo, consultado sob demanda durante a migração;
- `template/` passa a ser descrito explicitamente como referência documental da migração, não como template de aplicação.
