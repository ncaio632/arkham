# Módulos e estados — arkham

Resumo acionável; a [versão inglesa](architecture.en.md) detalha o contrato. Módulos são responsabilidades propostas, não serviços implantados. Um processo único pode implementá-las.

| Módulo | Responsabilidade e limite |
| --- | --- |
| Entrada de localização | Validar coordenadas e precisão transitórias; não registrar coordenadas. |
| Escopo da sessão | Criar/revogar sessão, base imutável, expiração e revisão. |
| Catálogo | Consultar somente pela base da sessão; devolver oportunidades e categorias. |
| Elegibilidade | Avaliar respostas explícitas com regras versionadas; nunca enviar ou alterar base. |
| Metadados de demonstração | Validar categorias, MIME e tamanho; nunca receber bytes ou atestar autenticidade. |
| Coordenador | Autorizar e gravar atomicamente comprovante simulado; recebimento real falha fechado. |
| Apresentação | Mostrar estado, motivos e recuperação; passo da interface não autoriza operação. |

Estados: `unbound → scoped → assessing → ready → simulated`. Avaliação inelegível/desconhecida vai para `blocked`; respostas corrigidas voltam a `assessing`. Mudança de regra/catálogo em `ready` retorna à avaliação. Qualquer estado ativo expira ou pode ser cancelado; cancelamento revoga a sessão. `expired` exige nova sessão. Alterar oportunidade na mesma base limpa elegibilidade e prontidão documental; alterar base exige nova sessão.

O [schema](../contracts/onboarding-snapshot.schema.json) representa um snapshot interno sintético, não a requisição existente de sessão nem uma escrita integral permitida ao cliente. Comandos propostos: `startSession`, `selectOpportunity`, `evaluateEligibility`, `validateMetadata`, `simulateApplication`, `cancelSession`. Cada mutação usa revisão esperada e incrementa `revision`; conflito 409 exige nova leitura.

O schema representa sessões já vinculadas; `unbound` fica fora dele. Autorizar origem/sessão primeiro; depois procurar a chave já aceita. Carga idêntica retorna comprovante antes de comparar a revisão antiga; carga alterada gera conflito. Chave nova exige revisão atual. Na simulação, comparação de revisão e gravação devem ser atômicas. Congelar revisão da oportunidade e impressão dos metadados sob a chave de idempotência, cujo escopo é a sessão. Outra chave não deve duplicar uma seleção já simulada. JSON Schema não verifica autorização, relógio, igualdade de bases, atualidade de regras ou cobertura completa de categorias.

Erros devem conter `code`, `retryable`, `correlation_ref` e caminhos seguros; exemplos: `SESSION_EXPIRED`, `BASE_CONFLICT`, `ELIGIBILITY_UNKNOWN`, `CATALOG_CHANGED`, `METADATA_INVALID`, `REAL_RECEIVING_DISABLED`. Verificar origem antes de mutar; origem não substitui autorização. Cookies, CSRF e armazenamento de idempotência precisam de revisão antes de exposição real.


[Engineering index](index.pt-BR.md)
