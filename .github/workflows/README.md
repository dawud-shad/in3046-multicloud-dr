# GitHub Actions workflows

Pipelines live here as `.yml` files. GitHub ignores this README, so it is safe to keep.

Planned:

- `terraform-plan` — plan on pull requests touching `infra/`, per cloud.
- `deploy` — apply on `main`, per cloud, credentials from repository secrets.
- `smoke-test` — hit the deployed service after a deploy and save the output to `docs/evidence/`.

Secrets are never committed. See `infra/README.md` and `CONTRIBUTING.md`.
