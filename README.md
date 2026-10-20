# SuporteTech

Sistema de gerenciamento de chamados de suporte técnico. O cliente abre chamados (app mobile, painel web ou chatbot no WhatsApp/Telegram), acompanha o status e recebe notificações. O atendente trata os chamados, registra observações e vê os que estão perto de vencer o prazo de SLA. Toda alteração é auditada.

> Projeto PBL — Arquitetura e Modelagem de Sistemas (SENAI) — **Grupo G**.
> Professor: Abraão de Oliveira Ferreira.

## Integrantes

- Ederlane
- Iran
- Christoffer Henrique da Silva Souza
- Ferdinando
- Paulo Ricardo Wosniak Soares

## Requisitos atendidos pelo design

| Código | Requisito |
|--------|-----------|
| RF01 | Gestão de usuários (cadastro, login e perfis de cliente e atendente) |
| RF02 | Abertura de chamados, com número de protocolo único |
| RF03 | Acompanhamento de status pelo cliente |
| RF04 | Notificação de atualização (app, e-mail ou WhatsApp) |
| RF05 | Categorização e histórico do chamado |
| RNF01 | Segurança (autenticação segura e isolamento dos dados de cada cliente) |
| RNF02 | Rastreabilidade e auditoria (logs inalteráveis com data, hora e autor) |
| RNF03 | Disponibilidade 24x7 |

## Arquitetura

O sistema segue o **design em quatro camadas** definido no Refino do Design (diagrama em [`docs/`](docs/)). A estrutura de `src/` e `tests/` espelha essas camadas:

```
src/
├── apresentacao/     # App Mobile, Interface Chatbot, Painel de Acompanhamento (Web), Painel do Atendente
├── aplicacao/        # API Gateway, Gestão de Usuários, Gestão de Chamados, Serviço de Notificações, Serviço de Auditoria
├── dominio/          # Entidades de Domínio, Regras de SLA, Validador de Permissões (LGPD)
└── infraestrutura/   # Repositório (PostgreSQL), Log de Auditoria, Adaptadores de Canal, Gateway de Mensageria
```

Decisões principais do design:

- **API Gateway** como entrada única: HTTPS, validação de token e limite de requisições.
- **Autenticação via provedor de identidade** (OAuth 2.0 + OpenID Connect com PKCE), sem login próprio.
- **Auditoria separada**: Serviço de Auditoria + Log de Auditoria com tabela **somente de inserção** (RNF02).
- **Regras de SLA** com várias políticas (por categoria e prioridade) e alerta antes do vencimento.
- **Padrão Strategy** nas notificações: interface `Canal` com `CanalApp`, `CanalEmail` e `CanalWhatsApp`.
- **Validador de Permissões (LGPD)** no backend: cada cliente só acessa os próprios chamados.

## Estrutura do repositório

| Caminho | Finalidade |
|---------|------------|
| `docs/` | Requisitos, diagramas, refino do design e decisões de arquitetura |
| `src/` | Código-fonte, organizado nas 4 camadas do design |
| `tests/` | Testes automatizados, espelhando `src/` |
| `.env.example` | Modelo de variáveis de ambiente (sem credenciais reais) |
| `.gitignore` | Arquivos que não devem ser versionados |

## Tecnologias previstas

- Banco de dados: PostgreSQL
- Execução e disponibilidade: Docker
- Autenticação: OAuth 2.0 / OpenID Connect
- Canais de notificação: push, e-mail, WhatsApp e Telegram
- Modelagem: UML (draw.io) · Versionamento: Git/GitHub

## Preparação inicial

1. Clone o repositório:
   ```bash
   git clone <URL-DO-REPOSITORIO>
   cd suportetech
   ```
2. Crie o arquivo de ambiente a partir do modelo:
   ```bash
   cp .env.example .env
   ```
3. Preencha o `.env` com os valores do seu ambiente. **Nunca** faça commit dele.
4. As instruções de execução (Docker, banco e dependências) serão adicionadas conforme a implementação avançar.

## Versionamento

- `main`: versão estável.
- Novas funcionalidades em branches `feature/<nome>`.
- Commits descritivos no padrão `tipo: descrição` (`feat`, `fix`, `docs`, `chore`, `test`).

## Status

Fase inicial: estrutura do repositório criada a partir do design refinado.
