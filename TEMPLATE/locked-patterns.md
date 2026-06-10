# Locked Patterns

> **AI AppShield — locked-patterns.md**
> This document lists everything that must NOT be changed without explicit human approval.
> Before proposing any change, the agent must check this document.
> If a proposed change touches anything listed here, STOP and ask for approval. Do not proceed.

---

## Locked Files — Do Not Modify

| File / Path | Reason Locked | Approval Required From |
|-------------|--------------|------------------------|
| [PLACEHOLDER] | [WHY] | [WHO] |
| [PLACEHOLDER] | [WHY] | [WHO] |

---

## Locked Architecture — Do Not Redesign

The following architectural decisions are final. Do not suggest replacing, refactoring, or significantly changing these components without explicit approval:

- **Authentication system:** [PLACEHOLDER — e.g., "Clerk — do not replace or modify auth flow"]
- **Payment provider:** [PLACEHOLDER — e.g., "Stripe — do not swap or restructure payment logic"]
- **Database ORM:** [PLACEHOLDER — e.g., "Prisma — do not switch to raw SQL or another ORM"]
- **CI/CD pipeline:** [PLACEHOLDER — e.g., "GitHub Actions — do not modify workflow files"]
- **Hosting infrastructure:** [PLACEHOLDER — e.g., "Replit — do not introduce Docker or external server config"]
- [PLACEHOLDER — add others as needed]

---

## Locked Dependencies — Frozen Versions

The following packages are pinned to specific versions. Do NOT suggest upgrading them. Each pin exists for a documented reason.

| Package | Pinned Version | Reason |
|---------|---------------|--------|
| [PLACEHOLDER] | [VERSION] | [WHY — e.g., "v4 breaks our ORM integration"] |
| [PLACEHOLDER] | [VERSION] | [WHY] |

**Agent rule:** Never suggest a dependency upgrade as part of a task unless the task explicitly requires it and the human has approved it.

---

## Locked API Permissions & Middleware

The permission and authorization middleware is production-critical. Changes here affect every protected route.

- **Middleware file:** [PLACEHOLDER — file path]
- **Permission model:** [PLACEHOLDER — describe your RBAC/ACL model briefly]
- **Rule:** Any change to permissions, roles, or middleware requires human review and approval BEFORE execution. No exceptions.

---

## Locked Database Schema

The following tables/collections are in production with live data. Schema changes require a migration plan:

| Table / Collection | Notes |
|-------------------|-------|
| [PLACEHOLDER] | [e.g., "Has 50k+ rows — migrations must be backward compatible"] |

**Agent rule:** Never modify a locked schema table without a migration plan approved by the human first.

---

## Scope Boundaries — Out of Scope for AI

The following are permanently out of scope for AI agent action, regardless of context:

- [ ] Replacing the authentication provider
- [ ] Changing the payment gateway
- [ ] Modifying environment variable names in production
- [ ] Changing the database provider
- [ ] Modifying CI/CD workflow files
- [ ] [PLACEHOLDER — add project-specific scope limits]

---

*Last updated: [DATE] by [WHO]*
