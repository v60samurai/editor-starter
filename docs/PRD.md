# PRD: Editor Starter

**Version**: 2.0 (day-to-day starter) | **Status**: Forkable template
**PM**: Harshit Badiger | **Program**: Rethink enablement, Editor Starter Kit | **Date**: 2026-05-17

---

## A Note to Whoever is Reading This

This PRD is the **day-to-day** version of Editor. The forty-five-minute workshop variant lives at `docs/editor/PRD.md` in the rethink-enablement repo. This starter kit takes that workshop spine and adds the two features that turn a one-session demo into a tool you bookmark and open three times a day: **authentication** (so the app survives shared URLs and multi-device use) and **memory** (so you can find a critique from last Tuesday).

The kit is meant to be **forked**. Drop this whole `editor-starter/` directory into a new repo, swap the six personalization slots, and ship your own version. The blank PRD, brand-guide, and implementation templates ship as a separate **companion templates pack** — see the README for the link.

This is a lean PRD. Sections that would be required for a shipped commercial product (full user research, market sizing, competitive deep dive) are abbreviated because the goal of Editor Starter is to teach the next level of agentic building and give you a daily-useful baseline, not to compete in a market.

---

> **Confidence Tags**
> 🟢 Confirmed by primary research (direct user interviews)
> 🟡 Confirmed by secondary research (market data, reports, reviews)
> 🔵 A direction I believe in but have not yet proven. Treat it as a hypothesis.

---

# PART 1: DISCOVERY

## 1. Problem Tension

### 1.1 Real User Scenario

Builders (PMs, designers, engineers, founders, marketers) write a lot. PRDs. Slack messages. Post drafts. Decision documents. Emails. Pitch decks. Tweets. The volume is roughly ten finished pieces of writing every week and many more drafts that never ship.

For every one of these pieces, the builder wishes they had a brutal editor who knows their voice and pushes back without being mean. In practice, that editor does not exist. Senior colleagues are slow. Real editors are expensive. ChatGPT gives generic feedback that rewrites the builder into someone else. Hemingway and Grammarly catch surface flaws but never the buried lede.

### 1.2 Observable Breakdown

The builder writes the draft. They show it to a friend or a colleague. The feedback comes back a day later, generic, often missing the actual problem. Or they paste it into ChatGPT and get a sanitized rewrite that sounds nothing like them. They learn to do without the second opinion entirely. Quality plateaus. The next draft has the same weaknesses as the last one.

### 1.3 Why Now

Three things changed recently:

1. The Vercel AI Gateway plus AI SDK v6 makes deploying a personalized AI editor a forty-five-minute job for builders who can follow a recipe.
2. Tool use in the AI SDK is now stable. An agent can call back into your code to check for weak verbs, count passive voice, score readability, and synthesize the findings into a critique.
3. The CLAUDE.md pattern proved that a single markdown file can carry a person's voice across many AI sessions. That same file works as the editor's voice in a deployed product.

> **Key Insight**
>
> A personalized editor is not a model fine-tuning problem. It is a system-prompt-and-tool-use problem. One CLAUDE.md plus a small corpus of your best writing is enough to ship an editor that sounds like you.

---

## 2. Target User

**Segment**: Builders. PMs, designers, engineers, founders, and marketers who write often, decide often, and ship often. They have an opinion about their craft and want their tools to reflect it.

**Behavioural traits**:

| Behaviour | Description |
|-----------|-------------|
| Writes ten things a week | PRDs, posts, emails, decision docs, pitches, tweets |
| Edits AI output | Rewrites about half of every AI response before using it |
| Maintains a CLAUDE.md | Has their own voice file at `~/.claude/CLAUDE.md` |
| Bookmarks tools | Will open a personal writing tool URL three times a day if it helps |

**Explicit exclusions**: We are not building for casual ChatGPT users who want a friendlier interface. We are not building for enterprise teams who need shared workspaces or seat-based licensing. We are not building for users without a CLAUDE.md style file.

---

## 3. Narrowed Problem Statement

Builders need a personal AI editor that knows their voice, catches the problems a generic editor misses, and works in five seconds. Today they have ChatGPT (generic, sanitizing) or human editors (slow, expensive). The gap is a personalized AI editor that lives at a URL the builder bookmarks, accepts any piece of writing, and returns three views in the builder's own voice. The voice comes from a single CLAUDE.md file and a small corpus of the builder's best writing.

**In scope:**

- A deployed web app at a personal URL, gated by a passwordless sign-in.
- Three core agentic features that cover the three editing moments builders need most: critique, tighten, rewrite-in-voice.
- **Authentication** via email magic link (single-account-per-deploy by default; trivially extends to a small team).
- **Memory**: every paste plus every output is saved against the user account and surfaced in a `/history` view.
- A persona file (CLAUDE.md) plus a voice corpus (sample paragraphs) as the single source of voice.
- The Studio Swap mechanic (via query param) that lets the builder switch between editor configurations.

**Out of scope:**

- Multi-tenant accounts with billing, teams, or seat licensing. The deploy is owned by you (or your team of two-or-three).
- A dropdown UI for the Studio Swap. The query-param hack is good enough for v1.
- Streaming token-by-token UI. Wait-for-full-response works at v1 scale.
- A fourth agentic-pattern feature. Three covers three different agentic patterns; auth and memory are infrastructure, not new agent patterns.
- Mobile-perfect responsive design.

### Key Assumptions

| Assumption | Evidence | Confidence |
|-----------|----------|------------|
| Builders will paste their writing into a personal Editor URL three times a day | Personal usage pattern across about ten builders I have spoken with | 🔵 |
| A single CLAUDE.md plus a five-paragraph corpus is enough to produce a recognizably personal critique | Demonstrated in Claude Code itself across many sessions | 🟢 |
| Three agentic patterns (tool use, agent loop, parallel few-shot) can be wired in a forty-five-minute attendee build | Demonstrated by a Harshit solo dry-run | 🟢 |

---

# PART 2: SOLUTION

## 4. Product Concept

### What We Are Building

Editor is a deployed personal writing studio. It lives at a personal URL (for example, `daisy-editor.vercel.app`). It has three features. All three features speak in the builder's voice, derived from a persona file and a voice corpus.

The product reuses every piece of wiring from Coach (Part 1) and adds five new agentic concepts on top: tool use, multi-step agent loops, voice corpus / few-shot grounding, streaming structured output, and a Studio Swap mechanic.

### Architecture in One Sentence

A Next.js 16 web app reads `src/persona/CLAUDE.md` and `src/corpus/voice-samples.md` on every request, builds a personalized system prompt with few-shot grounding, and calls Anthropic Claude through the Vercel AI Gateway. One of the three routes uses tool use. Another runs a three-step agent chain. The third runs three parallel few-shot agents.

### Non-Negotiables

| Constraint | What It Means |
|-----------|--------------|
| Persona plus corpus owns the voice | All three features pull personality from the persona file and writing samples from the corpus file. Nothing else. |
| Deploy via OIDC | No provider API keys. Authentication is OIDC through the Vercel AI Gateway. |
| Single-user per deployment | No accounts. The builder owns the URL. |
| Same wiring foundation as Coach | The codebase reuses Coach's parser, persona loader, and route shape. |

### Design Rationale: Why Three Different Agentic Patterns

- Three patterns force the builder to learn three different mental models in one build. Tool use, agent loops, and parallel few-shot are the three things every agent product uses.
- One pattern alone would not earn the title "Atelier's next level."
- Each feature has a clear use case that maps to a distinct moment in the editing workflow, so the patterns are not arbitrary.

---

## 5. The Three Features

### Feature 1: Roast (uses tool use)

**What it does**: The user pastes anything they wrote. Editor returns a structured critique with concerns located by line or paragraph reference, in the user's voice.

**The agentic pattern**: Tool use. The agent has four tools defined in `src/lib/editor-tools.ts` (for example: `find_weak_verbs`, `measure_readability`, `check_jargon`, `score_voice_match`). The agent decides which tools to call, calls them, receives their results, and synthesizes the critique.

**Examples of inputs**: an email draft, a paragraph from a doc, a Slack message, a code change, a tweet.

### Feature 2: Tighten (uses a multi-step agent loop)

**What it does**: The user pastes a paragraph that is too long. Editor cuts it in half while keeping the meaning. The user sees what was cut and why.

**The agentic pattern**: Sequential agent chain. Three LLM calls in sequence. First call plans which cuts to make. Second call executes the cuts. Third call validates that the meaning survived. If the meaning was lost, the third call flags it.

**Examples of inputs**: a long paragraph from a doc, a verbose email, a meandering Slack message, an over-explained tweet thread.

### Feature 3: Voice Match (uses voice corpus and parallel few-shot)

**What it does**: The user pastes a paragraph. Editor rewrites it three times in three of the user's voices (the user chose which three: terse, lyrical, formal, spicy, anything).

**The agentic pattern**: Parallel few-shot generation. Three LLM calls run in parallel. Each one gets the persona system prompt plus corpus samples filtered to one register. The output sounds genuinely like the user because the model has real examples of their writing in each register.

**Examples of inputs**: a paragraph the user wants to ship in three contexts (a tweet thread version, a LinkedIn post version, a long-form version).

---

## 6. The Studio Swap

This is the demonstration mechanic for Editor.

A studio is a `{persona, corpus}` pair. The product ships with three pre-built studios. The Studio Swap UI is a query parameter (`?studio=strunk`) that swaps the persona file and corpus file at request time. The same draft pasted into three studios returns three completely different critiques. The audience sees the same product become three products.

The full dropdown-and-redeploy version of Studio Swap is next-week homework.

---

## 7. The Six Personalization Slots

The spine is locked. Six slots make each attendee's Editor different.

| Slot | What you fill in | Examples |
|---|---|---|
| 1. Editor persona | `src/persona/CLAUDE.md` content | A strict Strunk-style editor, a kind mentor, a Pitchfork critic |
| 2. Voice corpus | 3 to 5 paragraphs of your best writing | Your published essays, your strongest internal memos, your sharpest tweets |
| 3. Three Voice Match registers | Strings in `src/config/registers.ts` | Terse, lyrical, formal, spicy, soft, contrarian |
| 4. Domain focus | Mentioned in CLAUDE.md, biases tool selection | PM, engineer, designer, marketer, sales, academic |
| 5. Tool selection | Which 3 of 8 tools you enable in `editor-tools.ts` | Weak verbs, passive voice, jargon, readability, voice fingerprint, hedging, buried lede, cliche check |
| 6. Studio name and visual mood | Name in `page.tsx`, theme tokens via Stitch | "The Workshop" with editorial-warm, "Roast Lab" with neon-brutalist |

The same code becomes a different product depending on what you put in the slots. Daisy the PM's Editor sounds like a senior PM. Marco the engineer's Editor catches passive voice ruthlessly. Priya the designer's Editor edits like a magazine art director.

> **For the deep dive on personalization** — how your global `~/.claude/CLAUDE.md` feeds each of these six slots, and the exact instructions the build agent should follow when generating your Implementation Guide — read `./PERSONALIZATION.md`. It is the spine-vs-variation contract that makes this kit forkable without producing identical clones.

---

## 8. Account and Memory (Infrastructure for Daily Use)

The workshop variant of Editor put auth and persistence out of scope because the URL was the access token and stateless requests fit a forty-five-minute build. The Starter Kit puts them back in because a tool you actually open every day needs to (a) survive a shared link and (b) let you find the critique you got last Tuesday.

These are infrastructure, not new agentic patterns. They wrap the three features without changing them.

### 8.1 Authentication

**What it does**: A `/login` page asks for an email. The user gets a magic link. Clicking the link creates a session that lasts thirty days. Sign out clears the session. The three editing routes (`/roast`, `/tighten`, `/voice-match`) refuse requests without a valid session.

**Stack**: Lucia + Arctic + Oslo for session-based auth (matches the rest of the stack guidance in the Implementation Guide template — companion templates pack). PostgreSQL holds `users` and `sessions` tables. Magic links are sent via Resend (or any SMTP — adapter in `src/lib/email.ts`).

**Owner model**: Single-account-per-deploy by default. The first email that signs in becomes the owner. Additional sign-ins are rejected unless `AUTH_ALLOWED_EMAILS` env var lists them. This keeps the "personal tool" feel while permitting a small trusted circle.

**Why not just guard with a password or basic auth**: Passwords are friction the user resents. Basic auth breaks on mobile and on shared computers. Magic links are zero-friction, multi-device, and revocable.

**Why not Clerk**: Clerk is excellent and a perfectly valid swap. The default is Lucia because Editor is meant to be forkable and self-hostable with no external auth dependency. If a forker prefers Clerk, the swap touches three files.

### 8.2 Memory

**What it does**: Every request to the three features writes one row to an `entries` table — `(id, user_id, feature, studio, input, output_json, created_at)`. A `/history` route renders the user's entries newest-first, filterable by feature and studio. Clicking an entry shows the full output. Each entry has a "Re-run with current studio" button that re-issues the request with the same input and the live persona.

**Stack**: PostgreSQL via Drizzle. Schema and queries live in `src/lib/db/`. Index on `(user_id, created_at DESC)` for the feed, and a separate index on `(user_id, feature)` for filtering.

**What gets stored**: The raw input text, the structured output the feature returned, the studio slug at the moment of the call, and the persona-file hash so you can tell if the critique came from an older version of your voice. **No user account email is stored on the entry row** — it's referenced via `user_id`.

**Search**: Out of scope for v2. The history feed is a chronological list with feature/studio filters. Postgres trigram search on input text is an easy v2.1 add and noted in the Risks section.

**Why this matters for day-to-day use**: The single largest behaviour change from "demo I built once" to "tool I open daily" is being able to look back. Builders re-read their own writing to find a phrasing that worked. Memory makes Editor's outputs first-class artefacts of the writing process, not throwaway responses.

---

## 9. Out-of-Scope and Why

| Excluded | Reason |
|----------|--------|
| Multi-tenant billing, teams, RBAC | This is a personal tool with an optional trusted-circle list. Real multi-tenant takes a different schema, billing wiring, and admin UI. |
| Streaming response UI | Token-by-token rendering adds complexity. Wait-for-full-response is good enough. |
| A fourth agentic-pattern feature | Three is the smallest number that demonstrates three different agentic patterns. |
| Studio Swap dropdown UI | The query-param version covers v1. Dropdown is next-week homework. |
| Mobile-perfect responsive design | Desktop-first is acceptable for the starter. |
| Full-text search on history | Trigram search lands in v2.1 once usage shows it is worth the index cost. |

---

## 10. Success Definition

The Editor Starter is successful for a forker if:

- Their Editor opens at `your-name-editor.vercel.app` and refuses access without sign-in.
- Magic-link sign-in works on a fresh email; the session persists across browser restarts for thirty days.
- All three editing features return real responses for any pasted input from a signed-in user.
- The Roast feature visibly invokes tools (at least two tool-call events).
- The Tighten feature shows three sequential agent phases in the UI.
- The Voice Match feature returns three visibly different rewrites.
- The Studio Swap (`?studio=<name>`) changes the response voice.
- Every paste-and-respond writes one row to `entries`; the `/history` page lists them newest-first and filters by feature.
- Their persona, corpus, and three voice registers are different from anyone else's.

The forker should arrive at a working build in roughly **two to three hours** (forty-five minutes for the three agentic features per the workshop spine, plus ninety minutes for auth + memory + history UI).

---

## 11. Dependencies

Editor Starter depends on:

- A working Coach build from Part 1 of Rethink enablement (the wiring, the OIDC auth, the deploy pattern carry over).
- A customised `~/.claude/CLAUDE.md` from pre-work, ready to copy into `src/persona/CLAUDE.md`.
- A voice corpus of three to five paragraphs the forker wrote themselves.
- A PostgreSQL database. Neon's free tier is the default in `IMPLEMENTATION_GUIDE.md`; any Postgres works.
- A transactional email provider for magic links. Resend's free tier is the default; any SMTP works via the adapter in `src/lib/email.ts`.
- The build sequence from the Session Playbook (`SESSION_PLAYBOOK.md`, companion templates pack), adapted for Editor — auth lands in Session 3, memory in Session 4 alongside the core pipeline.

---

## 12. Risks

| Risk | Likelihood | Mitigation |
|------|-----------|------------|
| Tool use loop never invokes any tools | Medium for first-timers | Tool descriptions must start with "Use when you suspect..." pattern. The build brief explains. |
| The agent loop in Tighten loses meaning during the Execute step | Medium | The Validate step flags meaning loss. If flagged, the UI surfaces the warning. |
| Voice corpus filtering returns wrong samples | Medium | TDD a regression test on `corpus-loader.ts` before relying on the filter. |
| An attendee's persona is too generic | Medium | The build brief lists four worked variants (PM, engineer, designer, marketer) attendees can adapt directly. |
| Magic-link emails land in spam on first send | High for new domains | Use Resend with a domain verified via DKIM + SPF before the first user signs in. The `IMPLEMENTATION_GUIDE.md` includes the DNS records. |
| Memory grows without bound and slows `/history` | Low until 10k entries, high after | Default index is `(user_id, created_at DESC)`. Above 10k entries per user, partition by month or add a `created_at`-truncated cursor. |
| Stored `input` text leaks if the DB is compromised | Low but the impact is the user's private writing | Application-layer encryption on `entries.input` and `entries.output_json` with a key from `AUTH_ENCRYPTION_KEY`. The schema in `IMPLEMENTATION_GUIDE.md` shows the encrypted-column pattern. |
| Forker forgets to set `AUTH_ALLOWED_EMAILS` and exposes their Editor to anyone with an email | Medium | The first run prints a console warning if the env var is unset and the deploy is on a public URL. |

---

*Editor Starter PRD v2, Harshit Badiger, 2026-05-17. The brand sheet is at `docs/BRAND.md`. The Implementation Guide template (`IMPLEMENTATION_GUIDE.md` in the companion templates pack) is what you fill in for your fork.*
