# SocialFlow

**Tipo:** Plataforma SaaS
**Stack:** Monorepo (pnpm + TypeScript), Node.js 24, React, Redis, BullMQ
**Local:** `C:\Users\arino\OneDrive\Documentos\Projetos\SocialFlow`
**GitHub:** [DevArinoBorba/SocialFlow](https://github.com/DevArinoBorba/SocialFlow)

## Descrição

Plataforma SaaS de automação de redes sociais e gestão de conteúdo, com monorepo gerenciado via pnpm workspaces.

## Stack Técnica

- **Runtime:** Node.js 24
- **Gerenciador:** pnpm 11.19
- **Linguagem:** TypeScript 6.0
- **Frontend:** React
- **Fila:** BullMQ + Redis
- **Testes:** Vitest + Playwright
- **Linting:** ESLint + Prettier

## Estrutura

- `apps/` — Aplicações (web, API, etc.)
- `packages/` — Pacotes compartilhados
- `database/` — Banco de dados e migrações
- `docs/` — Documentação
- `infra/` — Infraestrutura
- `agents/` — Agentes e automações

## Comandos

```bash
pnpm install          # Instalar dependências
pnpm dev              # Desenvolvimento
pnpm build            # Build
pnpm test             # Testes unitários
pnpm test:integration # Testes de integração
pnpm test:e2e         # Testes E2E
pnpm lint             # Linting
pnpm format           # Formatação
pnpm db:migrate       # Migrações do banco
pnpm db:seed          # Seed do banco
```

## Scripts de Banco

```bash
pnpm db:generate  # Gerar tipos
pnpm db:migrate   # Aplicar migrações
pnpm db:seed      # Popular banco
pnpm db:bootstrap # Setup completo
```
