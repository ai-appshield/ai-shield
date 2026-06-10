# Knowledge Base

> **AI AppShield — knowledge-base.md**
> This is the institutional memory of this project.
> The agent must read this document at session start.
> After every bug fix or lesson learned, the agent must update this document (Type 2 action — automatic).

---

## ⚠️ Large Document Notice

If this file exceeds 400 lines, add a Table of Contents here.
If it exceeds 600 lines, convert to a routing index (see README.md — Large Document Protocol).

---

## Confirmed Bugs & Fixes

> Log every bug that was found and fixed. Format: what broke, why it broke, how it was fixed.
> This prevents the same mistake from ever happening twice.

### [PLACEHOLDER — Bug Title]
- **Date discovered:** [DATE]
- **Symptom:** [What the user or developer saw]
- **Root cause:** [Why it happened]
- **Fix applied:** [What was changed]
- **Prevention:** [What rule or check prevents recurrence]

---

## Known Workarounds

> Log things that work in an unexpected or non-obvious way.
> If a future agent would likely "fix" something that shouldn't be fixed, document it here.

### [PLACEHOLDER — Workaround Title]
- **Component:** [What system or file this applies to]
- **Issue:** [What problem the workaround addresses]
- **Workaround:** [What we do instead of the obvious approach]
- **Why not the obvious approach:** [Why the normal way doesn't work here]
- **Do NOT change this without approval**

---

## Integration Quirks

> Third-party services often behave unexpectedly. Log those quirks here.

### [PLACEHOLDER — Service Name]
- **Quirk:** [What the unexpected behavior is]
- **Impact:** [What breaks if you don't account for this]
- **Handling:** [How we deal with it in code]

---

## Hard-Won Lessons

> General lessons learned from this project that future sessions should know.

- [PLACEHOLDER — e.g., "Replit's file watcher fires twice on save — debounce all file-watch handlers"]
- [PLACEHOLDER — e.g., "The Stripe webhook must verify signature before parsing body — never swap the order"]
- [PLACEHOLDER — add as many as needed]

---

## Performance Notes

> Log any performance findings — slow queries, expensive operations, caching decisions.

- [PLACEHOLDER — e.g., "The /dashboard endpoint N+1 queries — fixed with eager loading, do not revert"]

---

## Security Notes

> Log any security decisions that might look like mistakes to a future agent.

- [PLACEHOLDER — e.g., "CORS is intentionally restrictive — do not broaden without security review"]

---

*Last updated: [DATE] by [AGENT/WHO]*
