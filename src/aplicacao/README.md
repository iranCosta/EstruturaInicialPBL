# Camada de Aplicação

Orquestra os casos de uso e expõe a API do sistema.

- `api-gateway/`: entrada única (HTTPS, validação de token, limite de requisições).
- `gestao-usuarios/`: cadastro, perfis e consentimento LGPD; login delegado ao provedor de identidade.
- `gestao-chamados/`: recebe o chamado, valida, gera protocolo único, associa categoria e atualiza status.
- `servico-notificacoes/`: detecta mudança de status e envia pelo canal do cliente (padrão Strategy).
- `servico-auditoria/`: registra data, hora e autor de toda alteração em um chamado.
