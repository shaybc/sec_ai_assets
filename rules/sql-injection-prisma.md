---
name: sql-injection-prisma
description: Prevent SQL injection by using Prisma parameterization only.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/sql-injection-prisma
version: '1.0'
dcc_tags:
  - security
---

# SQL Injection Prevention

Database queries must be parameterized.

- MUST use Prisma query builder when possible.
- MUST use tagged template literals for raw queries.
- MUST NOT use `$queryRawUnsafe` with user input.
- MUST NOT concatenate SQL strings.
