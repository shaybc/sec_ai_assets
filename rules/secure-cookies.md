---
name: secure-cookies
description: Authentication cookies must define all security attributes explicitly.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/secure-cookies
version: '1.0'
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
