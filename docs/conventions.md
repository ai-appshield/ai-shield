# Conventions

This document defines the coding, naming, and documentation conventions for this repository. All contributors — human and AI — are expected to follow these standards.

## Code Style

### General
- Use 2-space indentation for all files (TypeScript, JavaScript, JSON, YAML)
- Maximum line length: 100 characters
- Use single quotes for strings in TypeScript/JavaScript
- Always include trailing commas in multi-line objects and arrays
- Semicolons required in TypeScript/JavaScript

### TypeScript
- Prefer `interface` over `type` for object shapes
- Use explicit return types on all exported functions
- No `any` — use `unknown` and narrow, or define proper types
- Prefer `const` over `let`; never use `var`
- Async functions must handle errors with `try/catch`

### React / Next.js
- All components use the `'use client'` or `'use server'` directive explicitly
- Component files use PascalCase: `MyComponent.tsx`
- Utility files use camelCase: `parseDate.ts`
- One component per file
- Props interfaces named `[ComponentName]Props`

## File & Directory Naming

| Type | Convention | Example |
|---|---|---|
| React components | PascalCase | `HealthScoreCard.tsx` |
| Utilities/helpers | camelCase | `formatDate.ts` |
| API routes | kebab-case | `scan-history.ts` |
| Documentation | kebab-case | `decision-log.md` |
| Config files | lowercase | `next.config.js` |
| Environment files | SCREAMING_SNAKE | `.env.local` |

## Git Conventions

### Branch Naming
- Features: `feat/short-description`
- Bug fixes: `fix/short-description`
- Docs: `docs/short-description`
- Refactors: `refactor/short-description`

### Commit Messages
Follow Conventional Commits:
```
<type>(<scope>): <short description>

[optional body]
[optional footer]
```
Types: `feat`, `fix`, `docs`, `refactor`, `test`, `chore`, `ci`

## Documentation Standards

- Every public function must have a JSDoc comment
- Every new feature requires an entry in `docs/decision-log.md`
- Breaking changes must be documented in `CHANGELOG.md`
- All markdown files use ATX-style headers (`#`, `##`, `###`)

## AI-Assisted Development

- All AI-generated code must be reviewed by a human before merging
- AI sessions must be documented in `docs/session-handoff.md`
- No AI agent may commit directly to `main` without human approval
- AI agents must follow the workflow defined in `docs/agent-workflow.md`

## Last Reviewed

**2026-06-25** — Next review: **2026-09-25**
