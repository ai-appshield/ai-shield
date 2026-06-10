# GitHub Copilot Instructions Snippet

> Copy the block below and paste it as the **very first content** in
> `.github/copilot-instructions.md`. Create the file and `.github/` directory if they don't exist.
> Nothing should appear above this block.

```markdown
# AI AppShield Directive

Read /docs before making any changes. These documents are the source of truth.

## Session Start Protocol
At session start, read in order:
1. docs/conventions.md — coding rules and patterns
2. docs/locked-patterns.md — frozen files and architecture
3. docs/knowledge-base.md — bugs, workarounds, lessons
4. docs/session-handoff.md — current status and next steps

Confirm with: "AI AppShield loaded. Status: [summary]. Ready for task."
Do not begin work before this confirmation.

## The Two-Action Rule
- Codebase changes (Type 1): Require explicit human approval BEFORE execution
- Documentation updates (Type 2): Execute automatically AFTER task completion

## Conflict & Scope Rules
- Conflict with /docs: explain conflict, await approval, silence = stop
- Never modify: auth system, payment provider, ORM, CI/CD pipeline, or locked-patterns.md items
- After every task: update relevant /docs files per update-process.md

github.com/ai-appshield/ai-shield
```
