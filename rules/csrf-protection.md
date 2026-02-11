---
name: csrf-protection
description: All state-changing requests must enforce CSRF validation.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/csrf-protection
version: '1.0'
dcc_tags:
  - security
---

# CSRF Protection

All state-changing requests must be CSRF-protected.

- MUST protect POST, PUT, PATCH, DELETE routes.
- MUST validate double-submit token.
- MUST use constant-time comparison.
- MUST generate tokens with ≥32 bytes entropy.
