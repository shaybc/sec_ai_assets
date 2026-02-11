---
globs:
  - '**/*.ts'
  - '**/*.tsx'
  - '**/*.js'
  - '**/*.jsx'
name: Password Hashing Policy
dcc_uri: sec/rules/password-hashing-policy
description: Passwords must be hashed using bcrypt or argon2 with explicit cost parameters.
version: '1.1'
dcc_tags:
  - security
---
# Password Hashing

Passwords must use dedicated hashing algorithms.

- MUST use bcrypt (≥12 rounds) or argon2id.
- MUST explicitly configure cost parameters.
- MUST NOT use general-purpose hashes (SHA256, MD5).
