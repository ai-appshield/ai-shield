# Decision Log

This file records significant architectural, product, and technical decisions made during the development of AppShield. It serves as institutional memory for the team and AI agents.

---

## Format

Each entry follows this structure:
```
## [DATE] — [Decision Title]
**Context:** Why this decision was needed
**Decision:** What was decided
**Alternatives Considered:** What else was evaluated
**Outcome:** Result / status
```

---

## 2026-06-23 — Dual-Mode Scanner Architecture
**Context:** The scanner was only checking 7 standard OSS files (README, SECURITY, etc.) but AppShield's core mission is scoring the 7 AppShield framework docs in `/docs/`.
**Decision:** Implement dual-mode scoring — `appShieldScore` for the 7 framework docs + `aiReadinessScore` for the 7 OSS files + a blended `overallScore`.
**Alternatives Considered:** Single score combining all 14 files; separate scan modes triggered by user toggle.
**Outcome:** Dual scores shipped in same scan pass. Both shown in UI with clear labels.

## 2026-06-16 — Scan History Parked for v2
**Context:** Supabase integration for scan history was causing 500 errors blocking the dashboard ship.
**Decision:** Remove scan history from v1 dashboard. Ship scanner + AI Audit cleanly. Revisit in v2.
**Alternatives Considered:** Defensive fallback with empty array; localStorage cache.
**Outcome:** Dashboard shipped cleanly. Supabase tables and lib/supabase.ts preserved for v2 wiring.

## 2026-06-15 — Clerk Production Migration
**Context:** Dev Clerk keys have 500 MAU cap and do not work on production domains.
**Decision:** Migrate to Clerk production instance before any public launch or marketing.
**Alternatives Considered:** Keep dev keys, manually whitelist domains.
**Outcome:** Completed. Production keys active at aiappshield.io.

## 2026-06-14 — GitHub PAT Over OAuth for Scanner
**Context:** GitHub App OAuth adds complexity. Server-side PAT allows 5,000 req/hr for scanning.
**Decision:** Use `GITHUB_PAT` env var on server as primary token. User OAuth token passed from client as override for private repos.
**Alternatives Considered:** GitHub App installation tokens; purely unauthenticated (60 req/hr too low).
**Outcome:** Working in production. Private repo scanning enabled via Clerk OAuth link.

## Last Updated
2026-06-23
