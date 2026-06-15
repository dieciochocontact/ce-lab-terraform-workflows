# Terraform Git Workflows Documentation

## Workflow Overview

1. Create feature branch from main
2. Make infrastructure changes
3. Push branch and open PR
4. GitHub Actions runs automatically
5. Review plan output in PR comment
6. Merge to main

## CI/CD Pipeline Steps

Format Check: ensures consistent code style with terraform fmt
Init: downloads providers and modules
Validate: catches syntax and configuration errors
Plan: shows exactly what will change in AWS before applying

## Branch Strategy

main: protected branch, only accepts PRs
feature/*: for new infrastructure
fix/*: for bug fixes
hotfix/*: for urgent production fixes

## Best Practices

Never commit tfstate files - they contain sensitive data
Never commit .terraform/ folder - its too large and auto-generated
Always specify provider versions to avoid breaking changes
Use variables instead of hardcoded values
Review the plan output before merging any PR

## Security

AWS credentials stored as GitHub Secrets, never in code
CODEOWNERS ensures platform team reviews all Terraform changes
Pre-commit hooks catch issues before they reach the pipeline