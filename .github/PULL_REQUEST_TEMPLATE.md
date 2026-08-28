<!--
Aleph-Alpha default pull request template.

Complete every section - if one does not apply, write "None" or "N/A"
and say why.

Write the JIRA ticket key in the branch name, PR title or Description below.
Prefer the branch name or title: the title becomes the squash-merge commit
message, so the link survives in git history. For a genuine no-ticket change,
apply a `no-ticket` label.

Do not paste test output here. Test evidence is collected automatically by the
test-and-report workflow wherever that workflow runs.
-->

## Description
<!--
Why change is needed and what changed. E,g Key decisions, trade-offs, or anything a reviewer needs to know.
This can also be a confluence page link.
Keep it to a few sentences - link the detail (JIRA ticket, confluence page)
rather than pasting it. Over-long descriptions are flagged by the
pr-description quality gate.
-->


## Risk classification
<!--
Change risk assessment (C5 DEV-03) and categorisation (C5 DEV-05).
Tick exactly ONE risk level, then all impact areas that apply.
If you add "None" or "N/A" in this field, then you have to say why or reference a doc
See [change management doc](https://aleph-alpha.atlassian.net/wiki/spaces/Customer/pages/2696118367/Change+Management+Process#Risk-categories) for more details
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


## Change monitoring
<!-- How will this be observed in production? Dashboards, metrics, logs, or alerts to watch after release. -->

## Rollback
<!-- How to revert if this goes wrong: revert PR, feature-flag off, down-migration, redeploy previous version, etc. -->
Revert this commit

## Manual changes
<!--
Any steps NOT contained in this PR that are required for it to work: data
migrations, config/secret changes, infrastructure, feature-flag flips, runbook
or doc updates. Write "None" if the change is fully automated.
-->
None
