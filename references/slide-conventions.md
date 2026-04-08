# Slide Conventions

Formatting rules, structural labels, and layout annotation system for slide-ready strategy copy.

---

## Structural Labels

These are the labeled section headers used in Julian's strategy decks. They appear as eyebrow text above the main headline, typically in a lighter weight or serif typeface.

### Core Labels (used across engines)

| Label | Purpose |
|-------|---------|
| The Challenge | States the brand's current problem |
| The Ambition | One-sentence vision of success |
| Brand DNA | The brand's founding purpose or core belief |
| Cultural Truth | How the world has shifted |
| The Key Insight | The human behavior that resolves the tension |
| The Reframe | A new way to see the problem |
| The Opportunity | Where the brand can own space |
| Our Strategy | The strategic direction |
| The Concept | The coined idea or positioning territory |

### Analytical Labels

| Label | Purpose |
|-------|---------|
| Foundational Truth | The brand's undeniable advantage |
| The Problem | The systemic issue in the category |
| False Choice / Our Belief | Binary exposed + resolution (used in pairs) |
| The Implication | What this means for the brand specifically |
| The Solution | Named system, product, or approach |
| How It Works | Mechanics of the solution |
| Use Case | Concrete demonstration |
| What You Get | Tangible outcomes |

### Evidence Labels

| Label | Purpose |
|-------|---------|
| The Key Problem | A sharpened version of the cultural challenge |
| Human Insight | Audience-level truth (vs Cultural Truth which is macro) |
| Looking Ahead | Emerging shift that creates the opportunity |
| A New [Category] Era | Cultural shift in the specific category |

### Structural Labels

| Label | Purpose |
|-------|---------|
| From / To | Transformation bridge (used as a pair) |
| Before / With [Solution] | Comparison table |
| Summary | Closing metrics or recap |
| What just happened: | Post-demo recap (used after walking through a use case) |

---

## Slide Role Declaration

Every slide in copy.md gets a **Role** field: one sentence describing its job in the argument chain. The Role is how you judge whether a headline is working.

### Schema

```
## Slide [N]: [Name]
- **Role:** [What job this slide does in the argument chain. One sentence.]
- **Key Message:** [The single takeaway the audience retains.]
```

### Headline Diagnostic

After writing all slides, run this check on every headline:

1. **"Does this headline DO the job its Role requires, or does it just DESCRIBE the topic?"** A headline that describes the topic ("Prediction markets proved demand and fragility") reports a finding. A headline that does the job ("300,000 users showed up on election night. 5,000 came back.") makes the room feel the retention gap.
2. **Body redundancy check:** Does any sentence in the body say the same thing as the headline? If yes, replace it with new information or cut it.
3. **Argument chain check:** Read all headlines in sequence. Do they build an argument where each makes the next feel inevitable? Or do they list topics?

### Eyebrow Rules

Eyebrows should frame the slide's purpose, not mark chapters.

| Good (purpose frame) | Bad (chapter marker) |
|----------------------|---------------------|
| THE CATEGORY | 01 / VISION |
| WHAT WE FOUND | 02 / BRAND STRATEGY |
| THE INTERSECTION | 03 / DESIGN |
| WHO WE'RE REACHING | Section 2 |

Chapter markers are wayfinding. Purpose frames tell the reader what kind of argument is on this slide. Purpose frames are preferred for strategy slides. Chapter markers are acceptable on plan/logistics slides (04 / THE PLAN, 04 / BUDGET) where wayfinding matters more than argument.

Eyebrows can also carry sub-framing: "THE CATEGORY: Main Shift" uses the purpose frame plus a qualifier that tells the reader what aspect of the category matters.

---

## Slide Copy Quality Rules

### Headlines are complete arguments, not asset inventories

A headline that lists ingredients ("Four verticals, a Polymarket partnership, and 3M users") is not a headline. It's a brief summary. Headlines must be complete sentences that make a point about the user, the behavior, or the insight. Benchmark: the Xbox Game Pass deck, where every headline argues ("They don't want more games, they want more gaming").

### Body copy extends, never restates

When a headline carries proof points or stats, the body must do NEW work. If body copy restates the headline in different words, it fails. This is the single most common failure mode in slide copy.

### Verbs carry thematic weight

Choose verbs that do double duty: name the action AND carry the slide's thematic payload. "Track the bettor" diagnoses a data problem. "Recognize the bettor" diagnoses an identity problem. If the deck's thesis is about identity, the verb should point at identity.

### Thread key words across the argument arc

Identify the 2-3 words that carry the argument (e.g., "lifestyle," "instinct," "identity"). Use them deliberately on the slides where they're load-bearing. The word that names the opportunity should return when you name the moat.

### Name emotions before insights

On problem/insight pairs, the insight side should name the emotional consequence of the problem before delivering the reframe. Structure: emotional consequence → question → insight. "This leaves him feeling unseen & bored. Why? He bets to prove his instinct."

### Problem scope must match solution scope

If the proposition covers four verticals, the problem statement must name or imply all four. Otherwise the solution overshoots what the argument earned.

### Natural connectors, not staccato fragments

Use "and," "but," "because" to make ideas flow as conversation. Three short fragments in a row ("Live products. Partnership signed. Users exist.") sound like AI. One sentence with conjunctions sounds human.

### Stats tell human stories

User counts and behavioral ratios belong in headlines and body. Revenue and volume figures belong in source lines. The room cares about "300K showed up, 5K stayed" — not "$21B in prediction volume."

---

## Copy Formatting Rules

1. **Sentence case for all copy.** No ALL CAPS headlines, no Title Case body text. Normal sentence case throughout.
2. **Structural labels use the label conventions above.** Italic serif is the design choice; in markdown output, indicate labels with the format: `*The Challenge*` or `[eyebrow: The Challenge]`.
3. **Headlines are short declarative sentences.** One idea per headline. If you need a comma, you probably need two slides.
4. **Body copy is 1-3 sentences max.** If a section needs more, it's doing two jobs. Split it.
5. **Accent words get called out.** In Julian's decks, 1-2 words per slide are highlighted in a brand accent color. In slide-ready output, indicate these with bold: **word**.
6. **No em dashes.** Use commas, periods, colons, or parentheses.
7. **Contractions always.** "Don't" not "do not." "Can't" not "cannot."
8. **Numbers as digits.** "67%" not "sixty-seven percent."

---

## Layout Annotations

When producing slide-ready copy, annotate each slide with a suggested layout type. These are directional cues, not rigid prescriptions.

### Layout Types

| Layout | Description | Best for |
|--------|-------------|----------|
| `[layout: full-bleed statement]` | Single headline centered on a full-color or image background | Key insights, provocations, coined concepts |
| `[layout: split-two]` | Two columns, usually Challenge/Ambition or Brand DNA/Cultural Truth | Paired tensions, before/after |
| `[layout: split-three]` | Three columns with equal weight | Framework pillars, phase breakdowns |
| `[layout: statement + evidence]` | Large headline left, supporting content right (quote, data, image reference) | Insights backed by cultural proof |
| `[layout: section break]` | Bold type on a colored background, minimal content | Case study openers, phase transitions |
| `[layout: comparison table]` | Before/After or Old/New rows | System demonstrations, proof points |
| `[layout: data callouts]` | Large numbers with short descriptors | Summary metrics, impact proof |
| `[layout: concept map]` | Central concept with radiating dimensions | Multi-faceted ideas (Romance as Muse/Mindset/Experience/Belief) |
| `[layout: positioning map]` | 2x2 or spectrum with competitors plotted | Competitive white space, positioning |
| `[layout: bridge diagram]` | From/To with a visual bridge between current and future state | Transformation narratives |
| `[layout: image grid + copy]` | Copy on one side, curated image grid on the other | Mood, cultural references, audience visualization |

### Layout Rules

1. **Never repeat the same layout back-to-back.** Rhythm comes from variety.
2. **Full-bleed statements need to be earned.** Only use for insights or concepts that carry the weight of everything before them.
3. **Section breaks should feel like a gear shift.** New energy, new visual treatment, signaling a change in the argument.
4. **Comparison tables work best after a demonstration.** Show the use case first, then show what changed.

---

## Slide Count Guidelines

| Brief type | Typical range | Notes |
|------------|---------------|-------|
| Brand positioning | 20-35 slides | Heavier on cultural context and insight |
| GTM / business strategy | 25-40 slides | Includes use cases and proof |
| Pitch / proposal | 30-45 slides | Full argument + team + investment |
| Marketing strategy | 15-25 slides | Focused on activation |
| Innovation | 20-30 slides | Heavier on cultural shifts and opportunity |

These are ranges, not rules. A 12-slide deck that lands is better than a 40-slide deck that wanders.
