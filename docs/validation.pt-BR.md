# Estratégia de validação

[README](../README.pt-BR.md)

| Cenário | Comportamento esperado |
| --- | --- |
| Missing session | Rejeitar antes de retornar dados da oportunidade ou inscrição |
| Base change | Retornar conflito em vez de substituir o vínculo |
| Real receiving disabled | Retornar indisponibilidade; não indicar armazenamento documental |
| Invalid document metadata | Rejeitar tamanho, tipo ou documento obrigatório inválido |

## Política de evidência

Registrar revisão, ambiente, classe de entrada, resultado esperado e observado para cada verificação executada. Separar cenários planejados de resultados medidos. Testes do backup privado e verificações desta documentação não certificam prontidão do produto, resultados de campanhas ou segurança de produção.
