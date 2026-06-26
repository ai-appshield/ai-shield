# Decision Log

This file records significant architectural, design, and policy decisions made in this project. Each entry explains the context, the decision made, and the rationale.

---

## Decision Format

```
## [YYYY-MM-DD] Title of Decision
**Status:** Accepted | Superseded | Revoked
**Deciders:** [names or roles]
**Context:** What situation prompted this decision?
**Decision:** What was decided?
**Rationale:** Why was this the right choice?
**Consequences:** What changes as a result?
```

---

## [2026-06-25] Rename TEMPLATE/ to docs/
**Status:** Accepted  
**Deciders:** TraghmTech Engineering  
**Context:** The AppShield scoring system requires AI governance documents to be located in a `docs/` directory. The existing `TEMPLATE/` directory name caused the repo to score poorly because the scanner could not locate required files.  
**Decision:** Rename `TEMPLATE/` to `docs/` and update all internal references.  
**Rationale:** Aligning with the AppShield framework standard ensures the repository serves as a valid example for customers adopting the framework.  
**Consequences:** All links to `TEMPLATE/` files must be updated in README and any external documentation.

---

## [2026-06-25] Use ai-appshield/ai-shield as Example Scan
**Status:** Accepted  
**Deciders:** TraghmTech Engineering  
**Context:** The AppShield dashboard was using `appshield-dashboard` itself as the example scan, which created a circular reference and wasn't demonstrating the framework's value.  
**Decision:** Change the example scan target to `ai-appshield/ai-shield`.  
**Rationale:** The `ai-shield` repo is the canonical reference implementation of the AppShield framework and should be used as the demo target.  
**Consequences:** Updated `ConnectRepo.tsx` quick-fill button and template link.

---

_Add new decisions above this line, newest first._
