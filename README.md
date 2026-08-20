# hmdocwize/.github

Org-wide GitHub defaults for the `hmdocwize` organisation.

GitHub reads a repository literally named `.github` for *default community health
files*. Anything defined here applies automatically to **every repository in the
org** that does not define its own copy of the same file. There is nothing to
install and nothing to copy into individual repos.

## What this repo provides

| File | Effect |
|---|---|
| `PULL_REQUEST_TEMPLATE.md` | Pre-fills the description of every new pull request in every org repo, including the **Security considerations** checklist |

A repository overrides the org default by committing its own
`.github/PULL_REQUEST_TEMPLATE.md`. That is the escape hatch for a repo where the
org template genuinely does not fit — use it sparingly, because a per-repo
template drifts from this one silently.

## What this repo cannot provide

**`CODEOWNERS` is not inheritable.** GitHub only reads it from the repository
being changed (`CODEOWNERS`, `.github/CODEOWNERS`, or `docs/CODEOWNERS` on the
base branch). Putting one here does nothing. Each repo needs its own file, which
is why the rollout is tracked as a per-repo issue rather than a single commit here.

Two other org-level files are supported but deliberately absent for now:

- `SECURITY.md` — a vulnerability disclosure policy. Worth adding, but it needs a
  monitored contact address decided first; an unanswered disclosure inbox is worse
  than none.
- `profile/README.md` — renders publicly on the organisation page. An outward-facing
  change, so it should be a deliberate one.

## Why the Security considerations section exists

ISO 27001 **A.8.26 (application security requirements)** asks that security
requirements be identified and specified *when developing applications* — at design
time, not after the fact. The Scytale evidence item for it, *Change Request Design
Security Review*, asks for a change checklist containing a security section.

Before this template, the change process had no such prompt anywhere: no PR
template in any repo, no org default, and no security field on the Docwize Portal
Dev Request form. The automated gates (Snyk, Dependabot, Trivy, the lint and build
jobs) find classes of problem a scanner can find; none of them asks a human whether
a change widens a tenant boundary or moves customer data somewhere new.

The related control **A.8.32 (change management)** is served by the *Linked request*
and *Rollback* sections.

## Related

- Engineering evidence for these controls lives in the `infrastructure` repo under
  `evidence-out/8.26-A.8.26-Application-security-requirements/`.
- Policies, registers and the Statement of Applicability live in Scytale, not in git.
