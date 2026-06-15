# Lab M4.10 - Terraform Git Workflows

## What I built
Professional Terraform CI/CD pipeline with GitHub Actions.
Every PR gets automatic format check, validation and plan output.

## Workflow

1. Create feature branch
2. Make infrastructure changes
3. Push and open PR
4. GitHub Actions runs format, validate, plan automatically
5. Plan output posted as PR comment so reviewers know exactly what will change
6. Merge to main

## CI/CD Pipeline

Format check: consistent code style
Validate: catches syntax errors before they hit AWS
Plan on PR: full visibility into changes before merge

## Repository Structure

.github/workflows/terraform.yml - the pipeline
.github/pull_request_template.md - PR checklist
.github/CODEOWNERS - who reviews Terraform changes
.pre-commit-config.yaml - local checks before pushing
main.tf - S3 bucket with encryption and versioning
variables.tf - configurable inputs
outputs.tf - bucket name and ARN

## Key Learnings

Running terraform apply from your laptop works for solo work.
Teams need pipelines so nobody breaks production by accident.
The plan output on PR is the most important part - reviewers
can see exactly what will change in AWS before approving.