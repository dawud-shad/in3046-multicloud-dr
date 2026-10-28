# Decision log

One entry per decision: date, what we decided, what we rejected, and why.

## Research paper 2026-10-21
**Chosen:** Li et al. (2025), multi-cloud HA and disaster recovery. Approved by module lead.
**Rejected:** federated-learning load balancing (Chennam 2025); ML Kubernetes scheduling (Dakić 2025).

## Repository
**Chosen:** GitHub - one repo for code and docs.
**Rejected:** separate docs repo (extra overhead); Drive-only (no version control evidence).

## Cloud providers
**Chosen:** AWS + Google Cloud.
**Reasons:** both are used on the module; GCP education credits available; covers multi-cloud requirement.

## Repository structure 2026-10-28
**Chosen:** `backend/` and `frontend/` as top-level siblings. The previous `app/` directory became `backend/`.
**Rejected:** `app/` as backend with `frontend/` alongside it (reads as asymmetric); `app/backend/` + `app/frontend/` (implies one deployable, which a static dashboard and a live service are not).
**Reasons:** symmetric naming, and each half deploys and is evidenced separately. Renamed before any code landed so the history stays readable.

## Infrastructure as code 2026-10-28
**Chosen:** Terraform, one root module per cloud in `infra/terraform/{aws,gcp}/`, shared modules in `infra/terraform/modules/`.
**Rejected:** Pulumi (adds a second language runtime for little gain); CloudFormation + Deployment Manager (two unrelated toolchains, no shared module story).
**Reasons:** one tool and one reviewable diff style across both providers is the least machinery that still covers the multi-cloud requirement.

## Terraform state 2026-10-28
**Chosen:** remote state — S3 bucket with DynamoDB locking for AWS, GCS bucket for GCP.
**Rejected:** local state (with several people planning from their own machines, drift and clobbered state are certain); Terraform Cloud (works, but adds an account and token to manage for no coursework benefit).
**Reasons:** remote state with locking stops two members applying at once, and is itself part of the availability story.

## Workflow 2026-10-28
**Chosen:** short-lived branches, Conventional Commits, one reviewer, `main` always working. Rules written down in `CONTRIBUTING.md`.
**Rejected:** committing straight to `main` (no review evidence for group marks).
**Reasons:** individual contribution has to be visible in the history, because each member defends their own part in the demo video.