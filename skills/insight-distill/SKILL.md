---
name: insight-distill
description: |
  Distill raw research into strategic building blocks: insights, tensions, audience truths,
  hypotheses, and white space. Bridges Phase 1 (Interrogating) and Phase 2 (Distilling).
  Use for "what does the research tell us," "find the way in," "distill the research,"
  or when transitioning from research to strategy.
---

<required_reading>
Read before doing ANY work:
1. `feedback-log.md` — Binding corrections from Julian
2. `rules/voice.md` — Voice rules apply to all output
3. `rules/quality-gates.md` — Quality gates apply
4. `references/research-deck-pattern.md` — Xbox Game Pass tissue deck benchmark. The gold standard for how research becomes slides: Misperception → Reality pattern, section truths, real human voices as proof.
</required_reading>

# /strategy:insight-distill

Takes raw research dossiers and extracts the strategic building blocks a strategist needs to crack the positioning. This is the bridge between casting wide (Phase 1) and finding the way in (Phase 2).

## What It Accepts

- Research dossier files (competitive landscape, category dynamics, audience/culture)
- The original brief (always loaded as the north star)
- Any additional context or hypotheses from Julian

## Philosophy

1. **Elevation over repetition.** If your "insight" restates a research finding with a different header, you've failed. Push until you find what the finding *means* for the strategy.
2. **Surprise over confirmation.** "The market is growing" confirms what the client already knows. "The market is growing but 61% of the target audience sees the product as gambling" changes the strategic problem.
3. **Tension over summary.** The most useful output is a tension that forces a choice. Strategy lives in choices.
4. **Julian's claim leads.** If Julian has hypotheses or instincts, those are the starting point. Research supports or challenges them, it doesn't replace them.

## Process

### Step 1: Load the Brief

Read the original brief. Restate the core challenge in one sentence. This sentence is the filter for everything that follows: does this insight change how you'd approach that challenge?

### Step 2: Read All Research

Read every research dossier file. Note:
- Findings with composite scores above 8 (high confidence)
- Contradictions between researchers
- Gaps where no evidence was found
- Cultural signals with real human voices

### Step 3: Spawn the Research Distiller Agent

Use the `strategy-engine:distill:research-distiller` agent to process the research and produce the distillation document. The agent's output format is defined in its agent file.

### Step 4: Quality Check

Before presenting to Julian, check the distillation:

| Check | Pass/Fail |
|-------|-----------|
| Every insight cites specific research findings | |
| No insight could be claimed by every competitor | |
| Tensions force genuine tradeoffs, not false choices | |
| Audience truths use real voices where available | |
| Hypotheses are testable, not vague | |
| White space map identifies specific gaps, not generic opportunity | |
| Voice DNA compliance (no banned phrases, no AI slop) | |

### Step 5: Present to Julian

Present the distillation as a working document. Julian decides:
- Which insights resonate with his strategic intuition
- Which tensions to lean into
- Which hypotheses to develop
- What additional research is needed
- What his own hypotheses are (these lead, the distillation supports)

### Step 6: Iterate

Julian will push back, redirect, or build on the distillation. This is Phase 2 work: Julian leads, Claude supports. The distillation is a starting point for conversation, not a finished strategic platform.

### Step 7: Lock the Strategic Platform

When Julian says "I have the way in," capture the locked platform:

```markdown
# Strategic Platform: [Project Name]

## The Core Insight
[One sentence. The truth that changes everything.]

## The Tension
[What two forces are pulling against each other?]

## The Audience Truth
[What does the target audience believe/feel that creates the opening?]

## The Strategic Bet
[What is the brand choosing to believe? What does it exclude?]

## The Way In
[How does this become a story? What's the narrative entry point?]
```

This document becomes the input for Phase 3 (Articulating / Narrative).

## Integration

### insight-distill → narrative
The locked strategic platform feeds directly into `/strategy:narrative` as the brief input.

### insight-distill → courtroom
Before locking, Julian can run the strategic platform through `/strategy:courtroom` to pressure-test it from 10 angles.

### insight-distill → research (backfill)
If gaps are identified, spawn targeted `/strategy:research` queries to fill them.

## Observation

Log the run per `rules/observation.md`. Track: number of insights surfaced, which Julian kept, which he rejected, what his own hypotheses were, and how the final platform differs from the initial distillation.
