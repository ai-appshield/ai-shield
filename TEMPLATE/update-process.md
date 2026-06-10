# Update Process

> **AI AppShield — update-process.md**
> Defines how and when `/docs` documents are updated.
> Agent: Follow this document after every completed task.

---

## The Two-Action Rule (Quick Reference)

| Type | Action | Approval | Timing |
|------|--------|----------|--------|
| **Type 1** | Any codebase change (code, config, permissions, schema, infrastructure) | Human approves **BEFORE** execution | Propose → Wait → Execute |
| **Type 2** | Any `/docs` update reflecting an approved change | **Automatic** — no approval needed | Execute immediately after task completion |

**The rule in plain English:** Reality (code) is always a human decision first. Documentation always follows reality automatically.

---

## Change-to-Document Mapping

After every completed task, update the appropriate documents:

| Change Type | Update These Documents |
|-------------|----------------------|
| New feature added | `session-handoff.md`, `conventions.md` (if new pattern introduced) |
| Bug fixed | `knowledge-base.md` (bug + fix), `session-handoff.md` |
| Architecture decision made | `decision-log.md`, `session-handoff.md` |
| Dependency added or changed | `conventions.md` (tech stack), `locked-patterns.md` (if pinned) |
| File or folder structure changed | `conventions.md` (file structure section) |
| New workaround discovered | `knowledge-base.md` (workarounds section) |
| Locked pattern added | `locked-patterns.md` |
| Session ended | `session-handoff.md` (always) |

---

## Conflict Resolution Protocol

If a requested change conflicts with any document in `/docs`:

1. **Stop.** Do not proceed with the change.
2. **Explain** the conflict clearly: which document, which rule, why there is a conflict.
3. **Propose options** if applicable: how the task could be achieved within the rules, or what would need to change.
4. **Wait** for human approval before taking any action.

**Silence = do not proceed.** If you are unsure whether something conflicts, ask. Never assume permission.

---

## Document Health Rules

- `session-handoff.md` must be updated at the end of EVERY session, no exceptions
- `knowledge-base.md` must be updated after EVERY bug fix
- Stale entries (older than 90 days with no relevance) may be archived to `docs/archive/` after human approval
- No document should be deleted — archive instead

---

## Large Document Escalation

If any document exceeds the following thresholds, flag it to the human:

| Threshold | Action |
|-----------|--------|
| 400 lines | Add Table of Contents |
| 600 lines | Propose splitting into sub-documents |
| 1000 lines | Mandatory split — do not add more content until restructured |

---

*Last updated: [DATE] by [WHO]*
