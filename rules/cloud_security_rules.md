---
alwaysApply: false
name: Cloud Security Rules
dcc_uri: sec/rules/cloud_security_rules
description: Security rules for cloud infrastructure, IAM, secrets, networking, CI/CD, and observability. Applies to developers, platform engineers, and admins working on cloud environments (AWS, GCP, Azure, Cloudflare, etc.).
version: '1.0.0'
dcc_tags:
  - dev
  - cloud
  - security
  - infra
---

# Cloud Security Rules

These rules apply to anyone writing infrastructure code, CI/CD pipelines, cloud configuration, or deployment scripts. They are not a compliance checklist — they are hard constraints on what gets generated and deployed.

---

## IAM & Access Control

- Never generate or suggest wildcard permissions (`s3:*`, `"*"`) or wildcard resources (`"Resource": "*"`). Always scope to the minimum actions and specific resource ARNs required.
- Never use root account credentials for any automated or programmatic task. Root is for account recovery only.
- Service accounts and automation must use short-lived credentials or role assumption (OIDC, instance profiles, workload identity). Never generate long-lived API keys for automated workloads.
- Never attach admin or power-user policies to a service role. If a task seems to require broad permissions, flag it and ask for the minimum viable scope instead.
- Apply IAM boundaries per environment: dev roles must not have access to production resources.

---

## Secrets Management

- Never emit secrets, API keys, passwords, or tokens inline in any generated code, config file, or IaC resource. Always reference them via a secrets manager (`secretsmanager:`, `vault:`, environment variable injection at runtime).
- Never store secrets in environment variable definitions inside version-controlled files (`.env`, `docker-compose.yml`, `values.yaml` committed to a repo). Reference them by name only; values live in the secrets manager.
- Do not log, print, or output secret values at any point — not in startup logs, not in debug output, not in error messages.
- Generated database credentials, API keys, and certificates must have rotation configured. A secret without a rotation plan is a latent breach.
- Secrets must be scoped per environment. A production secret must never be reachable from a dev or CI context.

---

## Network Security

- Never generate a security group, firewall rule, or network ACL that opens `0.0.0.0/0` on any port other than 80 and 443. Management ports (22, 3389, 5432, 3306, 6379, 27017, etc.) must never be open to the public internet.
- Databases, caches, and internal services must be placed in private subnets with no public IP. `publicly_accessible = true` on a database resource is never acceptable.
- Generate VPC flow logs and network ACLs as a default, not an afterthought.
- All inter-service traffic inside a VPC should use private DNS and security group references, not hardcoded IPs or public endpoints.
- Enforce TLS on every generated listener, load balancer, and service endpoint. Never generate an HTTP-only endpoint for anything other than a redirect to HTTPS.

---

## CI/CD Pipeline Security

- Always use OIDC-based authentication for CI/CD access to cloud providers. Never generate a workflow that stores a long-lived cloud access key as a CI secret.
- Generated pipeline workflows must request the minimum GitHub Actions / CI permissions needed (`permissions: contents: read` by default; expand only what the job requires).
- Every generated pipeline that deploys to production must include a dependency vulnerability scan and a secrets scan step.
- Pin all third-party actions and base images to a specific commit SHA or immutable tag. Never use `@latest` or a mutable branch reference.
- Separate build, test, and deploy jobs. A single job that builds and deploys without a test gate is never acceptable for production.

---

## Infrastructure as Code

- Every generated IaC resource that holds data (database, storage bucket, queue, cache) must have `deletion_protection` or its equivalent enabled.
- Storage buckets must default to private with explicit access policies. Never generate a public bucket unless the use case is explicitly a public static asset host, and even then block public ACLs and use a CDN in front.
- Enable encryption at rest on every generated storage resource (S3, RDS, EBS, etc.) using a managed or customer-managed key. Unencrypted storage resources must not be generated.
- Tag every generated resource with at minimum: `environment`, `service`, and `owner`. Untagged resources cannot be audited, cost-allocated, or cleaned up reliably.
- Never hardcode region, account ID, or environment-specific values in reusable modules. Parameterise them.

---

## Logging & Observability

- Every generated service deployment must include log forwarding to a centralised, tamper-evident log store. Logs that only exist on the instance are lost on restart.
- Audit logs (authentication events, admin actions, secret access, IAM changes) must be enabled and retained for a minimum of 90 days. Do not generate log configurations with shorter retention.
- Never log request bodies, response payloads, auth tokens, or PII fields. Log the event type, outcome, actor, resource, and correlation ID — nothing more.
- Generate CloudTrail / audit logging enablement as part of any account or project bootstrap. It must not be an optional add-on.
- Alerts must be generated alongside the resources they monitor. A deployment without an error rate alert or anomaly detection hook is incomplete.

---

## Backup & Recovery

- Every generated stateful resource (database, file store, message queue with persistence) must include an automated backup configuration with explicit retention.
- Backup retention must be at least 7 days for non-critical workloads and 30 days for anything handling user or financial data.
- Do not generate a disaster recovery configuration without defining both RPO and RTO, even as comments in the code.
- Backups in the same region as the source are not a disaster recovery strategy. Cross-region or cross-account replication must be included for production data.
