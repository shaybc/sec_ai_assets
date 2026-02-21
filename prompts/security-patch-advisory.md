---
name: Security Patch Advisory
dcc_uri: sec/prompts/security-patch-advisory
version: '0.2'
schema: ''
description: Generate a structured internal or external security advisory.
dcc_definition_type: prompt
dcc_tags:
  - security
invokable: true
prompt: |-
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
---

