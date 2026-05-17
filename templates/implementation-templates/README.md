# Vibe Coding Templates — Usage Guide

Three documents. One system. Build any product solo with Claude Code.

---

## What You Provide

| File | What it is |
|------|-----------|
| `PRD.md` | What to build, for whom, the core loop, pricing, edge cases |
| `USER_FLOWS.md` + `.jsx` | How users move through every screen (can be wireframes in code) |
| `BRAND_GUIDE.md` | Colors, typography, tone of voice, animation style, design principles |

## What This System Provides

| File | What it is |
|------|-----------|
| `IMPLEMENTATION_GUIDE.md` | Technical reference: architecture patterns, schema, analytics, security, launch checklist |
| `SESSION_PLAYBOOK.md` | Linear execution: what to build in what order, exact Claude Code prompts |
| `FINAL_PUSH.md` | Polish layer: demo prep, UI micro-details, milestone moments |

---

## How to Use It

### Step 1: Fill the templates

Search for `{{` in all three files. Every placeholder needs a value from your PRD, User Flows, or Brand Guide.

Key replacements:
- `{{PRODUCT_NAME}}` — your product's name
- `{{PRIMARY_COLOR}}` — your brand's primary hex color
- `{{entity}}` / `{{entities}}` — your domain object (deal, task, project, recipe, etc.)
- `{{core_action}}` — the main thing users do (log, create, analyze, book, etc.)
- `{{architecture_diagram}}` — fill from your PRD's system design

### Step 2: Add to your repo

```
/docs
├── PRD.md
├── USER_FLOWS.md
├── BRAND_GUIDE.md
├── IMPLEMENTATION_GUIDE.md
├── SESSION_PLAYBOOK.md
└── FINAL_PUSH.md
```

### Step 3: Write CLAUDE.md

At the project root, create `CLAUDE.md` using the template in the Session Playbook Pre-Flight section. This loads automatically in every Claude Code session.

### Step 4: Follow the Playbook

Run sessions in order. Do not skip checkpoints. The checkpoints exist to catch broken foundations before they become expensive.

---

## Sessions Overview

| Session | What You Build | Time |
|---------|---------------|------|
| Pre-Flight | Services, scaffold, CLAUDE.md | 30 min |
| 1 | Database schema | 30-45 min |
| 2 | Landing page | 60-90 min |
| 2.5 | Schema verification | 15 min |
| 3 | Backend skeleton + auth | 30-45 min |
| 4 | Core feature pipeline | 45-90 min |
| 5 | Auth UI + onboarding | 45-60 min |
| 🚀 A | Deploy backend | 15 min |
| 6 | Dashboard shell + home | 60-90 min |
| 7 | Core dashboard screens | 60-90 min |
| 8 | Settings + billing | 30-45 min |
| 9 | Background jobs + email | 45-60 min |
| 10 | PWA + responsive polish | 30-45 min |
| 🚀 B | Full loop test | 20 min |
| 11 | Edge cases | 30-45 min |
| 12 | Delight layer | 30-45 min |
| 13 | Analytics audit | 20-30 min |
| 14 | Launch prep | 30 min |

**Total: ~12-16 hours solo**

---

## What's Different from the HustlrAI Docs

Sections added that weren't in HustlrAI:
- **Analytics (PostHog)** — full event taxonomy, funnel setup, feature flags, server-side events
- **Error monitoring (Sentry)** — frontend + backend setup, PII scrubbing, error boundaries
- **Email service (Resend)** — templates for every lifecycle email, React Email setup
- **Payment integration (Stripe)** — webhook handler, checkout flow, billing portal
- **CI/CD pipeline** — GitHub Actions for lint, type check, test, deploy
- **Security checklist** — auth, database, API, frontend, infrastructure
- **Performance targets** — concrete numbers, Lighthouse thresholds
- **Launch checklist** — technical, legal, UX, content, SEO
- **Post-launch metrics** — what to track week 1, north star + leading indicators
- **Settings + billing session** — GDPR delete, subscription management
- **Analytics audit session** — verify every event fires, PostHog dashboard setup

---

## Adapting for Different Product Types

### Web-only (no bot, no background jobs)

Skip: Session 9 background jobs, all bot-related sections in IG and FP.
Add: More frontend-heavy sessions — more time on Sessions 6 and 7.

### Consumer app (B2C)

Add: Session for mobile app (React Native or PWA) — Session 10 becomes the primary focus.
Change: Analytics taxonomy emphasizes engagement metrics over business metrics.
Change: Payments via in-app purchase, not Stripe web.

### B2B SaaS with teams

Add: Organization/workspace schema (users belong to orgs, orgs own entities).
Add: Invitation flow session.
Add: Role-based access control (RBAC) — additional RLS policies.
Change: Billing is per-org, not per-user.

### AI-first product

Expand: Session 4 (core pipeline) to 2 sessions — one for pipeline, one for prompt engineering and output validation.
Add: Prompt versioning strategy (prompts in database, not code, for easy iteration).
Add: AI cost monitoring — log token usage per user per action.

---

## Version

Template v1.0 — built from HustlrAI production docs
Last updated: {{DATE}}
