# Serviço de Notificações

Identifica a mudança de status e envia a mensagem pelo canal do cliente (app, e-mail ou WhatsApp). Usa o padrão **Strategy**: interface `Canal` com `enviar(notificacao)` e as classes `CanalApp`, `CanalEmail` e `CanalWhatsApp` (RF04).
