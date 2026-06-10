# Cursor Rules Directive Snippet

> Copy the block below and paste it as the **very first content** in your `.cursorrules` file.
> Nothing should appear above this block.

```
# AI AppShield Directive
# Read /docs BEFORE any changes. These are the source of truth.

## Session Start (MANDATORY)
Before any task, read:
1. docs/conventions.md
2. docs/locked-patterns.md
3. docs/knowledge-base.md
4. docs/session-handoff.md

Confirm with: "AI AppShield loaded. Status: [from session-handoff]. Ready."
Do NOT begin any task before this confirmation.

## The Two-Action Rule
TYPE 1 (code/config/permissions): Human approves BEFORE execution. Propose first. Wait.
TYPE 2 (doc updates): Execute AUTOMATICALLY after every task. No approval needed.

## Hard Rules
- Conflict with /docs → explain and wait. Silence = do not proceed.
- NEVER touch: auth, payments, ORM, CI/CD, locked-patterns.md items — without explicit approval.
- After every task: update /docs per update-process.md.
- Use Composer for multi-file changes. Get plan approved first.

# github.com/ai-appshield/ai-shield
```
