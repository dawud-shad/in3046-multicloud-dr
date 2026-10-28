# Infrastructure

Infrastructure as code for both clouds, plus failover and health-check configuration.

Layout:

```
infra/
├── terraform/
│   ├── modules/   # shared modules
│   ├── aws/       # AWS root module
│   └── gcp/       # Google Cloud root module
└── README.md
```

Start at `infra/terraform/README.md`. Never commit credentials, Terraform state files or `.tfvars` containing secrets - see the root `.gitignore`. Cloud keys belong in GitHub Actions secrets.