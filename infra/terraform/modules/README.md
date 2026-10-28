# Modules

Reusable Terraform modules shared by both cloud root modules.

Anything provider-agnostic belongs here - failover DNS records, health-check policy shape, tagging conventions. Anything provider-specific belongs in `aws/` or `gcp/`.

Planned modules: `network`, `compute`, `database`, `dns-failover`.
