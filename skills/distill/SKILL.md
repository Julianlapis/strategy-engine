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
