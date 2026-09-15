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

The workflow runs the module checks in parallel with Terraform and OpenTofu: formatting, initialization without a backend, validation, TFLint, and Checkov security checks. Terraform and OpenTofu versions can be overridden through workflow inputs.

This repository also runs `actionlint` against its own GitHub Actions workflows to catch invalid syntax, expressions, action inputs, and reusable workflow interfaces.

For production use, prefer a versioned tag or commit SHA instead of `@main`.

## Release Please

Use the centralized release workflow from a repository workflow:

```yaml
name: Release

on:
  push:
    branches: [main]

permissions:
  contents: write
  issues: write
  pull-requests: write

jobs:
  release:
    uses: opsd-io/public-workflows/.github/workflows/release-please.yml@main
    with:
      release-type: terraform-module
```

The workflow creates or updates a release PR and, after that PR is merged, creates the version tag and GitHub release. It applies a shared release-notes layout with `🚀 Features` first, followed by fixes, performance, documentation, dependencies, refactoring, and maintenance. Repositories should use Conventional Commits, for example `feat: add ...` or `fix: correct ...`. A repository can still provide its own `release-please-config.json` when it needs a deliberate exception.
