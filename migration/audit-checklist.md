# Checklist de auditoria documental

## Classificação inicial

- [ ] avaliar se a documentação é suficiente, parcial/desatualizada ou praticamente inexistente;
- [ ] registrar o cenário identificado antes de iniciar a reorganização;
- [ ] definir quais fontes do repositório precisarão ser inspecionadas para suprir lacunas verificáveis.

## Inventário

- [ ] listar documentos existentes;
- [ ] identificar público principal de cada arquivo;
- [ ] identificar arquivos lidos automaticamente por agentes;
- [ ] localizar documentação histórica misturada à vigente;
- [ ] identificar áreas relevantes sem documentação.

## Evidências do repositório

Quando a documentação for insuficiente:

- [ ] inspecionar estrutura de diretórios;
- [ ] inspecionar código somente na medida necessária;
- [ ] verificar arquivos de configuração e manifestos;
- [ ] verificar scripts de execução, build e manutenção;
- [ ] verificar testes e fixtures relevantes;
- [ ] verificar CI/CD quando existir;
- [ ] identificar rotas, schemas, módulos e fronteiras observáveis;
- [ ] distinguir fatos observados de inferências;
- [ ] marcar como não definido o que exigir decisão do mantenedor.

Não criar regras, intenção arquitetural, convenções ou decisões de domínio sem evidência suficiente.

## Redundância

- [ ] localizar regras repetidas em README, AGENTS, CONTRIBUTING e docs;
- [ ] escolher fonte responsável para cada regra;
- [ ] substituir cópias por referências quando adequado.

## Estado atual

- [ ] conferir se arquitetura documentada corresponde ao código;
- [ ] conferir rotas, módulos e comandos citados;
- [ ] marcar conteúdo obsoleto;
- [ ] separar planos concluídos do estado vigente;
- [ ] preservar intenção arquitetural válida quando a implementação ainda divergir dela;
- [ ] classificar divergências como documentação obsoleta, implementação divergente, dívida técnica ou decisão ambígua quando possível.

## Regras permanentes

- [ ] identificar invariantes do projeto;
- [ ] identificar fontes de verdade;
- [ ] identificar proibições e fronteiras;
- [ ] identificar política de testes;
- [ ] identificar política de commits e changelog;
- [ ] identificar ações que exigem autorização humana;
- [ ] não apresentar como regra uma recomendação que ainda não tenha sido adotada pelo projeto.

## Contexto do agente

- [ ] criar/ajustar `AGENTS.md` como roteador;
- [ ] garantir que leitura inicial seja pequena;
- [ ] criar mapa de documentação sob demanda;
- [ ] retirar histórico do bootstrap;
- [ ] criar somente os documentos para IA realmente necessários ao projeto.

## Baseline para projetos sem documentação

- [ ] criar contexto mínimo do projeto com base em fatos verificáveis;
- [ ] registrar arquitetura observada sem atribuir intenção não comprovada;
- [ ] documentar comandos de build/teste comprováveis;
- [ ] documentar convenções consistentes somente quando sustentadas por evidência;
- [ ] sinalizar explicitamente lacunas de governança, domínio ou workflow;
- [ ] separar informação observada, inferida com alta confiança e não definida.

## Públicos

- [ ] separar conteúdo para IA;
- [ ] separar conteúdo para mantenedores;
- [ ] separar conteúdo para usuários;
- [ ] manter linguagem adequada ao público.

## Validação

- [ ] revisar links;
- [ ] revisar caminhos de arquivos;
- [ ] revisar comandos citados;
- [ ] registrar divergências código/documentação sem corrigir código;
- [ ] conferir que nenhuma política inexistente foi inventada;
- [ ] produzir relatório final da migração.