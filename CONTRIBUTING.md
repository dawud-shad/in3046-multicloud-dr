# Contributing

Group workflow for this module. `main` stays working at all times.

## Branches

Work on a short-lived branch and open a pull request:

| Prefix | Use |
|---|---|
| `feat/` | new capability, e.g. `feat/gcp-health-check` |
| `fix/` | bug fix |
| `docs/` | documentation only |
| `chore/` | tooling, dependencies, housekeeping |

Rebase on `main` before opening the PR rather than merging `main` into your branch.

## Commits

Conventional Commits: `type(scope): subject` - imperative mood, lower case after the colon, no trailing full stop. Scope is the area touched: `feat(infra): add aws health-check module`. British spelling throughout.

## Pull requests

- One reviewer minimum; nobody approves their own work.
- Describe what changed and why, and link the entry you added to `docs/decisions.md` if you made a design choice.
- Notation in `docs/genai-use-log.md` is a submission requirement, not a nicety - add the row in the same PR that the AI helped with.
- Never commit secrets, `.tfstate`, `.tfvars` or `.env` files. Cloud credentials live in GitHub Actions secrets; see `infra/README.md`.

## Ownership

Agree who owns which area before the first pull request and record it in `docs/decisions.md`: one member per cloud provider in `infra/terraform/`, plus backend and frontend. Each member explains their own part on camera in the demo video, so keep out of someone else's area unless you are reviewing it.
