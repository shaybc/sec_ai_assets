---
name: XSS Protection
dcc_uri: sec/rules/xss-protection
description: Prevent XSS by relying on React escaping and enforcing CSP.
version: '1.2'
globs:
  - '**/*.ts'
  - '**/*.tsx'
  - '**/*.js'
  - '**/*.jsx'
regex: ''
alwaysApply: true
dcc_definition_type: rule
dcc_tags:
  - security
---
# XSS Protection

User content must not execute as code.

- MUST rely on React default escaping.
- MUST sanitize HTML before using `dangerouslySetInnerHTML`.
- MUST define a Content Security Policy.
- MUST NOT render unsanitized user HTML.
