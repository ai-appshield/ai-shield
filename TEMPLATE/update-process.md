# Update Process

## Overview
This document defines how changes are reviewed, approved, and merged into this project. All contributors and AI agents must follow this process.

## Change Categories

| Category | Examples | Review Required |
|----------|----------|----------------|
| **Critical** | Auth, payments, data deletion | 2 reviewers + security check |
| **Feature** | New UI, new API endpoint | 1 reviewer |
| **Docs** | README, inline comments | Self-merge allowed |
| **Hotfix** | Production bug | 1 reviewer, expedited |

## Standard PR Process

1. **Branch** — Create a feature branch from `main`: `feat/`, `fix/`, `docs/`, `chore/`
2. **Develop** — Write code, run tests locally
3. **PR** — Open pull request with a clear title and description linking to the issue
4. **Review** — At least one approval required before merge
5. **CI** — All checks must pass (lint, type-check, build)
6. **Merge** — Squash and merge preferred; delete branch after merge

## AI Agent Guidelines

- AI agents may draft code but must not merge without human approval
- All AI-generated changes must be reviewed for security implications
- Agents should reference this file before proposing architectural changes

## Versioning

This project follows [Semantic Versioning](https://semver.org/):
- **MAJOR** — Breaking API changes
- **MINOR** — New backward-compatible features
- **PATCH** — Backward-compatible bug fixes

## Hotfix Process

For critical production issues:
1. Branch directly from `main` with prefix `hotfix/`
2. Fix, test, and open PR immediately
3. Tag one reviewer for expedited review
4. Deploy and monitor for 30 minutes post-merge

## Last Updated
2026-06-23
