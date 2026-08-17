<!--
Aleph-Alpha default pull request template.

Please complete every section - if one does not apply, write "None" or "N/A"
and say why. Based on the Engineering Quality Gates - Code Quality (SPHER-6434):
https://aleph-alpha.atlassian.net/wiki/spaces/Customer/pages/2242707545/Engineering+Quality+Gates+Code+Quality
-->

## Reference
<!--
Link the Jira ticket this change implements (e.g. SPHER-1234). Put the key in the
branch name or PR title as well, so the PR-to-Jira quality gate passes.
For a genuine no-ticket change, apply a `no-ticket` label and justify it below.
-->


## Purpose
<!-- Why is this change needed? The problem or goal, in 1-3 sentences. -->


## Detailed description
<!-- What changed and how. Key decisions, trade-offs, and anything a reviewer needs to know. -->


## Risk classification
<!--
Change risk assessment (C5 DEV-03) and categorisation (C5 DEV-05).
Tick exactly ONE risk level, then all impact areas that apply.
-->
- [ ] **Low** — isolated and easily reversible; no security or data-handling impact
- [ ] **Medium** — touches shared components or user-facing behaviour; contained blast radius
- [ ] **High** — security/data-handling, schema/data migrations, infrastructure, or wide blast radius

**Impact areas** (tick all that apply):
- [ ] Security / authentication / authorization
- [ ] Data handling / privacy
- [ ] Availability / performance
- [ ] Public API or other breaking change
- [ ] None of the above


## Testing
<!-- How was this verified? Automated tests added/updated, manual steps performed, evidence/links. -->


## Change monitoring
<!-- How will this be observed in production? Dashboards, metrics, logs, or alerts to watch after release. -->


## Rollback
<!-- How to revert if this goes wrong: revert PR, feature-flag off, down-migration, redeploy previous version, etc. -->


## Manual changes
<!--
Any steps NOT contained in this PR that are required for it to work: data
migrations, config/secret changes, infrastructure, feature-flag flips, runbook
or doc updates. Write "None" if the change is fully automated.
-->
