# ADR 001 — Cadastro de motoristas orientado por localização

[README](../README.pt-BR.md)

## Contexto

Projeto de cadastro mobile que vincula a oportunidade a uma base no servidor e valida elegibilidade antes da simulação de envio.

## Decisão

Vincular o escopo da oportunidade à sessão do servidor em vez de depender apenas de componentes ocultos na interface.

## Consequências

O escopo no servidor exige tratar o ciclo e a expiração da sessão; impede que o cliente selecione uma tabela operacional arbitrária.

## Limite da evidência

Existem handlers do protótipo no workspace privado. Esta edição pública documenta seus contratos; não inclui a aplicação nem uma implantação de produção.
