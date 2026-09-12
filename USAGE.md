# Como executar o Agent Ready Repository Protocol

O ARRP não é um programa que precisa ser instalado nem uma dependência que permanece vinculada ao projeto. Ele é um protocolo documental aplicado por um agente de IA ao repositório.

Existem dois momentos diferentes de uso:

1. **adoção ou migração** — preparar um projeto para seguir o protocolo;
2. **uso cotidiano** — trabalhar normalmente no projeto depois que o protocolo já foi incorporado.

## 1. Aplicar o protocolo em um projeto existente

Abra o repositório que será migrado no agente de desenvolvimento que terá acesso aos arquivos e ao histórico Git do projeto.

Use como instrução de entrada o arquivo deste repositório:

```text
migration/migration-prompt.md
```

A forma mais simples e independente de ferramenta é copiar ou anexar o conteúdo desse arquivo à primeira tarefa executada no repositório alvo.

Exemplo de solicitação:

```text
Aplique o Agent Ready Repository Protocol a este repositório usando as instruções de migração fornecidas.
Execute a migração documental completa.
Não altere código funcional.
```

O agente deve então:

```text
repositório atual
      ↓
classificar maturidade documental
      ↓
auditar documentação existente
      ↓
inspecionar código/configuração/testes quando necessário
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

A migração não exige que o projeto copie toda a estrutura deste repositório. O agente deve criar somente os documentos necessários ao projeto analisado.

### O protocolo precisa ficar conectado a este repositório?

Não.

O repositório `agent-ready-repository-protocol` funciona como **especificação e fonte do template de migração**. Depois da adoção, o projeto deve possuir em seu próprio repositório as regras e documentos necessários para operar de forma autônoma.

Atualizações futuras do ARRP podem ser aplicadas por uma nova revisão ou migração, mas o funcionamento cotidiano do projeto não depende de acesso permanente a este repositório.

## 2. Aplicar o protocolo em um projeto novo

Em um projeto novo, não é necessário executar uma migração completa.

Use `template/` como referência e crie apenas o conjunto mínimo necessário. Normalmente o primeiro passo é criar:

```text
AGENTS.md

docs/ai/
├── project-context.md
├── task-protocol.md
├── workflow-rules.md
└── documentation-map.md
```

Outros documentos, como arquitetura, domínio, testes ou convenções de commit, devem ser adicionados quando o projeto realmente possuir essas responsabilidades ou decisões.

Não copie arquivos vazios apenas para reproduzir a árvore do template.

## 3. O que acontece depois da migração?

Depois que o protocolo foi incorporado ao projeto, o ponto de entrada do agente passa a ser o `AGENTS.md` daquele próprio repositório.

A partir desse momento, não é necessário usar `migration/migration-prompt.md` em cada tarefa.

Uma tarefa cotidiana pode ser escrita normalmente:

```text
Reorganize a tela de cadastro para funcionar melhor em dispositivos móveis.
```

O agente deve utilizar o `AGENTS.md` para descobrir:

- quais regras permanentes se aplicam;
- quais documentos consultar;
- quais partes do código investigar;
- como validar a alteração;
- como decompor a tarefa quando necessário;
- como criar commits;
- como tratar recomendações de modelo.

O fluxo passa a ser:

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

## 4. Tarefas compostas e escolha de modelo

Ao receber uma tarefa composta, o agente deve fazer a análise inicial antes da implementação.

Se houver várias etapas, deve apresentar o checklist inicial. Se as etapas tiverem recomendações diferentes de capacidade/modelo, deve informar isso antes de começar e permitir que o usuário escolha entre:

- executar toda a tarefa com o modelo atual; ou
- pausar em fronteiras seguras para permitir troca de modelo.

Depois dessa decisão inicial, o objetivo é evitar supervisão constante do usuário.

Os commits intermediários funcionam como checkpoints técnicos. A tarefa continua até sua conclusão completa, salvo quando o usuário tiver escolhido previamente pausas para troca de modelo ou ocorrer um impedimento real.

## 5. Projeto com muita documentação

Quando o projeto já possui documentação extensa, o agente deve:

- preservar conhecimento válido;
- identificar duplicações e ambiguidades;
- definir fontes responsáveis;
- separar documentação atual de histórico;
- verificar afirmações relevantes contra código, testes e configuração;
- reorganizar o conteúdo conforme as responsabilidades do protocolo.

A migração não é uma simples cópia para novas pastas.

## 6. Projeto com pouca ou nenhuma documentação

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

As lacunas permanecem registradas para que mantenedores as definam posteriormente.

## 7. Forma recomendada de primeiro teste

Para validar a adoção em um projeto real:

```text
1. trabalhar em uma branch limpa ou estado Git conhecido;
2. fornecer migration/migration-prompt.md ao agente;
3. solicitar a migração documental completa;
4. deixar o agente analisar documentação e código conforme necessário;
5. revisar o relatório de divergências e lacunas;
6. revisar os commits documentais produzidos;
7. depois da migração, executar algumas tarefas reais usando apenas solicitações curtas;
8. observar se o AGENTS.md e o roteamento de contexto são suficientes.
```

O teste mais importante não é apenas verificar se os arquivos foram reorganizados. É verificar se, **depois da migração**, novas tarefas passam a exigir menos instruções do usuário sem perda de qualidade, rastreabilidade ou segurança.

## Resumo

Para um projeto existente:

```text
abra o projeto no agente
→ forneça migration/migration-prompt.md
→ solicite a migração
→ revise o resultado
→ passe a usar o AGENTS.md do próprio projeto
```

Para um projeto novo:

```text
use template/ como referência
→ crie somente a documentação necessária
→ configure AGENTS.md como roteador
→ evolua a documentação junto com o projeto
```

Depois da adoção, o protocolo deixa de ser uma tarefa de migração e passa a fazer parte da forma normal de trabalhar naquele repositório.
