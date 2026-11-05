# Requisitos — arkham

Resumo acionável em português. A [versão inglesa](requirements.en.md) contém a especificação completa. O alvo proposto deriva da [arquitetura pública](../docs/architecture.pt-BR.md); os módulos e verificações abaixo não são declarados implementados. O repositório público contém documentação, sem aplicativo.

O fluxo deve ligar uma sessão a uma base escolhida no servidor, mostrar uma oportunidade dessa base, explicar elegibilidade e emitir somente um comprovante de simulação. GPS orienta roteamento; não comprova identidade, residência ou habilitação profissional.

| ID | Critério obrigatório proposto |
| --- | --- |
| A01 | Exigir sessão antes do catálogo. Política de roteamento versionada define `base_code`. Sessão ausente/expirada: 401; roteamento negado: 403; localização malformada: 422. |
| A02 | Base imutável na sessão; ignorar seleção de base pelo cliente. Mudança: 409 e reinício explícito. |
| A03 | Latitude finita −90..90, longitude −180..180, precisão positiva. Permissão negada deve permitir nova tentativa, sem base padrão silenciosa. |
| A04 | Regras versionadas retornam `eligible`, `ineligible` ou `unknown` com motivos. Ausência de resposta continua desconhecida e bloqueia prontidão. |
| A05 | Oportunidade e documentos pertencem à mesma base/revisão. Revalidar disponibilidade e regras no envio; alteração: 409 e redescoberta. |
| A06 | Somente metadados fictícios: limite proposto de 10 MiB por item; PDF/JPEG/PNG; categorias completas, únicas. Tipo/tamanho/categoria inválida: 422. |
| A07 | Envio simulado exige mesma origem, sessão válida, elegibilidade atual e chave de idempotência. Origem inválida: 403; pré-condição: 409; recebimento real desativado: 503. |
| A08 | Comprovante inclui `simulation_only: true`. Mesma chave e carga retorna mesmo comprovante; carga alterada: 409. |
| A09 | Registrar somente códigos, revisão e referência de correlação; excluir coordenadas, documentos e respostas. |

A interface mostra base, motivos e “simulação”. Atualizar a página recupera estado do servidor. Cancelar invalida a sessão e remove o rascunho transitório conforme política futura. Antes de implementar, responsáveis devem definir fronteiras geográficas, precisão mínima, duração de sessão, regras, categorias e retenção. O limite e MIME acima são escolhas para demonstração sintética; não representam política operacional validada. Não há tecnologia ou provedor escolhido.


[Engineering index](index.pt-BR.md)
