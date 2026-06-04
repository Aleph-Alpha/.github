# `.github`

This is the organisation-wide **`.github`** repository. GitHub treats it specially: files placed here apply across the whole organisation, providing defaults and shared configuration for every repo that doesn't define its own.

## What lives here

### Octo STS trust policies

We use [octo-sts](https://github.com/octo-sts/app) — a Security Token Service for the GitHub API — to issue **short-lived, scoped tokens** to workloads that can produce OIDC tokens (GitHub Actions, GCP, etc.), so we can **eliminate long-lived PATs and org secrets**.

Trust policies are checked into:

```
.github/chainguard/<name>.sts.yaml
```

A trust policy has three parts: the claim-matching criteria, the permissions to grant, and — **for org-level policies** — the list of repositories the token may touch.

**Org-level policy** (note the `repositories:` field, required at org scope):

```yaml
# .github/chainguard/release-ci.sts.yaml
issuer: https://token.actions.githubusercontent.com
subject: repo:my-org/my-repo:ref:refs/heads/main

permissions:
  contents: read
  packages: write

repositories:
  - my-repo
  - another-repo
```

Claims can also be matched with regular expressions (`subject_pattern`, `claim_pattern`) instead of exact values — useful for federating non-GitHub issuers such as Google or GCP service accounts.

#### Guidelines

- **Least privilege.** Start read-only; add write scopes only when a workload needs them.
- **Scope narrowly.** Prefer an exact `subject` (e.g. `repo:org/repo:ref:refs/heads/main`) over broad patterns like `repo:org/repo:.*`.
- **One policy per workload.** Avoid catch-all policies; name files by intent (`release-ci`, `docs-deploy`).
- **List only needed repos** in `repositories:` for org-level policies.
- **Review as security-sensitive.** Enable branch protection here and require PR review for any `*.sts.yaml` change.
- The octo-sts GitHub App must be installed on the org with access to this repo and to every repo a policy grants permissions to.

### Adding or changing an octo-sts policy

1. Add or edit `.github/chainguard/<name>.sts.yaml`.
2. Set `issuer`, `subject` (or `subject_pattern`), the minimal `permissions`, and — for org-level — the `repositories` list.
3. Open a PR; require review (trust-policy changes are security-sensitive).
4. After merge, workloads federate against `<name>` to receive a scoped, short-lived token.
