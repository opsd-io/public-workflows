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

## Self-hosted runner requirements

The CLI release bundle workflow uses self-hosted runners because it publishes
native bundles for Linux x64 and macOS ARM64. The runner group must allow the
repositories that use the workflow and must expose these labels:

- Linux: `self-hosted`, `Linux`, `X64`;
- macOS Apple Silicon: `self-hosted`, `macOS`, `ARM64`.

Both runners need the following tools available to the runner service user:

- `rbenv`;
- the `ruby-build` plugin for `rbenv`;
- `git`, `curl`, and standard shell tools;
- GitHub CLI (`gh`), used to locate the GitHub Release and upload assets.

Ruby is selected from the repository's `.ruby-version` file. The runner should
have that version installed through `rbenv`, or the `ruby-build` plugin must be
able to build it. Ruby must not be installed separately through Homebrew.

### Linux runner

The Linux runner needs a compiler toolchain and Ruby build dependencies. On
Ubuntu, install at least:

```text
build-essential libffi-dev libyaml-dev libssl-dev zlib1g-dev
```

The runner service user must own its `rbenv` directory and have the
`ruby-build` plugin under `${RBENV_ROOT}/plugins/ruby-build`.

### macOS runner

The macOS runner needs Xcode Command Line Tools. `ruby-build` may use Homebrew
libraries such as `openssl@3` and `libyaml` as build dependencies, but Ruby
itself is installed and selected only through `rbenv`.

On macOS 26, the workflow applies a compatibility workaround for the macOS 27
SDK when compiling Ruby. macOS 27 and newer use the normal Ruby build path.

The workflow supplies `GH_TOKEN` automatically from the workflow token, so no
personal access token should be stored on the runner. The calling repository
must grant `contents: write` permission to the job.

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

For repositories whose source contains a release version, pass the matching
strategy and version file. For example, a Ruby application can use:

```yaml
with:
  release-type: ruby
  version-file: lib/opsd/version.rb
```

Release Please will update that file in the release PR so the source version,
tag, changelog, and generated artifacts remain aligned.

## CLI release bundles

Use the reusable CLI release workflow from a repository workflow triggered by a
version tag:

```yaml
name: Release bundle

on:
  push:
    tags:
      - 'v*.*.*'

permissions:
  contents: write

jobs:
  bundle:
    uses: opsd-io/public-workflows/.github/workflows/cli-release-bundle.yml@main
```

The workflow runs unit tests and builds Linux x64 and macOS ARM64 portable
bundles in parallel. It uploads each bundle and its SHA-256 checksum to the
GitHub Release for the pushed tag. Both runners select the Ruby version from
the checked-out repository's `.ruby-version` file.
