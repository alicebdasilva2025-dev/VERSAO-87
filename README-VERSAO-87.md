# LiDire — Versão 87

Implementado a partir da versão enviada como base (86):
- Substitui o símbolo ao lado das notificações familiares pelas iniciais LD.
- Permite excluir notificações recebidas, apenas da conta autenticada.
- Permite responder às notificações; a resposta é enviada ao remetente como nova notificação vinculada à original.
- Para notificações marcadas como `commitment` ou `commitment_change`, apresenta ações para confirmar ou sugerir alteração.
- Registra o estado da resposta na notificação original e preserva os registros de outras pessoas.

## Observações
- A rotina de compatibilidade do Worker adiciona as novas colunas sem apagar dados. Não é necessário recriar o banco D1.
- As ações de confirmar/sugerir aparecem quando a notificação contém `resource_type` igual a `commitment` ou `commitment_change`. A API de envio aceita `resourceType` e `resourceId` para vincular notificações a compromissos. O fluxo de criação automática de notificações a partir de compromissos já existentes não foi presumido; deve enviar esses campos ao criar a notificação.
- Verificação estática realizada; não houve deploy nem teste contra o D1 de produção.
