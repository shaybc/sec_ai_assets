---
name: Dependency Security Review
dcc_uri: sec/prompts/dependency-security-review
version: '0.2'
schema: ''
description: Analyze dependencies and supply chain risks.
dcc_definition_type: prompt
dcc_tags:
  - security
invokable: true
prompt: |-
  # Dependency Security Review

  You are performing a dependency risk analysis.

  ## Tasks

  1. Identify outdated dependencies.
  2. Identify known CVEs (if version known).
  3. Check for risky packages (low maintenance, high privilege).
  4. Evaluate transitive dependencies risk.
  5. Recommend upgrade or replacement.

  ## Output

  ### High Risk Dependencies
  ### Medium Risk Dependencies
  ### Recommended Actions
  ### Monitoring Strategy
---

