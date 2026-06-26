# Update Process

This document describes how and when the governance documents in `docs/` should be updated, who is responsible, and how to handle reviews.

## Update Triggers

Governance documents must be reviewed and updated when any of the following occur:

| Trigger | Documents to Update |
|---|---|
| New architectural decision made | `decision-log.md` |
| AI agent completes a session | `session-handoff.md` |
| New stable pattern established | `knowledge-base.md` |
| Convention changes | `conventions.md` |
| Agent workflow changes | `agent-workflow.md` |
| Pattern frozen or unfrozen | `locked-patterns.md` |
| This process itself changes | `update-process.md` |

## Scheduled Reviews

All documents in `docs/` must be reviewed on a **quarterly basis** (every 90 days) regardless of whether changes occurred. The AppShield freshness score degrades after 90 days of no updates.

**Review schedule:**
- Q1: January 1
- Q2: April 1  
- Q3: July 1
- Q4: October 1

## Who Reviews

| Document | Primary Owner | Backup |
|---|---|---|
| `agent-workflow.md` | Engineering Lead | CTO |
| `conventions.md` | Engineering Lead | Any senior engineer |
| `decision-log.md` | Any decider | Engineering Lead |
| `knowledge-base.md` | Any contributor | Engineering Lead |
| `locked-patterns.md` | CTO | Engineering Lead |
| `session-handoff.md` | Conducting agent/engineer | Engineering Lead |
| `update-process.md` | CTO | Engineering Lead |

## Update Procedure

1. **Check freshness** — Run an AppShield scan to see which documents are stale
2. **Review content** — Read the document and verify it reflects current reality
3. **Make updates** — Edit the document with accurate, current information
4. **Update the date** — Change the "Last reviewed" or "Last updated" date at the bottom
5. **Commit** — Use commit message format: `docs: update [filename] — quarterly review`
6. **Log if needed** — If the update reflects a significant change, add a `decision-log.md` entry

## AI Agent Updates

AI agents may update `session-handoff.md` and `knowledge-base.md` directly as part of their workflow. All other documents require human review before the update is committed to `main`.

## Freshness Standard

A document is considered **fresh** if it has been committed to `main` within the last **90 days**. Documents older than 90 days will reduce the AppShield freshness score.

**Last reviewed: 2026-06-25**  
**Next review: 2026-09-25**
