---
name: oauth-oidc-validation
description: OAuth and OIDC flows must validate anti-CSRF and token parameters.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/oauth-oidc-validation
version: '1.0'
dcc_tags:
  - security
---

# OAuth / OIDC Validation

OAuth flows must validate all trust boundaries.

- MUST validate `state`.
- MUST validate `nonce`.
- MUST verify token `issuer`.
- MUST verify token `audience`.
- MUST use explicit algorithm allowlist.
