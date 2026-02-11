---
name: file-upload-validation
description: File uploads must be strictly validated before processing.
globs: ["**/*.ts", "**/*.tsx", "**/*.js", "**/*.jsx"]
dcc_uri: sec/rules/file-upload-validation
version: '1.0'
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
