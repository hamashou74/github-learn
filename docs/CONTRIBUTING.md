# Contributing Guide

Thank you for contributing. This repository uses a GitFlow-based workflow and a monorepo layout (backend + frontend in the same repository).

## Table of Contents

- [How to Get Help](#how-to-get-help)
- [Reporting Issues](#reporting-issues)
- [Branching Model (GitFlow)](#branching-model-gitflow)
- [Branch Naming Convention](#branch-naming-convention)
- [Development Workflow](#development-workflow)
- [Pull Requests](#pull-requests)
- [Release and Hotfix Flow](#release-and-hotfix-flow)
- [Security](#security)

## How to Get Help

- For questions and support, use GitHub Discussions (preferred).
- For bugs and work items, open an Issue using the provided Issue Forms.

## Reporting Issues

- Always use the Issue Forms (Bug / Feature / Chore / Spike / Release / Hotfix).
- Provide clear reproduction steps, expected vs actual results, and relevant logs (redact secrets).
- For production emergencies, open a **Hotfix** issue (not a normal bug).

## Branching Model (GitFlow)

We use two long-lived branches:

- `main`: production
- `develop`: integration branch for ongoing work

Short-lived branches:

- `feature/*`: new features (from `develop`, merge back into `develop`)
- `bugfix/*`: non-emergency bug fixes (from `develop`, merge back into `develop`)
- `release/*`: release stabilization (from `develop`, merge into `main` and back into `develop`)
- `hotfix/*`: production emergencies (from `main`, merge into `main` and back into `develop` or active `release/*`)

This aligns with the widely used GitFlow branching model (feature/release/hotfix). :contentReference[oaicite:4]{index=4}

## Branch Naming Convention

Format:
`<type>/<issue-number>-<area>-<short-slug>`

Where:

- `<type>`: `feature`, `bugfix`, `chore`, `spike`, `hotfix`
- `<issue-number>`: GitHub issue number (required)
- `<area>`: `backend`, `frontend`, `infra`, `docs`, `cross`
- `<short-slug>`: kebab-case, ASCII, concise

Examples:

- `feature/123-frontend-login-form`
- `bugfix/332-backend-null-pointer`
- `chore/88-infra-ci-cache`
- `spike/415-cross-authz-design`
- `hotfix/501-backend-critical-500`

Release branches:

- `release/1.6.0`

## Development Workflow

1. Create or locate an Issue.
2. Create a branch from:
   - `develop` for `feature/*`, `bugfix/*`, `chore/*`, `spike/*`
   - `main` for `hotfix/*`
3. Implement changes with tests.
4. Open a Pull Request using the PR template.

General expectations:

- Keep PRs small and reviewable.
- Avoid mixing unrelated changes.
- Do not commit secrets (tokens, passwords, private keys).

## Pull Requests

- Use the PR template.
- Link the PR to an Issue using closing keywords when applicable (e.g., `Fixes #123`).
  GitHub can automatically close linked issues when the PR is merged. :contentReference[oaicite:5]{index=5}
- CI must pass, and reviews are required per branch protection rules (repository settings).

## Release and Hotfix Flow

### Release

1. Cut `release/<version>` from `develop`.
2. Stabilize on the release branch (fixes only; no new features).
3. Merge `release/<version>` into `main`.
4. Tag the release (e.g., `v1.6.0`) and deploy.
5. Merge `release/<version>` back into `develop`.

### Hotfix

1. Cut `hotfix/<...>` from `main`.
2. Apply the minimal safe fix, validate, then merge to `main`.
3. Merge the same hotfix back into `develop` (or active `release/*`) to prevent regression.

## Security

Do not report sensitive security issues in public Issues.
Use GitHub Security Advisories (private reporting), if enabled for this repository.
