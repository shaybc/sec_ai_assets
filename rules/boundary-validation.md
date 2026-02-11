---
name: boundary-validation
description: All external input must be validated at system boundaries.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/boundary-validation
version: '1.0'
dcc_tags:
  - security
---

# Input Validation

All external input must be validated before use.

- MUST validate at request boundary.
- MUST use explicit constraints (length, format, enum).
- MUST use safe parsing.
- MUST NOT expose validation internals to users.
