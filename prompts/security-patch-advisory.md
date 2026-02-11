---
invokable: true
name: security-patch-advisory
dcc_uri: sec/prompts/security-patch-advisory
description: Generate a structured internal or external security advisory.
version: '0.1'
dcc_tags:
  - security
---

# Security Patch Advisory

You are preparing a formal security advisory for a resolved vulnerability.

## Objective
Generate a clear and structured advisory document.

## Required Sections

### Title
Short vulnerability summary.

### Affected Components
Systems, versions, endpoints.

### Severity
Low / Medium / High / Critical

### Description
Explain the vulnerability in clear terms.

### Impact
What could an attacker achieve?

### Resolution
What was changed or patched?

### Mitigation
Temporary workarounds (if applicable).

### Timeline
Discovery date, patch date, disclosure date.

### Credits
If applicable.

## Output Style
Clear, professional, concise. No sensitive internal secrets.
