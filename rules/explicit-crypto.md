---
name: explicit-crypto
description: Cryptographic operations must use explicit secure algorithms.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/explicit-crypto
version: '1.0'
dcc_tags:
  - security
---

# Cryptography

Crypto defaults are forbidden.

- MUST explicitly specify hash, HMAC, and cipher algorithms.
- MUST use modern algorithms (e.g., sha256, aes-256-gcm).
- MUST NOT use deprecated algorithms (MD5, SHA1, DES, RC4).
- MUST prefer authenticated encryption modes.
