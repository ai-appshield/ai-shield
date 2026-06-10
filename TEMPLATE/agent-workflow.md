# Agent Workflow

> **AI AppShield — agent-workflow.md**
> Defines which AI model, mode, or tool to use for which type of task.
> Prevents using fast/cheap models for decisions that need careful reasoning.
> Agent: Follow this guide when deciding how to approach a task.

---

## Model Selection by Task Type

| Task Type | Recommended Model/Mode | Why |
|-----------|----------------------|-----|
| Architecture decisions | [PLACEHOLDER — e.g., "Claude Sonnet with extended thinking"] | Requires careful reasoning over tradeoffs |
| New feature planning | [PLACEHOLDER — e.g., "Claude Sonnet standard"] | Needs context + creativity |
| Bug investigation | [PLACEHOLDER — e.g., "Claude Sonnet standard"] | Needs systematic reasoning |
| Code generation (routine) | [PLACEHOLDER — e.g., "Claude Haiku or Cursor Tab"] | Speed over depth |
| Documentation updates | [PLACEHOLDER — e.g., "Any model"] | Low complexity |
| Security review | [PLACEHOLDER — e.g., "Claude Sonnet with extended thinking"] | High stakes, needs depth |
| Refactoring | [PLACEHOLDER — e.g., "Claude Sonnet standard"] | Needs full context |
| Code review / PR summary | [PLACEHOLDER — e.g., "Any capable model"] | Analytical but not deep |

---

## Session Size Rules

- **Small tasks** (1 file, under 50 lines changed): Single session, no plan required
- **Medium tasks** (2–5 files, under 200 lines): Propose steps, get approval, execute
- **Large tasks** (6+ files or architectural): Mandatory phased plan, approved before ANY execution

**Agent rule:** If a task grows beyond its original scope during execution, STOP. Report the scope change to the human and get approval before continuing.

---

## Context Window Management

- Load only the `/docs` files relevant to the current task
- For large documents, read the Table of Contents or routing index first, then load only the relevant section
- When context gets long, use `/compact` (Claude Code) or equivalent before loading new files
- Never attempt to load the entire codebase — load by feature area

---

## Multi-Session Projects

1. **Session start:** Read `session-handoff.md` first. Confirm status before any task.
2. **During session:** Follow `conventions.md` and check `locked-patterns.md` before changes.
3. **Session end:** Update `session-handoff.md` with completed work, in-progress items, and next steps.
4. **Blockers:** If blocked waiting for human input, document the blocker in `session-handoff.md` before ending.

---

## Tool-Specific Notes

### Replit Agent
- [PLACEHOLDER — any Replit-specific workflow notes]

### Claude Code
- Use `/compact` before loading large files
- Use extended thinking for architecture decisions (`claude --think`)
- [PLACEHOLDER — any Claude Code-specific notes]

### Cursor
- Use Composer for multi-file changes, get plan approved first
- [PLACEHOLDER — any Cursor-specific notes]

### GitHub Copilot
- [PLACEHOLDER — any Copilot-specific notes]

---

*Last updated: [DATE] by [WHO]*
