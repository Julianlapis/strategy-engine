---
name: courtroom
description: |
  Multi-agent debate engine. 10 strategy agents argue with each other until the idea
  is pressure-tested from every angle. Returns a distilled, bulletproof version of the idea
  plus the strongest surviving objections.
  Use for "debate this," "stress test this idea," "courtroom this," or when you want
  an idea sharpened through genuine friction between perspectives.
---

<required_reading>
Read `~/.claude/feedback/pre-flight.md` before any work.
Read before doing ANY work:
1. `feedback-log.md` — Binding corrections
2. `rules/voice.md` — Voice rules apply to all output including synthesis
3. `rules/quality-gates.md` — Quality gates apply to the final synthesis
</required_reading>

# /strategy:courtroom

A room full of strategists who disagree with each other. The value isn't just critique. It's that objections collide with other objections, and what survives is the signal.

## The Panel

10 agents, each with a named strategic lens:

| Agent | Lens | Job |
|-------|------|-----|
| **The Reductionist** | Simplicity | "What's the one sentence? If you can't say it in one, you don't have a strategy." |
| **The Contrarian** | Inversion | "What if the opposite is true?" |
| **The Empiricist** | Evidence | "Where's the proof? Show me the data, the behavior, the signal." |
| **The Competitor** | Category context | "Three other brands could say this. What makes it theirs?" |
| **The Cynic** | Organizational reality | "The CMO nods, then nothing changes. How does this survive the org?" |
| **The Culture Editor** | Cultural specificity | "Is this actually happening in culture or is this a strategist's projection?" |
| **The Creative** | Expressibility | "Can I make an ad from this? Or is it too abstract to execute?" |
| **The Audience** | Real person test | "I'm the target. Say this to my face. Do I care?" |
| **The Historian** | Pattern recognition | "This has been tried. Here's what happened." |
| **The Synthesizer** | Integration | Doesn't argue. Listens to all agents, finds the surviving thread, writes the final version. |

## Process

### Step 1: Frame the Debate

Read Julian's input. Extract:
- The core idea or strategic argument being debated
- Any context (brand, audience, category, competitive landscape)
- What Julian wants to know (is this defensible? is it sharp enough? what am I missing?)

Present the framing back to Julian:
> "Here's what I'm putting in front of the panel: [1-2 sentence summary of the argument]. The courtroom will debate this across [relevant angles]. Proceed?"

### Step 2: Round 1 — Independent Critique

Dispatch all 10 agents in parallel (batches of 3-4 to manage resources). Each agent receives:
- The core argument
- The context
- Their specific lens and instructions (from `agents/courtroom/[agent].md`)

Each agent returns:
- Their position (AGREE / DISAGREE / CONDITIONAL)
- Their argument (2-4 sentences)
- Their strongest objection OR strongest endorsement

**Do not show Round 1 to Julian.** This is internal deliberation.

### Step 3: Round 2 — Agents Argue

Feed each agent a summary of ALL Round 1 positions. Each agent now:
- Responds to the strongest objection from another agent
- Either reinforces their position or changes it based on new evidence
- Identifies which other agent's point they find most compelling (agree or disagree)

This is where the real sharpening happens. The friction between agents produces insights a single critic can't.

### Step 4: Synthesis

The Synthesizer agent receives all Round 1 and Round 2 output. It produces:

```markdown
## Courtroom Verdict: [Title]

### The Surviving Idea
[The refined, pressure-tested version of the original argument. This should be tighter, sharper, and more defensible than what went in.]

### What Survived
[The elements of the original idea that held up under scrutiny. With evidence from the debate.]

### What Got Killed
[The elements that didn't survive. Which agent killed them and why.]

### Strongest Surviving Objection
[The one critique that couldn't be fully resolved. This is valuable information, not a failure. It tells Julian where the idea is genuinely vulnerable.]

### Objections That Didn't Land
[Critiques that other agents successfully countered. These are actually validations, because they show the idea can withstand that line of attack.]

### The Debate Map
[A brief summary of who agreed with whom, where the real fault lines were, and which agents changed positions between rounds.]
```

### Step 5: Quality Gate

The synthesis output goes through Voice DNA + Stop-Slop + the full quality gate. The Synthesizer's writing should read like a sharp strategist summarizing a real conversation, not an AI summarizing AI output.

### Step 6: Present to Julian

Show the full synthesis. Let Julian react, ask follow-up questions, or request a deeper dive on any specific objection.

### Step 7: Observation

Log the run per `rules/observation.md`. Include agent performance data: which agents produced the strongest critiques, which were weakest, and which changed positions.

### Step 8: Cleanup

Kill orphaned subagent processes from the courtroom run:
```bash
~/.claude/scripts/cleanup-agents.sh
```

## Configuration

Julian can customize the panel for specific debates:
- "Run courtroom but skip The Historian, this is too new for historical precedent"
- "Add a Financial Analyst agent for this one"
- "Double down on The Audience, I want 3 different audience personas arguing"

The default panel is the 10 agents listed above. Custom agents are session-only unless Julian asks to persist them.
