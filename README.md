# Project 6: Version Control Infrastructure

## Goal

Track Terraform infrastructure updates using Git and GitHub.

## Tasks

- Push Terraform code to GitHub.
- Create and use a feature branch for infrastructure changes.
- Commit changes with clear commit messages.
- Raise a pull request for the changes.
- Merge the changes only after review and validation.

## Deliverables

- GitHub repository link
- Screenshot of the commit history
- Screenshot of the feature branch
- Pull request link
- Screenshot of the pull request and changed files
- Short project write-up

## Repository Structure

```text
.
├── main.tf
├── variables.tf
├── outputs.tf
├── providers.tf
├── terraform.tfvars.example
├── .gitignore
└── README.md
```

Update the files to match the infrastructure used in the project.

## Prerequisites

- Git
- Terraform 1.5 or later
- GitHub account
- Optional cloud-provider account and credentials

## Create the GitHub Repository

1. Sign in to GitHub.
2. Create a repository, for example `terraform-version-control`.
3. Add a README and `.gitignore` if GitHub prompts you to create them.
4. Copy the repository URL.

## Configure Git

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

## Initialize the Local Repository

```bash
git init
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
git add .
git commit -m "Initial Terraform infrastructure"
git push -u origin main
```

## Create Terraform Infrastructure

Initialize and validate the Terraform project:

```bash
terraform init
terraform fmt -recursive
terraform validate
terraform plan
```

Example provider-free Terraform configuration:

```hcl
terraform {
  required_version = ">= 1.5.0"

  required_providers {
    null = {
      source  = "hashicorp/null"
      version = "~> 3.0"
    }
  }
}

provider "null" {}

resource "null_resource" "example" {
  triggers = {
    environment = "development"
  }
}
```

Replace this resource with the provider and infrastructure required by the assignment.

## Create a Feature Branch

Create a separate branch for each infrastructure change:

```bash
git switch -c feature/terraform-change
```

After updating the Terraform files:

```bash
terraform fmt -recursive
terraform validate
git add .
git commit -m "Add Terraform infrastructure change"
git push -u origin feature/terraform-change
```

Keep commit messages short and descriptive.

## Raise a Pull Request

On GitHub:

1. Open the repository.
2. Select **Compare & pull request**.
3. Add a descriptive title.
4. Explain what changed and why.
5. List the Terraform resources affected.
6. Describe the validation commands completed.
7. Select **Create pull request**.
8. Save the complete pull request URL.

Example pull request description:

```markdown
## Summary

Added a Terraform infrastructure configuration and an infrastructure change.

## Changes

- Added a provider configuration.
- Added infrastructure resources.
- Added outputs and variables.
- Formatted and validated Terraform configuration.

## Validation

- terraform init
- terraform fmt -recursive
- terraform validate
- terraform plan
```

## Security

Do not commit:

- Cloud credentials
- Terraform state files
- Private `*.tfvars` files
- `.terraform/` directories
- Crash logs

Add this to `.gitignore`:

```text
.terraform/
*.tfstate
*.tfstate.*
*.tfvars
crash.log
.terraform.lock.hcl
```

## Evidence Screenshots

Capture clear screenshots of:

- The GitHub repository structure
- The GitHub commit history
- The feature branch
- The pull request description
- The pull request changed-files view
- The Terraform validation and plan output
- The merged pull request, if the project requires merging

Keep credentials and private values outside screenshots.

## Short Write-Up

Use this write-up in the project submission:

```text
Project: Version Control Infrastructure

Goal:
Track Terraform infrastructure updates using Git.

Implementation:
The Terraform project was initialized as a Git repository and pushed to GitHub.
Infrastructure changes were created in a feature branch and committed with
descriptive messages.

Collaboration:
A pull request was created to explain and review the infrastructure change.
The pull request includes the changed files and Terraform validation evidence.

Validation:
The project was initialized with terraform init, formatted with terraform fmt,
and checked with terraform validate. Where required, terraform plan was used
to review infrastructure changes.

Outcome:
Git and GitHub provide a traceable history of Terraform changes and allow
changes to be reviewed before they are merged.
```

## Submission Checklist

- [ ] GitHub repository created
- [ ] Terraform files committed
- [ ] Terraform initialized locally
- [ ] Terraform formatted
- [ ] Terraform configuration validated
- [ ] Feature branch created
- [ ] Pull request created
- [ ] Pull request has a clear summary
- [ ] Changed files are visible in the pull request
- [ ] Commit history screenshot captured
- [ ] Feature branch screenshot captured
- [ ] Pull request screenshot captured
- [ ] Terraform validation screenshot captured
- [ ] Pull request URL recorded
- [ ] No credentials or state files committed
- [ ] Repository README completed

## Project Links

- GitHub Repository: <https://github.com/komal-ae-sharma/Project-06>
- Pull Request: <https://github.com/komal-ae-sharma/Project-06/pull/2>
