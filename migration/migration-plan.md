# Plano genérico de migração

A migração deve adaptar o processo ao nível de maturidade documental do projeto. O protocolo não presume que todos os repositórios tenham a mesma quantidade ou qualidade de documentação.

## Cenários de entrada

Antes de iniciar, classifique o projeto em um dos cenários abaixo.

### 1. Documentação suficiente

Quando o projeto já possui documentação útil e razoavelmente atual:

- reorganize o conteúdo conforme o protocolo;
- consolide fontes responsáveis;
- remova redundâncias;
- separe documentação vigente de histórico;
- valide afirmações relevantes contra código, testes e configuração.

### 2. Documentação parcial, bagunçada ou desatualizada

Quando existe documentação, mas ela é incompleta, redundante, histórica ou contraditória:

- preserve informação válida;
- use o código atual como evidência do estado implementado;
- identifique intenção documentada que ainda não corresponde ao código;
- complemente apenas fatos que possam ser verificados;
- classifique divergências antes de decidir se a documentação deve ser atualizada ou se a decisão deve ser encaminhada ao mantenedor.

### 3. Pouca ou nenhuma documentação

Quando o repositório não possui documentação suficiente, gere apenas um baseline documental mínimo a partir de evidências observáveis no próprio projeto.

Podem ser usados como fontes:

- estrutura de diretórios;
- código-fonte;
- arquivos de configuração;
- manifesto de dependências;
- scripts de execução e build;
- testes;
- CI/CD;
- schemas;
- rotas;
- convenções consistentemente observáveis.

Não invente regras, intenção arquitetural, convenções ou decisões de domínio que não possam ser comprovadas.

Classifique informações produzidas como:

- **observado** — diretamente comprovado pelo repositório;
- **inferido com alta confiança** — conclusão sustentada por múltiplas evidências consistentes;
- **não definido** — depende de decisão do mantenedor.

Lacunas devem ser registradas explicitamente. Completar decisões de governança ou intenção que não existam não é responsabilidade automática da migração.

## Etapa 1 — Auditoria

Inventarie a documentação existente, quando houver, e leia código, configuração e testes na medida necessária para verificar o estado real. Classifique o nível de maturidade documental e os arquivos por público, atualidade e responsabilidade.

## Etapa 2 — Reconciliação entre documentação e implementação

Trate documentação e código como fontes complementares:

- a documentação pode registrar intenção, regras e histórico;
- código, testes e configuração demonstram o estado implementado;
- nenhum deles deve ser considerado automaticamente correto quando houver conflito.

Classifique divergências, quando possível, como:

- documentação obsoleta;
- implementação divergente da intenção documentada;
- dívida técnica conhecida;
- decisão ambígua que exige mantenedor.

Não altere código funcional durante a migração.

## Etapa 3 — Fonte responsável

Para cada regra importante, defina um único documento responsável. Elimine duplicação textual quando referências forem suficientes.

## Etapa 4 — Porta de entrada

Crie ou reduza `AGENTS.md` para conter invariantes essenciais e roteamento. Evite transformá-lo em enciclopédia.

## Etapa 5 — Documentação para IA

Crie somente os documentos necessários ao projeto. Use os arquivos em `template/docs/ai/` como base, removendo seções irrelevantes.

Quando documentação prévia não existir, documente apenas o que puder ser sustentado por evidências do repositório e marque lacunas para decisão posterior.

## Etapa 6 — Documentação humana

Preserve README, CONTRIBUTING e guias de usuário para pessoas. Mova decisões e históricos extensos para área de mantenedores quando apropriado.

## Etapa 7 — Estado atual x histórico

Arquive planos concluídos e documentação superada que ainda possua valor. Documentos operacionais devem refletir o estado vigente.

Quando uma arquitetura desejada estiver documentada, mas ainda não implementada, preserve a intenção e registre separadamente o estado atual e a divergência.

## Etapa 8 — Workflow

Defina ou consolide política de tarefa, decomposição, validação, changelog, commits e ações externas somente quando essas regras já existirem ou forem explicitamente decididas pelo mantenedor.

Não transforme recomendações do protocolo em políticas fictícias do projeto.

## Etapa 9 — Validação

Confira links, caminhos, comandos e consistência. Registre divergências entre código e documentação.

## Etapa 10 — Commits

Faça commits documentais por unidade lógica. Não altere código funcional durante a migração.

## Resultado

Entregue relatório contendo:

- cenário documental identificado;
- documentos criados;
- documentos movidos/arquivados;
- redundâncias removidas;
- regras consolidadas;
- informações extraídas do código;
- informações inferidas e respectivas evidências;
- lacunas não definidas pelo projeto;
- divergências encontradas;
- pontos que exigem decisão do mantenedor.