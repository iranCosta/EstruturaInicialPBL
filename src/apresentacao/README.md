# Camada de Apresentação

Interfaces com o usuário. Não contém regra de segurança: toda verificação é feita no backend.

- `app-mobile/`: login, abertura de chamados, acompanhamento e notificações (RF01–RF04).
- `chatbot/`: Interface Chatbot (WhatsApp/Telegram) que envia solicitações ao sistema (RF02).
- `painel-acompanhamento/`: Painel web onde o cliente vê chamados, histórico e status (RF03, RF05).
- `painel-atendente/`: Painel do Atendente: chamados, observações, alteração de status e alerta de SLA.
