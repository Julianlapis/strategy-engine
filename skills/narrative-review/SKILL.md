---
name: narrative-review
description: |
  Score a strategic narrative against the brief, distilled insights, and Julian's quality bar.
  Catches drift, missing requirements, unsupported claims, and weak story structure before
  the narrative goes to stakeholders.
  Use for "review the narrative," "is this ready for my boss," "check this against the brief,"
  or before any stakeholder socialization.
---

<required_reading>
Read before doing ANY work:
1. `feedback-log.md` — Binding corrections from Julian
2. `rules/voice.md` — Voice rules are enforced line-by-line
3. `rules/quality-gates.md` — Quality gates apply
4. `references/narrative-engines.md` — Know the narrative structures
5. `references/anti-patterns.md` — Know the failure modes
6. `references/pitch-deck-pattern.md` — C&T pitch deck structure (Acts 1-4, canonical from Bumble/Anthropic/Xbox)
</required_reading>

# /strategy:narrative-review

Quality gate for strategic narratives before they go to stakeholders. Scores on 7 dimensions, flags critical issues, and protects what's working.

## When to Use

- Before Julian socializes a strategic narrative with his boss or CEO
- After `/strategy:narrative` produces output and Julian has iterated on it
- Before building a deck from a narrative (catches problems cheaper in prose than in slides)
- When Julian asks "is this ready?"

## Process

### Step 1: Load Context

Read in this order:
1. The original brief (the north star)
2. The distilled strategic platform (insights, tensions, way in)
3. The narrative format reference (Julian's quality bar, e.g., Bumble case study)
4. The narrative being reviewed

### Step 2: Spawn the Narrative Reviewer Agent

Use the `strategy-engine:review:narrative-reviewer` agent. The agent scores on 7 dimensions and returns a structured review.

### Step 3: Synthesize

If the agent returns PASS (50+/70): present the review to Julian with a recommendation to proceed.
If REVISE (35-49): present critical issues and suggest specific fixes before resending.
If FAIL (<35): flag that the narrative needs significant rework. Identify the weakest dimensions.

### Step 4: Voice Check (Mandatory, Separate Pass)

Run the full narrative through Voice DNA + Stop-Slop rules independently. This is a line-by-line scan, not a vibe check. Any banned phrase is flagged with exact location.

### Step 5: Brief Alignment Check (Mandatory, Separate Pass)

Walk through the brief section by section and check:
- Does the narrative address this requirement?
- If yes, where? (cite the slide/section)
- If no, flag it as missing.

Output a brief alignment matrix:

```markdown
| Brief Section | Addressed? | Where in Narrative | Notes |
|---------------|------------|-------------------|-------|
| Brand positioning | Yes/No | Slide X | |
| Visual identity direction | Yes/No | Slide X | |
| Brand architecture | Yes/No | Slide X | |
| ...etc | | | |
```

### Step 6: Present Review

Give Julian:
1. The 7-dimension score table
2. Critical issues (must fix)
3. Brief alignment matrix
4. Voice check results
5. What's working (don't touch)

Julian decides what to fix and what to override.

## Integration

### narrative-review → narrative (revision)
After Julian addresses the critical issues, re-run the review to verify fixes landed.

### narrative-review → courtroom (optional)
If the Insight Quality or Strategic Courage scores are low, suggest running the narrative's core argument through `/strategy:courtroom` before revising.

### narrative-review → paper-slides (gate)
The narrative should PASS review before going into slide production. Building slides from a weak narrative wastes time.

## Observation

Log the run per `rules/observation.md`. Track: total score, which dimensions were weakest, how many critical issues, whether Julian agreed with the findings.
