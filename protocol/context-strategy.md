# Estratégia de contexto

O objetivo não é minimizar contexto a qualquer custo, mas utilizar o **menor contexto que permita uma decisão segura**.

## Categorias

### Bootstrap

Informações sempre necessárias para iniciar, normalmente `AGENTS.md` e a regra mínima de interpretação de tarefas.

### Sob demanda

Arquitetura, domínio, dados, UX, segurança, normas, testes e outras fontes específicas da área afetada.

### Finalização

Convenção de commit, release, changelog e outros procedimentos que só precisam ser carregados quando a execução chega a essa etapa, salvo quando influenciam o planejamento.

## Estados de relevância

- **ativo:** necessário para a decisão atual;
- **apoio:** disponível caso surja dependência ou dúvida;
- **fora do escopo inicial:** não deve ocupar o contexto atual, mas continua recuperável.

## Regras

1. Não leia toda a pasta `docs/` por padrão.
2. Prefira seções específicas quando a ferramenta permitir recuperação seletiva.
3. Não carregue histórico para implementar o estado atual, salvo quando a tarefa exigir compreender uma decisão passada.
4. Se uma mudança revelar dependência em outra camada, promova a documentação dessa camada para contexto ativo.
5. Não use redução de contexto como justificativa para ignorar uma regra conhecida como obrigatória.

## Exemplo

```text
Tarefa: reorganizar três ações em abas.

Bootstrap:
- AGENTS.md
- task-protocol

Ativo inicial:
- documentação de UI/UX
- componentes e rotas relacionados
- testes da interface

Apoio:
- arquitetura
- modelo de dados

Fora do escopo inicial:
- release
- histórico de migração
- documentação de funcionalidades não relacionadas
```
