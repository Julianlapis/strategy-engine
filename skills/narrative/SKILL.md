---
name: narrative
description: |
  Strategy docs and slide-ready copy from a brief. The original strategy mode.
  Use for brand positioning, GTM strategy, marketing strategy, innovation strategy.
  Produces a structured narrative document, then distills it to annotated slide copy.
---

<required_reading>
Read before doing ANY work:
1. `feedback-log.md` — Binding corrections. These override everything.
2. `rules/voice.md` — Voice DNA + Stop-Slop rules
3. `rules/quality-gates.md` — Scoring system and anti-patterns
4. `rules/process.md` — Phase sequencing
</required_reading>

# /strategy:narrative

Craft strategy documents and slide-ready copy from any brief.

## Core Philosophy

1. **Strategy is tension resolved.** Create a felt problem before offering a solution.
2. **Insights are specific or they're observations.** If a cultural claim could apply to a different brand, rewrite.
3. **The argument earns the strategy.** Each section builds on the last. Strategy should feel inevitable.
4. **Strategy makes choices.** If every brand in the category could endorse it, it's not a strategy.
5. **Write like a strategist, not a consultant.**

---

## Phase 0: Intake

Accept whatever Julian provides.

**If the input is thin (brand + problem only):**
Ask up to 5 clarifying questions:
- Who is the audience? (behavior and belief, not demographics)
- What does success look like?
- What has the brand tried before?
- What's the competitive context?
- Is this for a pitch, internal alignment, or creative briefing?

**If the input is rich:** Skip to Phase 1.

**Detect engine:**

| Type | Signals | Default engine |
|------|---------|----------------|
| Brand positioning | "positioning," "brand strategy," "what should the brand stand for" | Brand DNA vs Cultural Truth |
| GTM / business strategy | "go-to-market," "pitch," "sell this" | False Choice → Reframe |
| Marketing / creative strategy | "campaign," "launch," "activation" | Subculture → Mobilization |
| Innovation / product strategy | "new product," "service design," "experience strategy" | Audience Tension → Platform Expansion |
| Unclear | None of the above | Propose 2 engines with rationale, ask Julian |

The engine is a starting point. Adapt the section sequence to the brief.

---

## Phase 1: Structure (PAUSE for approval)

<required_reading>
Load: `references/narrative-engines.md`
</required_reading>

Using the selected engine:

1. Map the brief to the engine's section sequence
2. Draft the narrative architecture:

```
ENGINE: [Name]

NARRATIVE ARCHITECTURE
──────────────────────
01 — *The Challenge*: [one-sentence summary]
02 — *Brand DNA*: [one-sentence summary]
...
[N] — *The Strategy*: [one-sentence summary]

COINED CONCEPT CANDIDATES
─────────────────────────
1. [Concept] — [why it works]
2. [Concept] — [why it works]
3. [Concept] — [why it works]

EXPRESSION DEPTH: [Strategic frame only / Directional territories / Full concepts]
ESTIMATED SLIDES: [range]
```

3. **STOP. Wait for Julian's approval.** Do not proceed until confirmed.

---

## Phase 2: Write Strategy Document

Produce a structured markdown document.

```markdown
# [Strategy Title]
*[Brief type] for [Brand]*

---

## The Challenge
[1-3 paragraphs. State the problem bluntly. Cultural specificity. Make the reader feel it.]

## [Engine-specific sections...]
[Follow approved architecture. 1-3 paragraphs per section max.]

## The Concept
[The coined idea. 1-2 paragraph explanation of why it works.]

## The Strategy
[One sentence headline, then 3-4 supporting pillars.]

## Expressions (if brief type requires)
[2-3 activation territories with specific partners, formats, channels.]

---

*Quality score: [X/50]*
```

---

## Phase 3: Distill to Slide-Ready Copy

<required_reading>
Load: `references/slide-conventions.md`
</required_reading>

After the strategy doc is approved (or simultaneously if Julian prefers):

### Format per slide

```
---
SLIDE [N]
[layout: layout-type]

*[Eyebrow label]*

[Headline copy. One idea. Sentence case.]

[Body copy. 1-3 sentences max. Accent words in **bold**.]

[Layout note: visual direction if relevant]
---
```

### Rules
- Every slide lands exactly one idea. Two ideas = two slides.
- Annotate every slide with a layout type. Never repeat layouts back-to-back.
- Accent 1-2 words per slide in **bold** for color treatment.
- Include layout notes for image moments, data viz, positioning maps.
- The slide sequence must work as a standalone argument.

---

## Phase 4: Quality Gate (MANDATORY)

Run the full quality gate from `rules/quality-gates.md`.

**CRITICAL (from feedback-log.md 2026-03-18):** Both quality layers (Voice DNA + Stop-Slop) must be run LINE-BY-LINE on the strategy doc AND the slide copy. The quality gate is mandatory, not decorative. Every slide, every sentence. No exceptions.

Present the scored output to Julian. Flag any dimension below 7.

---

## Phase 5: Observation

After presenting, log a structured observation per `rules/observation.md`.
