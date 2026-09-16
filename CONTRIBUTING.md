# Contributing

## Pull Requests And Commits

Use the following format for the pull request title and every commit:

~~~text
type(scope): short imperative description
~~~

Allowed scopes are workflows, ci, docs, and release, for example
fix(workflows): pin checkout action. The required Conventional Commits check
must pass. Release Please uses these messages to build shared release notes.

## Workflow Changes

Reusable workflows must keep their inputs, permissions, secrets, and outputs
documented. Pin third-party actions to reviewed commit SHAs, run actionlint,
and avoid exposing credentials or cloud apply operations in public workflows.

Public infrastructure workflows may generate manifests and run Terraform and
OpenTofu plans, but must not create real cloud resources. Real apply tests
belong in private-workflows and use the shared scenarios from integration-tests.

Validate the affected workflow locally when possible and include the result
in the pull request. Changes to runner requirements must update the runner
section in the README.
