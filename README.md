# public-workflows
Public reusable GitHub Actions workflows shared by OPSd repositories.

## Terraform module checks

Use the reusable workflow from a repository workflow:

```yaml
name: Terraform module

on:
  push:
    branches: [main]
  pull_request:

jobs:
  checks:
    uses: opsd-io/public-workflows/.github/workflows/terraform-module.yml@main
    with:
      working-directory: .
```

The workflow runs Terraform formatting, initialization without a backend, validation, TFLint, and Checkov security checks.

This repository also runs `actionlint` against its own GitHub Actions workflows to catch invalid syntax, expressions, action inputs, and reusable workflow interfaces.

For production use, prefer a versioned tag or commit SHA instead of `@main`.
