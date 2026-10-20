# Camada de Domínio / Negócio

Regras de negócio, independentes de interface e de banco.

- `entidades/`: Cliente, Atendente, Chamado, Categoria e Histórico.
- `sla/`: Regras de SLA (várias políticas por categoria e prioridade, com alerta antes do vencimento).
- `permissoes/`: Validador de Permissões (LGPD).
