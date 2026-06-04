# `.github`

This repository contains organization-wide GitHub configuration. Files here act as defaults for all repositories that don't define their own configuration.

## Octo STS Trust Policies

We use `octo-sts` to issue short-lived, scoped GitHub tokens via OIDC (GitHub Actions, GCP, etc.), eliminating long-lived PATs and organization secrets.

Trust policies are stored in:

```text
.github/chainguard/<identity>.sts.yaml
```

Each policy defines:

* OIDC claim matching (`issuer`, `subject`)
* GitHub permissions to grant
* Allowed repositories (`repositories`, required for org-level policies)

### Example Policy

```yaml
issuer: https://token.actions.githubusercontent.com
subject: repo:org/my-repo:ref:refs/heads/main

permissions:
  contents: read

repositories:
  - repo-one
  - repo-two
```

### Using a Policy in GitHub Actions

```yaml
permissions:
  id-token: write # Required for OIDC federation
  contents: read

steps:
  - uses: octo-sts/action@f603d3be9d8dd9871a265776e625a27b00effe05 # v1.1.1
    id: octo-sts
    with:
      scope: org # GitHub Org name
      identity: <identity>

  - env:
      GITHUB_TOKEN: ${{ steps.octo-sts.outputs.token }}
    run: gh repo list
```

## Guidelines

* Use the **least privilege** required.
* Prefer exact `subject` matches over broad patterns.
* Create **one policy per workload** (for example: `release-ci`, `docs-deploy`).
* Only include repositories that the workload needs access to.
* Treat policy changes as security-sensitive and require PR review.
