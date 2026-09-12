# Como executar o Agent Ready Repository Protocol

O ARRP é um protocolo aplicado **exclusivamente por migração a repositórios de software já existentes**.

Ele não é um template para criar novos projetos, não deve ser usado como base de fork e não substitui um gerador de aplicações.

A porta de entrada operacional é o arquivo da raiz:

```text
MIGRATION.md
```

## Forma recomendada de uso

O agente deve ter acesso simultâneo a:

1. **o projeto existente que será migrado**;
2. **o repositório completo `agent-ready-repository-protocol`**, usado somente como especificação.

Para o primeiro uso, a forma mais simples é disponibilizar os dois como pastas ou ZIPs no mesmo contexto do agente.

Exemplo:

```text
/contexto
├── projeto-alvo/
│   └── ...
└── agent-ready-repository-protocol/
    ├── MIGRATION.md
    ├── protocol/
    ├── template/
    ├── migration/
    └── examples/
```

Depois, basta solicitar:

```text
Execute a migração ARRP no projeto-alvo.
Comece por MIGRATION.md do repositório agent-ready-repository-protocol.
Não altere código funcional.
```

O agente deve identificar claramente qual repositório é apenas a especificação e qual é o alvo da migração. O repositório ARRP não deve ser modificado durante esse processo.

## O que acontece durante a migração

`MIGRATION.md` orienta o agente a navegar pelo protocolo conforme necessário:

```text
MIGRATION.md
      ↓
migration/migration-prompt.md
      ↓
migration/audit-checklist.md
+ migration/migration-plan.md
+ migration/prerequisites.md
      ↓
template/ quando precisar estruturar documentos
      ↓
protocol/ quando precisar esclarecer contratos ou princípios
      ↓
examples/ quando um exemplo for útil
```

O repositório completo fica disponível, mas não deve ser lido integralmente por padrão. O agente deve carregar apenas o contexto necessário a cada etapa.

## O que o agente faz no projeto-alvo

O fluxo geral é:

```text
repositório existente
      ↓
classificar maturidade documental
      ↓
auditar documentação atual
      ↓
inspecionar código, configuração, testes e scripts quando necessário
      ↓
reconciliar documentação e estado implementado
      ↓
criar ou reorganizar AGENTS.md e documentação necessária
      ↓
separar conteúdo vigente, histórico e públicos
      ↓
validar referências e registrar lacunas/divergências
      ↓
criar commits documentais por unidade lógica
      ↓
entregar relatório da migração
```

A migração é documental. O código pode ser inspecionado para verificar a realidade do projeto, mas não deve ser refatorado ou alterado funcionalmente como parte da adoção do protocolo.

## Projeto com muita documentação

Quando o projeto já possui documentação extensa, o agente deve:

- preservar conhecimento válido;
- identificar duplicações e ambiguidades;
- definir fontes responsáveis;
- separar documentação atual de histórico;
- verificar afirmações relevantes contra código, testes e configuração;
- reorganizar o conteúdo conforme as responsabilidades do protocolo.

A migração não é uma simples cópia para novas pastas.

## Projeto com pouca ou nenhuma documentação

Quando a documentação for insuficiente, o agente deve criar somente um baseline mínimo baseado em evidências do próprio repositório.

Pode usar como evidência:

- estrutura de diretórios;
- código-fonte;
- arquivos de configuração;
- dependências;
- scripts;
- testes;
- CI/CD;
- rotas e schemas;
- relações entre módulos.

O agente deve diferenciar informações **observadas**, **inferidas com alta confiança** e **não definidas**.

O protocolo não deve inventar intenção, regras de domínio, convenções ou decisões arquiteturais que não possam ser sustentadas pelo projeto.

As lacunas permanecem registradas para decisão posterior do mantenedor.

## O papel de `template/`

A pasta `template/` não é um template de aplicação e não deve ser usada para iniciar um novo software.

Ela contém **modelos documentais de destino da migração**. O agente consulta esses arquivos para entender como uma responsabilidade deve ser documentada no projeto-alvo.

Nem todos os arquivos precisam ser criados. A migração deve adaptar a estrutura à realidade do projeto.

## Depois da migração

Depois que a migração termina, o projeto passa a operar de forma autônoma.

O ponto de entrada para tarefas futuras passa a ser o `AGENTS.md` do próprio projeto migrado. Não é necessário anexar o ARRP em cada tarefa cotidiana.

Exemplo de tarefa posterior:

```text
Reorganize a tela de cadastro para funcionar melhor em dispositivos móveis.
```

O fluxo normal passa a ser:

```text
solicitação do usuário
      ↓
AGENTS.md
      ↓
classificação da tarefa
      ↓
contexto necessário sob demanda
      ↓
plano/subtarefas quando necessário
      ↓
implementação
      ↓
validação
      ↓
commits locais por unidade lógica
      ↓
entrega completa
```

## Forma recomendada de primeiro teste

```text
1. deixe o projeto-alvo em uma branch limpa ou estado Git conhecido;
2. disponibilize ao agente o projeto-alvo e o repositório ARRP completo;
3. peça: "Execute a migração ARRP no projeto-alvo. Comece por MIGRATION.md.";
4. deixe o agente consultar os arquivos do protocolo conforme a necessidade;
5. revise o relatório de divergências e lacunas;
6. revise os commits documentais produzidos;
7. depois da migração, execute tarefas reais usando apenas solicitações curtas;
8. observe se o AGENTS.md e o roteamento de contexto são suficientes.
```

O teste principal é verificar se, depois da migração, novas tarefas passam a exigir menos instruções do usuário sem perda de qualidade, rastreabilidade ou segurança.

## Resumo

```text
projeto existente
+
repositório ARRP completo
      ↓
"Execute a migração ARRP. Comece por MIGRATION.md."
      ↓
migração documental
      ↓
projeto autônomo com AGENTS.md e documentação reorganizada
```

O ARRP termina sua função quando a migração documental é concluída. Ele não é usado para criar novos projetos.