# Backlog e rastreabilidade — arkham

Resumo acionável da [versão completa](delivery-validation.en.md). As verificações de produto estão **planejadas, não executadas**. Os [papéis](../agents/session-scope-steward.md) especificam responsabilidades manuais, sem chamadas automáticas.

| Ordem | Entrega e aceitação |
| --- | --- |
| B1 | Versionar regras sintéticas de roteamento, expiração, elegibilidade e documentos; distinguir ausência de negação e registrar políticas pendentes. |
| B2 após B1 | Validar entrada, fixar base, expirar sessão e revogar escopo antigo no reinício; nenhum log com localização bruta. |
| B3 após B2 | Catálogo somente da base; avaliação de três estados; trocar oportunidade limpa prontidão dependente. |
| B4 após B3 | Validar metadados e apresentar recuperação acessível; atualização lê servidor; não afirmar upload. |
| B5 após B4 | Verificar origem e revisões na gravação atômica; garantir uma simulação por seleção; recebimento real fechado. |
| B6 após B5 | Executar roteiro, registrar falhas/resultados e obter revisão independente com dados fictícios. |

| Requisito | Verificação planejada e observação |
| --- | --- |
| A01 | Sessão ausente/expirada ou rota negada: recusa sem catálogo/comprovante. |
| A02 | Manipular base e oportunidade, inclusive concorrência: manter A e não mostrar B. |
| A03 | Limites de coordenadas, permissão ausente, precisão não positiva: rejeição explícita. |
| A04 | true/false/ausente e mudança de regra: três resultados, unknown nunca pronto. |
| A05 | Fechar oportunidade/mudar catálogo antes de enviar: 409 e nenhuma gravação. |
| A06 | 10 MiB e 10 MiB+1, categoria ausente/duplicada: aceitar só conjunto permitido. |
| A07 | Origem proibida/revisão antiga/modo real: 403/409/503 sem mutar. |
| A08 | Mesma chave concorrente, carga alterada e segunda chave: um comprovante, conflito quando aplicável. |
| A09 | Inspecionar erros/logs: sem coordenadas, respostas ou documentos. |

[Snapshot válido](../examples/snapshot.valid.json) é fictício. [Forma inválida](../examples/snapshot.invalid-schema.json) excede tamanho e deve falhar em `documents[0].size_bytes`. [Semântica inválida](../examples/snapshot.invalid-semantic.json) passa o [schema](../contracts/onboarding-snapshot.schema.json), mas a oportunidade B em sessão A exige `BASE_CONFLICT`.

Usar validador Draft 2020-12; parse JSON não basta. Igualdade de bases, relógio, cobertura de categorias externas e autorização precisam de validação de domínio. Padrões de identificador são só para massas públicas, sem valor de segurança. Evidência futura deve registrar IDs do teste/requisito, revisão, massa, ambiente, esperado, observado, revisor e estado explícito `not_run/pass/fail/blocked`. A saída é uma implementação sintética revisada; produção permanece pendente de políticas, ameaças, acessibilidade, hospedagem e recuperação.


[Engineering index](index.pt-BR.md)
