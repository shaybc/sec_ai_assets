---
name: rate-limiting
description: APIs must enforce rate limiting to mitigate abuse.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/rate-limiting
version: '1.0'
dcc_tags:
  - security
---

# Rate Limiting

APIs must limit abuse and brute force.

- MUST apply general rate limiting to `/api/*`.
- MUST apply stricter limits to authentication endpoints.
- MUST use explicit window and max values.
- MUST return generic error messages.
