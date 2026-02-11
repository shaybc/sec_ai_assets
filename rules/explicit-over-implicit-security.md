---
name: explicit-over-implicit-security
description: Security-critical behavior must always be explicitly configured.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/explicit-over-implicit-security
version: '1.0'
dcc_tags:
  - security
---

# Explicit Over Implicit

Security-sensitive APIs must never rely on defaults.

- MUST explicitly configure algorithms, modes, issuers, audiences, expirations.
- MUST use allowlists, not blocklists.
- MUST NOT trust attacker-controlled headers or inferred configuration.
