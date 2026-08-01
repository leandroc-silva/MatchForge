# MatchForge — Repository Baseline v1.0

## Objetivo

Este documento define a estrutura mínima obrigatória do repositório antes do início do desenvolvimento.

Nenhuma aplicação (React, NestJS, Prisma etc.) deve ser criada antes que toda esta estrutura esteja concluída.

---

# Estrutura do Repositório

```text
MatchForge/
│
├── .github/
│   ├── ISSUE_TEMPLATE/
│   └── workflows/
│
├── .husky/
│
├── apps/
│   ├── api/
│   └── web/
│
├── docs/
│   ├── adr/
│   ├── architecture-book/
│   ├── assets/
│   ├── dms/
│   ├── erd/
│   ├── setup/
│   └── standards/
│
├── infrastructure/
│   ├── docker/
│   ├── nginx/
│   └── scripts/
│
├── packages/
│   ├── config/
│   │   ├── eslint/
│   │   ├── prettier/
│   │   └── tsconfig/
│   │
│   ├── core/
│   ├── shared/
│   └── ui/
│
├── prisma/
│   ├── migrations/
│   ├── schema/
│   └── seed/
│
├── tools/
│
├── .vscode/
│
├── .commitlintrc.cjs
├── .editorconfig
├── .env.example
├── .gitignore
├── .npmrc
├── .prettierignore
├── .prettierrc
├── CHANGELOG.md
├── docker-compose.yml
├── LICENSE
├── package.json
├── pnpm-lock.yaml
├── pnpm-workspace.yaml
├── README.md
├── tsconfig.base.json
└── turbo.json
```

---

# Arquivos Obrigatórios

## Configuração

- package.json
- pnpm-workspace.yaml
- turbo.json
- tsconfig.base.json

---

## Git

- .gitignore
- .editorconfig
- .commitlintrc.cjs

---

## Ambiente

- .env.example
- .npmrc

---

## Formatação

- .prettierrc
- .prettierignore

---

## Documentação

- README.md
- CHANGELOG.md
- LICENSE

---

## Docker

- docker-compose.yml

---

# Diretórios Obrigatórios

## Aplicações

- apps/api
- apps/web

---

## Packages

- packages/config
- packages/core
- packages/shared
- packages/ui

---

## Prisma

- prisma/migrations
- prisma/schema
- prisma/seed

---

## Documentação

- docs/architecture-book
- docs/adr
- docs/assets
- docs/dms
- docs/erd
- docs/setup
- docs/standards

---

## Infraestrutura

- infrastructure/docker
- infrastructure/nginx
- infrastructure/scripts

---

## Ferramentas

- tools

---

# Critérios de Aceitação

Antes de iniciar qualquer desenvolvimento:

- Estrutura criada
- Git inicializado
- Workspace configurado
- pnpm funcionando
- Turborepo funcionando
- Husky configurado
- Commitlint configurado
- Prettier configurado

---

# Próxima Etapa

Após validar esta baseline, iniciar:

DMS-00 Foundation

1. Workspace
2. React
3. NestJS
4. Prisma
5. Docker
6. Health Check
