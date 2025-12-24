# CI/CD Pipelines

This repository contains a small set of CI and CI/CD pipelines built with GitHub Actions, focused on real automation tasks rather than abstract examples.

Each pipeline is scoped to a specific part of the repository and does one thing clearly, such as building and publishing a Docker image or validating Terraform configuration. The workflows are intentionally explicit so it’s obvious what runs, when it runs, and why.

All pipelines live in the same repo but are kept separate by design, reflecting how CI and CI/CD are commonly structured in practice.

```
.
├─ README.md
├─ LICENSE
├─ .gitignore
│
├─ docker-build-publish/
│  ├─ Dockerfile
│  ├─ application files
│  └─ README.md
│
├─ terraform-validation/
│  ├─ main.tf
│  ├─ provider.tf
│  └─ README.md
│
└─ .github/
   └─ workflows/
      ├─ docker-build-publish.yml
      └─ terraform-ci.yml
```
Each directory represents a focused pipeline with its own code and documentation. All GitHub Actions workflows live in .github/workflows at the repository root, as required by GitHub Actions.

## Included pipelines

### Docker build and publish

A CI/CD pipeline that builds and publishes a Docker image on push. It focuses on:

- Building a container image from a scoped build context
- Tagging and publishing images to Docker Hub
- Authenticating securely using GitHub Actions secrets
- Keeping the workflow explicit and predictable

See [docker-build-publish/README.md](docker-build-publish/README.md) for details.

### Terraform validation

A CI pipeline that validates Terraform configuration without applying infrastructure. It focuses on:

- Enforcing consistent formatting with terraform fmt
- Validating configuration using terraform validate
- Catching errors early without requiring cloud credentials
- Keeping infrastructure changes out of CI by design

See [terraform-validation/README.md](terraform-validation/README.md) for details.

