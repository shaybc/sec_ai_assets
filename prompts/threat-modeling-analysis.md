---
name: Threat Modeling Analysis
dcc_uri: sec/prompts/threat-modeling-analysis
version: '0.2'
schema: ''
description: Perform structured threat modeling for a new feature or system change.
dcc_definition_type: prompt
dcc_tags:
  - security
invokable: true
prompt: >-
  # Threat Modeling


  You are acting as a security architect.


  ## Objective

  Analyze the provided feature/system and identify security threats and
  mitigations.


  ## Step 1: System Overview

  - Describe the feature

  - Identify assets (data, credentials, services)

  - Identify entry points (API, UI, webhooks, queues)


  ## Step 2: Trust Boundaries

  List all trust boundaries crossed.


  ## Step 3: Threat Analysis (STRIDE)

  For each category:

  - Spoofing

  - Tampering

  - Repudiation

  - Information Disclosure

  - Denial of Service

  - Elevation of Privilege


  List potential threats.


  ## Step 4: Risk Assessment

  - Likelihood (Low/Medium/High)

  - Impact (Low/Medium/High)


  ## Step 5: Mitigation Plan

  For each threat:

  - Recommended controls

  - Required security mechanisms

  - Monitoring/logging needs


  ## Output

  Structured markdown report with risks and mitigations.
---

