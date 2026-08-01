# MatchForge Documentation

> Central de documentação oficial do MatchForge.

---

# Índice

## 1. Setup

Documentação necessária para criar o ambiente de desenvolvimento.

| Documento | Descrição |
|------------|-----------|
| setup/00-repository-baseline.md | Estrutura oficial do repositório |
| setup/01-environment.md | Instalação do ambiente |
| setup/02-workspace.md | Configuração do Monorepo |
| setup/03-code-quality.md | Husky, Commitlint, Prettier |
| setup/04-react.md | Configuração React |
| setup/05-nest.md | Configuração NestJS |
| setup/06-prisma.md | Configuração Prisma |
| setup/07-docker.md | Infraestrutura Docker |

---

# 2. Architecture Book

Documentação conceitual do sistema.

| Documento | Descrição |
|------------|-----------|
| architecture-book/00-vision.md | Visão do produto |
| architecture-book/01-product.md | Funcionalidades |
| architecture-book/02-business-rules.md | Regras de negócio |
| architecture-book/03-user-flows.md | Fluxos |
| architecture-book/04-system-architecture.md | Arquitetura |
| architecture-book/05-technology-stack.md | Stack tecnológica |
| architecture-book/06-core-domain-model.md | CDM |
| architecture-book/07-bounded-context-map.md | BCM |
| architecture-book/08-module-dependencies.md | Dependências |
| architecture-book/09-schema-strategy.md | Estratégia Prisma |
| architecture-book/10-implementation-roadmap.md | Roadmap |
| architecture-book/11-coding-standards.md | Convenções |
| architecture-book/12-architecture-decisions.md | ADR resumido |
| architecture-book/glossary.md | Glossário |

---

# 3. ERD

Modelo de dados.

| Documento |
|------------|
| ERD-00 Foundation |
| ERD-01 Identity |
| ERD-02 Organization |
| ERD-03 Sports |
| ERD-04 Competition |
| ERD-05 Media |
| ERD-06 Design |
| ERD-07 Projects |
| ERD-08 Integrations |
| ERD-09 Publications |
| ERD-10 System |

---

# 4. DMS

Especificações técnicas dos módulos.

| Documento |
|------------|
| DMS-00 Foundation |
| DMS-01 Identity |
| DMS-02 Organization |
| DMS-03 Sports |
| DMS-04 Competition |
| DMS-05 Media |
| DMS-06 Design |
| DMS-07 Projects |
| DMS-08 Integrations |
| DMS-09 Publications |
| DMS-10 System |

---

# 5. ADR

Architecture Decision Records.

Cada decisão arquitetural possui um documento próprio.

Exemplo:

- ADR-001 Workspace
- ADR-002 Turborepo
- ADR-003 Prisma
- ADR-004 React
- ADR-005 NestJS

---

# 6. Coding Standards

Padrões utilizados no projeto.

| Documento | Descrição |
|------------|-----------|
| GIT.md | Git Flow |
| TYPESCRIPT.md | Convenções TS |
| REACT.md | Padrões React |
| NEST.md | Padrões NestJS |
| PRISMA.md | Convenções Prisma |
| API.md | Convenções REST |
| UI.md | Design System |

---

# 7. Assets

Diagramas oficiais.

- Arquitetura
- ERD
- Fluxos
- Wireframes
- Logos
- Ícones

---

# 8. Roadmap

## Foundation

- [ ] Workspace
- [ ] React
- [ ] NestJS
- [ ] Prisma
- [ ] Docker

## MVP

- [ ] Identity
- [ ] Organization
- [ ] Teams
- [ ] Players
- [ ] Championship
- [ ] Match
- [ ] Editor
- [ ] Export PNG

## Future

- [ ] Integração Copa Fácil
- [ ] Integração Jogueiros
- [ ] Mobile
- [ ] IA para geração de artes

---

# Fluxo de Desenvolvimento

```text
Setup
    ↓
Foundation
    ↓
Identity
    ↓
Organization
    ↓
Sports
    ↓
Competition
    ↓
Media
    ↓
Design Engine
    ↓
Projects
    ↓
Integrations
    ↓
Publications
    ↓
Release
```

---

# Documentação Oficial

Toda implementação deve seguir a seguinte ordem:

```
Architecture Book
        ↓
ERD
        ↓
DMS
        ↓
Implementação
        ↓
Testes
        ↓
Pull Request
        ↓
Merge
```

Nenhuma implementação deve ser iniciada sem documentação correspondente.
