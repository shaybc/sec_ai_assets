---
invokable: true
name: threat-modeling-analysis
dcc_uri: sec/prompts/threat-modeling-analysis
description: Perform structured threat modeling for a new feature or system change.
version: '0.1'
dcc_tags:
  - security
---

# Threat Modeling

You are acting as a security architect.

## Objective
Analyze the provided feature/system and identify security threats and mitigations.

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
