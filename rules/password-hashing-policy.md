---
name: password-hashing-policy
description: Passwords must be hashed using bcrypt or argon2 with explicit cost parameters.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/password-hashing-policy
version: '1.0'
dcc_tags:
  - security
---

# Password Hashing

Passwords must use dedicated hashing algorithms.

- MUST use bcrypt (≥12 rounds) or argon2id.
- MUST explicitly configure cost parameters.
- MUST NOT use general-purpose hashes (SHA256, MD5).
