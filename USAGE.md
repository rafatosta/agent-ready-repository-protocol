# Como executar o Agent Ready Repository Protocol

O ARRP é aplicado por migração a repositórios de software já existentes. Ele não cria projetos novos, não deve ser usado como base de fork e não é um gerador de aplicações.

Existem duas operações relacionadas ao protocolo:

1. **migração documental inicial**, que prepara o repositório existente para trabalhar segundo o ARRP;
2. **reconciliação documental posterior**, usada quando uma alteração de código já foi realizada sem atualizar a documentação correspondente.

## 1. Migração inicial

A porta de entrada é `MIGRATION.md`.

O agente deve ter acesso simultâneo ao projeto-alvo e ao repositório completo `agent-ready-repository-protocol`, usado somente como especificação.

Exemplo de contexto:

```text
/contexto
├── projeto-alvo/
│   └── ...
└── agent-ready-repository-protocol/
    ├── MIGRATION.md
    ├── DOCUMENT-CHANGE.md
    ├── protocol/
    ├── template/
    ├── migration/
    └── examples/
```

Solicitação mínima:

```text
Execute a migração ARRP no projeto-alvo.
Comece por MIGRATION.md do repositório agent-ready-repository-protocol.
Não altere código funcional.
```

O agente deve identificar qual repositório é a especificação e qual é o alvo. O ARRP não deve ser modificado durante a migração.

### Fluxo

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

A migração é documental. O código pode ser inspecionado, mas não deve ser refatorado ou alterado funcionalmente como parte da adoção do protocolo.

## 2. Projeto com muita documentação

Quando o projeto já possui documentação extensa, o agente deve preservar conhecimento válido, identificar duplicações e ambiguidades, definir fontes responsáveis, separar documentação atual de histórico e verificar afirmações relevantes contra código, testes e configuração.

A migração não é uma simples cópia para novas pastas.

## 3. Projeto com pouca ou nenhuma documentação

Quando a documentação for insuficiente, o agente deve criar somente um baseline mínimo baseado em evidências do próprio repositório.

Pode usar estrutura de diretórios, código-fonte, configuração, dependências, scripts, testes, CI/CD, rotas, schemas e relações entre módulos.

O agente deve diferenciar informações **observadas**, **inferidas com alta confiança** e **não definidas**. Não deve inventar intenção, regras de domínio, convenções ou decisões arquiteturais sem evidência suficiente.

## 4. Papel de `template/`

A pasta `template/` não é um template de aplicação. Ela contém modelos documentais de destino da migração.

Nem todos os arquivos precisam ser criados. A estrutura deve ser adaptada à realidade do projeto.

## 5. Depois da migração

Depois da migração, o projeto passa a operar de forma autônoma. O ponto de entrada para tarefas normais é o `AGENTS.md` do próprio projeto migrado.

Exemplo:

```text
Reorganize a tela de cadastro para funcionar melhor em dispositivos móveis.
```

O fluxo cotidiano passa a ser:

```text
solicitação do usuário
      ↓
AGENTS.md
      ↓
classificação da tarefa
      ↓
contexto necessário sob demanda
      ↓
implementação
      ↓
validação
      ↓
commits locais por unidade lógica
      ↓
entrega completa
```

## 6. Alteração de código feita fora do workflow documental

Uma contribuição humana pode corrigir corretamente o código sem conhecer ou executar todas as obrigações documentais do projeto.

Isso não torna a contribuição inválida. O mantenedor pode solicitar posteriormente uma **reconciliação documental da alteração**.

A porta de entrada de referência no ARRP é:

```text
DOCUMENT-CHANGE.md
```

No projeto já migrado, a operação deve usar a referência Git exata da mudança e a documentação local do próprio projeto.

Exemplos:

```text
Analise o último commit de código e reconcilie a documentação do projeto com essa alteração. Não altere código funcional.
```

```text
Documente as alterações introduzidas pelo commit a1b2c3d. Use somente esse commit como escopo.
```

```text
Analise este pull request e atualize apenas a documentação necessária para refletir o comportamento introduzido.
```

O agente deve comparar o diff com a documentação vigente e decidir se existe impacto documental. **Nenhuma atualização documental necessária** é um resultado válido.

O agente não deve transformar detalhes localizados do código em regras permanentes sem evidência suficiente.

Quando houver atualização, prefira um commit documental separado da contribuição de código para preservar autoria e rastreabilidade.

## 7. Primeiro teste recomendado

```text
1. deixe o projeto-alvo em uma branch limpa ou estado Git conhecido;
2. disponibilize ao agente o projeto-alvo e o repositório ARRP completo;
3. peça: "Execute a migração ARRP no projeto-alvo. Comece por MIGRATION.md.";
4. revise o relatório e os commits documentais;
5. execute algumas tarefas reais usando solicitações curtas;
6. escolha um commit ou PR de código já existente;
7. solicite a reconciliação documental dessa referência;
8. verifique se o agente atualiza somente o necessário e aceita corretamente casos sem impacto documental.
```

## Resumo

```text
MIGRAÇÃO INICIAL
projeto existente + ARRP completo
→ MIGRATION.md
→ projeto autônomo

MANUTENÇÃO POSTERIOR
commit/PR/diff existente
→ documentação local do projeto
→ reconciliação de impacto documental
→ commit documental, se necessário
```

O ARRP nunca é usado para criar um projeto novo. Sua adoção ocorre por migração de um repositório existente; a reconciliação posterior é uma capacidade documental instalada no projeto migrado.
