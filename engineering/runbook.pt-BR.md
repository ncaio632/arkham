# Roteiro ponta a ponta — arkham

Resumo de execução futura; [detalhes em inglês](runbook.en.md). Não há aplicativo nem comando executável neste pacote. Implementar primeiro os adaptadores e o harness com dados exclusivamente sintéticos.

1. Preparar armazenamento descartável e relógio controlado. Criar `SYN-BASE-A/B`, uma oportunidade por base e catálogo versão 1; o roteador fictício escolhe A sem usar localização real.
2. Regra de teste: `license_confirmed=true` produz elegível; false, inelegível; ausente, desconhecido. Não é regra jurídica ou operacional. Exigir categorias `identity` e `license`, limite 10 MiB e MIME PDF/JPEG/PNG. Recebimento real fica desativado.
3. Registrar revisão, versão da massa, relógio, ambiente e resultados esperados; manter `not_run` até execução observada.
4. Sem sessão, catálogo deve ser recusado. Iniciar sessão A, selecionar sua oportunidade aberta, avaliar respostas e validar as duas categorias. Snapshot esperado: `ready`, `eligible`, bases iguais e revisões atuais.
5. Enviar simulação com revisão e chave novas, da origem permitida. Exigir `simulation_only: true` e confirmação textual. Repetir após perda de conexão: mesmo comprovante e exatamente um registro na persistência.
6. Tentar mudar base ou selecionar oportunidade B: recusar sem dados de B. Expirar sessão e tentar cada mutação: exigir reinício. Negar GPS: oferecer tentativa/indisponibilidade, sem base automática.
7. Testar separadamente categoria ausente/duplicada, tamanho excessivo e MIME proibido: 422 sem comprovante. Alterar regra/catálogo antes do envio: 409 e reavaliação. Concorrência com mesma chave gera um resultado; chave reutilizada com outra carga gera conflito. Origem proibida: 403 antes de gravar. Recebimento real: 503 sem afirmar armazenamento.

Interromper diante de vazamento entre bases, recebimento real disponível ou dado pessoal no log. Guardar somente códigos e identificadores fictícios, desativar adaptador e descartar armazenamento de teste. Não corrigir conflito editando sessão manualmente. Cada evidência precisa de ID do requisito, entrada, esperado, observado, revisão, horário e resultado. Schema válido não comprova autorização nem atomicidade. Piloto real depende de políticas e revisões próprias.


[Engineering index](index.pt-BR.md)
