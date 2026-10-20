# SuporteTech

Sistema web de gerenciamento de chamados de suporte técnico. Permite que usuários abram solicitações de suporte, que técnicos acompanhem, atendam e atualizem o andamento dos chamados, e que a administração tenha visão geral do atendimento.

> Projeto desenvolvido em PBL (Aprendizagem Baseada em Projetos) no SENAI.

## Integrantes

- Ederlane
- Iran
- Christoffer
- Ferdinando
- Paulo

## Funcionalidades principais

- Abertura de chamados de suporte técnico
- Acompanhamento do status e histórico de cada chamado
- Atribuição e atendimento de chamados por técnicos
- Autenticação e controle de acesso por perfil de usuário
- Consulta e filtragem de chamados

> A lista completa de requisitos funcionais e não funcionais está em [`docs/`](docs/).

## Estrutura do repositório

```
suportetech/
├── docs/     # Documentação: requisitos, diagramas UML, protótipo e decisões de design
├── src/      # Código-fonte do sistema
├── tests/    # Testes automatizados
├── .env.example
├── .gitignore
└── README.md
```

| Pasta    | Finalidade                                                                 |
|----------|----------------------------------------------------------------------------|
| `docs/`  | Artefatos de modelagem e documentação (AV2, refino do design, protótipo).  |
| `src/`   | Implementação do sistema, organizada conforme o design do projeto.         |
| `tests/` | Testes que espelham a estrutura de `src/`.                                 |

## Preparação inicial

1. Clone o repositório:
   ```bash
   git clone <URL-DO-REPOSITORIO>
   cd suportetech
   ```
2. Crie o arquivo de variáveis de ambiente a partir do modelo:
   ```bash
   cp .env.example .env
   ```
3. Edite o `.env` com os valores do seu ambiente local. **Nunca** faça commit do `.env`.
4. Instale as dependências e execute o projeto (instruções detalhadas serão adicionadas em `src/` conforme a implementação avançar).

## Fluxo de versionamento

- Branch `main`: versão estável.
- Novas funcionalidades em branches próprias (`feature/nome-da-funcionalidade`).
- Mensagens de commit descritivas, preferencialmente no padrão `tipo: descrição` (ex.: `feat:`, `fix:`, `docs:`, `chore:`).

## Status

Em fase inicial: estrutura do repositório criada a partir do design elaborado nas etapas anteriores do projeto.
