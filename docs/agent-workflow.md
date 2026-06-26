# Agent Workflow

This document describes how AI agents interact with the AppShield framework in this repository.

## Overview

Agents operating in this codebase follow a structured workflow that prioritizes safety, transparency, and auditability. Each agent interaction is logged and reviewed against the policies defined in this directory.

## Workflow Stages

### 1. Pre-Task Checklist
Before starting any task, an agent must:
- Confirm the task scope aligns with the project's `CONTRIBUTING.md` guidelines
- Verify no locked patterns (see `locked-patterns.md`) are in scope for modification
- Check the `decision-log.md` for prior decisions that may affect the task
- Review relevant entries in `knowledge-base.md`

### 2. Execution
- Work within the boundaries established in `conventions.md`
- Flag any ambiguity or scope creep immediately
- Do not modify files outside the stated task scope without explicit approval
- Prefer reversible actions over irreversible ones

### 3. Post-Task Handoff
- Update `session-handoff.md` with a summary of changes made
- Log any significant decisions in `decision-log.md`
- Update `knowledge-base.md` if new stable facts were established
- Flag any items for human review before marking the task complete

## Escalation Policy

If an agent encounters any of the following, it must pause and request human review:
- A request to modify security-sensitive files
- Conflicting instructions between documents in this directory
- Any action that would affect more than 5 files simultaneously
- Uncertainty about whether an action is reversible

## Agent Boundaries

| Permitted | Requires Approval | Prohibited |
|---|---|---|
| Read any file | Modify locked patterns | Delete core config files |
| Create new feature files | Refactor shared utilities | Push directly to `main` |
| Update docs in `docs/` | Change CI/CD configuration | Expose secrets or tokens |
| Run tests | Merge pull requests | Bypass review process |

## Versioning

This workflow document was last reviewed: **2026-06-25**  
Next scheduled review: **2026-09-25**
