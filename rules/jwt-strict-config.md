---
globs:
  - '**/*.ts'
  - '**/*.tsx'
  - '**/*.js'
  - '**/*.jsx'
name: JWT Strict Config
dcc_uri: sec/rules/jwt-strict-config
description: JWT signing and verification must use explicit secure configuration.
version: '1.1'
dcc_tags:
  - security
---
# JWT Strict Configuration

JWT usage must be strict and explicit.

- MUST set explicit `algorithm` when signing.
- MUST set explicit `expiresIn`.
- MUST verify with `algorithms` allowlist.
- MUST validate `issuer` and `audience`.
- MUST NOT disable expiration validation.
