---
globs:
  - '**/*.ts'
  - '**/*.tsx'
  - '**/*.js'
  - '**/*.jsx'
name: CSRF Protection
dcc_uri: sec/rules/csrf-protection
description: All state-changing requests must enforce CSRF validation.
version: '1.1'
dcc_definition_type: rule
dcc_tags:
  - security
---
# CSRF Protection

All state-changing requests must be CSRF-protected.

- MUST protect POST, PUT, PATCH, DELETE routes.
- MUST validate double-submit token.
- MUST use constant-time comparison.
- MUST generate tokens with ≥32 bytes entropy.
