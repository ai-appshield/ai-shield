# Project Conventions

> **AI AppShield — conventions.md**
> This document defines the coding rules and patterns for this project.
> The AI agent must read this document at session start and follow every rule here without exception.
> If a task would require violating a rule, the agent must explain the conflict and wait for human approval.

---

## Tech Stack

| Layer | Technology | Version |
|-------|-----------|--------|
| Frontend | [PLACEHOLDER] | [VERSION] |
| Backend | [PLACEHOLDER] | [VERSION] |
| Database | [PLACEHOLDER] | [VERSION] |
| Auth | [PLACEHOLDER] | [VERSION] |
| Hosting | [PLACEHOLDER] | — |
| CI/CD | [PLACEHOLDER] | — |

---

## File & Folder Structure

```
[PLACEHOLDER — paste your project's folder structure here]
```

**Rules:**
- New files go in [PLACEHOLDER — define where new files belong]
- Never create files outside the defined structure without approval
- File naming convention: [PLACEHOLDER — e.g., kebab-case, PascalCase]

---

## Naming Conventions

| Item | Convention | Example |
|------|-----------|--------|
| Components | [PLACEHOLDER] | [EXAMPLE] |
| Functions | [PLACEHOLDER] | [EXAMPLE] |
| Variables | [PLACEHOLDER] | [EXAMPLE] |
| Database tables | [PLACEHOLDER] | [EXAMPLE] |
| API endpoints | [PLACEHOLDER] | [EXAMPLE] |
| CSS classes | [PLACEHOLDER] | [EXAMPLE] |

---

## Patterns — Always Use

- [PLACEHOLDER — e.g., "Always use async/await, never .then() chains"]
- [PLACEHOLDER — e.g., "All API responses use the standard envelope: { data, error, meta }"]
- [PLACEHOLDER — e.g., "All database queries go through the repository layer, never direct ORM calls in controllers"]
- [PLACEHOLDER — add as many as needed]

---

## Patterns — Never Use

- [PLACEHOLDER — e.g., "Never use inline styles — all styles go in the CSS module"]
- [PLACEHOLDER — e.g., "Never commit console.log statements"]
- [PLACEHOLDER — e.g., "Never use var — only const and let"]
- [PLACEHOLDER — add as many as needed]

---

## Error Handling

[PLACEHOLDER — describe your error handling standard]
- Where errors are caught
- How errors are logged
- What the user sees vs. what goes to logs
- Which errors are recoverable vs. fatal

---

## API Conventions

[PLACEHOLDER — describe your API design standards]
- Base URL pattern
- Authentication header format
- Standard response envelope
- Error response format
- Versioning strategy

---

## Testing Standards

[PLACEHOLDER — describe your testing approach]
- What must be tested
- Test file location and naming
- Minimum coverage requirements
- How to run tests

**Agent rule:** After any code change, propose what tests should be run or written before marking the task complete.

---

## Environment & Configuration

- Environment variables go in: [PLACEHOLDER]
- Never hardcode credentials, API keys, or environment-specific values
- Config file location: [PLACEHOLDER]
- How to add a new environment variable: [PLACEHOLDER]

---

## Task Segmentation Rule

For any task touching more than 2 files or involving architectural change:
1. Propose a phased plan listing each step
2. Wait for human approval of the plan
3. Execute one phase at a time
4. Confirm completion of each phase before proceeding

Never execute a large multi-file change in a single shot without an approved plan.

---

*Last updated: [DATE] by [WHO]*
