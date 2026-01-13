# Issue Triage Playbook

This document defines how we triage issues in a monorepo (backend + frontend) using GitFlow.

## Goals

- Ensure every new issue is categorized, actionable, and routed quickly.
- Maintain a predictable queue with clear priorities.
- Escalate production incidents to hotfix workflow immediately.

## Triage Roles

- **Triage Captain (rotating)**: performs daily/regular triage.
- **Area Owners**: backend/frontend/infra owners respond to questions and review prioritization.
- **Release Captain (when in release)**: governs release readiness and scope.

## Triage Cadence (Recommended)

- Daily for `priority:p0` / production-facing issues.
- 2–3x per week for all other incoming issues.
- Weekly backlog grooming for `priority:p2/p3`.

## Required Labels (Definition of “Triaged”)

An issue is considered triaged when it has:

- Exactly one `type:*`
- At least one `area:*`
- Exactly one `priority:*`
- Exactly one `status:*` (at minimum `status:ready` or `status:needs-info`)

## Label Taxonomy

### Type

- `type:bug`, `type:feature`, `type:chore`, `type:spike`, `type:release`, `type:hotfix`, `type:docs`

### Area

- `area:backend`, `area:frontend`, `area:infra`, `area:docs`, `area:cross`

### Priority

- `priority:p0` Immediate / production emergency
- `priority:p1` High priority, near-term
- `priority:p2` Normal priority
- `priority:p3` Low priority / backlog

### Status

- `status:triage` Newly created / awaiting triage
- `status:needs-info` Waiting for reporter clarification
- `status:ready` Ready to be picked up
- `status:in-progress` Work started (PR or assignee)
- `status:blocked` Blocked by dependency / decision
- `status:needs-review` PR awaiting review
- `status:needs-qa` Awaiting QA verification (optional)

## Priority Guidance

### Set `priority:p0` when:

- Production outage or severe degradation
- Data loss/corruption risk
- Active security exposure risk
- Business-critical workflow broken for many users

For `priority:p0`, open/convert to **Hotfix** issue and follow hotfix flow (branch from `main`).

GitFlow hotfix branches are intended for urgent production fixes. :contentReference[oaicite:6]{index=6}

## Triage Workflow (Step-by-Step)

1. **De-duplicate**
   - Search existing issues; mark duplicates and link them.
2. **Validate category**
   - Confirm correct `type:*` and `area:*`.
3. **Assess impact**
   - Assign `priority:*`. If production emergency, escalate to hotfix.
4. **Make it actionable**
   - Ensure reproduction steps / acceptance criteria exist.
   - If missing, set `status:needs-info` and request details.
5. **Route**
   - Assign/mention area owners; add to milestone if applicable.
6. **Set status**
   - `status:ready` if actionable and prioritized.
   - `status:needs-info` if waiting for reporter.
   - `status:blocked` if dependency is known and tracked.

## “Needs Info” Policy

- If an issue is `status:needs-info` and there is no response for 7–14 days:
  - Post a reminder once.
  - If still no response after an additional 7 days, close the issue as stale.
  - Allow reopening if new information is provided.

## Linking Issues and PRs

- Encourage PR authors to link PRs to issues using keywords like `Fixes #123`.
  GitHub will automatically close the issue when the PR is merged. :contentReference[oaicite:7]{index=7}

## Definition of Done (DoD) for Issues

An issue can be closed when:

- The fix/feature is merged (or explicitly decided against), and
- Verification is completed (tests/QA), and
- Release notes / migration notes are added when relevant.
