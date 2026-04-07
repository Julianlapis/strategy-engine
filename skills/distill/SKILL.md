---
name: distill
description: |
  Compress strategic copy without losing meaning or story. Cuts word count, merges slides,
  tightens sentences. Use 4 words where the draft used 8. Proposes a plan before cutting.
  Use for "tighten this," "make it shorter," "can we cut slides," or before building in Paper.
---

<required_reading>
Read before doing ANY work:
1. `feedback-log.md` — Binding corrections
2. `rules/voice.md` — Voice rules guide what "tight" sounds like
3. `references/slide-conventions.md` — Understand slide types so you know what can merge
</required_reading>

# /strategy:distill

Takes a deck narrative, strategy doc, or any prose deliverable and compresses it. Preserves every piece of meaning and the full narrative arc. Cuts the container, not the content.

## What It Accepts

- Deck narratives (slide-by-slide copy)
- Strategy documents
- Brief copy
- Any prose that's too long for what it's doing

## The Rule

**Cut the words. Keep the meaning. Preserve the story.**

If a sentence can lose 3 words and say the same thing, lose them. If two slides share a beat, merge them. If a paragraph restates something the headline already said, kill the paragraph.

Never cut:
- A distinct idea or argument
- Evidence that supports a claim
- Specificity (names, numbers, examples)
- Narrative transitions that hold the arc together
- Voice texture (the copy should still sound like Julian, not a summary)

Always cut:
- Redundancy between headline and body
- Setup sentences that delay the point
- Connector phrases ("What's changed since then is...")
- Adjective pileups
- Body copy that explains what the headline already said clearly
- Slides that exist for a single sentence that could live elsewhere

## How It Works

### Step 1: Read the Full Piece

Read everything. Map the narrative arc. Identify every distinct idea. Count slides (if deck).

### Step 2: Propose a Plan (MANDATORY)

Before making any changes, present Julian with:

1. **Current state:** Slide/section count, approximate word count
2. **Target:** What you think the compressed version looks like
3. **Merges:** Which slides/sections combine, and what the merged version covers
4. **Kills:** Anything that can be fully removed (rare, must justify)
5. **Tightening:** Specific examples of copy that gets shorter

Wait for approval before cutting.

### Step 3: Compress

Work slide by slide (or section by section):

**For each slide/section, apply in order:**
1. Does the headline say it? Cut body copy that restates it.
2. Can two short sentences become one? Merge them.
3. Are there filler phrases? ("Based on what we've heard," "What's changed since then is") Strip to the point.
4. Can a 12-word bullet become a 6-word bullet without losing specificity? Do it.
5. Is there a setup sentence before the real sentence? Kill the setup.

**For merging slides:**
1. Do two slides share a narrative beat? (e.g., "the loop" and "the longer view" are both about the system getting smarter)
2. Can the merged slide hold both ideas without feeling cramped? Use a divider line, two sections, or top/bottom layout.
3. Does the merge break the rhythm? (Don't merge a red bg slide with a white bg slide unless there's a good reason)

### Step 4: Present the Compressed Version

Output the full tightened copy. For decks, include slide numbers, tags, headlines, body, and layout notes, same format as the input.

At the bottom, include:

```markdown
## Distill Summary

**Before:** [X] slides, ~[X] words
**After:** [X] slides, ~[X] words
**Reduction:** [X]% fewer words, [X] fewer slides

### What Changed
- [Slide X + Y merged] — [why]
- [Slide Z body tightened] — [what was cut]
- [Copy example: "before" → "after"]
```

### Step 5: Quality Gate

Run Voice DNA + Stop-Slop on the compressed output. Compression sometimes introduces passive voice or strips the texture out of copy. Check that the tightened version still sounds like Julian, not a telegram.

### Step 6: Observation

Log the run per `rules/observation.md`. Track input size, output size, what was merged, and whether Julian accepted the cuts.

## What Good Distillation Looks Like

**Before:** "Based on what we've heard from the field, advisors spend the majority of their working hours preparing for meetings: pulling collateral, rehearsing positioning, matching prospects to the right approach."

**After:** "Advisors spend most of their working hours pulling collateral, rehearsing positioning, matching prospects to the right approach."

(Cut 11 words. Same meaning. The "based on what we've heard" was a credibility hedge that weakened the statement.)

**Before:** "Same persona, same trigger, different messaging depending on the advisor's style, the geography, and the situation."

**After:** "Same persona, same trigger, different messaging based on advisor style, geography, and situation."

(Cut 4 words. Removed unnecessary articles.)

## Failure Modes

- **Over-compression:** Copy reads like bullet points, not prose. Lost the voice.
- **Meaning drift:** Tightened sentence says something slightly different than the original.
- **Arc damage:** Merged two slides and broke the narrative flow.
- **Specificity loss:** Cut the example that made the claim concrete.

If Julian says "you cut too much" or "this lost the feel," log it in feedback-log.md and recalibrate.

---

## Deck Mode: Cross-Slide Redundancy Detection

Activated when the input is slide-by-slide copy (detected by slide numbering format) or when invoked with `--deck` flag. This mode finds the same idea appearing across multiple slides and proposes consolidation without flattening voice.

### Core Principle

**Keep the sharpest instance. Cut or redirect the others. Never rewrite to "merge."**

This mirrors copy-compression's "select, don't summarize" but applies it across the full deck instead of within a single slide.

### Phase 1: Idea Mapping

Extract every distinct idea from every slide (headline + body). Assign each a short tag. Build a cross-reference table showing where each idea appears:

```
IDEA: "competitors can't show losses"
  - Slide 08 body: "No app on the market tracks that."
  - Slide 12 headline: "...that's why they can't follow us here"
  - Slide 18 subtitle: "Losses carry the same weight."
```

An "idea" is a claim, insight, or argument. Not a word or phrase. Two slides can share the word "instinct" without sharing an idea. Two slides can share an idea ("losses are visible") using different words.

### Phase 2: Score Each Instance

For every idea that appears 2+ times, score each instance on the Distillation Rubric.

#### Distillation Rubric (5 dimensions, 1-10 each)

| Dimension | What it measures | 10 looks like | 1 looks like |
|-----------|-----------------|---------------|--------------|
| **Sharpness** | Most concrete, specific version? | Named numbers, physical verbs, specific example | Vague restatement of the concept |
| **Voice Texture** | Sounds like Julian wrote it? | Contractions, register shifts, specificity as wit | Could be any strategist's writing |
| **Narrative Position** | Earns its place HERE in the arc? | This slide needs this idea to set up the next beat | The idea works but could live anywhere |
| **Load-Bearing** | If cut, does the slide collapse? | The slide's argument depends on it | The slide works fine without it |
| **Freshness** | First time the audience encounters this? | First appearance, full weight | 3rd+ time hearing it, diminished impact |

#### Scoring Rules

- Each instance scored 5-50 (sum of 5 dimensions)
- **Home instance:** highest score across all appearances. Keep.
- **Redundant (35+):** idea appears elsewhere but this version adds a distinct angle. Flag for Julian's judgment.
- **Redundant (below 35):** idea is better served elsewhere. Recommend cut.
- **No home above 40:** flag that the best version of this idea isn't sharp enough. Propose an alternative that preserves voice texture.

### Phase 3: Propose, Don't Execute (MANDATORY)

Present the full redundancy map and proposed cuts. For each flagged instance:

1. Quote the exact text
2. Show all 5 dimension scores
3. Name the "home" slide where this idea lives best
4. Recommendation: KEEP, CUT, or REDIRECT (move a specific phrase to the home slide)
5. If no instance scores above 40: propose an alternative. Julian can accept, reject, or rewrite.

**Never apply changes without Julian's approval.**

### Phase 4: Apply Approved Cuts

After Julian signs off, apply only the approved changes. For each cut:
- Remove the redundant text from the slide
- Verify the slide still reads coherently without it
- If removing creates a gap, flag it rather than filling it

### What Good Deck Distillation Looks Like

```
## Redundancy Map

### IDEA: "losses shown at equal weight" (3 instances)

HOME: Slide 12 body (Score: 44/50)
  Sharpness: 9 | Voice: 8 | Position: 10 | Load-bearing: 9 | Freshness: 8
  "Every competitor's retention model breaks if they show losses at equal weight."

REDUNDANT: Slide 18 subtitle (Score: 31/50)
  Sharpness: 6 | Voice: 7 | Position: 6 | Load-bearing: 5 | Freshness: 3
  "Losses carry the same weight."
  Recommendation: CUT. Slide 12 landed this 6 slides earlier. Here it restates without advancing.

### Summary: 24 unique ideas. 6 repeated. 4 cuts proposed.
```

### Failure Modes (Deck-Specific)

- **Flattening:** Rewrote an instance instead of selecting among existing versions. Lost the original's sharpness.
- **Narrative damage:** Cut an instance that was doing setup work for a later payoff. The payoff now feels unearned.
- **Over-detection:** Flagged two instances as "the same idea" when they were actually distinct arguments sharing a theme.
- **Voice averaging:** Proposed alternative sounds like a summary of all instances instead of the sharpest possible version.

If Julian flags any of these, log in feedback-log.md with the specific instance and what went wrong.
