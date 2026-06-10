# AI AppShield v1.5

> **Battle-tested AI coding framework by TraghmTech.**
> Stop AI agents from breaking your codebase. Start every project right.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.5-blue.svg)]()
[![TraghmTech](https://img.shields.io/badge/by-TraghmTech-teal.svg)]()

---

## What Is AI AppShield?

AI AppShield is a structured documentation framework that sits between your team and your AI coding agent. It is a set of markdown files your agent reads before touching a single line of code — a living contract that defines how your codebase works, what must never change, and what the agent learned from past mistakes.

Without a framework like this, AI agents:
- Rewrite settled architecture on a whim
- Repeat the same bugs across sessions
- Contradict decisions made in previous sessions
- Make "improvements" that break unrelated features
- Upgrade locked dependencies without asking

With AI AppShield, agents confirm they have read the rules before every session. They propose changes before executing them. They update documentation automatically after every task. And they never touch locked patterns without explicit human approval.

---

## The Core Principle

AI AppShield is built on one idea: **the agent works for the documentation, not the other way around.**

Code changes reality. Documentation records reality. Agents must always reflect reality as the human has approved it — never invent their own.

---

## The Two-Action Rule

Every AI agent action falls into exactly one of two types:

| Type | What It Is | Who Decides | When |
|------|-----------|-------------|------|
| **Type 1 — Codebase** | Any change to code, config, permissions, infrastructure, schema | Human approves **BEFORE** execution | Always propose first, wait for go-ahead |
| **Type 2 — Documentation** | Any update to `/docs` reflecting an approved change | Agent executes **AUTOMATICALLY** | After every completed task, no approval needed |

**Why this matters in production:** Without this rule, agents ask for approval on doc updates (slow) and execute code changes silently (dangerous). The Two-Action Rule makes the right thing the easy thing.

**Real example:** An agent was asked to add a new API endpoint. Without the Two-Action Rule, it added the endpoint AND silently changed the permission middleware to make it work. The permission change broke three other endpoints. With the Two-Action Rule, the agent proposes the endpoint (Type 1, waits for approval), builds it after approval, then automatically updates `knowledge-base.md` and `session-handoff.md` (Type 2, no approval needed).

---

## Five Core Principles

1. **Docs first, code second.** The agent reads `/docs` before any task — no exceptions.
2. **Propose before you execute.** All Type 1 (codebase) changes require human approval first.
3. **Silence means stop.** If a change conflicts with `/docs`, the agent explains and waits. It never proceeds on ambiguity.
4. **Every session leaves a trail.** `session-handoff.md` is updated after every session so the next session starts in seconds, not minutes.
5. **Mistakes become permanent knowledge.** Every bug, workaround, and lesson gets logged in `knowledge-base.md` so it can never happen again.

---

## Quick Start

### Step 1 — Copy the Templates

Copy everything in the `/TEMPLATE` folder into a `/docs` folder at the root of your project:

```
your-project/
└── docs/
    ├── conventions.md
    ├── locked-patterns.md
    ├── knowledge-base.md
    ├── session-handoff.md
    ├── update-process.md
    ├── decision-log.md
    └── agent-workflow.md
```

### Step 2 — Fill In the Templates

Each template has `[PLACEHOLDER]` sections. Fill them in for your specific project:
- `conventions.md` — your stack, naming rules, coding patterns
- `locked-patterns.md` — architecture that must never change
- `knowledge-base.md` — start with any known bugs or workarounds
- `session-handoff.md` — current status and what's next

### Step 3 — Add the Directive to Your Agent

Copy the appropriate snippet from the `/DIRECTIVE` folder into your AI tool's context file:

| AI Tool | Context File | Snippet |
|---------|-------------|----------|
| Replit Agent | `replit.md` | `DIRECTIVE/replit-snippet.md` |
| Claude Code | `CLAUDE.md` | `DIRECTIVE/CLAUDE-snippet.md` |
| Cursor | `.cursorrules` | `DIRECTIVE/cursorrules-snippet.md` |
| GitHub Copilot | `.github/copilot-instructions.md` | `DIRECTIVE/copilot-instructions-snippet.md` |
| Windsurf | `.windsurfrules` | Use `DIRECTIVE/cursorrules-snippet.md` as base |
| OpenAI Codex | `AGENTS.md` | Use `DIRECTIVE/CLAUDE-snippet.md` as base |

### Step 4 — Start Your Session

At the start of every AI session, the agent should respond with:

```
AI AppShield loaded. I have read all required documents.
Current status: [one sentence from session-handoff.md]. Ready for task.
```

If the agent does not send this confirmation, prompt it:
> "Read the AppShield docs and confirm before we start."

### Step 5 — Keep It Alive

After every session, verify the agent updated `session-handoff.md`. After every bug fix, verify it updated `knowledge-base.md`. The framework only works if it stays current.

---

## Document Reference

### `docs/conventions.md`
The coding constitution for your project. Defines your tech stack, naming conventions, file structure rules, patterns to always use, and patterns to never use. The agent treats this as law. Everything it writes must conform to what is written here.

### `docs/locked-patterns.md`
The no-touch list. Files, modules, architecture decisions, and dependency versions that must never be changed without explicit human approval. This is where you protect your auth system, payment provider, ORM configuration, CI/CD pipeline, and API permission middleware. The agent reads this first and checks every proposed change against it.

### `docs/knowledge-base.md`
Institutional memory. Logs confirmed bugs and their fixes, known workarounds, integration quirks, and hard-won lessons. Every time an agent causes a problem that gets fixed, the fix goes here so no future session can repeat the same mistake.

### `docs/session-handoff.md`
The session bridge. Written at the end of every session, read at the start of the next. Captures current state, what was just completed, what is in progress, what is next, and any open questions. Transforms a cold-start session from a 15-minute re-briefing into a 30-second confirmation.

### `docs/update-process.md`
The rules for keeping `/docs` current. Defines which document to update after which type of change, how to handle conflicts, and the Two-Action Rule in detail. The agent follows this automatically after every task.

### `docs/decision-log.md`
Architecture Decision Records (ADRs). Logs the context, options considered, decision made, and rationale for every major architectural choice. Prevents agents from questioning and overriding settled decisions because the reasoning is already documented.

### `docs/agent-workflow.md`
Multi-model guidance. Defines which AI model or mode to use for which type of task — architecture decisions, bug fixes, code generation, review. Prevents using a fast cheap model for decisions that need careful reasoning.

---

## Large Document Protocol

As projects grow, `/docs` files — especially `knowledge-base.md` — will grow large. A document over 600 lines can exceed an agent's practical context window. AI AppShield includes a built-in scaling strategy.

### Size Thresholds

| Document Size | Strategy |
|--------------|----------|
| Under 200 lines | Standard — no changes needed |
| 200–400 lines | Add a Table of Contents with section summaries at the top |
| 400–600 lines | ToC + consider splitting the heaviest sections into sub-documents |
| 600+ lines | Split into sub-documents with a routing index |
| 1000+ lines | Mandatory split + archive stale entries to `docs/archive/` |

### The Routing Index Pattern

When a document grows past 600 lines, convert it into a routing index:

```markdown
# knowledge-base.md (Routing Index)

> This document is the index. Read the relevant sub-document for details.
> Do NOT read all sub-documents. Read only what your current task requires.

## Index
- Authentication issues → docs/kb/auth.md
- Payment & billing → docs/kb/payments.md  
- API integrations → docs/kb/integrations.md
- Database & ORM → docs/kb/database.md
- Performance → docs/kb/performance.md
- Deployment → docs/kb/deployment.md
```

### Agent Directive for Large Documents

Add this block to your agent context file when any `/docs` file exceeds 400 lines:

```
## Large Document Protocol
If any /docs file exceeds 400 lines:
1. Read the Table of Contents or routing index first
2. Identify which section is relevant to your current task
3. Read only that section — do not load the entire document
4. If unsure which section applies, ask before loading
Never attempt to load a document over 600 lines in full.
```

---

## Has This Been Done Before?

Partial implementations exist — `.cursorrules` files, `CLAUDE.md` patterns, and the CSO Framework (project_milestones + documentation) are widely used in the community. What makes AI AppShield different is the combination of:

- **Conflict resolution protocol** (silence = stop) as a first-class rule
- **The Two-Action Rule** separating codebase and documentation actions
- **Locked patterns** as a dedicated, structured document
- **Session handoff** as a mandatory end-of-session artifact
- **Large document scaling strategy** built into the framework from day one

No public framework combines all five. AI AppShield is the first to formalize them together as a complete, tool-agnostic system.

---

## Community

- **Contribute:** See [CONTRIBUTING.md](CONTRIBUTING.md)
- **Issues & ideas:** [Open an issue](https://github.com/ai-appshield/ai-shield/issues)
- **Built with AI AppShield?** Add it to the [EXAMPLES](EXAMPLES/) folder

---

*Built by [TraghmTech](https://github.com/NerdChild137) · Dallas, Texas*
*MIT License — free to use, fork, and build upon*
