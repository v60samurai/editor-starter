# PRD: [Product Name]

**Version**: 1.0
**Status**: Draft / Under Review / Approved
**Last Updated**: YYYY-MM-DD
**PM**: [Name] | **Eng Lead**: [Name] | **Design Lead**: [Name]

---

## A Note to the Team Building This

This document is written for you. Every section exists to give you context so you can make good decisions without coming back to ask. I have explained the "why" behind every choice I made. If something is not clear, that is my failure, not yours. Please ask and I will fix it.

I did the research so you do not have to guess what users need. I made the hard prioritisation calls so you do not have to. I listed the edge cases so you do not discover them mid-build. This is the information I wish I had given you on day one of every previous project.

Build with confidence. I have your back.

---

## Confidence Tag Legend

Use these tags anywhere in this document to show how certain a claim is.

| Tag | Meaning |
|-----|---------|
| 🟢 | Confirmed by primary research (direct user interviews or observation) |
| 🟡 | Confirmed by secondary research (market data, reports, reviews) |
| 🔵 | A direction we believe in but have not yet proven. Treat it as a hypothesis. |
| 🔴 | We tested this and it turned out to be wrong. Do not rely on it. |

---

# PART 1: DISCOVERY

This part is the foundation. It explains the problem we are solving and the people we are solving it for. Read this before you read the solution section. The decisions in Part 2 only make sense if you understand Part 1.

---

## 0. Document Overview

### 0.1 Purpose and Scope

This document analyses the problem space surrounding [domain]. It covers how [user workflow] operates in [context], where that workflow breaks down, why existing [tools/solutions] fail this segment, and how primary and secondary research validates a narrowed problem statement and solution direction.

**What this document covers**: [List the specific decisions this PRD enables.]

**What this document does not cover**: [List what is explicitly out of scope.]

### 0.2 Research Scope

**Target Segment**: [One paragraph. Who these people are, the structural condition that defines them - not just company size or role, but the behaviour or constraint that makes them a distinct segment.]

**Research Inputs**:

| Input Type | Volume | Period | Method |
|-----------|--------|--------|--------|
| Primary interviews | n = [X] | [date range] | [1:1 conversations / contextual observation / diary study] |
| Secondary sources | [X] sources, [X] findings | [date range] | [Market reports, community forums, product reviews] |
| Competitive audit | [X] products across [X] tiers | [date range] | [Hands-on testing, teardown analysis, review mining] |

### 0.3 Confidence Tags

| Level | Description |
|-------|-------------|
| 🟢 High Confidence | Multiple interviews, consistent cross-segment patterns, strong secondary support. |
| 🟡 Moderate Confidence | Limited primary signals + secondary findings. Valid but requires further validation. |
| 🔵 Emerging Signals | Early observations from few interviews or edge cases. Not yet a confirmed pattern. |

---

## 1. Problem Tension

### 1.1 Real User Scenario

Write a scene. One person, one context, one moment when the problem is at its worst. Do not write abstractions. Write it the way you would describe a scene in a story. Source this from the real interviews you conducted.

[Paragraph 1: Who the person is and what their daily context looks like. Be specific about numbers - how many [things] they manage simultaneously, across which channels, with what tools.]

[Paragraph 2: A typical [workflow/journey path]: [Step A] -> [Step B] -> [Step C] -> [Step D] -> multiple [interactions] before [outcome].]

[Paragraph 3: Because [structural reason], there is no single system of record capturing [the critical context]. The user relies on [informal tools]. This works temporarily but breaks as [volume/complexity] grows.]

### 1.2 Observable Breakdown

When [volume/complexity] increases, users attempt [solution adoption], but a predictable failure cycle follows:

- [Initial setup and enthusiasm]
- [Manual effort required after every interaction]
- [Effort fatigue within days]
- [Partial, inconsistent usage]
- [Abandonment by week [X]]

[Describe why the failure is structural, not motivational. The user intended to use the tool. The tool demands effort at the exact moment the user has none to give.]

### 1.3 Evidence of the Problem

| Evidence | Magnitude | Source | Confidence |
|----------|-----------|--------|-----------|
| [How often the core failure happens] | [X percent] | [Source, Year] | 🟢 |
| [What it costs the user] | [Amount or time] | [Source, Year] | 🟡 |
| [How many attempts users make before giving up] | [X percent resort to Y] | [Primary + secondary] | 🟢 |
| [How quickly existing solutions are abandoned] | [X percent within Y weeks] | [Source, Year] | 🟡 |

Additional inefficiencies: [List 2-3 specific observed inefficiencies from research. Be concrete - "founders scroll through WhatsApp before every call to recall context" not "context is lost."]

### 1.4 Why This Problem Matters Now

[Paragraph 1: What has changed in the environment - market growth, channel shifts, technology advances - that makes this problem both urgent and newly solvable.]

[Paragraph 2: What is now technically possible that was not possible before.]

> **Key Insights from this Section**
>
> Important signals:
> - [Signal 1 with the number that proves it]
> - [Signal 2]
> - [Signal 3]
> - [Signal 4]
>
> This is powerful because it shows [behavioural inevitability / structural pattern].
> The failure is not: [What people assume]. It is [what it actually is].

> **Product Insight**
>
> The core issue is [name the root mechanism].
> [Tool/system] requires users to [action] right [when/where], which is precisely when [constraint is highest]. As a result, [the critical step] gets skipped.
> This reveals that the failure is not [surface cause] but [structural cause].

---

## 2. Broader Problem Statement

### 2.1 Industry-Level Problem

[Category tools] were designed for [structured context]: [list the assumptions - dedicated teams, defined processes, consistent behaviour, centralised channels]. [Target users] operate oppositely: [list the reality - informal, relationship-driven, dynamic, conversational]. This mismatch makes existing tools feel [too complex / too enterprise-focused / too maintenance-heavy].

[One editorial sentence that captures the architectural mismatch. For example: "The CRM industry built a hammer optimised for enterprise nails. Early-stage founders are a different fastener entirely - and no one has built the right tool yet."]

### 2.2 User-Level Problem

[Target users] spend their time [list their actual high-value activities]. [Tool maintenance] competes directly with these activities. When forced to choose, users consistently prioritise [high-value activity] over [documentation/maintenance].

[High-value activity time] >> [Documentation time]

### 2.3 Systemic Gap in Existing Solutions

All existing solutions depend on [the structural requirement that fails - e.g., manual logging]. Since [core activity] occurs outside [the tool] and [the requirement] demands additional effort, the system structurally fails: [describe the cascade - input data missing -> triggers never fire -> visibility becomes unreliable].

[If there is a geography-specific or context-specific amplifier, describe it here.]

> **Product Insight**
>
> This reveals a category-level mismatch.
> Existing [category] systems were designed for [context where the category works], but the target users here are [people for whom this activity is one of many responsibilities].
> Therefore, the problem is not about improving [category] features. It is about rethinking the fundamental [interaction model / input model / design assumption] of [category] tools.

---

## 3. Context

### 3.1 The Environment

[Target companies: stage, size, team structure, revenue range. The structural conditions that define the environment.]

[One editorial sentence. For example: "At this stage, the founder IS the sales process. There is no system to improve - there is only a person to support."]

### 3.2 The User's Reality

[The user handles the full lifecycle: list all responsibilities. These activities occur [informally/conversationally] and rarely follow a predefined structure.]

[One editorial sentence about cognitive load. For example: "The founder carries the full revenue function in their head. Every hiring decision, product call, or investor meeting competes directly for the same cognitive budget as sales."]

### 3.3 The Multi-Channel Landscape

| Channel | Role |
|---------|------|
| [Channel 1] | [How it is used] |
| [Channel 2] | [How it is used] |
| [Channel 3] | [How it is used] |
| [Channel 4] | [How it is used] |

A single [deal/workflow] typically moves: [Channel A intro] -> [Channel B conversation] -> [Channel C proposal] -> [Channel D negotiation] -> Close.

This fragmentation prevents any single tool from capturing the full [deal/workflow] narrative.

> **Product Insight**
>
> Because [context] is spread across multiple [channels/platforms], no single tool captures the full narrative. As a result:
> - [Consequence 1 - e.g., pipelines represent only a partial view]
> - [Consequence 2 - e.g., users must manually reconstruct context before every important interaction]
>
> This creates high cognitive overhead and increases the risk of [the core failure mode].

---

## 4. Target User Definition

### 4.1 Stage Definition

[Stage range], [size range], [revenue/maturity range]. [Users] are still discovering their [process]. A [tool] that imposes structure before that process is understood will always be abandoned.

### 4.2 User Responsibilities

The user acts as the entire [function]: [list all roles they play]. Their workflow is extremely time-constrained.

### 4.3 Behavioural Characteristics

| Behaviour | Description |
|-----------|-------------|
| [Behaviour 1, e.g., High context switching] | [Specific description of what this looks like] |
| [Behaviour 2, e.g., Mobile-first interaction] | [Description] |
| [Behaviour 3, e.g., Low tolerance for admin] | [Description] |
| [Behaviour 4, e.g., Relationship-driven] | [Description] |

[One editorial sentence. For example: "The four behavioural traits of this user are not fixable with better onboarding. They define a fundamentally different product requirement."]

> **Product Insight**
>
> These traits translate directly into product design constraints:
> - [Constraint 1]
> - [Constraint 2]
> - [Constraint 3]
>
> This section effectively defines the behavioural environment the product must operate within.

---

## 5. Problem Space Context

### 5.1 Current User Behaviour

#### 5.1.1 Sources / Inputs

| Source | Role |
|--------|------|
| [Source 1] | [How it fits in the workflow] |
| [Source 2] | [Role] |
| [Source 3] | [Role] |
| [Source 4] | [Role] |

#### 5.1.2 Communication Channels and Lifecycle

[Describe how work flows across channels. Multiple [interactions] are required before [outcome], making untracked [activity] a direct cause of [failure].]

[One editorial sentence about the gap. For example: "All high-converting lead sources immediately move to WhatsApp. The CRM never sees the lead at the highest-trust moment of the relationship."]

### 5.2 Current Management Practices

#### 5.2.1 Tracking Methods Used

| Method | Limitation |
|--------|-----------|
| [Method 1, e.g., Memory] | [Why it fails] |
| [Method 2, e.g., Starred messages] | [Why it fails] |
| [Method 3, e.g., Spreadsheets] | [Why it fails] |
| [Method 4, e.g., Dedicated tools] | [Why it fails] |

#### 5.2.2 Follow-Up and Tracking

[Describe the current state: reactive, based on personal reminders, visibility reconstructed manually.]

[One editorial sentence about zero-friction competition. For example: "Founders don't choose informal tools because they're lazy. They choose them because those tools impose zero cost at the moment of use. Any replacement must match that zero-friction bar at the point of capture."]

> **Product Insight**
>
> The real competition for any [category] product in this segment is not other [category] tools. The true competitor is [the simplest tool they actually use]. Any successful product must provide equal or lower friction at the point of [capture/use].

---

## 6. Business Impact of the Problem

[One paragraph framing: In [user context], [activities] occur across multiple channels. Because these are rarely captured in a structured system, [follow-ups/handoffs/tracking] slip through the cracks. While these failures appear small, they compound over time and result in significant [revenue leakage / productivity loss / opportunity cost].]

### 6.1 Illustrative Scenario

Walk through a concrete calculation with real numbers. Show your math.

| Stage | Estimated Numbers | Explanation |
|-------|------------------|-------------|
| [Starting volume] | ~[X] / [period] | [Where these come from] |
| [Failure point] | ~[X] | [The percentage and why] |
| [Potential outcome from failures] | [X]-[Y] | [Conversion rate basis] |
| [Average value] | [Amount] | [Typical for this segment] |
| [Estimated leakage] | [Amount range] | [Direct calculation] |

### 6.2 Operational Impact

| Problem | Operational Effect | Estimated Impact |
|---------|-------------------|-----------------|
| [Problem 1] | [What happens operationally] | [Quantified impact] |
| [Problem 2] | [Effect] | [Impact] |
| [Problem 3] | [Effect] | [Impact] |
| [Problem 4] | [Effect - time cost] | [Hours/cost estimate] |
| [Problem 5] | [Effect - handover/transition] | [Impact] |

### 6.3 Combined Impact Estimate

When these effects compound:
- [Failure 1] -> [Amount range per period]
- [Failure 2] -> [Amount range per period]
- [Failure 3] -> [Amount range per period]

Estimated total: **[Amount range per period]**
Annualised: **[Amount range]**

> **Key Insight**
>
> The breakdown in [tracking/management] is not merely an operational inefficiency. In [user context], [fragmented workflows] and [missed actions] create a systematic [leakage/loss] mechanism, where small process gaps accumulate into substantial [financial/operational] loss over time.

---

## 7. Existing Ecosystem

### 7.1 The Real Existing Solutions

Before evaluating [category tools], the baseline tools users actually use:

- **[Baseline tool 1]**: [How many users rely on it]. [Zero setup, zero maintenance, zero proactive value.]
- **[Baseline tool 2]**: [Set up with intent, accurate for X weeks, abandoned as volume grows. Why it fails.]
- **[Baseline tool 3]**: [Why some users build rather than buy.]

These are the baselines. [Category] tools are the aspirational alternatives that consistently fail.

[One editorial sentence. For example: "The most popular CRM among early founders is WhatsApp starred messages. That is the benchmark the product must beat - not HubSpot."]

### 7.2 Tool Landscape

Organise by tiers that represent structurally different approaches, not just price points.

| Tier | Products | Design Assumption | User Fit | Key Limitation |
|------|----------|-------------------|----------|----------------|
| Tier 1: [Category] | [Products] | [Who they were built for] | [Fit score X/10] | [Core limitation for target user] |
| Tier 2: [Category] | [Products] | [Design assumption] | [Fit] | [Limitation] |
| Tier 3: [Category] | [Products] | [Design assumption] | [Fit] | [Limitation] |
| Tier 4: [Category] | [Products] | [Design assumption] | [Fit] | [Limitation] |

[One editorial sentence about the tiers. For example: "Every tier assumes the user has more time, money, or familiarity than the target segment actually has. The tiers differ in complexity and price, not in their fundamental design assumption."]

### 7.3 The Actual Usage Pattern

Regardless of tier, the adoption pattern is identical:

- **Week 1**: [Initial setup. Feels productive.]
- **Weeks 2-3**: [Where logging/usage drops. What continues but incompletely.]
- **Week 4+**: [State of the tool. Percentage of data missing. Reversion to informal tools.]

[One editorial sentence about why this happens. Not a discipline problem - a timing problem.]

### 7.4 Architectural Ceilings

These are the 2-4 constraints that prevent any current tool from solving this problem. They are not product problems waiting to be fixed with better UX. They are structural constraints that define the design space.

**Ceiling 1: [Name]**: [Explain the constraint - technical, regulatory, or economic - and why it cannot be overcome from within current product architecture.]

**Ceiling 2: [Name]**: [Explain. Focus on timing, workflow, or economic barriers.]

**Ceiling 3: [Name]**: [Explain. Focus on pricing or adoption barriers.]

[One editorial sentence. For example: "These three ceilings are not product problems waiting to be fixed with better UX. They are structural constraints that define the design space. Any solution must work within them, not assume they can be removed."]

---

## 8. Primary Research

### 8.1 Methodology

| Parameter | Detail |
|-----------|--------|
| Sample | [X] interviews + [any aggregated sources]. [Breakdown by subsegment.] |
| Format | [Semi-structured / structured], [remote/in-person], [duration] |
| Selection | [Selection criteria] |
| Key Biases | [Honest assessment of sample bias. What the sample over-represents and under-represents.] |

[One editorial sentence about the research gap. For example: "The research captures failure clearly but has a blind spot: zero satisfied users in the sample. Validating what makes a tool succeed for this segment requires a separate research phase."]

### 8.2 The Say-Do Gap

This is the most valuable section. The gap between what users say and what they actually do is where the real insight lives.

| What Users Say | Reality |
|---------------|---------|
| "[Stated behaviour 1]" | [Observed reality] |
| "[Stated behaviour 2]" | [Observed reality] |
| "[Stated behaviour 3]" | [Observed reality] |
| "[Stated behaviour 4]" | [Observed reality] |

[One sentence insight. For example: "Every founder claims to track leads. Actual tracking happens in memory and WhatsApp."]

### 8.3 A Week in the Life (Composite)

Build a synthesised week from what you heard across all interviews. Show the problem as lived experience, not as a list of pain points.

- **Monday**: [A specific scene showing the problem being planted.]
- **Tuesday**: [A moment where good intent meets no system.]
- **Wednesday**: [The consequence of earlier gaps.]
- **Thursday**: [The compounding failure - something slips.]
- **Friday**: [What the user has to do to dig out. The wasted effort.]

[One editorial sentence. For example: "Deals don't die in a dramatic moment. They die in the 48-hour gap between a good conversation and the follow-up that never happened."]

### 8.4 Friction Points (Ranked by Severity)

| Friction Point | Evidence (X/Y) | Severity | Best Quote |
|----------------|----------------|----------|------------|
| [Friction 1] | [X/Y - HIGH] | HIGH | "[Quote]" - [P-number] |
| [Friction 2] | [X/Y - HIGH] | HIGH | "[Quote]" - [P-number] |
| [Friction 3] | [X/Y - HIGH] | HIGH | "[Quote]" - [P-number] |
| [Friction 4] | [X/Y - HIGH] | MEDIUM | "[Quote]" - [P-number] |
| [Friction 5] | [X/Y - MEDIUM] | HIGH | "[Quote]" - [P-number] |

[One insight sentence. For example: "The highest-severity friction is not a feature gap - it is a timing gap."]

### 8.5 Recurring Behavioural Patterns

These patterns appeared in multiple interviews, independent of any specific feature request. They are the behaviours the product must work with, not against.

**Pattern 1: [Name] (HIGH)**: [Description and what it reveals about constraints or psychology. Product implication.]

**Pattern 2: [Name] (HIGH)**: [Description and implication.]

**Pattern 3: [Name] (HIGH)**: [Description and implication.]

**Pattern 4: [Name] (HIGH)**: [Description and implication.]

**Pattern 5: [Name] (MEDIUM)**: [Description and implication.]

[One editorial sentence identifying the core design constraint from these patterns.]

### 8.6 Key Verbatim Pain Signals

- "[Quote 1]" - [P-number]
- "[Quote 2]" - [P-number]
- "[Quote 3]" - [P-number]
- "[Quote 4]" - [P-number]
- "[Quote 5]" - [P-number]
- "[Quote 6]" - [P-number]
- "[Quote 7]" - [P-number]

[One editorial sentence about what the quotes reveal collectively. For example: "Every quote is about missing context or lost momentum - not missing features. The product gap is not functional, it is temporal."]

---

## 9. Secondary Research

Synthesised from [X]+ sources and [X] findings across market reports, community forums, and review platforms.

### 9.1 Market Sizing

| Metric | Finding |
|--------|---------|
| [Market] ([year]) | [Amount] ([Source]) |
| CAGR | [X%] - [comparison to global/adjacent] |
| Projected [year] | [Amount] |
| Intent vs adoption | [X% intend; only Y% have structured usage] |
| [Relevant sub-segment] | [CAGR/size with no dominant player] |

[One editorial sentence about the gap. For example: "The gap between 94% intent and 50% adoption confirms the problem is product-fit, not awareness."]

### 9.2 User Time Allocation

[Source consensus on how users spend their time.]

| Activity | Time Allocation |
|----------|----------------|
| [Primary activity] | [X%] |
| [Secondary activity] | [X%] |
| [Tertiary activity] | [X%] |
| [Other activities] | [X%] |
| [Tool/system maintenance] | [X%] |

[One editorial sentence about the ceiling. For example: "CRM gets 5% of founder time by default - and that ceiling doesn't move with better UX. The only lever is reducing how much time the tool requires, not improving how the time is spent."]

### 9.3 Community Pain Signals

Universal signals across [platforms]:

- "[Pain signal 1]"
- "[Pain signal 2]"
- "[Pain signal 3]"
- "[Pain signal 4]"
- "[Pain signal 5]"
- "[Pain signal 6]"

[Context-specific signals, if applicable]: [Describe geographic, demographic, or segment-specific patterns.]

[One editorial sentence about the convergence.]

### 9.4 Product Review Patterns

| Review Pattern | Frequency |
|----------------|-----------|
| [Pattern 1] | Very High - across [X] tools |
| [Pattern 2] | Very High - across [X] tools |
| [Pattern 3] | High - [specific tools] |
| [Pattern 4] | High - [specific tools] |
| [Pattern 5] | Medium - across [X] tools |

[One editorial sentence about what reviews reveal. For example: "Tools that track email-only conversations fire follow-up reminders for contacts who replied on WhatsApp two days prior. The tool creates confidence where none should exist."]

### 9.5 Industry Insights

These are not individual data points. They are conclusions that multiple data points, taken together, lead to.

**1. [Insight Name]**: [What the data adds up to. What it means for product design.]

**2. [Insight Name]**: [What the data adds up to. For example, which feature frequency drives retention.]

**3. [Insight Name]**: [The chain or cascade. How failures compound in sequence and what solving the first one enables.]

---

## 10. Competitor Analysis

### 10.1 Feature Coverage Summary

| Feature | Coverage (X/Y tools) | Implication |
|---------|---------------------|-------------|
| [Feature 1] | [X/Y] have it | [Is this a differentiator or table stakes?] |
| [Feature 2] | [X/Y] support it | [The gap and why it matters] |
| [Feature 3] | [X/Y] have one | [Quality assessment] |
| [Feature 4] | [X/Y] have partial | [Why partial doesn't work] |
| [Feature 5] | [X/Y] have genuine tier | [Pricing implications] |
| [Feature 6] | [Partial in X] | [What's missing and why] |

[One editorial sentence about what is table stakes vs. what is the moat.]

### 10.2 Key Product Gaps

| Gap | Tier | Severity | Description |
|-----|------|----------|-------------|
| [Gap 1: Target user design] | [Tier] | High | [All tools assume X. None design for Y.] |
| [Gap 2: Input model] | [Tier] | High | [Description] |
| [Gap 3: Channel coverage] | [Tier] | High | [Description] |
| [Gap 4: Proactive features] | [Tier] | High | [Description] |
| [Gap 5: Mobile experience] | [Tier] | High | [Description] |
| [Gap 6: Pricing] | [Tier] | Medium | [Description] |

### 10.3 Competitive Positioning Summary

- [No existing tool designs for the target user's actual context.]
- [The core gap is structural and unsolvable through integration.]
- [Closest tools each solve one dimension while failing at the behavioural anchor.]
- [No tool has achieved the architectural shift. This is the white space.]

[One editorial sentence about the nature of the white space. For example: "The white space is not a feature gap - it is an architectural gap."]

---

## 11. Problem Clustering

### 11.1 [Cluster 1 Name]

- [Sub-problem 1]: [Description and evidence.] [SEVERITY]
- [Sub-problem 2]: [Description. Hard constraint vs. product gap.] [SEVERITY]
- [Sub-problem 3]: [Description from primary research.] [PRIMARY RESEARCH]

[One editorial sentence about when the failure begins.]

### 11.2 [Cluster 2 Name]

- [Sub-problem 1]: [Description with evidence.] [SEVERITY]
- [Sub-problem 2]: [Description.] [X/Y participants]

[One editorial sentence about how failures compound.]

### 11.3 [Cluster 3 Name]

- [Sub-problem 1]: [Description of gap.]
- [Sub-problem 2]: [Description of illusion/misconception.]
- [Sub-problem 3]: [Description of drift/decay.]

[One editorial sentence about the structural nature of the gap.]

---

## 12. Problem Prioritisation

### 12.1 Identified Problems

| Problem | Description | Frequency | Severity |
|---------|-------------|-----------|----------|
| P1 - [Name] | [Description] | [X/Y affected] | HIGH |
| P2 - [Name] | [Description] | [X/Y cited] | HIGH |
| P3 - [Name] | [Description] | [X/Y cited] | HIGH |
| P4 - [Name] | [Description] | [X/Y cited] | MODERATE |
| P5 - [Name] | [Description] | [X/Y cited] | MODERATE |
| P6 - [Name] | [Description] | [X/Y cited] | MODERATE |
| P7 - [Name] | [Description] | | HIGH |
| P8 - [Name] | [Description] | | MODERATE |
| P9 - [Name] | [Description] | | MODERATE |
| P10 - [Name] | [Description] | | HIGH |

### 12.2 Prioritisation Logic

- **P1, P2, P3** are root-cause problems: [why - frequency, severity, directly cause the core failure, architecturally unaddressed].
- **P4-P6** are symptomatic - downstream consequences of P1 and P2.
- **P7-P10** are tractable adoption barriers once P1-P3 are solved; they do not independently cause [the core failure].

### 12.3 Selected Priority: The [Name] Chain

**[P1] -> [P2] -> [P3] -> [CORE FAILURE]**

Why this chain:
- [Frequency]: [Evidence]
- [Architectural gap]: [No tool addresses this]
- [Direct impact]: [Causes outcome loss, not just productivity loss]
- [Technical feasibility]: [Why it is now solvable]
- [Position in chain]: [Addressing it prevents all downstream failures]

[One editorial sentence about the strategic decision. For example: "Solving P1 + P2 + P3 together as a single architectural decision, not three separate features, is the product strategy."]

---

## 13. Prioritisation Rationale

### 13.1 Why This Problem

| Reason | Evidence |
|--------|----------|
| Frequency | [X/Y participants identified this exact cluster] |
| [Impact] directness | [Causes outcome loss, not just inefficiency. ROI case is immediate.] |
| Competitive white space | [None of X tools addresses the full chain] |
| [Technology] timing | [Relevant tech mature enough for the solution approach] |
| Market urgency | [CAGR, intent vs adoption gap. First to remove the barrier captures the market.] |

[One editorial sentence about convergence. For example: "Five independent signals converge on the same problem. That convergence is rare. It indicates this is the right problem at the right time."]

### 13.2 Why Not Other Problems

| Problem | Reason Excluded |
|---------|----------------|
| [Excluded 1] | [Structurally different. Would dilute core solution.] |
| [Excluded 2] | [Requires baseline that doesn't exist yet. Phase 2.] |
| [Excluded 3] | [Requires data foundation. Phase 3.] |
| [Excluded 4] | [Target user doesn't need this. Out of scope.] |

[One editorial sentence about sequencing. For example: "Each excluded problem is real - but solving it requires a data foundation that doesn't yet exist. The sequencing is intentional."]

### 13.3 Trade-Offs

| Trade-off | Analysis |
|-----------|----------|
| [Trade-off 1, e.g., Privacy vs convenience] | [How we resolve it and why] |
| [Trade-off 2, e.g., Simplicity vs completeness] | [Resolution and reasoning] |
| [Trade-off 3, e.g., Speed vs accuracy] | [Resolution and reasoning] |

[One editorial sentence about the direction. For example: "All three trade-offs resolve in the same direction: a slightly imperfect tool the user actually uses is categorically better than a perfect tool they abandon."]

---

## 14. Narrowed Problem Statement

### 14.1 Core Problem Definition

[One paragraph. Target user + context + structural failure + consequence + why every existing solution fails + what kind of approach is needed. No solution language. A developer who has never spoken to a user should feel the weight of the problem after reading this.]

[One editorial sentence. For example: "Every existing tool requires the user to adapt to the tool. The solution must adapt to the user."]

### 14.2 Target User Segment

**Primary**: [Precise definition. Role, stage, geography, size, revenue range.]

**Adjacent**: [Secondary segment with higher [relevant trait] and lower [familiarity/resource].]

**Explicit exclusions**: [List each excluded group with a one-word reason.]

### 14.3 Problem Scope

**In Scope**:
- [Specific failure mode 1]
- [Specific failure mode 2]
- [Specific failure mode 3]

**Out of Scope**:
- [Item 1]
- [Item 2]
- [Item 3]
- [Item 4]

---

## 15. Key Assumptions

### 15.1 User Behaviour

| Assumption | Evidence / Basis | Confidence |
|-----------|-----------------|------------|
| [Core behaviour assumption] | [Primary evidence] | HIGH |
| [Adoption assumption] | [Evidence] | MODERATE |
| [Engagement assumption] | [Evidence] | MODERATE |
| [Trust assumption] | [Evidence] | MODERATE |
| [Advocacy assumption] | [Evidence] | EMERGING |

### 15.2 Market

| Assumption | Evidence / Basis | Confidence |
|-----------|-----------------|------------|
| [Market growth assumption] | [Source] | HIGH |
| [Pricing assumption] | [Evidence] | HIGH |
| [Segment assumption] | [Evidence] | MODERATE |
| [Adoption assumption] | [Evidence] | MODERATE |
| [Onboarding assumption] | [Evidence] | EMERGING |

---

# PART 2: SOLUTION

---

## 1. Product Concept

### 1.1 The [Name] Chain - What We Are Solving

The Discovery PRD identified [X] root-cause failures that compound in sequence. Solving the first breaks the entire chain downstream:

**[Failure 1]** -> [Description of what fails and why.]
**[Failure 2]** -> [Description.]
**[Failure 3]** -> [Description.]

The solution does not patch these failures. It replaces the [input model / interaction model] entirely.

### 1.2 What We Built

[Product Name] is not a [simpler version of existing category]. It is a fundamentally different product category - one that inverts the relationship between [the core activity] and [the record/system].

In every existing [category tool], [a core activity] is an input that requires a record. The user must [stop, open the tool, and log what happened]. In [Product Name], [the core activity] is the record. The user [describes the zero-friction capture mechanism] - and the system builds the record automatically.

| Every [Category] Today | [Product Name] |
|------------------------|----------------|
| [Current paradigm 1] | [New paradigm 1] |
| [Current paradigm 2] | [New paradigm 2] |
| [Current paradigm 3] | [New paradigm 3] |
| [Current paradigm 4] | [New paradigm 4] |
| [Current paradigm 5] | [New paradigm 5] |
| [Current paradigm 6] | [New paradigm 6] |

### 1.3 Architecture in One Sentence

[Component A] captures [context] passively from the user's existing behaviour. [Component B] makes that context visible. Neither requires the user to do anything they are not already doing.

### 1.4 The Non-Negotiables

Any feature, flow, or design decision that violates one of these constraints was excluded from the MVP. These are not preferences - they are survival conditions for this persona.

| Constraint | What It Means in Practice | Research Basis |
|-----------|--------------------------|---------------|
| [Constraint 1] | [Specific implication] | [Evidence from research] |
| [Constraint 2] | [Implication] | [Evidence] |
| [Constraint 3] | [Implication] | [Evidence] |
| [Constraint 4] | [Implication] | [Evidence] |

### 1.5 Design Rationale - [Key Architecture Choice]

The choice of [architecture/platform/approach] is not arbitrary. It is the only architecture that satisfies all non-negotiables simultaneously:

- [Reason 1: Why alternatives don't work]
- [Reason 2: Native capability that matters]
- [Reason 3: Friction comparison]
- [Reason 4: Context/workflow alignment]
- [Reason 5: Compliance/regulatory alignment]

[One editorial sentence. For example: "The forward architecture is not a workaround. It is the product."]

---

## 2. Primary User Persona

### 2.1 The [Persona Name]

| Attribute | Detail |
|-----------|--------|
| Name and Age | [Composite name], [age] |
| Company | [Type]. [Stage]. [Team size]. |
| Location | [Primary city (applicable to others)] |
| [Domain] Reality | [Key numbers - how many active items, which channels, what lifecycle looks like] |
| Current Toolkit | [List of actual tools used today] |
| Primary Goal | [One sentence - what they want to accomplish without becoming] |
| Core Frustration | "[Verbatim or near-verbatim quote from research]" |
| [Category] History | [What they tried and why each failed] |
| Technical Comfort | [Level. What they use. What they won't tolerate.] |

---

## 3. Product Flows

The product has [X] distinct flows. Each is designed to require zero friction at the point of use. The user never opens a [category] interface to log something. They interact with [the capture surface] in the same way they already interact with [people/colleagues] - via [existing behaviours].

### 3.1 Onboarding Flow

Design principle: Zero cognitive load at entry. [The structure] is generic. Value arrives before any configuration is required.

| Step | Action | What the User Sees | Time |
|------|--------|-------------------|------|
| 1 | [Entry action] | [What they see] | [Time] |
| 2 | [Connection action] | [What they see] | [Time] |
| 3 | [Welcome] | [Welcome message content] | Instant |
| 4 | [First value action] | [First record created. Confirmed.] | < 30 seconds |

[List what is NOT required: no name, no company info, no configuration. The system waits for first input.]

### 3.2 Input Layer

The user has [X] input modes. The system accepts all interchangeably. There is no "correct" way to log.

| Input Type | User Action | What AI Extracts |
|-----------|-------------|-----------------|
| [Input 1] | [Specific user action] | [What the system extracts - be specific about fields] |
| [Input 2] | [Action] | [Extraction] |
| [Input 3] | [Action] | [Extraction] |

Edge cases not in MVP: [List explicitly. These are Phase 2 inputs.]

### 3.3 [Core Processing] Flow

Once an input arrives, the system runs a structured extraction sequence. The user confirms a card - they do not fill one in.

| Step | System Action | User Sees | User Action |
|------|--------------|-----------|-------------|
| 1 | [Processing] | [Indicator] | Waits |
| 2 | [Card generation] | [Card with specific fields listed] | Reviews |
| 3 | [Missing field check] | [One clarifying question max] | Replies (optional) |
| 4 | [Confirmation] | [Edit options. No form.] | Confirms or edits |
| 5 | [Storage + next action] | [Confirmation + what happens next] | Done |

Fields auto-populated: [List all fields the AI extracts. Note that rules per field are defined in the system prompt - the user never sees them.]

### 3.4 [Context Recall] Flow

The highest-frequency use case from primary research: [describe the specific pain this solves].

| Input | User Action | System Response |
|-------|-------------|----------------|
| [Command] | [Types specific command] | [What they get back - be specific about fields] |
| [Natural language] | [Types a question] | [Conversational response with specific fields] |
| [Voice] | [Speaks a request] | [Voice-optimised response] |

### 3.5 [Proactive Action] Flow

The system fires [actions/nudges] automatically. The user does not set reminders manually. The logic is triggered by [inactivity/signals], not by the user's calendar.

| Trigger | System Message | User Action |
|---------|---------------|-------------|
| [Trigger 1 with timing] | [Specific message content] | [One-tap options] |
| [Trigger 2 with timing] | [Message] | [Options] |
| [Trigger 3 - daily] | [Digest content and limits] | [Review and act] |
| [Trigger 4 - milestone] | [Celebration + optional prompt] | [Optional action] |

[State the rules explicitly: timing by stage/status, what exits the queue, what is configurable vs. system-set in MVP.]

---

## 4. Workflow Mapping - Before and After

### 4.1 Before [Product Name] - A Day in [Current] Mode

| Time | User Action | System State | Cost |
|------|-------------|-------------|------|
| [Morning] | [Manual reconstruction] | [Nothing logged] | [Time cost] |
| [Mid-morning] | [Good interaction, means to log later] | [No record created] | [Context lost] |
| [Midday] | [Action taken, no follow-up set] | [No trigger queued] | [Risk] |
| [Afternoon] | [Old item goes cold] | [Status unknown] | [Outcome lost] |
| [Late afternoon] | [Pre-interaction prep via scrolling] | [All context in chat threads] | [Time wasted] |
| [Evening] | [Stakeholder asks for update. Reconstruction from memory.] | [No real data] | [Time + inaccuracy] |

### 4.2 After [Product Name] - Same Day, Structured Mode

| Time | User Action | System State | Outcome |
|------|-------------|-------------|---------|
| [Morning] | [Reviews digest] | [Full visibility. Priority ranked.] | [Time. Day planned.] |
| [Mid-morning] | [Quick capture after interaction] | [Record created. Actions queued.] | [Time. Context captured.] |
| [Midday] | [Logs action. System auto-queues follow-up.] | [Status updated. Reminder set.] | [Time.] |
| [Afternoon] | [System nudges about aging item] | [Inactivity detected.] | [Outcome saved.] |
| [Late afternoon] | [Quick context recall command] | [Brief returned in seconds.] | [Interaction starts informed.] |
| [Evening] | [Stakeholder asks. Quick command.] | [Live snapshot returned.] | [Time. Accurate.] |

---

## 5. [Secondary Surface / Platform]

### 5.1 Architectural Principle

The [secondary surface] is a visibility layer, not a capture layer. The [primary surface] captures. The [secondary surface] displays. The user never needs to open the [secondary surface] to keep the system alive.

This means: if the user never opens the [secondary surface], the system still functions. This is not a failure state. It is the intended design.

### 5.2 Feature Set

| Feature | What It Shows | Phase | Priority |
|---------|-------------|-------|----------|
| [Feature 1] | [Description. Note any limitations like read-only.] | Phase 1 | P0 |
| [Feature 2] | [Description] | Phase 1 | P0 |
| [Feature 3] | [Description] | Phase 1 | P0 |
| [Feature 4] | [Description] | Phase 1 | P0 |
| [Feature 5] | [Description] | Phase 1 | P0 |
| [Feature 6] | [Description. Note minimum data requirements.] | Phase 2 | P1 |
| [Feature 7] | [Description] | Phase 2 | P1 |
| [Feature 8] | [Description] | Phase 3 | P2 |

### 5.3 Key Differentiators

| Design Decision | Why (Evidence) | What This Replaces |
|----------------|---------------|-------------------|
| [Decision 1] | [Research-backed reason] | [What existing tools do instead] |
| [Decision 2] | [Reason] | [Replacement] |
| [Decision 3] | [Reason] | [Replacement] |
| [Decision 4] | [Reason] | [Replacement] |

### 5.4 Permanent Constraints

[Describe any hard architectural boundaries that are permanent, not roadmap deferrals. Explain the technical, regulatory, or platform reasons.]

---

## 6. User Stories

User stories are written from the perspective of [Persona Name]. Each story maps to a product flow and a specific pain point validated in primary research. Stories are organised by job-to-be-done, not by feature.

### 6.1 [Job Category 1] - [Name, e.g., "Getting Things Into the System"]

| # | Story | Acceptance Criteria | Pain Point Addressed |
|---|-------|-------------------|---------------------|
| U1 | As a [user], I want to [action] so I never have to [painful alternative]. | [Specific, testable criteria: timing, fields shown, taps required, visibility.] | [The specific research finding this addresses.] |
| U2 | As a [user], I want to [action] so [outcome]. | [Criteria] | [Pain point] |
| U3 | | | |
| U4 | | | |

### 6.2 [Job Category 2] - [Name, e.g., "Knowing the Context Before Acting"]

| # | Story | Acceptance Criteria | Pain Point Addressed |
|---|-------|-------------------|---------------------|
| U5 | | | |
| U6 | | | |
| U7 | | | |

### 6.3 [Job Category 3] - [Name, e.g., "Things Moving, Not Dying"]

| # | Story | Acceptance Criteria | Pain Point Addressed |
|---|-------|-------------------|---------------------|
| U8 | | | |
| U9 | | | |
| U10 | | | |

### 6.4 [Job Category 4] - [Name, e.g., "Seeing the Full Picture"]

| # | Story | Acceptance Criteria | Pain Point Addressed |
|---|-------|-------------------|---------------------|
| U11 | | | |
| U12 | | | |
| U13 | | | |

---

## 7. MVP Scope

### 7.1 MVP in One Sentence

[The minimum coherent product in one sentence. If a feature is not captured in this sentence, it is not in the MVP.]

### 7.2 The Hypotheses Driving MVP Design

The MVP is built to validate [X] specific hypotheses before any [next phase] begins. If any of H1-H3 fail, the product does not proceed.

| H# | Hypothesis | Kill Signal | Gate For |
|----|-----------|-------------|----------|
| H1 | [Core capture behaviour] | [< X% threshold] | [What this gates - the entire architecture if it fails] |
| H2 | [Secondary capture behaviour] | [< X% threshold] | [What this gates] |
| H3 | [Core value behaviour] | [< X% threshold] | [What this gates] |
| H4 | [Engagement behaviour] | [No measurable improvement] | [What this gates] |
| H5 | [Architecture preference] | [Majority contradicts assumption] | [What this gates] |

### 7.3 In Scope for MVP

| Feature | Description | Priority |
|---------|-------------|----------|
| [Feature 1] | [Specific description of what it does] | P0 - MUST HAVE |
| [Feature 2] | [Description] | P0 - MUST HAVE |
| [Feature 3] | [Description] | P0 - MUST HAVE |
| [Feature 4] | [Description] | P0 - MUST HAVE |
| [Feature 5] | [Description] | P0 - MUST HAVE |
| [Feature 6] | [Description] | P0 - MUST HAVE |
| [Feature 7] | [Description] | P0 - MUST HAVE |
| [Feature 8] | [Description] | P0 - MUST HAVE |
| [Feature 9] | [Description] | P0 - MUST HAVE |
| [Feature 10] | [Description] | P0 - MUST HAVE |
| [Feature 11] | [Description] | P0 - MUST HAVE |
| [Feature 12] | [Description] | P0 - MUST HAVE |
| [Feature 13] | [Description] | P1 - SUPPORTING |
| [Feature 14] | [Description] | P1 - SUPPORTING |
| [Feature 15] | [Description] | P0 - MUST HAVE |

---

## 8. What We Left Out and Why

Every feature below was explicitly considered and excluded from the MVP. The exclusions are not oversights - they are architectural decisions.

| Excluded Feature | Why It Was Considered | Why It Was Excluded | Phase |
|-----------------|---------------------|-------------------|-------|
| [Feature 1] | [Legitimate reason to want it] | [Structural reason for exclusion] | Phase 1 |
| [Feature 2] | [Reason] | [Exclusion logic] | Phase 2 |
| [Feature 3] | [Reason] | [Exclusion logic] | Phase 2 |
| [Feature 4] | [Reason] | [Exclusion logic] | Phase 2 |
| [Feature 5] | [Reason] | [Exclusion logic] | Phase 2 |
| [Feature 6] | [Reason] | [Exclusion logic] | Phase 2 |
| [Feature 7] | [Reason] | [Exclusion logic] | Phase 3 |
| [Feature 8] | [Reason] | [Why it is not viable - permanent constraint] | Not viable |
| [Feature 9] | [Reason] | [Permanent constraint explanation] | Permanent exclusion |

---

## 9. Success Metrics

Metrics are behaviour-first. We measure what users do, not what they say they will do. User-reported satisfaction is not a success signal. Behaviour change is the only signal that matters.

Kill condition: if any P0 metric misses its 30-day target, the corresponding hypothesis is marked as failed and the team pauses feature development to diagnose before proceeding.

| Metric | What It Measures | 30-Day Target | Kill Signal | Hypothesis |
|--------|-----------------|---------------|-------------|------------|
| [Metric 1] | [Specific behaviour] | > [X%] | < [Y%] | H1 |
| [Metric 2] | [Behaviour] | > [X%] | < [Y%] | H2 |
| [Metric 3] | [Behaviour] | > [X%] | < [Y%] | H3 |
| [Metric 4] | [Behaviour] | > [X%] | < [Y%] | H4 |
| [Metric 5] | [Behaviour] | > [X%] via [preferred method] | < [Y%] via [preferred] | H5 |
| D7 Retention | Active users at day 7 | > [X%] | < [Y%] | Core |
| D30 Retention | Active users at day 30 | > [X%] | < [Y%] | Core |

---

## 10. Implementation Plan

[Link to detailed implementation guide if separate, or include phases here.]

### 10.1 Build Phases

| Phase | Duration | What Ships | Hypothesis Tested | Gate to Proceed |
|-------|----------|-----------|------------------|----------------|
| Phase 0: Foundation | [X days] | [Infrastructure, auth, data model] | None - setup | [Live, no P0 bugs] |
| Phase 1: Core Loop | [X days] | [Primary capture + processing] | H1, H2 | [H1 threshold met] |
| Phase 2: Value Delivery | [X days] | [Context recall + nudges] | H3, H4 | [H3 threshold met] |
| Phase 3: [Secondary Surface] | [X days] | [Visibility layer] | H5 | [Usage confirms architecture] |

### 10.2 Technical Approach

**Stack**: [Core technology choices with one-line reasons.]

**Critical path**: [The dependency chain that, if delayed, delays everything.]

---

## 11. Trade-offs and Limitations

### 11.1 What This Product Does Not Solve

| Area | Why It Is Out of Scope |
|------|----------------------|
| [Limitation 1] | [Honest explanation of what the product cannot change] |
| [Limitation 2] | [Explanation] |
| [Limitation 3] | [Explanation] |
| [Limitation 4] | [Explanation] |
| [Limitation 5] | [Explanation] |

### 11.2 Known Trade-offs in MVP Design

| Trade-off | What We Gave Up | Why We Made It |
|-----------|----------------|---------------|
| [Trade-off 1] | [Cost] | [Reasoning with evidence] |
| [Trade-off 2] | [Cost] | [Reasoning] |
| [Trade-off 3] | [Cost] | [Reasoning] |
| [Trade-off 4] | [Cost] | [Reasoning] |
| [Trade-off 5] | [Cost] | [Reasoning] |

### 11.3 Dependency Risks

- [Risk 1: External service dependency and its impact.]
- [Risk 2: AI/ML quality dependency and failure modes.]
- [Risk 3: Input quality dependency and degradation scenarios.]
- [Risk 4: Third-party data dependency for future phases.]

---

## 12. The Moonshot

**Phase [X]+**
**Separate Surface**

[One paragraph positioning statement: what the moonshot moves the product from and to. For example: "from a context management tool to an active intelligence layer."]

### 12.1 The Problem This Solves

[Describe the pattern from primary research that this addresses. Include a verbatim quote.]

> "[Quote from a user that captures the unmet need]" - [Name], [Role] - Primary Research

### 12.2 How It Works

| Track | What Happens | Output to User |
|-------|-------------|---------------|
| [Background track] | [Continuous enrichment/analysis] | [How the user's experience improves silently] |
| [On-demand track] | [Triggered by user request] | [Structured output - list the specific components] |
| [Intelligence track] | [Pattern analysis over time] | [Personalised recommendations based on user's data] |

### 12.3 Why This Is Not in the MVP

| Reason | Detail |
|--------|--------|
| [Data dependency] | [Needs X records to be valuable] |
| [Surface dependency] | [Output depth requires a separate interface] |
| [Infrastructure dependency] | [Separate pipeline/architecture needed] |
| [Hypothesis dependency] | [Core hypotheses must validate first] |

### 12.4 If Validated - Strategic Implication

[The moonshot as moat. Why this feature cannot be replicated by general-purpose tools. Describe the flywheel: more [captures] -> richer [intelligence] -> better [output] -> higher [outcomes] -> stronger [retention].]

---

*All interview notes and secondary research sources are available at [link or folder location].*
