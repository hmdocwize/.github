# hmdocwize/.github

Shared GitHub configuration for the `hmdocwize` organisation.

## Pull request template

`PULL_REQUEST_TEMPLATE.md` is the standard pull request description used across
Docwize repositories. It has four sections, and each one exists to be answered
before a change is merged rather than after it ships:

| Section | Purpose |
|---|---|
| **What this changes** | The reviewer knows what behaviour is different before reading the diff |
| **Linked request** | Ties the change to the Dev Request that authorised it, and to the engineering issue that tracks it |
| **Security considerations** | The design-level security review for the change |
| **Testing** / **Rollback** | What proves it works, and how it is undone |

### Security considerations

A short checklist of the ways a change can affect security: data exposure,
authentication and authorisation, dependencies, secrets, data at rest, network
exposure, and schema migrations. The author ticks what the change touches and
explains each one; where nothing applies, there is an explicit box for that.

Automated tooling covers the classes of problem a scanner can detect. This
section covers the ones only a person can answer — whether a change widens a
tenant boundary, or moves customer data somewhere new. It is answered by the
author and read during code review.

This supports ISO/IEC 27001 **A.8.26** (application security requirements),
which asks that security requirements be identified and specified while an
application is being developed. **A.8.32** (change management) is served by the
*Linked request* and *Rollback* sections.

## Using it in a repository

Copy `PULL_REQUEST_TEMPLATE.md` to `.github/PULL_REQUEST_TEMPLATE.md` in the
repository. GitHub then pre-fills it into every new pull request there.

Keep the copy identical to this one so the wording stays consistent across
repositories. If a repository needs a genuine variation, change it there and say
why in the file.

## Code owners

`CODEOWNERS` is intentionally not in this repository. GitHub reads it only from
the repository being changed — `CODEOWNERS`, `.github/CODEOWNERS`, or
`docs/CODEOWNERS` on the base branch — so it cannot be shared from here. Each
repository defines its own.
