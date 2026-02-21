---
globs:
  - '**/*.ts'
  - '**/*.tsx'
  - '**/*.js'
  - '**/*.jsx'
name: No Error Leakage
dcc_uri: sec/rules/no-error-leakage
description: Errors must not expose internal details to clients.
version: '1.1'
dcc_definition_type: rule
dcc_tags:
  - security
---
# Error Handling

Errors must not leak internal information.

- MUST NOT return `error.message` or `error.stack`.
- MUST log full details server-side.
- MUST use generic user-facing messages.
- MUST prevent user enumeration in auth flows.
