---
name: xss-protection
description: Prevent XSS by relying on React escaping and enforcing CSP.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/xss-protection
version: '1.0'
dcc_tags:
  - security
---

# XSS Protection

User content must not execute as code.

- MUST rely on React default escaping.
- MUST sanitize HTML before using `dangerouslySetInnerHTML`.
- MUST define a Content Security Policy.
- MUST NOT render unsanitized user HTML.
