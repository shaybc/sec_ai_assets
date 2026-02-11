---
name: no-error-leakage
description: Errors must not expose internal details to clients.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/no-error-leakage
version: '1.0'
dcc_tags:
  - security
---

# Error Handling

Errors must not leak internal information.

- MUST NOT return `error.message` or `error.stack`.
- MUST log full details server-side.
- MUST use generic user-facing messages.
- MUST prevent user enumeration in auth flows.
