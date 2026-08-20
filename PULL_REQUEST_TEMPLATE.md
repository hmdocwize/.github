<!--
Standard Docwize pull request description.

Keep every section. If one does not apply, say so in a word - "n/a" tells the
reviewer you considered it, a deleted section tells them nothing.
-->

## What this changes

<!-- One or two sentences: what behaviour is different after this merge? -->

## Linked request

<!--
Link the origin of this change. At least one of the two.
Dev Request = the Docwize Portal record that carries the business approval.
Issue       = the engineering item.
-->

- Dev Request:
- Closes #

## Security considerations

<!--
Tick every item this change touches, then explain each ticked item below.
If none apply, tick the last box instead.

This section is the design-level security review for the change. It is
answered by the author and read during code review, and it supports
ISO/IEC 27001 A.8.26 (application security requirements).
-->

- [ ] **Data exposure** — changes what data is returned, logged, cached, exported, or sent to a third party
- [ ] **Authentication / authorisation** — adds or alters a permission check, role, token scope, or tenant boundary
- [ ] **Dependency** — adds or upgrades a package, base image, or external service
- [ ] **Secrets** — reads, writes, moves, or prints a credential, key, token, or connection string
- [ ] **Data at rest** — creates or relocates a volume, bucket, table, or file path that holds customer data
- [ ] **Network exposure** — opens or widens a port, route, ingress, firewall rule, or CORS origin
- [ ] **Schema migration** — includes a migration; state below whether it is reversible without data loss
- [ ] **Nothing above applies** — reviewed the list; this change has no security impact

**Explanation for each ticked item:**

<!-- One line each. "Adds boto3 3.1.4, no new network egress" is enough. -->

## Testing

<!-- Name what proves this works. A CI job name is fine; so is pasted output. -->

- [ ] Covered by automated tests
- [ ] Verified manually — say how, and in which environment

## Rollback

<!-- How is this undone if it misbehaves in production? "Revert the commit" is a valid answer when it is true. -->
