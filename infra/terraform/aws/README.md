# AWS root module

Terraform root module for the AWS deployment: VPC, compute, database and the health check that triggers failover. Run `terraform` from this directory.

Remote state: S3 bucket with a DynamoDB lock table.
