---
name: go
description: |
  The strategy engine's front door. Understands what Julian needs and routes to the right mode.
  Use when starting strategy work, saying "help me think through this," or unsure which mode to use.
---

<required_reading>
Read before doing anything:
1. `feedback-log.md` — Binding corrections from Julian
2. `rules/process.md` — Phase sequencing
</required_reading>

# /strategy:go

The entry point. Understand what Julian needs, route to the right mode.

## Process

### Step 1: Understand the Input

Julian might provide:
- A full brief with brand, audience, problem, and context
- A sentence or question
- A link or pasted document
- A request to iterate on previous work
- A vague "help me think through X"

Read whatever Julian provides. Don't ask unnecessary questions.

### Step 2: Detect the Mode

| If the input suggests... | Route to... |
|--------------------------|-------------|
| Brand positioning, repositioning, narrative strategy | `/strategy:narrative` |
| Creative brief for a campaign or activation | `/strategy:brief` |
| Product spec, product vision, service design | `/strategy:product` |
| "What's wrong with this," "poke holes," critique | `/strategy:pressure-test` |
| "Debate this," "stress test," multi-perspective | `/strategy:courtroom` |
| "Tighten this," "make it shorter," "cut slides," compress | `/strategy:distill` |
| "Research this," "find evidence," "verify claim," "back this up," "find examples" | `/strategy:research` |
| "What does the research tell us," "find the way in," "distill the research" | `/strategy:insight-distill` |
| "Is this ready for my boss," "review the narrative," "check against the brief" | `/strategy:narrative-review` |
| "Improve this skill," "autoresearch" | `/strategy:sharpen` |

### Step 3: Confirm and Route

If the mode is obvious, state it and proceed:
> "This reads like a brand positioning brief. I'll run it through narrative mode with the Brand DNA vs Cultural Truth engine. Here's the architecture..."

If the mode is ambiguous, propose 2 options with rationale and let Julian pick:
> "I could approach this two ways:
> 1. **Narrative mode** — full strategy doc with cultural grounding, coined concept, slide-ready copy
> 2. **Brief mode** — tight creative brief with a single proposition and mandatories
> Which fits what you need?"

### Step 4: Handoff

Once the mode is confirmed, invoke that mode's skill with Julian's full input carried forward. Don't make Julian repeat context.

## Downstream: Build

Strategy-engine produces strategy. It does not build software. When the strategic
artifacts are ready and Julian wants to build:

- **Solo build:** Route to `/arc:vision` (reads `04-brief-handoff.yaml` automatically),
  then the full Arc suite (`arc:ideate` → `arc:build` → `arc:implement` → ship).
- **Team build:** The team works from `docs/map/` and `docs/strategy/`. Arc is only
  used for `vision.md` generation.
- **Full pipeline reference:** `/strategy:pipeline` documents the complete 7-step sequence.

## Cross-Mode Transitions

If Julian wants to chain modes (e.g., "now turn this positioning into a brief"), carry forward:
- The brief summary
- The approved concept
- Any feedback Julian gave during the current session
- The quality scores from the previous mode's output

Propose the transition. Don't auto-chain.
