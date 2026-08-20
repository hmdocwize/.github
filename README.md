# hmdocwize/.github

Canonical source for GitHub defaults in the `hmdocwize` organisation.

## ⚠️ Read this before assuming the template is live

GitHub reads *default community health files* from a repository literally named
`.github` — but **only when that repository is public.** Per GitHub's own
documentation: *"The `.github` repository must be public for most default
community health files to be applied organization-wide. Private `.github`
repositories are not supported."*

**This repository is private**, and every repository in the org is private. So
nothing here is inherited by anything. `PULL_REQUEST_TEMPLATE.md` in this repo is
the canonical text; it takes effect in a repository only when that repository
holds its own copy at `.github/PULL_REQUEST_TEMPLATE.md`.

Two ways forward, and they compose — a per-repo copy always overrides the org
default, so doing one does not block the other later:

| | Effect | Cost |
|---|---|---|
| **Keep private, copy per repo** (current approach) | Applies only where copied | One file per repo; the copies drift silently |
| **Make this repo public** | Applies to all 26 repos automatically, including future ones | The template and this README become world-readable — sanitise before flipping |

If this repo is ever made public, strip anything that reads as an internal
assessment first. A public statement that the change process previously had no
security review step is an admission worth not publishing, and internal repo
names do not need to be world-readable either.

## What lives here

| File | Status |
|---|---|
| `PULL_REQUEST_TEMPLATE.md` | Canonical text. Copy into a repo's `.github/` to make it effective there. |

Rollout of the per-repo copies is tracked in:

- `hmdocwize/portal#524`
- `hmdocwize/docs#42`
- `hmdocwize/docwize-dot-com#26`

## What cannot live here

**`CODEOWNERS` is not inheritable at all**, public or private. GitHub only reads
it from the repository being changed (`CODEOWNERS`, `.github/CODEOWNERS`, or
`docs/CODEOWNERS` on the base branch). Each repo needs its own; that is the main
subject of the three issues above.

Two supported files are deliberately absent:

- `SECURITY.md` — worth adding, but it needs a monitored contact address decided
  first; an unanswered disclosure inbox is worse than none.
- `profile/README.md` — renders publicly on the organisation page. An
  outward-facing change, so it should be a deliberate one.

## Why the Security considerations section exists

ISO 27001 **A.8.26 (application security requirements)** asks that security
requirements be identified and specified *when developing applications* — at
design time, not after the fact. The Scytale evidence item for it, *Change
Request Design Security Review*, asks for a change checklist containing a
security section.

The automated gates already in place (Snyk, Dependabot, Trivy, the lint and build
jobs) find the classes of problem a scanner can find. None of them asks a human
whether a change widens a tenant boundary or moves customer data somewhere new.
That question is what this section adds.

The related control **A.8.32 (change management)** is served by the *Linked
request* and *Rollback* sections.

## Related

- Engineering evidence for these controls lives in the `infrastructure` repo under
  `evidence-out/8.26-A.8.26-Application-security-requirements/`.
- Policies, registers and the Statement of Applicability live in Scytale, not git.
