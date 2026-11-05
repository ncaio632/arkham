![arkham](assets/header.svg)

# arkham

### Cadastro de motoristas orientado por localização

[English](README.md) · [Português (Brasil)](README.pt-BR.md) · [日本語](README.ja.md)


Projeto de cadastro mobile que vincula a oportunidade a uma base no servidor e valida elegibilidade antes da simulação de envio.

## Escopo

Existem handlers do protótipo no workspace privado. Esta edição pública documenta seus contratos; não inclui a aplicação nem uma implantação de produção.

## Notas de engenharia

- [Arquitetura e invariantes](docs/architecture.pt-BR.md)
- [Contratos de dados](docs/contracts.pt-BR.md)
- [Registro de decisão técnica](docs/decisions.pt-BR.md)
- [Estratégia de validação](docs/validation.pt-BR.md)
- [Exemplo sintético de contrato](examples/contract.json)

## Guia de leitura

Comece pela arquitetura, consulte o exemplo de contrato e depois leia o compromisso da decisão e a matriz de validação. Os cenários descrevem o que deve ser verificado; não afirmam que uma implementação pública executável passou nesses testes.

## Limite da publicação

Esta edição técnica exclui cadastros privados, exportações de contas, caminhos da máquina, conversas e objetos históricos de backup. O acervo operacional original permanece um ativo privado separado.
