# Plano genérico de migração

A migração deve adaptar o processo ao estado documental do projeto e também ao histórico de adoção do próprio ARRP.

## Etapa 0 — Detectar modo de migração

Antes de reorganizar qualquer documento, verifique se o repositório já foi migrado anteriormente ou já possui responsabilidades equivalentes ao ARRP.

Classifique a execução como:

- **migração inicial** — ainda não existe estrutura compatível;
- **atualização incremental** — o projeto já foi migrado ou já está parcialmente conforme.

Em atualização incremental, consulte `../protocol/migration-update-policy.md`, identifique o delta em relação ao protocolo vigente e preserve tudo que já estiver correto. Nenhuma mudança é um resultado válido quando não houver delta real.

## Cenários de maturidade documental

### 1. Documentação suficiente

Reorganize somente quando necessário, consolide fontes responsáveis, remova redundâncias reais, separe vigente de histórico e valide afirmações relevantes contra código, testes e configuração.

### 2. Documentação parcial, bagunçada ou desatualizada

Preserve informação válida, use o código atual como evidência do estado implementado, identifique intenção ainda não implementada, complemente apenas fatos verificáveis e classifique divergências antes de agir.

### 3. Pouca ou nenhuma documentação

Gere apenas um baseline mínimo a partir de estrutura, código, configuração, dependências, scripts, testes, CI/CD, schemas, rotas e convenções consistentemente observáveis. Diferencie observado, inferido com alta confiança e não definido.

## Etapa 1 — Auditoria

Inventarie a documentação e leia código, configuração e testes apenas na medida necessária. Em projetos já migrados, identifique primeiro quais responsabilidades do ARRP já estão satisfeitas.

## Etapa 2 — Reconciliação

Documentação e implementação são fontes complementares. Classifique divergências como documentação obsoleta, implementação divergente da intenção documentada, dívida técnica conhecida ou decisão ambígua que exige mantenedor. Não altere código funcional.

## Etapa 3 — Fonte responsável

Para cada regra importante, defina uma única fonte responsável. Evite duplicação textual quando referências forem suficientes.

## Etapa 4 — Porta de entrada

Crie ou reduza `AGENTS.md` para conter apenas invariantes essenciais, estáveis e roteamento. Estados transitórios devem permanecer em documentação especializada, salvo quando sua leitura em toda tarefa for indispensável para evitar erro grave.

## Etapa 5 — Documentação para agentes

Crie somente os documentos necessários. Verifique se existem responsabilidades equivalentes para:

- contexto e mapa de leitura sob demanda;
- interpretação e decomposição de tarefas;
- política consultiva de capacidade/modelo;
- decisões e divergências, quando aplicável;
- workflow, validação e commits;
- reconciliação documental de commits, PRs ou diffs já implementados.

Essas responsabilidades podem estar consolidadas em menos arquivos quando isso for mais claro. Não copie o template mecanicamente.

## Etapa 6 — Documentação humana

Preserve README, CONTRIBUTING e guias humanos. Mova histórico extenso para área apropriada quando necessário.

## Etapa 7 — Estado atual x histórico

Arquive planos concluídos e documentação superada que ainda possua valor. Preserve intenção ainda não implementada, mas diferencie-a do estado atual.

## Etapa 8 — Workflow

Consolide política de tarefa, decomposição, validação, changelog, commits e ações externas somente quando essas regras existirem ou forem explicitamente decididas.

## Etapa 9 — Validação de idempotência

Em atualização incremental, revise o diff final e remova alterações que sejam apenas churn documental. Não renomeie, mova ou reformate conteúdo já conforme sem motivo funcional.

## Etapa 10 — Commits

Faça commits documentais por unidade lógica quando permitido. Não altere código funcional.

## Resultado

Entregue relatório contendo:

- modo da migração;
- cenário de maturidade documental;
- responsabilidades já conformes e preservadas;
- delta encontrado em relação ao ARRP vigente;
- documentos criados, alterados, movidos ou arquivados;
- redundâncias removidas;
- informações observadas e inferidas;
- lacunas e divergências;
- validações executadas;
- commits produzidos;
- ou confirmação de que nenhuma mudança documental foi necessária.