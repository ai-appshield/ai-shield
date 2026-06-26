# Agent Workflow

This document defines how AI agents (Copilot, Claude, Cursor, Perplexity, etc.) should interact with this codebase. Following these guidelines ensures consistent, safe, and productive AI-assisted development.

---

## Core Principles

1. **Read before writing** — Always read the relevant file before proposing changes
2. **Minimal footprint** — Change only what is necessary for the task at hand
3. **Cite decisions** — Reference `docs/decision-log.md` when proposing architectural changes
4. **Respect locked patterns** — Never override items in `docs/locked-patterns.md`
5. **Human approval** — No merge without explicit human confirmation

---

## Session Start Protocol

At the start of every development session, an agent should:
1. Read `docs/session-handoff.md` — understand where the last session ended
2. Read `docs/decision-log.md` — understand major decisions already made
3. Read `docs/locked-patterns.md` — know what must not change
4. Confirm the current task with the human before writing any code

---

## File Ownership

| Area | Files | Notes |
|------|-------|-------|
| Scanner logic | `lib/scanner.ts` | Core scoring — changes require justification |
| Auth | `middleware.ts`, Clerk config | Never modify without security review |
| Database | `lib/supabase.ts`, `supabase/` | Schema changes need migration file |
| UI Components | `components/` | Free to iterate with human approval |
| API Routes | `app/api/` | All routes must validate auth via Clerk |

---

## Prohibited Actions

- Do not delete or overwrite `docs/` files without explicit instruction
- Do not add new environment variables without updating `.env.example`
- Do not change the scoring algorithm without updating `docs/decision-log.md`
- Do not introduce new npm dependencies without noting them in the PR description
- Do not push directly to `main` — always via PR (except emergency hotfixes)

---

## Recommended Workflow for New Features

```
1. Read docs/session-handoff.md + docs/decision-log.md
2. Confirm feature scope with human
3. Identify affected files (read them first)
4. Write code changes
5. Check against docs/locked-patterns.md
6. Present diff to human for approval
7. Push on approval
8. Update docs/session-handoff.md
```

---

## Session End Protocol

At the end of every productive session:
1. Update `docs/session-handoff.md` with what was completed
2. Log any significant decisions in `docs/decision-log.md`
3. Note the next agenda item clearly

## Last Updated
2026-06-23
