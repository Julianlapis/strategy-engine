---
name: product
description: |
  Product vision briefs, product specs, and component maps.
  The brief is the core document in the pipeline. Everything downstream flows from it.
  Three modes: vision (the brief), spec (capabilities + requirements), map (component structure).
  Use for "product brief," "product spec," "product vision," "product strategy," "component map."
---

<required_reading>
Read `~/.claude/feedback/pre-flight.md` before any work.
Read before doing ANY work:
1. `feedback-log.md` — Binding corrections from Julian. Override everything.
2. `references/sacred-six.md` — Universal brief framework. Sacred Six sections, per-section rubrics, quality gate process. ALL briefs follow this structure.
3. `~/.claude/feedback/strategy/sharpness-rubric.md` — Sharpness scoring. Run BEFORE presenting.
4. `rules/voice.md` — Voice DNA + Stop-Slop enforcement.
5. `rules/quality-gates.md` — Scoring, anti-patterns, mandatory checks.
6. `rules/process.md` — Phase sequencing, approval gates.
7. `~/.claude/voice-dna.md` — Full voice identity (Layer 1).
8. `~/.claude/copy-polish.md` — Client polish (Layer 2, applied to all product output).
</required_reading>

# /strategy:product

Product strategy documents. Three modes, one skill. Each mode produces a different
artifact in the pipeline, but they share the same brain: user problems, capabilities,
positioning against alternatives, success metrics, explicit exclusions.

## The Pipeline Context

This skill produces the core artifacts in a 7-step pipeline:

```
1. INTAKE    → 2. RESEARCH    → 3. DISTILL    → 4. BRIEF    → 5. SPEC    → 6. MAP    → 7. BUILD
                                                    ↑              ↑            ↑
                                                 vision          spec          map
                                                  mode           mode         mode
```

**Vision mode** (Step 4) produces THE BRIEF. The core document. 2-4 pages at every size.
It does not scale with project size. The research scales. The brief stays tight.

**Spec mode** (Step 5) extends the brief into buildable capabilities and requirements.

**Map mode** (Step 6) translates the spec into component cards, zone maps, and user flows
that human designers and developers work from.

Each mode expects the previous artifact to exist. Vision mode takes distilled insights
as input. Spec mode takes the brief. Map mode takes the spec.

---

## Mode 1: Vision (The Brief)

The brief is the load-bearing document. When the client pushes back, when the team gets
overwhelmed, when features change, when six months pass and nobody remembers the kickoff:
the brief is what survives.

### The Rallying Cry

Every brief has a core statement at its center. 2-5 words. The thing the entire strategy
collapses to when someone asks "what are we doing?" in a hallway.

**Requirements:**
- Fits on a sticky note (2-5 words)
- Makes a choice a competitor wouldn't make
- Names what you're giving up (the sacrifice must be visible)
- A designer can gut-check a layout against it
- A developer can resolve an edge case against it
- Someone who wasn't in the room can repeat it after hearing it once

**Calibration:**
- "More gaming" (GamePass) — chose breadth over depth. Sacrifice: not chasing prestige or exclusivity.
- "Watch, don't browse" — chose content surfacing over catalog. Sacrifice: not building the best library organization.
- "Faster for everyone" — FAILS. Names a benefit, not a sacrifice. Any company in any category could claim this.
- Good rallying cries make a trade-off visible. If it could describe any product in the category, it fails.

**Process:** Propose 2-3 candidate rallying cries during the Structure phase. Julian picks.
Each candidate should name the choice it makes and what it leaves behind.

### Brief Structure

The brief follows this exact structure. Do not add sections. Do not reorder.
Sections can be compressed (fewer sentences) but not removed.

```markdown
# [Project Name]

## The Rallying Cry
[2-5 words. The core statement. Bold it.]

## The Problem
[Who has this problem? What's broken? Be specific. Use data from the research.
Not "users struggle with X." Name the user. Name the struggle. Name the cost.
1-2 paragraphs. Every sentence carries data or a named example.]

## The Audience
[Behavior-based, not demographic. What they do, not who they are.
"25% of men under 30 already bet online" not "males 18-34."
What they believe. What they're willing to pay for. What they reject.
1-2 paragraphs.]

## The Proposition
[What we're building and why it wins. Three sentences max.
Sentence 1: What it is.
Sentence 2: Why it's different.
Sentence 3: Why now.]

## Success
[3-5 measurable outcomes. Numbers, not vibes.
Each metric has a timeframe and a target.
"1,000 active users within 90 days" not "strong user adoption."]

## Constraints
[What we're working within. Budget, timeline, tech, legal, org politics,
content availability, team size. Bullet list. Each constraint is one line.]

## What We're NOT Doing
[The most important section after the rallying cry. Explicit exclusions.
Things the client might expect. Things the team might assume.
Things that feel obvious but are out of scope. Name them. Kill them here.
This section saves more time than any other section in the document.]

## Decision Log
[Starts empty. Updated when the first major decision deviates from this brief.
Format: "YYYY-MM-DD: [What changed] — [Why] — [What section this affects]"
This section turns the brief from a sacred document into scaffolding.
When this section has 3+ entries, the brief needs a revision pass.]
```

**Handoff contract:** The brief generates a sidecar file at `docs/strategy/04-brief-handoff.yaml`
that Arc:vision reads to produce `docs/vision.md`. This file is NOT embedded in the brief
(it breaks when copy-pasted into decks or Notion). The skill auto-generates it from the
brief content during Phase 3.

Sidecar format (`04-brief-handoff.yaml`):
```yaml
# Auto-generated from 04-brief.md. Do not edit directly.
# Arc:vision reads this to produce docs/vision.md.
purpose: [One sentence. What this product/service does.]
rallying_cry: [The 2-5 word core statement.]
audience: [Who it's for. Behavior-based.]
goals:
  - [Goal 1 (measurable)]
  - [Goal 2 (measurable)]
  - [Goal 3 (measurable)]
success: [How we know it's working. Quantitative.]
non_goals:
  - [Explicit exclusion 1]
  - [Explicit exclusion 2]
principles:
  - [Decision-making heuristic 1]
  - [Decision-making heuristic 2]
```

### Vision Mode Process

```
PHASE 1: INTAKE
  Accept whatever Julian provides (research dossier, distilled insights,
  client brief, verbal description). Read it. Identify:
  - The core problem (who, what's broken, what it costs)
  - The audience (behavior, not demographics)
  - The competitive context (who else, why they fail)
  - Any constraints mentioned

PHASE 1.5: CONTEXT GATE (first run only)
  If this is the first product skill run on this project, fire the Project
  Context Gate (see section above). Capture delivery type, builder, fidelity.
  If context was already captured in a prior mode, confirm it still holds.

PHASE 2: STRUCTURE (PAUSE for Julian's approval)
  Present:
  a) The problem in one sentence
  b) 2-3 candidate rallying cries with the choice each one makes
  c) The proposed proposition in one sentence
  d) The key exclusions (what we're NOT doing)

  DO NOT proceed until Julian approves direction and picks a rallying cry.
  Julian may redirect, combine candidates, or propose his own.

PHASE 3: WRITE
  Write the full brief following the template structure exactly.
  Apply Voice DNA (Layer 1) line by line as you write.
  Apply Copy Polish (Layer 2) since this is client-facing.

PHASE 4: QUALITY GATE (mandatory, internal)
  Run the three-layer scoring rubric (see below).
  All three layers must hit 35/50.
  If any layer fails:
    - Identify the weak dimensions
    - Revise the specific failing sections
    - Re-score
    - Repeat until all layers pass
  DO NOT present to Julian until all layers pass.

PHASE 5: PRESENT
  Present the scored brief to Julian.
  Include the three scores and the rallying cry check (pass/fail).
  Flag any dimension that scored below 8 with a note on what's weak.

PHASE 6: OBSERVATION
  Log to execution-log.md per observation.md rules.
```

### Vision Mode Failure Modes

Product strategy has specific failure patterns. Check for these during Phase 4:

1. **Solution looking for a problem.** The product is described before the pain is felt.
   Fix: spend more time on The Problem section. The reader should feel stuck before
   they see the proposition.

2. **Feature list as strategy.** Capabilities listed without a thesis connecting them.
   Fix: the rallying cry should explain why these capabilities (and not others) exist.

3. **Unmeasurable success.** "Users love it" isn't a metric.
   Fix: name the specific behavior that indicates success. A number, a timeframe.

4. **Everything-for-everyone.** No explicit exclusions.
   Fix: "What We're NOT Doing" must contain at least 3 items that a stakeholder
   might reasonably expect to be in scope. If the exclusions are obvious, they're
   not doing their job.

5. **Rallying cry is a sentence.** If it takes more than 5 words, it's a tagline, not a rallying cry.
   Fix: compress until it hurts. The constraint is generative.

6. **Constraints are generic.** "Limited budget" and "tight timeline" appear on every project.
   Fix: name the specific number, the specific date, the specific limitation.

---

## Mode 2: Spec

The spec extends the brief into buildable capabilities. It takes the brief as input
and produces a numbered capability list with requirements, metrics, and constraints.

### Spec Structure

```markdown
# [Project Name]: Spec
*[Date] — v[X.X]*

## Context
[2-3 sentences. Link to or summarize the brief. State the rallying cry.]

## User
[Who uses this. Behavior-based. What they're trying to do when they reach
for this product. Carried from the brief's audience section, refined.]

## Capabilities
[Numbered list. Each capability described from the user's perspective.
Not features ("AI-powered search") but outcomes ("find the answer in
3 seconds instead of 30 minutes").]

1. **[Capability name]**
   [What the user can do. One paragraph, plain language.]
   - *UX:* [How the user experiences it. Interaction model.]
   - *Success metric:* [How we measure this capability works. Specific number + timeframe.]
   - *Required:* [What must be true for this to work.]
   - *Optional:* [Nice-to-haves that can be cut if needed.]

2. **[Capability name]**
   ...

## Constraints
[Numbered list. Technical, legal, budget, timeline, dependencies.
Each constraint is specific: "$50K budget" not "limited budget."
"Must integrate with Salesforce" not "CRM integration."]

## Out of Scope (This Version)
[Carried from the brief's "What We're NOT Doing" section.
Extended with technical specifics: "No native mobile app in v1.
Web-responsive only." "No real-time collaboration. Single-user editing."]

## Open Questions
[Things that need answers before or during build.
Each question has an owner (who answers it) and a deadline.
Format: "Q: [question] — Owner: [name] — By: [date]"]
```

### Spec Mode Process

```
PHASE 1: INTAKE
  Read the brief (docs/strategy/04-brief.md).
  If the brief doesn't exist, stop. Tell Julian to run vision mode first.
  Extract: rallying cry, proposition, audience, constraints, exclusions.

PHASE 1.5: CONTEXT GATE
  If project context wasn't captured during vision mode, fire the Project
  Context Gate now. If it was, confirm it still holds for spec mode.

PHASE 2: STRUCTURE (PAUSE for Julian's approval)
  Present:
  a) Proposed capability list (names and one-line descriptions)
  b) How capabilities map to the rallying cry (each one should serve it)
  c) Any capabilities Julian might expect that you're excluding and why

  DO NOT proceed until Julian approves the capability list.

PHASE 3: WRITE
  Write the full spec. Apply Voice DNA (Layer 1). Apply Copy Polish (Layer 2).
  Every capability must trace back to the brief's proposition.
  Every success metric must be measurable with a number and timeframe.

PHASE 4: QUALITY GATE
  Run the spec-specific checks:
  - Every capability has a success metric with a number and timeframe
  - Every constraint is specific (named system, dollar amount, date)
  - Out of Scope carries everything from the brief + adds technical specifics
  - Open questions have owners and deadlines
  - No capability exists that the rallying cry can't justify
  Voice score must hit 35/50. Polish score must hit 35/50.

PHASE 5: PRESENT + OBSERVATION

PHASE 6: OFFER .SPECS/ GENERATION (optional)
  After the spec is approved, offer to generate the .specs/ directory:
  "The spec is locked. Want me to generate agent-structured specs in .specs/?
  This creates per-capability folders with acceptance criteria that agents can
  work from independently."
  If yes: read references/specs-format.md for the format contract.
  Generate manifest.yaml + one folder per capability.
  If no: skip. The spec alone is sufficient for human teams.
```

### Spec Failure Modes

1. **Capability without a metric.** If you can't measure it, you can't tell if it works.
2. **Metric without a number.** "Improved load time" isn't a metric. "Page loads in under 2 seconds" is.
3. **Orphan capability.** A capability that doesn't serve the rallying cry. Cut it or change the rallying cry.
4. **Constraint without specificity.** "Must be accessible" → "Must meet WCAG 2.1 AA. Screen reader tested with VoiceOver and NVDA."
5. **Open question without an owner.** Unanswered questions without owners stay unanswered.

---

## Mode 3: Map

The map translates the spec into the artifact human designers and developers work from.
Component cards, zone maps, user flows. The Cenex pattern.

**At Small size (Julian + 1 designer, shared repo):** Map mode is optional. If the designer
is working directly from the spec in the same repo, the map adds ceremony without value.
Skip it and let the designer work from the brief + spec. Use map mode when there's enough
team size or trust distance that people need a reference document to work from independently.

### Map Structure: Dual-Audience Files

Each map file uses YAML frontmatter (agent-parseable) + markdown body (human-readable).
One file, two audiences. No synchronization problem.

The map produces files in `docs/map/`:

**components.md** — One card per component:
```markdown
### [Component Name]

<!-- YAML block: agents parse this, humans read the markdown below -->
```yaml
id: [component-id]
category: [Global | Headers & Heroes | Pathing | Cards | Education]
capability: [which spec capability this serves]
pages: [list of pages/templates]
required: [list of required elements]
optional: [list of optional elements]
variations: [list of named variations]
sprint: [which sprint, if phased]
```

**What it is**
[1-2 sentences. Plain language description.]

**Where it lives**
[Which pages/templates this component appears on.]

**Requirements**
- REQUIRED: [bullet list of required elements]
- OPTIONAL: [bullet list of optional elements]
- VARIATIONS: [named variations, or N/A]

**Open questions**
[Specific questions for the client or team. Each tagged with who needs to answer.]

**Decisions**
[Resolved questions. Format: "YYYY-MM-DD: [Decision] — [Rationale]"]
```

**zones.md** — Page-level zone maps:
```markdown
### [Page/Template Name]

```yaml
template: [template name]
instances: [list of page instances that use this template]
```

| Zone | Name | Type | Components | Flexibility |
|------|------|------|------------|-------------|
| 1 | [zone name] | Fixed / Flexible / Optional | [which components] | [rules] |
| 2 | ... | ... | ... | ... |

**Fixed** = Required zone, required component, fixed placement.
**Flexible** = Required zone, flexible in component selection, quantity, and placement.
**Optional** = Not required. If used, follows its own fixed/flexible rules.

**Templates vs. Page Instances:** A template is the reusable page structure (e.g., Product
Landing Page). A page instance uses that template with specific content (e.g., Lubricants,
Fuels, Propane). The zone map defines the template. The instance specifies which components
fill the flexible zones.
```

**flows.md** — User task flows (not sitemaps):
```markdown
### [Flow Name]: [User Goal]

```yaml
entry: [starting page/state]
success: [completion criteria]
steps: [number of steps]
decision_points: [number of branches]
```

**Entry point:** [Where the user starts]
**Success:** [What "done" looks like]

1. [User action] → [System response] → [Next screen/state]
2. [Decision point]: If [A] → [path A]. If [B] → [path B].
3. ...

**Edge cases:**
- [What happens if X fails]
- [What happens if user abandons at step N]
```

**open-questions.md** — Consolidated assumptions log + decision record:
```markdown
## Open

| # | Question | Section | Owner | Date Added |
|---|----------|---------|-------|------------|
| 1 | [question] | [which component/zone/flow] | [who answers] | [date] |

## Resolved

| # | Question | Decision | Decided By | Date |
|---|----------|----------|-----------|------|
| 1 | [question] | [what we decided] | [who] | [date] |
```

### Map Mode Process

```
PHASE 1: INTAKE
  Read the spec (docs/strategy/05-spec.md).
  If the spec doesn't exist, stop. Tell Julian to run spec mode first.
  Extract: capabilities, requirements, constraints, open questions.

PHASE 1.5: CONTEXT GATE
  If project context wasn't captured during spec mode, fire the Project
  Context Gate now. If it was, confirm it still holds for map mode.
  Map mode is the most affected by delivery context: a pitch map looks
  very different from a production map.

PHASE 2: STRUCTURE (PAUSE for Julian's approval)
  Present:
  a) Proposed component list derived from capabilities
  b) Proposed page/template list
  c) Proposed zone model for the primary page (homepage or equivalent)
  d) Which capabilities map to which components
  e) If delivery_type is "pitch": proposed tier assignments per component

  DO NOT proceed until Julian approves the structure.

PHASE 3: WRITE
  Write all four map files. Apply Voice DNA (Layer 1) to descriptions.
  Every component must trace to a capability in the spec.
  Every zone must have a flexibility classification.
  Every flow must have a success condition and edge cases.

PHASE 4: QUALITY GATE
  - Every capability from the spec has at least one component
  - Every component has Required/Optional/Variations defined
  - Every page has a zone map with flexibility rules
  - Primary user flows are documented with decision points
  - Open questions are consolidated with owners
  Voice score on descriptions must hit 35/50.

PHASE 5: PRESENT + OBSERVATION
```

### Map Failure Modes

1. **Orphan component.** A component that doesn't trace to a spec capability. Cut it.
2. **Missing zone flexibility.** Every zone needs Fixed/Flexible/Optional. No "TBD."
3. **Flow without edge cases.** Happy path only is a wireframe, not a flow.
4. **Open questions without owners.** Same rule as spec mode.

---

## The Three-Layer Scoring Rubric (Vision Mode)

The brief is scored on three layers. All must pass before presenting to Julian.
Layers 1 and 2 also apply to spec and map modes (Layer 3 is brief-only).

### Layer 1: Strategic Integrity (/50)

| Dimension | 10 | 7 | 4 | 1 |
|---|---|---|---|---|
| **Rallying Cry** | Memorable, makes a choice, competitor can't claim it. You'd put it on a wall. | Clear and directional but could be sharper. | Generic. Any company in the category could use it. | Missing, or a full sentence disguised as a rallying cry. |
| **Problem Specificity** | Named user, named behavior, named cost. Data from research. You feel the pain. | Real problem but could be more concrete. | Described at category level. "Users want better X." | Vague or missing. |
| **Proposition Clarity** | One paragraph, three sentences or fewer. Smart outsider gets it on first read. | Clear but takes two reads, or clear but not differentiated. | Requires context from the research to understand. | Jargon-laden, circular, or tries to be everything. |
| **Exclusions Quality** | Names things the client expects but we're cutting. Each exclusion saves real scope. Controversial ones included. | Has exclusions but they're safe picks. | Generic ("out of scope: things not in scope"). | Missing or pro-forma. |
| **Durability** | Hand this to a new team member in six months and they know exactly what to build. | Mostly durable but some sections assume kickoff context. | Needs a walkthrough to understand. | Time-bound. Won't make sense in a month. |

**Threshold: 35/50.**

**HARD STOP: Rallying Cry below 7/10 = Layer 1 fails regardless of other scores.**
A competent, specific, well-voiced brief about a generic strategy still fails.
The rallying cry is the decision. Without it, the rest is decoration.

**Calibration:**
- "No one combines all four verticals. Betr tried. It's struggling." = 10/10 Problem Specificity.
- "We need to create a best-in-class digital experience" = 1/10 Proposition Clarity.
- GamePass "More gaming" = 10/10 Rallying Cry. Names the sacrifice (not chasing prestige).
- "Better banking" = 4/10 Rallying Cry. Passes word count but names no sacrifice. Generic.

### Layer 2: Voice Quality (/50)

Apply voice-dna.md scoring. Five dimensions, 1-10 each:

| Dimension | Question |
|---|---|
| Directness | Statements or announcements? |
| Rhythm | Varied or metronomic? |
| Trust | Respects reader intelligence? |
| Authenticity | Sounds human? |
| Density | Anything cuttable? |

**Threshold: 35/50.**

Run the full quick checks from voice-dna.md before scoring:
- Any adverbs? Kill them.
- Any passive voice? Find the actor.
- Any throat-clearing? Cut to point.
- Any em dashes? Remove.
- Any vague declaratives? Name the specific thing.
- Any inanimate object doing a human verb? Name the person.

### Layer 3: Polish (/50) — All product output

Apply copy-polish.md scoring. Five dimensions, 1-10 each:

| Dimension | Question |
|---|---|
| Accessibility | Could a smart non-expert follow this? |
| Jargon | Any undefined terms surviving? |
| Sentence load | Any sentence carrying more than one idea? |
| Evidence | Every claim backed by a specific number, name, or example? |
| Order | Information arranged for the reader's logic, not the writer's? |

**Threshold: 35/50.**

### Score Card

```
BRIEF QUALITY GATE
──────────────────────────────────────────────────
Layer 1: Strategic Integrity           ___/50
Layer 2: Voice Quality                 ___/50
Layer 3: Polish                        ___/50
──────────────────────────────────────────────────
All layers must hit 35/50 to present.

RALLYING CRY CHECK (pass/fail):
[ ] 2-5 words
[ ] Makes a choice a competitor wouldn't make
[ ] Names what you're giving up (sacrifice visible)
[ ] Designer can gut-check a layout against it
[ ] Developer can resolve an edge case against it
[ ] Repeatable from memory after hearing it once
```

### What Happens When a Layer Fails

If any layer scores below 35/50:

1. Identify the dimensions scoring below 7.
2. Revise ONLY the failing sections. Don't rewrite what works.
3. Re-score the revised sections.
4. If the layer still fails after two revision passes, flag it to Julian:
   "Layer [X] is scoring [Y/50]. The weak dimensions are [Z]. I've revised twice.
   Want me to continue revising or present as-is with the flags?"
5. Julian decides. The engine doesn't present below-threshold work silently.

---

## Product-Specific Anti-Patterns

These are hard failures specific to product mode. They stack on top of the
universal anti-patterns in quality-gates.md.

1. **Solution looking for a problem.** Product described before pain is felt.
2. **Feature list as strategy.** Capabilities without a thesis connecting them.
3. **Unmeasurable success.** "Users love it" isn't a metric. Name the number.
4. **Everything-for-everyone.** No explicit exclusions means no choices.
5. **Rallying cry is a sentence.** More than 5 words = tagline, not rallying cry.
6. **Constraints are generic.** "Limited budget" appears on every project. Name the number.
7. **Consultant-speak proposition.** "Best-in-class digital experience" says nothing. Name the specific thing this product does that no competitor does.
8. **Demographic audience.** "Males 18-34" is a media buy, not an audience. Name the behavior.

---

## T-Shirt Size Behavior

The skill adjusts depth based on project size, but the brief structure stays fixed.

### Vision Mode (The Brief)

| | Small | Medium | Large |
|---|---|---|---|
| **Brief length** | 2-3 pages | 2-4 pages | 2-4 pages |
| **Rallying cry candidates** | 2 | 2-3 | 3 |
| **Problem section** | 1 paragraph with data | 1-2 paragraphs | 1-2 paragraphs |
| **Exclusions** | 3+ items | 5+ items | 5+ items, including politically sensitive ones |
| **Quality layers** | Layer 1 + 2 | Layer 1 + 2 + peer review | Layer 1 + 2 + 3 + narrative-review |
| **Copy Polish** | Applied | Applied | Applied + narrative-review scores it |

**THE BRIEF DOES NOT GET LONGER AT LARGE. The research gets deeper. The brief stays tight.**

### Spec Mode

| | Small | Medium | Large |
|---|---|---|---|
| **Capabilities** | 3-8 | 5-15 | 10-30 |
| **Constraint specificity** | Named systems, dates | + legal, content reqs | + integration deps, data reqs |
| **Open questions** | 3-5 | 5-15 | 10-30, all with owners and deadlines |

### Map Mode

| | Small | Medium | Large |
|---|---|---|---|
| **Components** | 5-15 | 15-30 | 30-60 |
| **Zone maps** | Primary page only | 3-5 key pages | Every template |
| **User flows** | 1-2 primary flows | 3-5 flows | All critical flows + edge cases |
| **Sprint phasing** | Not needed | Optional | Required (which components in which sprint) |

---

## Project Context Gate (Mandatory, All Modes)

Between INTAKE and STRUCTURE in every mode, pause to capture the project's delivery
context. This gate exists because the same pipeline produces pitch prototypes, MVP specs,
and full production maps. The depth, tiering, and artifact shape change based on what's
being built and who's building from it.

**When to fire:** First time the product skill runs on a project. The answers persist
for subsequent modes in the same project (spec inherits the brief's context, map inherits
the spec's context). If context was captured in an earlier mode, confirm it still holds
and move on.

**Questions (ask via AskUserQuestion, not chat):**

```
PROJECT CONTEXT GATE
─────────────────────────────────────────────────────
1. DELIVERY TYPE: What's the final output?
   [ ] Pitch / demo prototype (limited screens, sell the vision)
   [ ] MVP / v1 (shippable product, scoped tight)
   [ ] Full product (complete system, production-ready)

2. BUILDER: Who builds from this document?
   [ ] Solo (Julian + Arc agents)
   [ ] Designer + Julian (small team, shared repo)
   [ ] Full team (agency or multi-discipline)

3. FIDELITY: What level of design is needed?
   [ ] Screen-level (key screens designed, rest described)
   [ ] Flow-level (full user journeys designed end-to-end)
   [ ] System-level (design system, every template, every state)

4. ANYTHING UNUSUAL? (free text, optional)
   Timeline pressure, regulatory constraints, team context,
   client expectations that would change how you scope this.
─────────────────────────────────────────────────────
```

**How answers shape output:**

| Answer | Effect on spec | Effect on map |
|--------|---------------|---------------|
| **Pitch** | Capabilities stay full (the vision matters). Success metrics can reference industry benchmarks rather than commitments. | Components get tiered (demo/conceptual/reference). Flows get tiered (demo 2, describe rest). Edge cases parked. Shot list added. |
| **MVP** | Capabilities scoped to v1 only. "Optional" fields are explicit cut candidates. | Components are all buildable. No conceptual tier. Flows have edge cases. |
| **Full product** | Full capability matrix. Integration requirements. Data model. | Full Cenex-style map. Every template, every zone, every flow. Sprint phasing required. |
| **Solo builder** | .specs/ generation offered. Agent-structured YAML matters. | YAML frontmatter is load-bearing (agents consume it). |
| **Designer + Julian** | Human-readable descriptions matter most. | Zone maps and component cards are the primary artifacts. |
| **Full team** | Both human and agent readability. | Dual-audience format (YAML + markdown). |
| **Screen-level** | N/A | Tier system required. Shot list required. |
| **Flow-level** | N/A | All primary flows designed, edge cases included. |
| **System-level** | N/A | Design system tokens, every state, every variation documented. |

**Persistence:** Store context answers in the spec or map file's YAML frontmatter
so downstream modes and future sessions can read them:

```yaml
# Project context (captured at spec phase, confirmed at map phase)
delivery_type: pitch
builder: designer-and-julian
fidelity: screen-level
notes: "Pitch to win Punt as client. Deck to client April 9. Limited prototype for demo."
```

**If context wasn't captured and you're already in STRUCTURE:** Stop. Ask. The 30 seconds
this takes saves hours of over-building or under-building.
