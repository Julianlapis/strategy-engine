---
name: pressure-test
description: |
  Single-agent adversarial critique of any strategic argument. Fast, focused, one perspective.
  Use for "poke holes in this," "what's wrong with this," "play devil's advocate,"
  or quick gut checks before a meeting. Returns a structured critique with specific fixes.
---

<required_reading>
Read `~/.claude/feedback/pre-flight.md` before any work.
Read before doing ANY work:
1. `feedback-log.md` — Binding corrections
2. `rules/voice.md` — Voice rules apply to critique output too
3. `rules/quality-gates.md` — Use the anti-patterns list as a critique lens
</required_reading>

# /strategy:pressure-test

A single sharp critic. Hand it any strategic argument and get back a structured teardown with specific fixes.

## What It Accepts

Anything strategic:
- A positioning statement
- A creative brief
- A product thesis
- A strategy document
- A single paragraph with a strategic claim
- Slide copy
- A concept name and explanation

## How It Works

### Step 1: Read the Input

Understand the argument being made. Identify:
- The core claim or thesis
- The evidence or reasoning supporting it
- The intended audience
- What the argument is trying to persuade someone to do

### Step 2: Attack From 7 Angles

Run through each lens. Skip any that don't apply to the input.

| Lens | Question |
|------|----------|
| **Specificity** | Could a competitor say this? Could you swap the brand name? |
| **Evidence** | What's asserted without proof? Where's the data, the signal, the behavior? |
| **Tension** | Is there a real tension, or does the strategy arrive without earning it? |
| **Audience** | Would the actual target care? Would they recognize themselves? |
| **Feasibility** | Can the org actually do this? What kills it in execution? |
| **Competition** | Has someone already claimed this territory? What's the counter-move? |
| **Logic** | Does the argument hold? Could different evidence lead to a different conclusion? |

### Step 3: Structure the Critique

```markdown
## Pressure Test: [Title of what's being tested]

### Verdict: [STRONG / HAS GAPS / WEAK]

### What Holds
[1-3 things that are genuinely strong about the argument. Be specific.]

### What Breaks
[Numbered list. Each item:]
1. **[Problem name]** — [What's wrong, specifically]
   - *Evidence:* [The specific sentence, claim, or gap]
   - *Fix:* [What to do about it. Concrete, not "make it more specific."]

### The Kill Shot
[The single strongest objection. The one that would make a smart CMO pause. If this can't be answered, the strategy needs rework.]

### Revised Core Argument (if needed)
[If the argument is fundamentally sound but poorly expressed, offer a tightened version. If it's fundamentally weak, say so and explain why.]
```

### Step 4: Quality Gate

Even critique output goes through Voice DNA + Stop-Slop. The pressure test should read like a sharp strategist talking, not a rubric being applied.

### Step 5: Observation

Log the run per `rules/observation.md`. Track what was tested, the verdict, and whether Julian agreed with the critique.
