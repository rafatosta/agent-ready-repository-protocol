# Pré-requisitos para migração

O Agent Ready Repository Protocol é aplicado **somente a repositórios de software já existentes**.

Ele não cria novos projetos, não serve como template inicial de aplicação e não deve ser usado como base de fork para desenvolvimento de um produto.

Para uma migração assistida, recomenda-se que o projeto-alvo possua:

- repositório versionado com Git;
- código-fonte acessível;
- estrutura minimamente compreensível;
- forma conhecida de executar, buildar ou validar o projeto;
- testes, quando existirem;
- documentação existente, mesmo incompleta ou redundante;
- mantenedor disponível para resolver ambiguidades relevantes.

## Não é obrigatório possuir

- `AGENTS.md`;
- documentação para IA;
- arquitetura formal;
- cobertura completa de testes;
- changelog perfeito;
- histórico de decisões organizado.

A migração existe justamente para organizar ou criar o baseline documental necessário a partir de um projeto que já existe.

## Condições de segurança

A migração documental pode inspecionar código para conferir a realidade do projeto, mas não deve alterar comportamento funcional. Problemas encontrados incidentalmente devem ser registrados separadamente.

O repositório ARRP deve ser tratado somente como especificação da migração. As alterações devem ocorrer no repositório-alvo.