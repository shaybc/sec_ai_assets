---
globs:
  - '**/*.ts'
  - '**/*.tsx'
  - '**/*.js'
  - '**/*.jsx'
name: Secure Cookies
dcc_uri: sec/rules/secure-cookies
description: Authentication cookies must define all security attributes explicitly.
version: '1.1'
dcc_definition_type: rule
dcc_tags:
  - security
---
# Secure Cookies

All sensitive cookies must be hardened.

- MUST set `httpOnly`.
- MUST set `secure` in production.
- MUST set explicit `sameSite`.
- MUST set explicit `path`.
- MUST set explicit expiration (`maxAge` or `expires`).
