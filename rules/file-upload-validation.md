---
globs:
  - '**/*.ts'
  - '**/*.tsx'
  - '**/*.js'
  - '**/*.jsx'
name: File Upload Validation
dcc_uri: sec/rules/file-upload-validation
description: File uploads must be strictly validated before processing.
version: '1.1'
dcc_definition_type: rule
dcc_tags:
  - security
---
# File Upload Validation

All uploads must be validated at the boundary.

- MUST enforce size limits.
- MUST enforce MIME allowlist.
- MUST enforce extension allowlist.
- SHOULD verify file signature (magic bytes).
- MUST reject invalid files before storage.
