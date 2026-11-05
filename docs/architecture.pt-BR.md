# Arquitetura

[README](../README.pt-BR.md)

## Fluxo de processamento

```text
Location input → validated session → base-scoped opportunity → eligibility → required document metadata → simulated receipt
```

## Invariantes

1. A sessão estabelece a base no servidor; o endpoint de oportunidade consulta essa sessão.
2. Uma sessão não pode trocar silenciosamente de base; o handler consultado retorna 409.
3. O envio rejeita solicitações sem sessão válida e verifica solicitações de mesma origem.
4. O handler consultado aceita metadados documentais em demonstração; o recebimento real fica desativado com 503.
5. A proximidade GPS é uma entrada de roteamento, não prova de identidade, residência ou elegibilidade profissional.

## Limite da implementação

Existem handlers do protótipo no workspace privado. Esta edição pública documenta seus contratos; não inclui a aplicação nem uma implantação de produção.
