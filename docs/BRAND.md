# Brand Guide: Editor

> Editorial workshop. Three-column layout. The brand bends to the persona you pick.

This is the **mini** brand guide for Editor. Five sections from the full brand-guide template (companion templates pack — see the README for the link).

For Editor, the brand serves a special role: each forker picks a studio mood (Strunk, Pitchfork, Mentor, or their own) and Stitch generates tokens that match that mood. So the brand here describes the **spine of the brand** (the rules that apply across all studios) and leaves the **studio-specific visual** to each forker.

**Source PRD**: `./PRD.md`
**Generated from**: a partial fill of the full brand-guide template (companion templates pack)
**Owner**: Harshit Badiger
**Last updated**: 2026-05-17

The deep dive on brand voice, components, motion, microcopy, and accessibility lives in a separate session.

---

## 1. The Brief (from the PRD)

| Field | Value |
|---|---|
| Target user | Builders who write ten things a week and want a personal editor |
| Primary job to be done | Get a critique of any piece of writing in my voice, in five seconds |
| Top 3 things the user must see | 1. The studio name and current voice indicator, 2. The three feature tabs, 3. The output (critique, tightened text, or voice rewrites) |
| Platforms | Web only |
| Locale | English |
| Dark mode | None for v1 |

---

## 3. Visual Idea (spine, per-studio overrides allowed)

> *Editorial workshop. Three-column layout for Voice Match. Hairline rules between findings. The brand bends to the studio mood the attendee picks.*

**We chose this because** Editor's value depends on each attendee's variant looking and sounding different from the others. A locked visual brand would defeat the personalization story. The spine is the layout grammar (columns, hairlines, eyebrow tags). The variable part is the studio mood, which Stitch generates per attendee.

**We rejected** a locked palette and font set because then every attendee's Editor would look like Harshit's. The Studio Swap moment loses impact.

---

## 4. Typography (spine)

| Role | Family | Notes |
|---|---|---|
| Display | **Variable** per studio | Stitch picks a display font matched to the studio mood (editorial serif for Strunk, condensed sans for Pitchfork, calligraphic for Mentor) |
| Body | **Inter** | Locked across studios for readability |
| Mono (eyebrow labels) | **JetBrains Mono** | Locked across studios for technical legibility |

**Rule:** Body and mono are locked. The display font varies per studio. This gives each attendee's Editor a unique top-of-page feel without breaking readability for the long stretches of editing output.

---

## 5. Color (spine plus studio token)

The base palette is the same warm-paper editorial system Coach uses. Each studio adds one mood-specific accent that Stitch generates.

| Token | OKLCH | Use |
|---|---|---|
| `--color-stone-50` | `oklch(96.5% 0.018 75)` | Background. Warm paper. Locked across studios. |
| `--color-stone-900` | `oklch(22% 0.020 30)` | Body text. Locked. |
| `--color-accent` | **Studio-specific** | Stitch generates this per studio based on the mood adjective the attendee picked. Strunk gets ink-blue. Pitchfork gets neon-pink. Mentor gets sage-green. |

**Rule:** One studio accent token. Used three to five times per screen. Never more.

---

## 13. Microcopy

**Voice ownership.** Editor's voice in the critique, tighten output, and voice match output comes entirely from the persona file plus the voice corpus. The product itself uses minimal microcopy.

**Product microcopy rules:**

- Button labels say what they do, not what they encourage. "Roast it" not "Get your roast." "Tighten" not "Tighten me."
- Empty states use one italic sentence in stone-500. Example: *"Paste anything you wrote."*
- Error states say what failed and what to try, in stone-900, no emoji.
- The current studio name appears in the top-left at all times so the user always knows which voice is loaded.

---

## 17. What This Brand is NOT

- Editor is not a chat product with personality stickers. It is an editing studio.
- Editor is not a single locked aesthetic. Each studio can look completely different.
- Editor is not multi-color within one studio. One accent per studio, used sparingly.
- Editor is not friendly by default. Friendliness comes from the persona file if the attendee writes it that way.

---

## What is intentionally not in this mini guide

Sections from the full brand-guide template that we skipped for time and will cover in the separate branding session:

- Surface Declaration
- Spacing and Shape system
- Motion
- Iconography
- Information Hierarchy
- States (full matrix)
- Data and Formatting
- Accessibility (full WCAG checklist)
- Components (the full library)
- Surface-Specific Patterns
- Global Anti-Patterns (full list)
- Token Scaffolds (machine-readable)

For Editor today, Stitch generates the per-studio tokens live during the build and applies them to `globals.css`. The full disciplined brand work lives in its own session.

---

*Editor BRAND.md v2, Harshit Badiger, 2026-05-17. The PRD is at `./PRD.md`. The Implementation Guide template ships in the companion templates pack.*
