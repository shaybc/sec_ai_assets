---
globs:
  - '**/*.ts'
  - '**/*.tsx'
  - '**/*.js'
  - '**/*.jsx'
name: SQL Injection Prisma
dcc_uri: sec/rules/sql-injection-prisma
description: Prevent SQL injection by using Prisma parameterization only.
version: '1.1'
dcc_definition_type: rule
dcc_tags:
  - security
---
# SQL Injection Prevention

Database queries must be parameterized.

- MUST use Prisma query builder when possible.
- MUST use tagged template literals for raw queries.
- MUST NOT use `$queryRawUnsafe` with user input.
- MUST NOT concatenate SQL strings.
