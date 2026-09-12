# Prompt de migração documental

Use este arquivo como base para adaptar um repositório existente ao Agent Ready Repository Protocol.

---

Analise este repositório e migre **somente sua documentação e instruções para agentes** para o Agent Ready Repository Protocol.

## Objetivo

Organizar a documentação para que:

- `AGENTS.md` funcione como porta de entrada e roteador de contexto;
- agentes carreguem apenas documentação necessária à tarefa;
- regras permanentes não precisem ser repetidas em prompts;
- documentação para IA, mantenedores e usuários tenha público claro;
- estado atual fique separado de histórico;
- redundâncias sejam consolidadas sem perda de informação válida.

## Limite obrigatório

Esta é uma migração documental.

Você pode:

- ler código para verificar a realidade do projeto;
- criar, mover, consolidar e atualizar documentação;
- criar ou ajustar `AGENTS.md`;
- corrigir links e referências documentais;
- arquivar documentação obsoleta;
- registrar divergências encontradas.

Você não pode, como parte desta tarefa:

- refatorar código funcional;
- alterar comportamento;
- mudar APIs ou schemas;
- trocar dependências;
- corrigir bugs encontrados incidentalmente;
- fazer release, deploy ou outras ações externas.

## Processo

1. Leia a documentação existente e inspecione a estrutura do repositório.
2. Use `migration/audit-checklist.md` como referência conceitual do protocolo, adaptando-a ao projeto.
3. Classifique documentos por público: IA, mantenedores/desenvolvedores, usuários e histórico.
4. Identifique regras repetidas e escolha uma fonte responsável para cada uma.
5. Identifique invariantes, fontes de verdade, fronteiras, workflow, testes, commits e autorizações.
6. Crie/reduza `AGENTS.md` para um bootstrap pequeno e roteador.
7. Crie somente os documentos de `docs/ai/` realmente necessários ao projeto.
8. Preserve documentação humana útil sem torná-la leitura obrigatória do agente.
9. Separe documentação vigente de planos ou decisões históricas concluídas.
10. Valide caminhos, links, comandos e referências.
11. Registre divergências entre documentação e código; não corrija código nesta tarefa.
12. Faça commits documentais por unidade lógica, se a política do repositório permitir.

## Entrega

Apresente:

- estrutura documental final;
- arquivos criados, movidos e consolidados;
- redundâncias removidas;
- fontes responsáveis definidas;
- documentos históricos separados;
- divergências ainda pendentes;
- validações executadas;
- commits produzidos.

Não trate o template do protocolo como estrutura obrigatória. Simplifique quando o projeto não precisar de todos os arquivos.
