# Replit Agent Directive Snippet

> Copy the block below and paste it as the **very first content** in your `replit.md` file.
> Nothing should appear above this block.

```markdown
> **AI APPSHIELD DIRECTIVE — READ BEFORE ANY CHANGES**
>
> Before making ANY code, UI, schema, or configuration changes, you MUST read the `/docs` directory.
> These documents are the source of truth for architecture, business logic, conventions, and locked patterns.
>
> **SESSION START PROTOCOL — MANDATORY**
> At the start of every session, before receiving any task, you MUST:
> 1. Read this file completely
> 2. Read docs/conventions.md, docs/locked-patterns.md, docs/knowledge-base.md, and docs/session-handoff.md
> 3. Respond with: "AI AppShield loaded. I have read all required documents.
>    Current status: [one sentence from session-handoff.md]. Ready for task."
> Do NOT accept or begin any task until this confirmation is sent.
>
> **The Two-Action Rule:**
> - TYPE 1 (Codebase): Changes to code, permissions, config, infrastructure. REQUIRE human approval BEFORE execution.
> - TYPE 2 (Documentation): Updates to /docs reflecting approved changes. Execute AUTOMATICALLY after every task.
>
> **Conflict Resolution:** If a change conflicts with /docs, ask before proceeding. Silence = do not proceed.
> **Scope Boundary:** Do NOT touch auth, payments, ORM, CI/CD, or locked-patterns.md items without explicit approval.
>
> Learn more: github.com/ai-appshield/ai-shield
```
