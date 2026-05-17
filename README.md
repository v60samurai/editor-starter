# Editor Starter

> A forkable kit for a personal AI editor that already knows your voice. **Same spine, infinite variations** — the taste comes from your own `~/.claude/CLAUDE.md`.

Paste any piece of writing in. Get three views back: a structured **critique**, a **tightened** version, and three rewrites in **your own voice**. Sign-in, history, multi-device — the boring infrastructure that turns a demo into a tool you bookmark.

This is the **day-to-day** evolution of Editor, the product from Part 2 of Rethink enablement. The workshop variant shipped in forty-five minutes and treated the URL as the access token. This starter takes that spine and adds the two features that turn a demo into a tool you open three times a day: **authentication** and **memory**.

Two people forking this from scratch should ship two genuinely different products — different voice, different mood, different critique register — without writing different code. The spine is the engineering. The variation is the taste. The taste comes from your global `CLAUDE.md`, which you already have.

---

## Quick Start

```bash
# 1. Clone the kit into a new project
git clone https://github.com/v60samurai/editor-starter.git my-editor
cd my-editor && rm -rf .git && git init

# 2. Read the worked example (10 min)
cat docs/PRD.md docs/BRAND.md docs/PERSONALIZATION.md

# 3. Open Claude Code and paste the build prompt
#    (See "The one-line build prompt" below)

# 4. Ship to Vercel
vercel
```

Total time from clone to deployed Editor: **two to three hours** end to end. Forty-five minutes are for the three core agentic features. The rest is auth, memory, history UI, and personalization audit.

---

## What's in here

```
editor-starter/
├── README.md                          ← you are here
├── docs/                              ← the worked example: Editor
│   ├── PRD.md                         ← v2: includes Auth + Memory sections
│   ├── BRAND.md                       ← the editorial-workshop spine
│   └── PERSONALIZATION.md             ← the spine-vs-variation contract; agent trigger for the build
└── templates/                         ← blank templates to spin new products
    ├── brand-guide-template.md        ← the full brand template
    ├── prd/
    │   ├── template-full-depth.md     ← 16-section discovery + solution PRD
    │   └── template-lean-submission.md← lean PRD for a single-session build
    └── implementation-templates/      ← Shipwright's three-document system
        ├── IMPLEMENTATION_GUIDE.md
        ├── SESSION_PLAYBOOK.md
        ├── FINAL_PUSH.md
        └── README.md                  ← the Usage Guide (read this second)
```

`docs/` is one product (Editor) filled in. `templates/` is the blank kit you use to make another. **`docs/PERSONALIZATION.md` is what makes your fork look nothing like anyone else's** — read it before you start.

---

## How to fork this into your own product

1. **Copy this directory into a fresh repo.** `cp -R editor-starter ../my-editor && cd ../my-editor && git init`.
2. **Read the worked example.** Open `docs/PRD.md`, then `docs/BRAND.md`. This shows you what good looks like.
3. **Run the Personalization Pre-Flight.** Open `docs/PERSONALIZATION.md` Section 5. Ten minutes. Skip this and your fork will look like everyone else's.
4. **Spin your own PRD.** Copy `templates/prd/template-lean-submission.md` to `docs/PRD.md` (overwrite Editor's). Fill it in. Decision Rationale rule applies: every non-obvious choice gets a one-line defense.
5. **Spin your own brand guide.** Copy `templates/brand-guide-template.md` to `docs/BRAND.md`. Fill in five sections minimum for v1.
6. **Generate the implementation pack — point Claude Code at `docs/PERSONALIZATION.md` first.** The Agent Instructions in Section 6 tell the agent how to pull your taste from `~/.claude/CLAUDE.md` into the Implementation Guide. Then run [Shipwright](https://github.com/v60samurai/shipwright) on your PRD, or fill `templates/implementation-templates/{IMPLEMENTATION_GUIDE,SESSION_PLAYBOOK,FINAL_PUSH}.md` by hand. Read `templates/implementation-templates/README.md` for the usage guide.
7. **Hand the four documents to Claude Code.** Build the product session by session.
8. **Run the Personalization Audit before shipping.** Five questions in `docs/PERSONALIZATION.md` Section 7. Pass all five or iterate.

If your fork is also a personal-tool-with-auth-and-memory product, the schema in step 6 should include the `users`, `sessions`, and `entries` tables described in Section 8 of `docs/PRD.md`.

### The one-line build prompt

When you are ready to generate the Implementation Guide, paste this into Claude Code:

> Read `docs/PERSONALIZATION.md` end to end, then follow the Agent Instructions in Section 6. Pull my taste from `~/.claude/CLAUDE.md`, propose first passes for the six personalization slots with one line of reasoning per slot, then generate the Implementation Guide and a draft of `src/persona/CLAUDE.md`. Run the Personalization Audit at the end and report any failures.

---

## The features Editor ships with

| Feature | Agentic pattern | What it does |
|---|---|---|
| **Roast** | Tool use | Critique any paste, located by line, in your voice |
| **Tighten** | Sequential agent loop | Cut a paragraph in half without losing meaning, with a third-call meaning-validator |
| **Voice Match** | Parallel few-shot | Rewrite the same paste in three of your own voices (terse, lyrical, formal — whatever three you pick) |
| **Auth** | Infrastructure | Email magic link via Lucia + Arctic + Oslo. Sessions last thirty days. Default: single-account-per-deploy. |
| **Memory** | Infrastructure | Every paste + output written to `entries`. `/history` lists them newest-first, filterable. Re-run any past entry against the current studio. |

The three core features are unchanged from the workshop. Auth + memory are the two additions that earn the "day-to-day" label.

---

## What this is not

- **Not a SaaS template.** No billing, no teams, no admin UI. Add those in your fork if you need them.
- **Not a hosted product.** You deploy it yourself (Vercel one-click works). The kit is for builders who want to own their tools.
- **Not opinionated about the editor's personality.** The persona file plus voice corpus do all the personality work. The kit is the wiring; the soul is what you put in `src/persona/CLAUDE.md` and `src/corpus/voice-samples.md`.

---

## Stack

- **App**: Next.js 16 App Router, React 19, TypeScript strict, Tailwind 4
- **AI**: Vercel AI Gateway → Anthropic Claude, AI SDK v6, OIDC auth (no provider keys)
- **Auth**: Lucia + Arctic + Oslo (passwordless email magic link)
- **DB**: PostgreSQL via Drizzle (queries) + Prisma (migrations)
- **Email**: Resend (swap to any SMTP via `src/lib/email.ts`)
- **Deploy**: Vercel

The full architecture and the schema scaffolds live in `templates/implementation-templates/IMPLEMENTATION_GUIDE.md` — fill it in for your fork.

---

## Roadmap (post-v2)

- **v2.1**: Postgres trigram search on `entries.input` so you can find a critique by text content.
- **v2.2**: Studio Swap dropdown UI.
- **v2.3**: Mobile-perfect responsive design.
- **v3**: Streaming token-by-token UI for the Tighten flow's three phases.

These are noted in `docs/PRD.md` as out-of-scope-for-now. Fork and ship them if you want.

---

## Contributing

This kit is meant to be **forked**, not maintained as a shared codebase. The expected workflow is:

1. Fork the repo.
2. Build your own Editor on top of it.
3. If you discover an improvement to the **spine** (auth, memory, agentic patterns, deploy story), open a PR back here.
4. If you discover an improvement to a **slot** (your persona, your tools, your studio mood), keep it in your fork. That is by design — variations stay personal.

PRs that touch `docs/PERSONALIZATION.md` or the templates in `templates/` are especially welcome.

---

## License

MIT — see `LICENSE`. Use it, fork it, sell what you build with it. Attribution appreciated but not required.

---

## Credits

Built by [Harshit Badiger](https://github.com/v60samurai). Spun out of Part 2 of Rethink enablement. The three-document Shipwright workflow inside `templates/implementation-templates/` was first published at <https://github.com/v60samurai/shipwright>.

---

*Editor Starter v2.0 · 2026-05-17*
