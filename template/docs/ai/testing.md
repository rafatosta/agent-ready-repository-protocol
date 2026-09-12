# Estratégia de testes

## Princípio

Validação deve ser proporcional durante a execução e suficiente para comprovar a tarefa ao final.

## Mapa

| Tipo de alteração | Testes mínimos | Validação final |
|---|---|---|
| documentação | links/estrutura quando aplicável | revisão documental |
| UI | testes do componente/fluxo | suíte de UI/E2E aplicável |
| domínio | unitários/regressão | suíte relevante |
| persistência | unitários/integração | round-trip/migração quando aplicável |
| arquitetura | testes de fronteira | suíte completa aplicável |

Adapte a tabela ao projeto.

## Comandos

```bash
# preencher comandos reais do projeto
```

## Falhas

Corrija falhas causadas pela tarefa. Não altere testes apenas para silenciar comportamento correto sem justificar a mudança.

## Relatório

Informe o que foi executado, o que não foi e por quê.