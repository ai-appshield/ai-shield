# Knowledge Base

This document captures stable, reusable facts, patterns, and domain knowledge for this project. It is intended to help AI agents and new contributors get up to speed quickly and avoid repeating past research.

## Project Overview

**AppShield** is an AI governance framework that helps software teams score, track, and improve the AI-readiness of their repositories. It scans repos for the presence, completeness, and freshness of key governance documents.

## Scoring Model

AppShield scores repositories on three dimensions:

| Dimension | Description | Weight |
|---|---|---|
| **Presence** | Required files exist in the correct location (`docs/`) | 40% |
| **Completeness** | Files contain substantive content, not just placeholders | 40% |
| **Freshness** | Files have been updated within the review window (90 days) | 20% |

## Required Files

The following 7 files must exist in the `docs/` directory for a full score:

1. `docs/agent-workflow.md` — How AI agents interact with the codebase
2. `docs/conventions.md` — Coding and documentation standards
3. `docs/decision-log.md` — Record of significant decisions
4. `docs/knowledge-base.md` — This file; stable domain knowledge
5. `docs/locked-patterns.md` — Patterns that must not be changed without approval
6. `docs/session-handoff.md` — Summary of recent AI sessions
7. `docs/update-process.md` — How governance docs are maintained

## Architecture

- **Frontend:** Next.js 14 (App Router), React, TypeScript
- **Backend:** Next.js API routes
- **Auth:** NextAuth.js with GitHub OAuth
- **Database:** Supabase (PostgreSQL)
- **AI Audit:** Perplexity API
- **Deployment:** Vercel

## Key Integrations

### GitHub API
Used for: scanning repo file trees, reading file contents, OAuth login, commit monitoring.

### Supabase
Used for: storing saved repositories, scan history, user sessions.

### Perplexity API
Used for: AI Readiness Audit — reads file contents, generates findings and a score, immediately discards contents.

## Common Gotchas

- The scanner looks for files in `docs/` specifically — files in `TEMPLATE/`, `templates/`, or root-level won't score
- Freshness is based on the file's last `git commit` date, not file metadata
- The `locked-patterns.md` file must list at least 3 patterns to be considered complete

## Last Updated

**2026-06-25**
