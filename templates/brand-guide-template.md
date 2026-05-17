# Brand Guide

> [One-line design philosophy. A constraint, not a mission statement.]

---

## How to use this template

This is the single source of truth for branding, UI, and UX for one product. Fill it once, feed it to your AI coder (Claude Code, Cursor, Lovable), and reference it for every design decision.

**Source of truth rule:** if an AI coder asks "what font / what color / what spacing / what copy," the answer is in this file. If it isn't, the answer is "stop and ask." Never let the AI default to Tailwind or shadcn values.

**Fill order:**

1. The Brief (precondition; nothing below works without it)
2. Surface Declaration (which sections apply)
3. Visual Idea (the single constraint)
4. Foundations (Typography through Components)
5. Surface-specific patterns for declared surfaces
6. Run the anti-pattern check per section

**Decision Rationale Requirement.** Every non-obvious choice in this file carries a one-line defense:

> We chose [X] because [Y]. We rejected [Z] because [W].

If you can't write that sentence, the choice isn't made yet. No silent choices.

---

## Table of Contents

1. The Brief
2. Surface Declaration
3. Visual Idea
4. Typography
5. Color
6. Spacing & Shape
7. Motion
8. Iconography
9. Information Hierarchy
10. States
11. Data & Formatting
12. Accessibility
13. Microcopy
14. Components
15. Surface-Specific Patterns
16. Global Anti-Patterns
17. What This Brand is NOT
18. Appendix: Token Scaffolds

---

## 1. The Brief

Mandatory. Empty fields force generic output.

### Target user

[Specific. Name a role with their situation. Not "busy professionals," not "early adopters." Example: "D2C founder running a Shopify store with ₹50L to ₹5Cr ARR, using 4+ tools daily, values speed over polish."]

### Primary job to be done

[One sentence. `When [situation], the user wants [motivation], so they can [outcome].` Only one. If you have three, pick the one whose absence breaks the product.]

### Top 3 things the user must see

In priority order. On any screen, the visual hierarchy surfaces these first, second, third.

1. [Primary]
2. [Secondary]
3. [Tertiary]

### Constraints

- **Platforms:** [Web / iOS / Android / CLI / other. Only what ships in v1.]
- **Performance budget:** [Initial load target. Font payload ceiling. Interactive time target.]
- **Locale:** [Primary locale. Note secondary locales if multi-locale.]
- **Accessibility target:** [WCAG AA or AAA. Pick one.]
- **Technical stack:** [E.g., Next.js 14 + Tailwind + shadcn.]
- **Dark mode:** [Required / Optional / None.]

### Rejected directions

Minimum three. The obvious directions you considered and ruled out.

1. [Not this, because...]
2. [Not this, because...]
3. [Not this, because...]

---

## 2. Surface Declaration

Tick every surface this product ships. Skip Section 15 subsections you don't tick.

- [ ] **Landing** — marketing site, home page, lead capture
- [ ] **App** — authenticated product UI, dashboards, settings
- [ ] **Conversational** — chat interface, agent, bot (Telegram, WhatsApp, in-app chat)
- [ ] **Transactional** — email, receipt, PDF export, invoice
- [ ] **Mobile** — native iOS / Android or mobile-first web
- [ ] **CLI** — terminal, command-line, developer tool
- [ ] **Docs** — developer documentation, API reference

Foundations (sections 4 to 14) apply to all surfaces. Surface-specific patterns (section 15) only for ticked surfaces.

---

## 3. Visual Idea

One sentence: **[core visual principle in bold].**

[2 to 3 sentences explaining WHY this direction. Name specific tools or products that validate the choice. End with the decision framework: when does the user see X, when do they see Y.]

**The rule:** [The single constraint. Violations get rejected without further discussion.]

**Why not [obvious alternative 1]:** [1 to 2 sentences.]

**Why not [obvious alternative 2]:** [1 to 2 sentences.]

---

## 4. Typography

### 4.1 Font selection

Declare every font used. Each carries a defense. Popular fonts (Inter, Geist, Switzer, Fraunces, Clash Display, Satoshi, Instrument Serif) are not banned. Picking them without defense is. "Trending on Fontshare" is not a defense.

**Display font:** [Name]. [Source.]
- Character: [1 line.]
- Usage: [Hero headlines, section titles, display numbers above Xpx]
- Defense: We chose [this] because [reason]. We rejected [runner-up] because [reason].

**Body font:** [Name]. [Source.]
- Character: [1 line.]
- Usage: [Running copy, UI labels.]
- Defense: We chose [this] because [reason]. We rejected [runner-up] because [reason].

**Monospace font (if used):** [Name]. [Source.]
- Character: [1 line.]
- Usage: [Code blocks, specific tabular numeral contexts — see 4.6.]
- Defense: We chose [this] because [reason].

**Stack count rule:** max 3 font families. Four fonts means one is doing the job of another.

### 4.2 Type scale

One canonical scale. Every text element maps to a row.

| Role | Font | Weight | Size (px) | Line height | Tracking |
|------|------|--------|-----------|-------------|----------|
| Hero display | | | | | |
| H1 | | | | | |
| H2 | | | | | |
| H3 | | | | | |
| Body large (lead) | | | | | |
| Body | | | | | |
| Body small | | | | | |
| UI label | | | | | |
| Button | | | | | |
| Caption / metadata | | | | | |
| Micro (legal, timestamp) | | | | | |

**Rule:** no text element sits outside this table. If you need one, add a row and defend it.

### 4.3 Weight usage

Which weights ship, and where. Three or four is typical. Using one weight for everything collapses hierarchy.

- **400 (Regular):** [body copy, captions, long-form reading]
- **500 (Medium):** [UI labels, secondary emphasis]
- **600 (Semibold):** [buttons, H3, running-copy emphasis]
- **700 (Bold):** [H1, H2, hero]
- **Variable axis (if the font supports it):** [declare axis, range used]

Weights not on this list don't ship.

### 4.4 Line height

Set per type role in the scale above. Defaults produce slop: body too tight, headings too loose.

Rules of thumb (adjust to the font):
- Display: 1.0 to 1.1
- Headlines: 1.1 to 1.25
- Body: 1.4 to 1.6
- UI labels, buttons: 1.0 to 1.2

### 4.5 Italic rules

Italic is a deliberate choice. Declare where it appears.

- [Running copy emphasis / book titles / pull quotes / technical identifiers / specific hero word per Visual Idea]

**Pattern to avoid:** one italic word in a hero that says "crafted," "reimagined," "thoughtfully," or "actually." Italic in a hero is fine if the word and reason are declared in the Visual Idea.

**Font pairing rule:** different fonts have different italics (Fraunces italic is restrained, Instrument Serif italic is tilted-calligraphic). Pick one italic language and stay in it.

### 4.6 Numbers and monospace

- **Tabular numerals** (fixed-width): tables, dashboards, financial readouts, timers. Aligns on decimal.
- **Proportional numerals** (default): running copy, dates in prose, metadata.
- **Monospace font:** code blocks, API examples, copy-paste strings. Mono on calendar dates or prices is slop ("it looks technical"). Defense required if mono escapes code contexts.

### 4.7 Typographic details

- **Smart quotes always:** `"` and `'`, not `"` and `'`.
- **En-dash** for ranges (`5 – 9`). **Em-dash** for breaks (only if the Visual Idea allows).
- **ASCII hyphen** only for compound words.
- **Ellipsis:** `…`, not `...`.

### 4.8 OpenType features and variable axes

If a font ships stylistic sets, optical size axis, or other variation axes, declare which are active and why.

- [Feature or axis]: [where applied, why]

`font-feature-settings: 'ss01', 'ss02'` pasted globally from a Tailwind config without knowing what the features do is slop.

### 4.9 Font loading and performance

**Payload budget:** [X KB total woff2, post-subsetting]. State it.

- **Subsetting:** Latin + Latin-Extended only unless the locale requires more.
- **`font-display: swap`** required on all web fonts.
- **Preload:** display font (above fold). Body fonts swap.
- **Self-host vs CDN:** [declare]. Self-host for stable perf.

```html
<link rel="preload" href="/fonts/[display].woff2" as="font" type="font/woff2" crossorigin>
```

### 4.10 Typography anti-patterns

- Everything at `font-semibold`. Hierarchy collapses.
- Two sizes only (`text-4xl` hero, `text-base` everything). No lead paragraphs, no metadata.
- Gradient text on hero by reflex. Allowed only if declared in Visual Idea.
- `tracking-tight` on display without checking the font's defaults.
- Popular fonts picked without defense ("Fraunces because it's pretty").
- Display fonts at body sizes (Fraunces at 14px).
- Four fonts loaded, two actually used.
- Italic used only for the one-word-in-hero trope.

---

## 5. Color

### 5.1 Neutral axis

Pick one. Default Tailwind `zinc` or `slate` untouched is slop.

- [ ] **Warm** (stone, sand, cream): hex anchor `#XXXXXX`
- [ ] **Cool** (slate, blue-gray): hex anchor `#XXXXXX`
- [ ] **Pure** (true gray): hex anchor `#XXXXXX`
- [ ] **Custom** (specific off-neutral): hex anchor `#XXXXXX`

Defense: We chose [axis] because [reason].

### 5.2 Surface elevation

Declare 4 levels minimum. Without this, cards, modals, and popovers all sit on the same background.

| Level | Token | Light | Dark | Usage |
|-------|-------|-------|------|-------|
| 0 | `bg` | | | Page background |
| 1 | `surface` | | | Cards, panels |
| 2 | `surface-raised` | | | Hovered cards, dropdowns, focused inputs |
| 3 | `surface-overlay` | | | Modals, sheets, popovers |
| 4 | `surface-tooltip` | | | Tooltips, top z-index overlays |

### 5.3 Text colors

| Token | Light | Dark | Usage |
|-------|-------|------|-------|
| `text` | | | Primary text |
| `text-secondary` | | | Descriptions, labels |
| `text-muted` | | | Placeholders, timestamps, disabled |
| `text-inverse` | | | Text on accent-filled surfaces |

### 5.4 Borders

| Token | Light | Dark | Usage |
|-------|-------|------|-------|
| `border` | | | Dividers, card borders |
| `border-strong` | | | Active inputs, emphasis |
| `border-accent` | | | Accent-adjacent borders |

### 5.5 Accent

One accent. Two only if defended.

**Primary accent:** [color name], `#XXXXXX`
- Usage: [primary CTAs, active nav, focus rings, selected states]
- Hover state: `#XXXXXX`
- Dim state (subtle backgrounds): `#XXXXXX`

**Secondary accent (optional):** [color], `#XXXXXX`
- Usage: [where, why distinct from primary]
- Defense: two accents because [reason].

**Cap:** accent on no more than X% of any screen. Most surfaces are neutral.

### 5.6 Semantic (status)

| Token | Light | Dark | Usage |
|-------|-------|------|-------|
| `success` | | | Confirmation, positive trends |
| `warning` | | | Caution, soft alerts |
| `danger` | | | Destructive actions, errors |
| `info` | | | Neutral informational state |

Rule: semantic colors are tonally adjusted to match the brand. Raw `red-500`, `green-500`, `yellow-500` straight from Tailwind is slop.

### 5.7 Data viz palette

Charts and data need their own palette. Accent is usually wrong for data viz because it competes with CTAs.

**Sequential scale** (one variable, intensity): 5 to 7 stops, single hue, light to dark. [stops]

**Categorical scale** (multiple series): 5 to 8 distinct hues, perceptually even. [colors]

**Empty chart state:** show a message, not empty axes. See section 10.

**Rule:** never ship Recharts, Chart.js, or D3 default color sequences.

### 5.8 Gradient rules

Declare where gradients are allowed. Silence means "none."

- [ ] Hero background only
- [ ] Illustration / decorative surfaces
- [ ] Button backgrounds (which buttons)
- [ ] Text (rare; defended in Visual Idea)
- [ ] Banned everywhere

If used, declare stops: [Start] → [End]. Direction: [angle].

### 5.9 Dark mode (only if declared in Brief)

Skip if not in Brief.

**Derivation rule:**
- [ ] **Mirrored palette:** explicit dark tokens paired with light. Not algorithmic inversion.
- [ ] **Single-mode only:** no dark mode ships.

**Rules for mirrored approach:**
- Pure `#000` background is slop. Use near-black (e.g., `#0A0A0B`, `#111113`).
- Shadows reduced opacity, sometimes colored with accent glow.
- Contrast targets (5.10) apply to both modes.

### 5.10 Contrast targets

From the Brief (AA or AAA):

| Element | AA | AAA |
|---------|-----|------|
| Body text | 4.5:1 | 7:1 |
| Large text (18pt+, or 14pt+ bold) | 3:1 | 4.5:1 |
| UI controls, focus rings, borders | 3:1 | 3:1 |
| Disabled state | no requirement | no requirement |

### 5.11 Color count cap

Max distinct colors visible on one screen (excluding images, user content, data viz): [N]. Typical 5 to 8.

### 5.12 Color anti-patterns

- Default Tailwind `slate-900` / `zinc-900` on `slate-50` / `zinc-50`.
- Default shadcn primary (`indigo-600` or `violet-600`) unchanged.
- Accent only on main CTA, gray everywhere else.
- `from-purple-600 via-pink-500 to-orange-400` on hero, button, card, and logo.
- Algorithmic dark mode.
- Shadows on dark mode as if light mode.
- Semantic colors untonalized.
- Recharts default palette on every chart.

---

## 6. Spacing & Shape

### 6.1 Spacing scale

Base unit: [4px or 8px]. Every spacing value is a multiple.

| Value | Common use |
|-------|------------|
| 4 | Icon-to-label gap, tight inline |
| 8 | Within compact elements |
| 12 | Within cards, form groups |
| 16 | Between related elements |
| 24 | Between component groups |
| 32 | Section-internal spacing |
| 48 | Section-to-section |
| 64 | Major layout rhythm |
| 96+ | Page-level rhythm (landing) |

**Rule:** no arbitrary spacing values. If a design needs a value not on the scale, add and defend, or redesign.

### 6.2 Control height standard

Every interactive control in a horizontal row shares a height. Common tell: 40px button, 44px input, 36px select in one form.

- **Standard control height:** [X px, typical 36 to 44]
- Applies to: buttons, inputs, selects, date pickers, badges in interactive rows.
- Icons inside controls: optically centered.
- **Touch target minimum:** 44x44 (iOS), 48x48 (Android).

### 6.3 Radius scale

Philosophy: [One line. E.g., "Soft but not pillowy. 8px default." Or: "Sharp edges throughout."]

| Element | Radius |
|---------|--------|
| Buttons | |
| Inputs | |
| Cards | |
| Modals, sheets | |
| Avatars | |
| Dots, indicators | |
| Pills, badges | |
| Tooltips | |

**Rule:** different element types get different radii based on role. `rounded-2xl` on everything reflexively is slop.

### 6.4 Spacing and shape anti-patterns

- `p-4 gap-4 space-y-4` on everything.
- `py-24` between every section because "whitespace = premium."
- Inconsistent button padding (each generated independently).
- Mismatched control heights in one row.
- `rounded-full` on avatars and `rounded-2xl` on buttons with no rationale.
- `max-w-7xl mx-auto` on every page with nothing in the margins.

---

## 7. Motion

### 7.1 Principles

State 2 to 3 rules. What motion is FOR, what it is NOT.

Example:
- Motion clarifies state change. It does not decorate.
- Motion follows causality (the thing you clicked is the thing that moves).
- Motion respects `prefers-reduced-motion`.

### 7.2 Duration ladder

| Duration | Usage |
|----------|-------|
| 100ms | Hover, tooltip appearance, focus ring |
| 150ms | Button press, checkbox toggle, small state |
| 250ms | Dropdown open, tab switch, inline expansion |
| 400ms | Modal enter, page transition, major state |
| 600ms+ | Hero reveal on page load, celebratory moment |

Values outside this ladder don't ship.

### 7.3 Easing curves

- **Standard (in-out):** `cubic-bezier(0.4, 0, 0.2, 1)`
- **Ease-out:** `cubic-bezier(0, 0, 0.2, 1)` for entrances
- **Ease-in:** `cubic-bezier(0.4, 0, 1, 1)` for exits
- **Spring (optional):** declare library and defaults.

Linear easing only where motion IS mechanical (progress bars). Linear on UI transitions reads as lazy.

### 7.4 Motion taxonomy

Categorize every animation:

- **Entrance:** 150 to 400ms, ease-out, one per mount.
- **Exit:** 100 to 250ms, ease-in. Always shorter than entrance.
- **Hover:** 100 to 150ms, ease-out.
- **Press:** 50 to 100ms, snap.
- **Scroll-triggered:** declare threshold (~20% visible), once or repeat.
- **Ambient** (background loops): slow (3s+), subtle.

### 7.5 Reduced motion

Required.

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

Override only for accessibility-essential motion.

### 7.6 Motion anti-patterns

- `hover:scale-105 transition-all duration-300` on every clickable element.
- Framer Motion imported to fade in a div.
- Entrance animations on every element on page load.
- Toast for non-events.
- Missing reduced-motion handling.
- Scroll-triggered animations re-firing on every scroll-by.

---

## 8. Iconography

### 8.1 Library

One library. Mixing Lucide + Heroicons + react-icons is a slop tell.

- **Library:** [Lucide / Heroicons / Phosphor / Radix / custom / other]
- Defense: We chose [this] because [reason]. We rejected [alternative] because [reason].

### 8.2 Size, stroke, color

- **Default size:** [16px or 20px] inline with text. [24px] for featured contexts.
- **Compact size:** [14px] for dense tables.
- **Stroke width:** [1.5 or 2]. Matches body text weight visually.
- **Active / filled variant:** [declare if used]
- **Color:** inherits from text (`currentColor`).

### 8.3 When to use, when not to

Icons aid scannability. They don't decorate.

**Use icons for:** navigation (sidebar, tabs), actions in lists (edit, delete, share), empty state illustrations, status indicators (success, error), buttons where text alone is ambiguous (back, close, menu).

**Don't use icons for:** form labels (a field called "Name" doesn't need a person icon), every button ("Save" doesn't need a disk icon), every section heading.

**Rule:** if removing the icon doesn't hurt comprehension, remove it.

### 8.4 Optical alignment

Icons align to the text's optical center, not its bounding box. Most libraries render icons 1 to 2px too high. Nudge with `transform: translateY(1px)` or flexbox `items-center` plus manual adjustment.

### 8.5 Emoji as design elements

Emoji are not forbidden. Generic emoji decoration is.

**Emoji as systematic design (fine):**
- Product categories (Headout-style: 🎢 rides, 🏛️ museums, 🎭 shows)
- Geographic surfaces (country flags 🇮🇳 🇬🇧 🇺🇸)
- Weather, status, or reaction signals
- Social / emotion-driven feedback UIs
- Custom emoji pickers (Slack-style)

If emoji are used as design elements, declare the set and rules:
- [Emoji or category]: [meaning, context]

**Emoji as slop (banned):**
- 🚀 in hero headlines as "launch" or "speed" filler
- ✨ as "magic" or "AI" filler
- 🎯 as "goals" or "focus" filler
- 👋 as greeting on dashboards ("Welcome back!")
- ⭐ as generic "premium" signal
- Any emoji added to a heading or CTA with no systematic role

**The test:** if the emoji could be removed without losing meaning, it's decoration, not design.

### 8.6 Iconography anti-patterns

- Lucide next to every label whether it adds meaning or not.
- Mixed icon sets (Lucide + Heroicons + react-icons + emoji).
- Default stroke width when type needs heavier stroke.
- Icons at different sizes across the app.
- Icons in their own color by reflex.

---

## 9. Information Hierarchy

This is the thing the model collapses. "Everything is semibold" is the tell.

### 9.1 Emphasis tiers

Declare 3 or 4 tiers. Every element sits in one.

**Tier 1: Primary.** [The thing the user sees first on a screen. ~1 per viewport.]
- Signaled by: [size + weight + color]

**Tier 2: Secondary.** [Supporting, the "why."]
- Signaled by: [size + weight + color]

**Tier 3: Tertiary.** [Context, metadata, detail.]
- Signaled by: [size + weight + color]

**Tier 4: Micro (optional).** [Timestamps, legal, system.]
- Signaled by: [size + weight + color]

### 9.2 Signaling rules

Four levers. Combine, don't pile.

1. **Size** — bigger = more important (within reason)
2. **Weight** — heavier = more important (one weight per tier)
3. **Color** — accent > primary text > secondary > muted
4. **Position** — top-left and center get more attention

**Never use all four at once.** Pick 2 to 3 per tier. All four = visual shouting.

### 9.3 Hierarchy anti-patterns

- Everything at semibold. Nothing is emphasized.
- Three primary CTAs on one screen at equal weight.
- Long body paragraphs with no lead, no pull quote, no subhead.
- Stat cards at equal weight (no "the one number that matters").
- Sidebar nav with every item at the same weight and color.

---

## 10. States

Every screen has these. Designing only the happy path is slop.

### 10.1 Empty states

**Rule:** tell the user what to do next.

**Structure:**
1. Short headline: "No projects yet."
2. One-line context: "Projects organize your tasks and team."
3. Primary CTA: "Create your first project" button.
4. Secondary hint (optional): "Or import from Jira" link.

**Visual treatment:** [illustration / icon / plain type]. If illustration, matches Visual Idea.

**Anti-patterns:**
- "No items found 😊" with no action.
- Blank screen with sad illustration.
- Multiple CTAs at equal weight.
- Marketing-tone empty state copy on internal tools.

### 10.2 Loading states

**Duration thresholds:**
- <200ms: no indicator. Flash is worse than wait.
- 200ms–1s: subtle spinner or shimmer.
- 1s–3s: skeleton matching expected layout.
- 3s–10s: progress (percentage, steps, or staged messages).
- 10s+: long operation. Notify when done, don't make user wait.

**Skeleton rules:**
- Matches the layout that will appear. Don't skeleton a card grid and render a list.
- Subtle shimmer. Full-brightness shimmer is loud.

**Anti-patterns:**
- Infinite spinner, no timeout, no error.
- Full-page "Loading..." text.
- Spinners at full accent brightness.
- Loading indicator on every keystroke in autosave. Debounce.

### 10.3 Error states

**Rule:** what happened + what to do + recovery path. Three things, every time.

**Examples:**
- Bad: "Something went wrong."
- Good: "We couldn't reach your bank. Session hasn't expired. Retry or contact support."
- Bad: "Error 500."
- Good: "Server hit a snag. Work saved locally. Reload to try again."

**Form validation:**
- Don't validate on every keystroke. Validate on blur (field) and submit (form).
- Error text next to the offending field, not in a toast.
- Not "Invalid input." Yes "Email needs an @ and a domain."

**Anti-patterns:**
- "Something went wrong." Useless.
- Error codes without human explanation.
- Red-text errors with no recovery action.
- Toast for form errors.

### 10.4 Success states

**Rule:** match confirmation intensity to action stakes.

- **Trivial** (filter applied, toggle changed): silent.
- **Standard** (saved, created, sent): inline confirmation (brief "Saved" text, or button shows a check).
- **Significant** (submission complete, payment made): dedicated confirmation screen or modal with next step.
- **Celebratory** (first project, milestone): moment designed specifically.

**Anti-patterns:**
- Toast for "Copied," "Saved," "Loaded," "Refreshed."
- Full modal for tiny actions.
- "Success!" with no context of what succeeded.
- More than 1 toast visible at once unless queued.

### 10.5 All-states anti-patterns

- Happy path only.
- States designed as afterthoughts, different visual language from the rest.
- Emoji replacing actionable copy.
- Errors that blame the user.
- Celebrating trivial actions.

---

## 11. Data & Formatting

Numbers, dates, data rendering. Defaults produce slop, especially across locales.

### 11.1 Numbers

- **Abbreviation rules:**
  - <1,000: raw (847)
  - 1,000 to 999,999: with thousand separator per locale (1,234 or 1.234 or 1,23,456)
  - 1,000,000+: abbreviated (1.2M, 3.4B) in UI. Raw in exports and financial tables.
- **Decimal places:** contextual. Currency: 2. Percentages: 0 to 1. Ratios: 1 to 2.
- **Large numbers in tables:** tabular numerals, align on decimal.

### 11.2 Currency

- **Symbol position per locale.** USD: `$1,234.56`. INR: `₹1,23,456.78`. EUR (most): `1.234,56 €`.
- **Symbol vs ISO code:** symbol (`$`, `₹`, `€`) for UI. Code (`USD`, `INR`, `EUR`) when multi-currency ambiguity matters.
- **Multi-currency on one screen:** always show code alongside symbol.

### 11.3 Dates and time

- **Locale-aware format.** en-US: `Mar 15, 2026`. en-GB: `15 Mar 2026`. India: `15 Mar 2026`.
- **Never `MM/DD/YYYY` in mixed-locale products** (reads as `DD/MM` in most of the world).
- **Relative time:** "2 minutes ago," "in 3 days" for recent or upcoming. Absolute for anything older than ~7 days.
- **Time zones:** user's local zone by default. Source zone when collaboration spans zones.
- **Timestamps in lists:** relative + tooltip with absolute. Don't hide precise time.

### 11.4 Percentages

- **Whole percentages in UI** (72%, not 72.0%). Decimals only when precision matters.
- **Sign on deltas:** `+12%`, `-3.4%`. Never bare `12%` for a change.

### 11.5 Units

- **Space between value and unit** (`500 ms`, not `500ms`), except tight UI where declared.
- **Unit choice per locale.** Metric vs imperial. Don't mix.

### 11.6 Null states

- Don't render "null," "undefined," or blank. Use em-dash, "Not set," or "—".

### 11.7 Data formatting anti-patterns

- `1234567` no separators.
- Dollar sign on rupee amounts in India-facing products.
- Recharts default tooltip `1234567.89` with no formatting.
- Relative time ("3 months ago") when absolute is more useful (legal, financial).
- `MM/DD/YYYY` dates in India.
- "null" or "undefined" rendered in UI.

---

## 12. Accessibility

Target declared in Brief (AA or AAA).

### 12.1 Contrast

Declared in section 5.10. Verify every combination.

### 12.2 Focus states

Every interactive element has a visible focus state.

- **Outline:** 2 or 3px solid, 2px offset, accent or high-contrast neutral.
- **Never `outline: none` without a visible replacement.**

```css
:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 2px;
}
```

### 12.3 Touch targets

- iOS: 44x44 px minimum
- Android: 48x48 dp minimum
- Web mobile: match above.

Icon-only buttons are the usual failure point.

### 12.4 Keyboard navigation

- Tab order follows visual order. Test by tabbing.
- Escape closes modals, popovers, dropdowns.
- Arrow keys inside menus, tabs, option lists.
- Enter and Space activate buttons.
- Skip link at the top to jump past nav.

### 12.5 Reduced motion

Covered in section 7.5.

### 12.6 Screen reader labels

- Icon-only buttons need `aria-label`.
- Images need `alt`. Decorative: `alt=""`. Informative: describe the content.
- Form inputs need associated `<label>`. `placeholder` is not a label.
- Live regions (`aria-live="polite"` or `assertive`) for dynamic updates.
- Headings are semantic. `<h1>` through `<h6>`, not styled `<div>`.

### 12.7 Accessibility anti-patterns

- `outline: none` without replacement.
- Touch targets smaller than 44x44 on mobile.
- Placeholder as the only label.
- Color as the only signal (red-only error, green-only success). Add icon or text.
- Icon-only buttons without `aria-label`.
- Autoplay video or looping motion without pause.

---

## 13. Microcopy

Voice is personality. Microcopy is the specific patterns.

### 13.1 Voice and tone

- **Brand voice in 3 adjectives:** [e.g., direct, warm, technical]
- **Anti-adjectives:** [e.g., not corporate, not cute, not hype]
- **Tone spectrum per surface:**
  - Landing: [e.g., confident and inviting]
  - App: [e.g., clear and neutral, gets out of the way]
  - Error messages: [e.g., honest, no blame, action-oriented]
  - Onboarding: [e.g., encouraging, specific]

### 13.2 Button labels

- **Verb only.** "Save," "Continue," "Send," "Delete."
- **No adverbs.** Not "Save instantly" or "Continue seamlessly."
- **Specific over generic** when the action varies. "Create project" > "Create."
- **Sentence case** unless the Visual Idea declares otherwise.

### 13.3 Form labels

- **Above the field** (not placeholder, not floating unless supported product-wide).
- **Sentence case.**
- **Specific.** "Email address" > "Email."
- **Optional fields marked "(optional)"** if most are required. Mark the minority.

### 13.4 Empty state copy

See section 10.1. Action-oriented, not descriptive.

### 13.5 Error messages

See section 10.3. What happened + what to do + recovery.

### 13.6 Confirmations

- **Destructive confirmation says what happens specifically.** "Delete 3 projects? This can't be undone."
- **Button label matches the action.** "Delete" or "Remove," not "Yes" or "OK."
- **Cancel secondary, not primary.** Safe path is explicit but not emphasized.

### 13.7 Tone rules

- **The signal is tone-match, not tone-ban.** Hype belongs on landing. Utility belongs in app. Misalignment is slop, not the language itself.
- **No self-congratulation.** Product doesn't call itself "amazing" or "powerful."
- **No emoji-as-tone-softener** ("We couldn't find that 😊"). Copy works or it doesn't.
- **Match formality to surface.** Landing can be casual. Compliance UI can't.

### 13.8 Microcopy anti-patterns

- "Welcome back! 👋" on every dashboard.
- "Let's get started ✨" on onboarding.
- Adverb buttons: "Save instantly," "Continue seamlessly."
- "Something went wrong."
- "No results found." (instead of "Try broadening the search or removing a filter.")
- Lorem ipsum shipped.
- Placeholder as label.
- Mixed formality across the product.

---

## 14. Components

Each component: purpose, variants, states, internal rules.

### 14.1 Button

**Variants:**
- **Primary:** one per screen max (2 in rare cases). Accent background, inverse text.
- **Secondary:** neutral background, primary text. Supporting actions.
- **Tertiary / Ghost:** no background, inherited text color. Low-priority.
- **Destructive:** danger color, confirms destructive intent.

**States (every variant):**
- Rest, hover, active (press), focus, disabled, loading.
- Loading: inline spinner + dimmed label. Button keeps width (no layout shift).

**Internal rules:**
- Height: standard control height (6.2).
- Horizontal padding: 1.5 to 2x height.
- Radius: from 6.3.
- Icon + label: icon left, gap per 6.1.
- Label: sentence case, verb-only (13.2).

### 14.2 Input

**Variants:** text, number, email, password, search, textarea, select, date, file upload.

**States:** rest, hover, focus, error, disabled, readonly, filled.

- Focus: border + subtle ring (2px accent-dim or offset per 12.2).
- Error: border = danger, message below field.

**Internal rules:**
- Height: matches button standard.
- Label above (13.3).
- Helper text below, secondary color.
- Character count (constrained fields) bottom-right of field.

### 14.3 Card

**Variants:**
- **Content card:** static information. No hover state.
- **Interactive card:** clickable or expandable. Hover from Motion.
- **Stat card:** used sparingly. See 14.8.

**Rules:**
- Background: `surface`.
- Border: `border`.
- Padding: from 6.1.
- Radius: from 6.3.
- **No card-in-card.** Nested cards are slop. Group content inside a card with dividers or spacing.

### 14.4 Table

- **Row density:** compact (40px) / standard (48px) / comfortable (56px). One per context.
- **Zebra striping:** off by default. On only when 10+ rows and scanning matters.
- **Sort indicators:** arrows on sortable columns only.
- **Numeric columns:** right-aligned, tabular numerals.
- **Empty table:** state from 10.1 (not empty rows).
- **Sticky header** for tables taller than one viewport.

### 14.5 Modal, Sheet, Popover

- **Modal:** center, scrim behind, blocks page. Critical decisions.
- **Sheet:** slides from edge (right or bottom). Secondary flows without blocking. Escape closes.
- **Popover:** anchored to trigger. Brief info or small actions. Outside click dismisses.
- **Z-index order:** page < dropdown < popover < sheet < modal < tooltip < toast.

### 14.6 Toast / Notification

- **Position:** [declare. Typically top-right desktop, top mobile.]
- **Duration:** 4 to 6s informational. Permanent until dismissed for errors or action-required.
- **Max concurrent:** 3. Queue rest.
- **Types:** info, success, warning, error. Differentiated by semantic color or icon.
- **Never toast trivial actions.** Autosave "Saved" is noise.

### 14.7 Navigation

- **Primary nav location:** [declare per surface. Top bar for landing, left sidebar for apps, bottom nav for mobile.]
- **Active state:** accent color or accent-dim background. Distinct from hover.
- **Mobile collapse:** hamburger or bottom tabs. Declare.

### 14.8 Stat card (specific rules, slop risk)

Stat cards are fine as a component. The slop is placeholder data and over-use.

- **Only when actionable.** "Total users: 1,234" is rarely actionable. "Orders pending approval: 12" is.
- **Real data, not placeholders.** Wire up before shipping. `1,234 +12%` hardcoded is the loudest dashboard slop tell.
- **Delta with context.** "+12%" compared to what, over what period? Label it.
- **Max 3 on a screen.** Four is dashboard theater.

### 14.9 Component anti-patterns

- Different button heights across the product.
- Card-in-card-in-card.
- Stat cards with placeholder data.
- Modals for trivial actions.
- Toasts for trivial success.
- Zebra striping on 3-row tables.
- Icon-only buttons without `aria-label`.
- Dropdown opening wider than trigger for no reason.

---

## 15. Surface-Specific Patterns

Fill only for surfaces ticked in section 2.

### 15.1 Landing

**Sections (typical):**
1. Hero — value prop + primary CTA
2. Social proof (logos, testimonials)
3. Product overview (1 to 3 key features)
4. How it works
5. Pricing (if relevant)
6. FAQ
7. Footer

**Rules:**
- **Max content width:** [e.g., 1200px]
- **Section rhythm:** vary padding. Not every section is `py-24`.
- **Hero constraint:** 1 primary CTA, 1 secondary max. Not a field of buttons.
- **Asymmetry allowed.** Landing is where editorial layout earns its place. Not every section centered.
- **Social proof:** real logos, real testimonials.

**Anti-patterns:**
- Hero → 3-column features → CTA → Footer as every landing. No variation.
- Parallax on everything.
- "Join 10,000+ users" with no proof.
- 6 identical feature cards.
- "Jane D., CEO" testimonials (first name + last initial is fake).

### 15.2 App

**Layout:**
- **Shell:** [top bar / left sidebar / bottom tabs — declare]
- **Content area:** [max-width or fluid]
- **Density:** [compact / standard / comfortable]

**Rules:**
- **Speed over polish.** Returning daily users feel friction differently than first-time visitors.
- **Keyboard shortcuts:** declare the set. Discoverable via `?` or menu.
- **Settings location:** predictable (account menu, top right, or bottom of sidebar).
- **Tone match:** app copy is utility-grade. Misplaced marketing language on a settings page is slop.

**Anti-patterns:**
- Marketing copy on settings pages.
- Dashboard-ification of simple forms.
- Full-page loading for partial data updates.
- Sidebars with 20+ items at equal hierarchy.

### 15.3 Conversational

**Message structure:** declare per platform (Telegram, WhatsApp, in-app).
- User messages: right-aligned, accent background (or platform convention).
- Agent messages: left-aligned, surface background.
- System messages: centered, secondary text, compact.

**Streaming state:** visible cursor or typing indicator during generation. Distinct from loading.

**Tool call display:** visible when agent uses tools. Collapsed by default ("Searching...") with expand-to-detail. Never hidden.

**Citation / source:** inline when agent retrieves info (link, badge, footnote).

**Error in conversation:** appears as a message, not a toast. User stays in context.

**Retry / regenerate:** available on every agent message.

**Message actions:** copy, edit (user messages), regenerate (agent messages), share.

**Context window limit:** when exceeded, user is told and offered "start new" or "summarize." Silent truncation is bad UX.

**Anti-patterns:**
- Agent messages with no streaming indicator (looks broken).
- Tool calls hidden entirely.
- Generic "I'm thinking..." with no specifics.
- No way to retry a failed message.
- Emoji-heavy agent voice contradicting Microcopy.
- Agent messages styled like notifications (breaks conversation metaphor).

### 15.4 Transactional

**Email:**
- Single column, max 600px.
- Plain-text version always alongside HTML.
- Subject line: specific, action-oriented. Not "Update from [Company]."
- Preheader: visible preview, second subject line.
- CTA buttons: 1 primary per email. Bulletproof button code (table-based).
- Images: hosted, with `alt`. Don't rely on images; clients block them.
- Dark mode: test. Many clients force it.

**Receipt / invoice:**
- Transaction details prominent (amount, date, merchant, line items).
- Reference number scannable (monospace, copyable).
- Legal text bottom, smaller but readable.
- Downloadable as PDF.

**PDF export:**
- Designed for A4 and US Letter.
- Fonts embedded (not web-loaded).
- Page numbers, footer with source attribution.

**Anti-patterns:**
- Hero-image-only emails (no text fallback).
- "Click here to view in browser" as first line.
- Subject lines with fake "Re:" or "Fwd:".
- Receipts without prominent reference number.
- PDFs relying on web fonts.

### 15.5 Mobile

**Rules:**
- **Touch targets:** 44x44 iOS, 48x48 Android. No exceptions.
- **Primary nav:** bottom tabs (max 5).
- **Gestures:** declare which are supported (swipe to delete, pull to refresh, long press).
- **Safe areas:** respect notch, home indicator, status bar.
- **Keyboard handling:** inputs scroll into view on focus.
- **Offline behavior:** declare (banner, queue, or block).

**Anti-patterns:**
- Desktop UI squished. Tables overflow, cards break.
- Hover-dependent interactions.
- Tiny touch targets on icon-only buttons.
- Modals that can't be gesture-dismissed.
- Date pickers that only go back 10 years (birthday broken).

### 15.6 CLI

**Rules:**
- **Color:** respect `NO_COLOR` env var. Monochrome fallback.
- **Output shape:** standard per command (status, details, next steps).
- **Progress:** spinner for unknown duration, bar for known.
- **Exit codes:** 0 = success, non-zero = error. Declare the table.
- **Help:** `--help` on every command, including subcommands.
- **Interactive prompts:** default in brackets (`[Y/n]`). Ctrl-C cancels cleanly.

**Anti-patterns:**
- Output without newlines, hard to scan.
- Errors without codes.
- Color that breaks when piped.
- Progress indicators that don't update.
- Verbose logging by default.

### 15.7 Docs

**Rules:**
- **Structure:** Get Started → Concepts → API Reference → Examples → Troubleshooting.
- **Code blocks:** language-tagged, copy button, line numbers where referenced.
- **Search:** prominent, keyboard-accessible (`/` or `⌘K`).
- **Navigation:** sidebar with current page highlighted; TOC for long pages.
- **Versioning:** selector visible if multiple versions supported.
- **Examples:** runnable where possible. Every endpoint gets a cURL + at least one SDK example.

**Anti-patterns:**
- Prose without code examples.
- Code examples without expected output.
- "See our GitHub" instead of inline examples.
- No search.
- Marketing language. Docs are reference.

---

## 16. Global Anti-Patterns

Apply across every section. Module-specific anti-patterns live in each section above.

- **Defaults are the enemy.** If this guide doesn't specify a value, the answer is "ask," not "use Tailwind default."
- **No `rounded-2xl shadow-lg bg-gradient-to-br` by reflex.** Each is a decision.
- **No default shadcn theme.** Customize before shipping.
- **No dashboard-ification.** Forms are forms. Don't wrap them in stat cards.
- **No dark mode unless declared** in the Brief.
- **No toast spam.** Trivial actions don't notify.
- **No hover-only interactions on mobile.**
- **No placeholder data in production.** Wire it up or cut it.
- **No "Something went wrong."** Every error says what happened + what to do + how to recover.
- **No Lorem Ipsum in production.** Loudest tell of all.

---

## 17. What This Brand is NOT

Explicit anti-directions for this product. Minimum 5. Guardrails against drift.

- Not [anti-direction 1].
- Not [anti-direction 2].
- Not [anti-direction 3].
- Not [anti-direction 4].
- Not [anti-direction 5].

---

## 18. Appendix: Token Scaffolds

When filling this guide, generate the token file(s) for your stack. Canonical format: CSS custom properties. TS const is derived.

### 18.1 CSS custom properties (canonical)

```css
:root {
  /* Neutrals & surfaces */
  --bg: /* */;
  --surface: /* */;
  --surface-raised: /* */;
  --surface-overlay: /* */;
  --surface-tooltip: /* */;

  /* Text */
  --text: /* */;
  --text-secondary: /* */;
  --text-muted: /* */;
  --text-inverse: /* */;

  /* Borders */
  --border: /* */;
  --border-strong: /* */;
  --border-accent: /* */;

  /* Accent */
  --accent: /* */;
  --accent-hover: /* */;
  --accent-dim: /* */;

  /* Semantic */
  --success: /* */;
  --warning: /* */;
  --danger: /* */;
  --info: /* */;

  /* Typography */
  --font-display: /* stack */;
  --font-body: /* stack */;
  --font-mono: /* stack */;

  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
  --space-12: 48px;
  --space-16: 64px;

  /* Radius */
  --radius-sm: /* */;
  --radius-md: /* */;
  --radius-lg: /* */;
  --radius-full: 9999px;

  /* Motion */
  --duration-instant: 100ms;
  --duration-fast: 150ms;
  --duration-standard: 250ms;
  --duration-slow: 400ms;
  --ease-standard: cubic-bezier(0.4, 0, 0.2, 1);
  --ease-out: cubic-bezier(0, 0, 0.2, 1);
  --ease-in: cubic-bezier(0.4, 0, 1, 1);

  /* Control heights */
  --control-height: /* */;
}

[data-theme="dark"] {
  /* Mirror every token with dark values — only if dark mode declared */
}
```

### 18.2 TypeScript const (derived)

```ts
export const tokens = {
  color: {
    bg: 'var(--bg)',
    surface: 'var(--surface)',
    // ... all tokens referenced as CSS vars
  },
  font: { /* */ },
  space: { /* */ },
  radius: { /* */ },
  duration: { /* */ },
  ease: { /* */ },
} as const
```
