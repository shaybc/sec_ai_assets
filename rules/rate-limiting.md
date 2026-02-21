---
globs:
  - '**/*.ts'
  - '**/*.tsx'
  - '**/*.js'
  - '**/*.jsx'
name: Rate Limiting
dcc_uri: sec/rules/rate-limiting
description: APIs must enforce rate limiting to mitigate abuse.
version: '1.1'
dcc_definition_type: rule
dcc_tags:
  - security
---
# Rate Limiting

APIs must limit abuse and brute force.

- MUST apply general rate limiting to `/api/*`.
- MUST apply stricter limits to authentication endpoints.
- MUST use explicit window and max values.
- MUST return generic error messages.
