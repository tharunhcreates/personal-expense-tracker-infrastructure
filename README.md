# Personal Expense Tracker – Infrastructure Automation

## Project Overview

This project demonstrates automated multi-cloud infrastructure provisioning for a Personal Expense Tracker platform using Terraform, GitHub Actions, AWS, Azure, and Confluent Cloud.

The objective is to implement a secure and controlled Infrastructure as Code (IaC) workflow with automated validation, deployment, and environment promotion.

## Project Objectives

- Automate infrastructure provisioning using Terraform.
- Implement GitHub branch protection and pull request reviews.
- Build CI/CD pipelines using GitHub Actions.
- Provision resources across AWS, Azure, and Confluent Cloud.
- Implement secure authentication using OIDC and workload identity federation.
- Promote infrastructure changes from Dev to Test with manual approval.

## Technology Stack

| Technology | Purpose |
|---|---|
| GitHub | Source code management |
| GitHub Actions | CI/CD automation |
| Terraform | Infrastructure as Code |
| AWS | Networking and storage |
| Azure | Networking and storage |
| Confluent Cloud | Kafka event streaming |

## Cloud Resources

### AWS
- Virtual Private Cloud (VPC)
- S3 storage bucket

### Azure
- Resource Group
- Storage Account

### Confluent Cloud
- Kafka expense transaction topic

## Deployment Environments

- **Dev:** Development infrastructure and initial validation.
- **Test:** Infrastructure promoted after manual approval.

Each environment will maintain an independent Terraform state.

## CI/CD Workflow

1. Developer creates a feature branch.
2. Changes are submitted through a pull request.
3. GitHub Actions executes Terraform fmt, validate, and plan.
4. Required reviewers approve the pull request.
5. Approved changes are merged into the protected main branch.
6. GitHub Actions authenticates securely and applies infrastructure changes.
7. Dev infrastructure is promoted to Test through manual approval.

## Security Practices

- Protected main branch.
- Mandatory pull request reviews.
- AWS OIDC authentication.
- Azure workload identity federation.
- No hardcoded cloud credentials.
- Terraform state and sensitive files excluded from Git.

## Project Structure

```text
personal-expense-tracker-infrastructure/
├── .github/
│   ├── workflows/
│   └── CODEOWNERS
├── environments/
│   ├── dev/
│   └── test/
├── modules/
│   ├── aws/
│   ├── azure/
│   └── confluent/
├── README.md
├── .gitignore
├── providers.tf
├── versions.tf
├── variables.tf
└── outputs.tf
```

## Expected Outcome

A secure, automated, multi-cloud infrastructure deployment workflow with reviewed changes, automated Terraform validation, controlled deployments, and manual Dev-to-Test promotion.

---

**Project:** Personal Expense Tracker Infrastructure Automation  
**Focus:** GitOps, Terraform, CI/CD, Multi-Cloud and DevSecOps
