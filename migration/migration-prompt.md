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
- redundâncias sejam consolidadas sem perda de informação válida;
- projetos pouco documentados recebam um baseline mínimo baseado em evidências reais do repositório.

## Limite obrigatório

Esta é uma migração documental.

Você pode:

- ler código para verificar a realidade do projeto;
- inspecionar configuração, testes, scripts e CI/CD quando necessário;
- criar, mover, consolidar e atualizar documentação;
- criar ou ajustar `AGENTS.md`;
- corrigir links e referências documentais;
- arquivar documentação obsoleta;
- registrar divergências encontradas;
- gerar documentação mínima quando ela não existir, desde que baseada em evidências verificáveis.

Você não pode, como parte desta tarefa:

- refatorar código funcional;
- alterar comportamento;
- mudar APIs ou schemas;
- trocar dependências;
- corrigir bugs encontrados incidentalmente;
- inventar regras, convenções, decisões arquiteturais ou regras de domínio sem evidência suficiente;
- fazer release, deploy ou outras ações externas.

## Classificação inicial

Antes de migrar, classifique o projeto em um dos seguintes cenários:

1. **documentação suficiente** — reorganizar, deduplicar e validar;
2. **documentação parcial, bagunçada ou desatualizada** — preservar, reconciliar, complementar e registrar divergências;
3. **pouca ou nenhuma documentação** — gerar apenas um baseline documental mínimo a partir do estado observável do repositório.

Registre qual cenário foi identificado.

## Relação entre documentação e código

Trate documentação e implementação como fontes complementares.

- documentação pode representar intenção, regras e histórico;
- código, testes e configuração representam o estado implementado;
- nenhum dos dois deve ser considerado automaticamente correto quando houver conflito.

Quando houver divergência, classifique-a quando possível como:

- documentação obsoleta;
- implementação divergente da intenção documentada;
- dívida técnica conhecida;
- decisão ambígua que exige mantenedor.

Não altere código para resolver essas divergências nesta tarefa.

## Quando a documentação for insuficiente

Use apenas fontes observáveis do repositório, como:

- estrutura de diretórios;
- código-fonte;
- configuração;
- manifestos de dependências;
- scripts;
- testes e fixtures;
- CI/CD;
- rotas;
- schemas;
- módulos e dependências entre camadas.

Ao gerar documentação, diferencie:

- **observado** — diretamente comprovado pelo repositório;
- **inferido com alta confiança** — conclusão sustentada por evidências consistentes;
- **não definido** — informação que depende de decisão humana.

Não preencha lacunas de intenção com suposições. Registre-as para o mantenedor.

## Processo

1. Leia a documentação existente, quando houver, e inspecione a estrutura do repositório.
2. Classifique a maturidade documental do projeto.
3. Use `migration/audit-checklist.md` como referência conceitual do protocolo, adaptando-a ao projeto.
4. Classifique documentos por público: IA, mantenedores/desenvolvedores, usuários e histórico.
5. Identifique regras repetidas e escolha uma fonte responsável para cada uma.
6. Identifique invariantes, fontes de verdade, fronteiras, workflow, testes, commits e autorizações que estejam efetivamente definidos.
7. Compare afirmações relevantes com código, testes, configuração e scripts.
8. Crie/reduza `AGENTS.md` para um bootstrap pequeno e roteador.
9. Crie somente os documentos de `docs/ai/` realmente necessários ao projeto.
10. Se a documentação for insuficiente, gere apenas o baseline mínimo sustentado por evidências e marque lacunas.
11. Preserve documentação humana útil sem torná-la leitura obrigatória do agente.
12. Separe documentação vigente de planos ou decisões históricas concluídas.
13. Valide caminhos, links, comandos e referências.
14. Registre divergências entre documentação e código; não corrija código nesta tarefa.
15. Faça commits documentais por unidade lógica, se a política do repositório permitir.

## Entrega

Apresente:

- cenário documental identificado;
- estrutura documental final;
- arquivos criados, movidos e consolidados;
- redundâncias removidas;
- fontes responsáveis definidas;
- documentos históricos separados;
- informações extraídas do estado observável do repositório;
- inferências relevantes e evidências que as sustentam;
- lacunas que ainda dependem de decisão do mantenedor;
- divergências ainda pendentes;
- validações executadas;
- commits produzidos.

Não trate o template do protocolo como estrutura obrigatória. Simplifique quando o projeto não precisar de todos os arquivos.

O objetivo da migração é produzir documentação confiável e navegável, não preencher artificialmente todos os arquivos previstos pelo protocolo.