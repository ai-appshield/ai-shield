# Claude Code Directive Snippet

> Copy the block below and paste it as the **very first content** in your `CLAUDE.md` file.
> Nothing should appear above this block.

```markdown
# AI AppShield Directive

Read /docs before making any changes. These documents are the source of truth.

## Session Start (MANDATORY)
Before any task, read in this order:
1. docs/conventions.md
2. docs/locked-patterns.md
3. docs/knowledge-base.md
4. docs/session-handoff.md

Then respond: "AI AppShield loaded. Current status: [from session-handoff]. Ready."
Do NOT start any task before sending this confirmation.

## The Two-Action Rule
- TYPE 1 (Codebase changes): ALWAYS require explicit human approval BEFORE execution
- TYPE 2 (Doc updates): Execute AUTOMATICALLY after every completed task. No approval needed.

## Rules
- Conflict with docs → explain conflict, wait for approval. Silence = stop.
- Do NOT touch: auth, payments, ORM, CI/CD, or anything in locked-patterns.md without approval.
- After every task: update /docs per update-process.md (Type 2 — automatic).
- Use /compact when context window gets long.

Learn more: github.com/ai-appshield/ai-shield
```
