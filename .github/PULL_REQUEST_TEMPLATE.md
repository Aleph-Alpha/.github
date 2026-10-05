<!--
Aleph-Alpha standard change pull request template.

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
Standard change patterns are assigned a default risk category. Pick the pattern from the list below.
Try to keep the scope of the change within one of the patterns to keep the risk within bounds.
If the change does not fit into one of the boxes below, or the risk is higher than moderate, it is a Normal change and requires a risk assessment.
See [change management doc](https://aleph-alpha.atlassian.net/wiki/spaces/Customer/pages/2696118367/Change+Management+Process#Risk-categories) for more details
-->

Standard change patterns are assigned a default risk category (negligible - moderate):

**Change Pattern** (tick only one):
- [ ] Security / authentication / authorization
- [ ] Data handling / privacy
- [ ] Availability / performance
- [ ] Public API or other breaking change
- [ ] Routine change (none of the above)


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
