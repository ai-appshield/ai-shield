# Locked Patterns

This document lists code patterns, architectural decisions, and conventions that are **frozen** — they must not be changed without an explicit decision recorded in `decision-log.md` and approval from a project maintainer.

AI agents must check this file before making any changes that could affect these patterns.

---

## Locked Patterns

### 1. Authentication Flow
**Pattern:** All authentication is handled exclusively through NextAuth.js with the GitHub provider.  
**Reason:** Changing auth providers requires migration of all existing user sessions and tokens.  
**Locked since:** 2026-01-01  
**To change:** Requires maintainer approval + migration plan in `decision-log.md`

### 2. Database Schema — `saved_repos` Table
**Pattern:** The `saved_repos` table schema (columns: `id`, `user_id`, `repo_full_name`, `created_at`) must not be altered without a migration script.  
**Reason:** Schema changes affect all existing users' saved data.  
**Locked since:** 2026-01-01  
**To change:** Requires a Supabase migration file + maintainer approval

### 3. Scoring Algorithm Output Format
**Pattern:** The `ScanResult` interface shape must remain stable. New fields may be added (non-breaking) but existing fields must not be renamed or removed.  
**Reason:** The scoring output is consumed by multiple components and the AI audit endpoint.  
**Locked since:** 2026-03-01  
**To change:** Requires a deprecation period + update to all consumers

### 4. `docs/` Directory as Governance Root
**Pattern:** All AppShield governance documents must live in `docs/`. The scanner is hardcoded to look in this path.  
**Reason:** Standardization across all repos using the AppShield framework.  
**Locked since:** 2026-06-25  
**To change:** Would require a scanner update + migration guide for all users

### 5. Perplexity API — No Persistent Storage of File Contents
**Pattern:** File contents read during AI audits must never be stored in the database. Only the audit result (score, findings, summary) may be persisted.  
**Reason:** Privacy and data minimization — users' source code must not be retained.  
**Locked since:** 2026-01-01  
**To change:** Requires explicit user consent mechanism + privacy policy update

---

_Last reviewed: **2026-06-25**_
