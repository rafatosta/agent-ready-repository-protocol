# Exemplo — migração documental

## Situação inicial

Um projeto possui:

- README com instruções de usuário e regras para agentes;
- CONTRIBUTING repetindo testes e commits;
- `docs/architecture.md` com estado atual e planos antigos;
- documentação de UI com seções adicionadas a cada refatoração;
- `AGENTS.md` pedindo leitura de toda a pasta `docs/`.

## Migração

1. manter README focado em pessoas;
2. reduzir `AGENTS.md` e criar roteamento;
3. consolidar workflow em fonte única;
4. mover histórico arquitetural para documentação de mantenedores;
5. reescrever documentos operacionais para descrever somente o estado atual;
6. criar mapa de leitura sob demanda;
7. validar referências sem alterar código.

## Resultado

O repositório pode continuar muito bem documentado, mas uma tarefa simples deixa de carregar toda a documentação antes de começar.