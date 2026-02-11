---
name: secrets-policy
description: Secrets must never be exposed and must be securely validated and rotated.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/secrets-policy
version: '1.0'
dcc_tags:
  - security
---

# Secrets Management

Secrets must be handled defensively.

- MUST load secrets from environment variables.
- MUST validate required env vars at startup.
- MUST NOT log or return secrets.
- MUST use constant-time comparison for secret checks.
- MUST support secret rotation (current + previous).
- MUST ignore `.env`, `.key`, `.pem` in git.
