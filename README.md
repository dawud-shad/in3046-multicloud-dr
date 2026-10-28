# IN3046 - Multi-Cloud High Availability & Disaster Recovery

Group project for IN3046 Cloud Computing, City St George's, University of London.

## Project
A small web application deployed across two cloud providers (AWS and Google Cloud) with
automated fault detection and failover, so the service stays available if one provider fails.

**Based on:** W. Li, G. Ma, W. Fang, X. He, and J. Li, "Multi-Cloud Management Architecture
Design and Disaster Recovery Strategy for High Availability," *Journal of Cyber Security and
Mobility*, vol. 14, no. 5, pp. 1173–1198, Dec. 2025, doi: 10.13052/jcsm2245-1439.1456.

## Repository layout

| Path | Contents |
|---|---|
| `backend/` | Server-side API, business logic and database access |
| `frontend/` | User interface and the live status/failover dashboard |
| `infra/` | Terraform for both clouds - start at `infra/README.md` |
| `scripts/` | Load generation and fault-injection tests |
| `docs/` | Proposal, decision log, evidence, references |

Every directory has its own README saying what belongs in it. Read `docs/decisions.md` before proposing a design change, and see `CONTRIBUTING.md` for the branch, commit and review rules.