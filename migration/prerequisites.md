# Pré-requisitos para migração

A adoção do protocolo pode ocorrer em projetos novos ou existentes. Para uma migração assistida, recomenda-se:

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

A migração existe justamente para organizar parte desse material.

## Condições de segurança

A migração documental pode inspecionar código para conferir a realidade do projeto, mas não deve alterar comportamento funcional. Problemas encontrados incidentalmente devem ser registrados separadamente.