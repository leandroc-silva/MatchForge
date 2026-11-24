# ERD-00 — Foundation

## Status

Definido e congelado para implementação inicial.

## Objetivo

O ERD-00 Foundation define estruturas transversais compartilhadas pelos
demais módulos do MatchForge.

Este módulo não implementa entidades de negócio de Identity, Organization,
Sports, Competition ou Media.

---

# 1. Entidade conceitual BaseEntity

BaseEntity não representa uma tabela física.

É uma convenção reutilizada pelas entidades que necessitam de auditoria,
versionamento e soft delete.

Campos conceituais:

| Campo       | Tipo         | Obrigatório | Descrição                            |
| ----------- | ------------ | ----------: | ------------------------------------ |
| id          | UUID         |         Sim | Identificador único                  |
| createdAt   | DateTime UTC |         Sim | Data de criação                      |
| updatedAt   | DateTime UTC |         Sim | Data da última atualização           |
| deletedAt   | DateTime UTC |         Não | Data do soft delete                  |
| createdById | UUID         |         Não | Identificador do criador             |
| updatedById | UUID         |         Não | Identificador do último editor       |
| version     | Int          |         Sim | Controle de versão                   |
| metadata    | JSON         |         Não | Dados complementares não estruturais |

## Regras

- UUID é o padrão para identificadores.
- Datas são armazenadas em UTC.
- Soft delete utiliza `deletedAt`.
- `version` inicia em 1.
- `metadata` deve ser usado apenas para dados que não justificam uma coluna
  estruturada.
- `createdById` e `updatedById` não possuem relação física nesta etapa,
  pois a entidade User pertence ao módulo Identity.

---

# 2. Entidade AuditLog

## Objetivo

Registrar eventos relevantes de criação, alteração, exclusão, autenticação
e outras ações auditáveis.

## Modelo conceitual

| Campo          | Tipo         | Obrigatório | Descrição                         |
| -------------- | ------------ | ----------: | --------------------------------- |
| id             | UUID         |         Sim | Identificador do registro         |
| action         | String       |         Sim | Ação executada                    |
| entityType     | String       |         Sim | Tipo da entidade afetada          |
| entityId       | UUID/String  |         Não | Identificador da entidade afetada |
| actorId        | UUID         |         Não | Identificador do agente           |
| organizationId | UUID         |         Não | Organização relacionada           |
| previousData   | JSON         |         Não | Estado anterior                   |
| newData        | JSON         |         Não | Estado posterior                  |
| metadata       | JSON         |         Não | Contexto adicional                |
| ipAddress      | String       |         Não | IP da origem                      |
| userAgent      | String       |         Não | User-Agent da origem              |
| createdAt      | DateTime UTC |         Sim | Momento do evento                 |

## Regras

- AuditLog é append-only.
- Registros de auditoria não utilizam `updatedAt`.
- Registros de auditoria não utilizam soft delete.
- `actorId` não possui relação física nesta etapa.
- `organizationId` não possui relação física nesta etapa.
- A ausência dessas relações permite que Identity e Organization sejam
  implementados posteriormente sem dependência circular.

---

# 3. Índices

## AuditLog

Índices:

- `entityType + entityId`
- `actorId`
- `organizationId`
- `action`
- `createdAt`

---

# 4. Relacionamentos

Nesta versão não existem relacionamentos físicos entre entidades.

Referências a:

- actorId
- organizationId
- createdById
- updatedById

serão integradas posteriormente quando os módulos proprietários dessas
entidades forem implementados.

---

# 5. Limites do módulo

O ERD-00 não contém:

- User
- Login
- Telefone
- SMS
- Role
- Permission
- Organization
- Team
- Player
- Championship
- Match

Essas entidades serão definidas nos respectivos ERDs de domínio.

---

# 6. Implementação Prisma

Nesta etapa será criada apenas uma tabela física:

- AuditLog

BaseEntity permanecerá como convenção de modelagem, não como tabela.
