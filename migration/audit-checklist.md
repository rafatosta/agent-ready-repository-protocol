# Checklist de auditoria documental

## Inventário

- [ ] listar documentos existentes;
- [ ] identificar público principal de cada arquivo;
- [ ] identificar arquivos lidos automaticamente por agentes;
- [ ] localizar documentação histórica misturada à vigente.

## Redundância

- [ ] localizar regras repetidas em README, AGENTS, CONTRIBUTING e docs;
- [ ] escolher fonte responsável para cada regra;
- [ ] substituir cópias por referências quando adequado.

## Estado atual

- [ ] conferir se arquitetura documentada corresponde ao código;
- [ ] conferir rotas, módulos e comandos citados;
- [ ] marcar conteúdo obsoleto;
- [ ] separar planos concluídos do estado vigente.

## Regras permanentes

- [ ] identificar invariantes do projeto;
- [ ] identificar fontes de verdade;
- [ ] identificar proibições e fronteiras;
- [ ] identificar política de testes;
- [ ] identificar política de commits e changelog;
- [ ] identificar ações que exigem autorização humana.

## Contexto do agente

- [ ] criar/ajustar `AGENTS.md` como roteador;
- [ ] garantir que leitura inicial seja pequena;
- [ ] criar mapa de documentação sob demanda;
- [ ] retirar histórico do bootstrap.

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
- [ ] produzir relatório final da migração.