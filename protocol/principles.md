# Princípios

## 1. Prompt pequeno, repositório forte

O prompt deve priorizar objetivo, escopo e restrições específicas. Arquitetura, convenções e procedimentos permanentes pertencem ao repositório.

## 2. Contexto mínimo suficiente

Documentação disponível não é documentação obrigatoriamente carregada. Comece pequeno e amplie sob demanda.

## 3. Leitura orientada pela tarefa

O agente identifica as áreas afetadas e consulta apenas as fontes necessárias. Dependências descobertas durante a execução podem ampliar o contexto.

## 4. Intenção humana é diferente de elaboração automática

Requisitos confirmados pelo mantenedor devem ser distinguíveis de sugestões auxiliares geradas por outro agente.

## 5. Informação não necessária fica recuperável

Evite a ideia de descartar conhecimento. Classifique-o como ativo, de apoio ou fora do escopo inicial.

## 6. Tarefa completa, execução incremental

Uma tarefa grande pode ser decomposta em etapas, mas a entrega padrão continua sendo completa. Cada etapa deve deixar o repositório em estado válido quando possível.

## 7. Validação proporcional

Durante a implementação, execute verificações proporcionais ao risco e ao escopo. Na conclusão, execute a bateria final exigida pelo projeto quando aplicável.

## 8. Modelo recomendado não bloqueia

A política de modelos orienta custo e capacidade. A decisão final pertence ao usuário. O agente continua com o modelo atual se isso for tecnicamente possível.

## 9. Documentação tem público

Arquivos para IA usam linguagem operacional. Arquivos para mantenedores explicam contexto e decisões. Arquivos para usuários ensinam uso.

## 10. Estado atual separado de histórico

Documentos operacionais descrevem o estado vigente. Decisões antigas e planos concluídos devem ir para histórico quando ainda tiverem valor.

## 11. Ações externas exigem autorização

Commits locais podem ser permitidos pela política do projeto. Push, merge, release, deploy e outras ações externas ou irreversíveis exigem autorização explícita, salvo política diferente claramente definida.
