# Infrastructure

Infrastructure as code for both clouds, plus failover and health-check configuration.

Never commit credentials, Terraform state files or `.tfvars` containing secrets - see the root `.gitignore`. Cloud keys belong in GitHub Actions secrets.