# Terraform

One root module per cloud, sharing common modules:

```
infra/terraform/
├── modules/   # reusable: network, compute, database, dns-failover
├── aws/       # AWS root module
└── gcp/       # Google Cloud root module
```

Rules:

- Run `terraform` from inside `aws/` or `gcp/`, never from this directory.
- Keep `.terraform.lock.hcl` tracked in both root modules so everyone resolves the same provider versions.
- State is remote — see `docs/decisions.md`. Planning against local state will corrupt it; don't.
- Backend settings come from a non-committed `backend.tfvars` passed with `-backend-config`. Commit `backend.tfvars.example` instead.
- Variables: commit `terraform.tfvars.example`, never `terraform.tfvars`.
