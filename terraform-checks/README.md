# Terraform Validation Pipeline

This directory contains a CI pipeline that validates Terraform configuration using GitHub Actions.

The focus here is on catching issues early by enforcing consistent formatting and validating configuration correctness, without applying infrastructure or requiring cloud credentials. The pipeline is designed to act as a guardrail, not a deployment mechanism.

Terraform code is read and checked, but never executed against a real environment.

---

## What this Pipeline Demonstrates

- Enforcing Terraform formatting using `terraform fmt -check`
- Validating Terraform configuration with `terraform validate`
- Using CI to catch errors before infrastructure changes are applied
- Keeping infrastructure provisioning out of CI by design

---

## Pipeline Behaviour

- Triggered on push
- Runs Terraform from the `terraform-validation` directory
- Initialises Terraform to load provider schemas
- Checks formatting and validation
- Does not apply or plan infrastructure

---

## Successful Checks

<p align="center">
  <img src="/assets/terraform-ci-checks.png" alt="Successful Terraform validation pipeline run" width="1000">
</p>
