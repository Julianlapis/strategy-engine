---
name: narrative
description: |
  Strategy docs and slide-ready copy from a brief. The original strategy mode.
  Use for brand positioning, GTM strategy, marketing strategy, innovation strategy.
  Produces a structured narrative document, then distills it to annotated slide copy.
---

<required_reading>
Read `~/.claude/feedback/pre-flight.md` before any work.
Read before doing ANY work:
1. `feedback-log.md` — Binding corrections. These override everything.
2. `rules/voice.md` — Two-layer voice system (Layer 1: identity, Layer 2: client polish)
3. `~/.claude/copy-polish.md` — Layer 2: plain language, directness, jargon elimination (this skill is client-facing)
4. `rules/quality-gates.md` — Scoring system and anti-patterns
5. `rules/process.md` — Phase sequencing
6. `references/pitch-deck-pattern.md` — C&T pitch deck structure (from Bumble, Anthropic, Xbox decks). The canonical Act 1-4 structure for all pitch narratives.
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
[role: What job this slide does in the argument chain — one sentence]
[key-message: The single takeaway the audience retains]

*[Eyebrow label]*

[Headline copy. One complete sentence that argues. Not a list.]

[Body copy. 1-3 sentences max. Must do NEW work — never restate headline.]

[Layout note: visual direction if relevant]
---
```

### Rules
- Every slide lands exactly one idea. Two ideas = two slides.
- Annotate every slide with a layout type. Never repeat layouts back-to-back.
- Accent 1-2 words per slide in **bold** for color treatment.
- Include layout notes for image moments, data viz, positioning maps.
- The slide sequence must work as a standalone argument.

### Headline vs Role Audit (MANDATORY after writing all slides)

After writing all slides, run this three-part check:

1. **Role test:** Read each headline against its [role:] field. Does the headline DO the job the role requires, or does it just describe the topic? Headlines that describe topics are observations. Headlines that do jobs are arguments.
2. **Body redundancy test:** For each headline + body pair, check: does any body sentence restate what the headline already said? If yes, replace it with new information or cut it.
3. **Argument chain test:** Read all headlines in sequence without body copy. Do they build an argument where each makes the next feel inevitable? Key word threading: do the 2-3 words that carry the argument (e.g., "lifestyle," "instinct," "identity") appear on the slides where they're load-bearing?

This audit replaces the looser "Headline Flow" dimension from Phase 5 scoring. The structured audit is more rigorous.

### Extract, Don't Summarize (MANDATORY)

The strategy doc from Phase 2 is the copy source. Slide headlines and body should be **lifted verbatim** from the strategy doc, not rewritten into shorter neutral language.

- **Headline** = the sharpest sentence from the corresponding strategy doc section. Promote it directly.
- **Body** = the 1-3 sentences from the doc that carry the most evidence or voice texture. Lift them.
- **Source attribution** = note which strategy doc section each slide draws from.
- **If shortening:** cut words from the original line. Don't rephrase. Replacing a specific, voiced sentence with a generic summary is a skill failure.

**Anti-blandification check:** After writing all slide copy, compare each slide against its source section. Did you lose a physical verb? Flatten a rhythm? Replace a named example with an abstraction? Cut a number? If yes, restore from the source.

**Why:** On 2026-03-24, a distilled essay was turned into slide copy that stripped its voice. Physical verbs became neutral summaries. Cascading rhythms became single flat sentences. This rule prevents that from recurring.

### Handoff to agentic-slides

If the user wants to build the deck in Paper or Figma after Phase 3, invoke `/paper-slides` (agentic-slides) with the slide-ready copy as the content file input.

**Handoff contract:** copy.md exiting this phase is finalized: voiced, role-audited, headline-vs-role checked, anti-blandification verified. Agentic-slides compresses for visual constraints (word budgets per layout type) and validates narrative comprehension in rendered form. It does not rewrite for strategic quality. If agentic-slides finds a strategic issue (e.g., a headline that doesn't argue), it flags it back to the user rather than rewriting.

---

## Phase 4: Quality Gate (MANDATORY)

Run the full quality gate from `rules/quality-gates.md`.

**Copy Quality Gate:**
Invoke `/write:voice` (which spawns the `voice-review` agent with fresh context). This is mandatory. The agent reads voice-dna.md and copy-polish.md from disk, receives only the copy to review, and returns line-by-line violations with rewrites. Mechanical checks (banned phrases, em dashes, adverbs) are handled by the copy linter hook. The agent focuses on judgment calls: rhythm, register, voice authenticity, thematic verb weight, key word threading.

Present the scored output to Julian. Flag any dimension below 7.

---

## Phase 5: Observation (MANDATORY — feeds auto-sharpen)

After presenting, log a structured observation to **both** locations:

### 1. Plugin log (strategy-engine internal)
Append to `logs/execution-log.md` per `rules/observation.md`.

### 2. Feedback execution log (triggers auto-sharpen)
Append to `~/.claude/feedback/logs/execution-log.md` using this exact format:

```markdown
---
skill: strategy-engine:narrative
date: YYYY-MM-DD
brief_summary: [1-2 sentence summary]
---

### Scores
| Dimension | Score |
|-----------|-------|
| Tension | /10 |
| Specificity | /10 |
| Narrative Arc | /10 |
| Headline Flow | /10 |
| Slide Discipline | /10 |
| Cultural Grounding | /10 |
| Persuasion | /10 |
| **Total** | **/70** |

### Weak Dimensions
[Any dimension below 7 with what was weak]

### Self-Corrections
[What was caught and fixed before presenting]

### User Feedback
[Updated after Julian responds]
```


**Scoring the new dimensions:**
- **Headline Flow** (10): Can you read headlines alone and follow the argument? Do they connect like a conversation? Each one a complete thought?
- **Slide Discipline** (10): Under 30 slides? Stats in margins? Body copy optional? No process slides? Dividers carry weight?

These dimensions are scored against `~/.claude/feedback/strategy/checklist.md` items 10-18.
