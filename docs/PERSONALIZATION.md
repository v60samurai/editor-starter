# Personalization: How Your Editor Becomes Yours

> The spine is locked. The variation is infinite. The variation comes from **you**.

This document is the contract between Editor Starter and the person forking it. The kit ships with a fixed spine — wiring, features, file structure — but the *taste* of the product is meant to be yours, derived almost entirely from a file you already have: your global `~/.claude/CLAUDE.md`.

If you do this right, your Editor and your neighbour's Editor share zero visible surface. Same code. Different products.

This doc is also the **trigger for the build agent**. When Claude Code is about to generate the Implementation Guide for your fork, point it at this file. The Agent Instructions section near the bottom tells the agent exactly how to fold your taste into the build.

---

## 1. The Premise: Spine and Variation

A product like Editor has two layers.

**The spine** is the part nobody should redo. It is the agentic wiring, the route structure, the auth pattern, the persistence schema, the deploy story, the safety rails. The spine is the unsexy 80% of code that takes weeks to get right and that you only want to write once in your life. Editor Starter owns the spine and you should treat it as load-bearing.

**The variation** is everything you would have made different anyway. The mood. The brand. The voice of the critique. The exact tool selection. The studio name. The microcopy. The choice between strict-and-cutting versus warm-and-mentoring as the default critique register. Editor Starter explicitly refuses to choose for you here — and the six personalization slots in the PRD are the seams where your choices land.

The product gets its identity from the variation. Not from the spine.

> **Key Insight**
> The spine is engineering. The variation is taste. Engineering can be copied. Taste cannot. That is why this is forkable and still useful.

---

## 2. Why the Variation Comes From Your Global CLAUDE.md

Your global `~/.claude/CLAUDE.md` is already a structured representation of how you think, write, decide, and approach work. It has tone rules. Stack preferences. Forbidden patterns. Voice instructions. Behavioural rules. Quality bars. It has been refined over hundreds of Claude Code sessions and it is the densest signal of *you* anywhere on your machine.

A persona file inside Editor (`src/persona/CLAUDE.md`) is supposed to encode the same thing — but most forkers will not have the discipline to write one from scratch. The trick is to recognize that **a personal `~/.claude/CLAUDE.md` is already 80% of what a persona file needs to be**. The remaining 20% is light editing to point the voice at writing critique instead of code generation.

So the workflow is:

1. The forker already has `~/.claude/CLAUDE.md`.
2. The build agent reads it.
3. The agent generates the Implementation Guide *and* a first draft of `src/persona/CLAUDE.md` derived from the global file.
4. The forker reviews, edits, ships.

The agent does the heavy lift. The forker keeps editorial control.

---

## 3. How Taste Flows Through the Build

Taste is not a one-time decision; it propagates through the artefacts. Here is where your global file leaves a fingerprint.

| Stage | Artefact | What your global file influences |
|---|---|---|
| Discovery | `docs/PRD.md` | The framing of the problem, the verbs you use, the level of confidence tagging, the way exclusions are phrased |
| Brand | `docs/BRAND.md` | The visual mood, the typography rule strictness, the microcopy register |
| Implementation | `IMPLEMENTATION_GUIDE.md` (filled-in; template ships in the companion templates pack) | The stack choices, naming conventions, file structure, test discipline, comment philosophy |
| Runtime persona | `src/persona/CLAUDE.md` | The voice the critique speaks in: warm vs cutting, terse vs lyrical, hedging vs declarative |
| Runtime corpus | `src/corpus/voice-samples.md` | Few-shot examples that anchor the voice in actual writing you have done |

You do not have to fill any of these from scratch. The build agent reads `~/.claude/CLAUDE.md` and proposes a first pass for each one. You edit. You ship.

---

## 4. The Six Slots, Mapped to Your Global File

The PRD names six personalization slots. Each one has a natural source in a well-maintained global `CLAUDE.md`.

| Slot | What it is in Editor | What your global gives you |
|---|---|---|
| 1. **Editor persona** | `src/persona/CLAUDE.md` | The tone rules, decision-rationale style, behavioural rules sections. These translate almost directly into critique voice. |
| 2. **Voice corpus** | 3–5 paragraphs of your best writing | The examples you have committed to your repos' `docs/` folders, your published essays, your sharpest commit messages. The agent can surface candidates. |
| 3. **Three Voice Match registers** | Strings in `src/config/registers.ts` | Your "Response Style" section if you have one, plus any voice rules in your global. Common picks: terse, lyrical, contrarian, formal, mentoring. |
| 4. **Domain focus** | A line in the persona file biasing tool selection | The "Identity" or "Role" section of your global. PM, engineer, designer, founder — whatever your day job calls you. |
| 5. **Tool selection** | Which 3 of 8 tools you enable in `src/lib/editor-tools.ts` | The "Forbidden Patterns" and "Quality Bar" sections. If you obsess over weak verbs, enable that tool. If passive voice does not bother you, drop it. |
| 6. **Studio name and visual mood** | Name in `src/app/page.tsx`, theme tokens via Stitch | Your favourite product references (often in CLAUDE.md as design feedback vocab), your preferred density, your colour preferences. |

If your global is sparse, this mapping shows you what to add to it next. The personalization layer doubles as a diagnostic for your meta-file.

---

## 5. The Personalization Pre-Flight (Run This Before Session 1)

Before you start the implementation build, run this checklist. It takes ten minutes and saves the variant from feeling like Harshit's product with your name on it.

- [ ] `~/.claude/CLAUDE.md` exists and is at least one hundred lines. If not, fill it before forking.
- [ ] You have read your own `CLAUDE.md` in the last week. If not, re-read it.
- [ ] You can name three things about your taste that are non-obvious to a stranger. Examples: "I refuse em dashes." "I always start emails with a one-line frame." "I think 90% of design feedback should be about hierarchy."
- [ ] You have three to five paragraphs of writing you would happily quote in a portfolio. These become the voice corpus.
- [ ] You have picked a studio name that you would say out loud without flinching.

If any of these is missing, do not start the build. The spine works without them but the variation collapses, and you will ship something that looks like a tutorial output.

---

## 6. Agent Instructions (read this when generating the Implementation Guide)

The build agent (Claude Code, in practice) should treat this section as **executable instructions** when it is asked to generate or fill the Implementation Guide for a fork. Pass the path to this file in the prompt; the agent reads from here.

### Step A — Read the forker's global file

Read `~/.claude/CLAUDE.md` end to end. Extract:

1. **Tone rules** (any section about voice, response style, communication, microcopy).
2. **Stack preferences** (frameworks, libraries, tools the forker likes; libraries the forker forbids).
3. **Behavioural rules** (how the forker wants you to act, what they want you to avoid).
4. **Quality bar** (the rules they hold code/writing to).
5. **Forbidden patterns** (the explicit nope list).

### Step B — Map extracted signal to the six slots

For each of the six personalization slots in Section 4 above, propose a first pass derived from what you extracted in Step A. Show the forker your reasoning in one line per slot. Example:

> Slot 1 (Editor persona): your global forbids em dashes and asks for "caveman English." Proposing a Strunk-Hemingway hybrid persona: terse, declarative, surgical with verbs, no decoration.

### Step C — Generate the Implementation Guide

Fill the Implementation Guide template (from the companion templates pack) using the stack preferences extracted in Step A. Where the template offers a default (e.g. "PostgreSQL" or "Lucia"), check whether the forker's global names a different choice and substitute if so. Where the template asks for a comment-style or test-style decision, mirror the forker's stated rules verbatim.

### Step D — Draft the persona file

Write `src/persona/CLAUDE.md` as a *focused* derivative of the global. Strip the parts about code generation and product management; keep the parts about voice, tone, behavioural rules, forbidden patterns, and quality bar. Add a one-paragraph framing at the top: "You are the editor. You critique writing the way the person below thinks. Here is how they think:" followed by the extracted rules.

### Step E — Surface candidates for the voice corpus

Scan the forker's filesystem (ask permission first) for `*.md` files in their personal projects' `docs/` folders, their resume, their published essays, their commit messages with non-trivial bodies. Surface the three to five strongest candidates and ask the forker to pick. Do not write to `src/corpus/voice-samples.md` without confirmation — corpus content is high-stakes; one wrong paragraph poisons every Voice Match output.

### Step F — Confirm the personalization audit

Before reporting the Implementation Guide as ready, run the Personalization Audit in Section 7 below and report failures inline.

---

## 7. The Personalization Audit (run this before shipping)

Five questions. If any answer is no, the variation has not landed.

1. If you handed your Editor URL to your closest collaborator with no context, could they guess it was yours within thirty seconds of reading one critique?
2. Does at least one of the three Voice Match registers say something a stranger could not have written?
3. Does the studio name read like a brand your friends would say without quotation marks, or like a tutorial placeholder ("MyEditor", "EditorApp")?
4. Does the visual mood look different from the screenshots in the Editor Starter README?
5. Is the persona file fewer than two hundred lines? (More than two hundred and you have copied your global verbatim instead of focusing it.)

Pass all five before shipping. Fail any one and iterate on that slot specifically before launch.

---

## 8. What If You Do Not Have a Global CLAUDE.md Yet

Editor Starter is still useful. The work shifts: instead of the agent extracting taste from a file, it interviews you. The pre-flight becomes an explicit conversation:

- Show me a piece of writing you are proud of. (For corpus seed.)
- Show me a piece of writing you would re-write today. (For critique direction.)
- What are three things a generic editor always gets wrong about your work? (For tool selection.)
- Who would you trust to edit your writing? Name three. (For persona reference.)

After the build, the agent should offer to compile these answers into a starter `~/.claude/CLAUDE.md` for the forker. Your global file is one of the most valuable artefacts you can own; building Editor is a good excuse to start one.

---

## 9. Why This Matters

The product industry has a pattern: someone ships a starter template, three people fork it, and the three forks look identical because nobody bothered to push past the defaults. That outcome is the failure mode this document exists to prevent.

Editor Starter is a sharp version of the same idea: the spine is so engineered that a beginner can build a working product in a few hours, but the variation surface is so wide that two builds done by people with different `CLAUDE.md` files end up genuinely different products.

The doc you are reading is the contract. Read it. Hold the agent to it. Ship the variation.

---

*Personalization v1, Harshit Badiger, 2026-05-17. Companion to `./PRD.md` and `./BRAND.md`. The build agent should read this file before generating the Implementation Guide for your fork.*
