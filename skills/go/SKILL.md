---
name: go
description: |
  The strategy engine's front door. Understands what Julian needs and routes to the right mode.
  Use when starting strategy work, saying "help me think through this," or unsure which mode to use.
---

<tool_restrictions>
## REQUIRED TOOLS:
- **AskUserQuestion**:for all user-facing questions. Use structured options.
## BANNED TOOLS:
- **EnterPlanMode** / **ExitPlanMode**:this skill has its own routing structure.
</tool_restrictions>

<required_reading>
Read before doing anything:
1. `feedback-log.md`:Binding corrections from Julian
2. `rules/process.md`:Phase sequencing
</required_reading>

# /strategy:go

The entry point. Understand what Julian needs, route to the right mode.

## Process

### Step 0: Gather Context

Before reading Julian's input, check what already exists.

**Check for existing strategy artifacts:**
```bash
ls docs/strategy/*.md docs/strategy/*.yaml 2>/dev/null
```

**Check last strategy activity:**
```bash
git log --oneline -5 -- 'docs/strategy/*' 2>/dev/null
```

**Route based on findings:**

**If strategy artifacts exist**, determine what stage they represent:
- `01-intake.md` only: research phase is next
- `02-research.md` but no `03-distill.md`: distillation is next
- `03-distill.md` but no `04-brief.md`: brief is next
- `04-brief.md` but no `05-spec.md`: spec is next
- `04-brief-handoff.yaml` exists: ready for Arc build pipeline

Present what was found:

```
AskUserQuestion:
  question: "You have strategy work in progress: [list artifacts found, with dates]. What do you want to do?"
  header: "Strategy in Progress"
  options:
    - label: "Continue where I left off"
      description: "[Next logical step based on artifacts, e.g. 'Take the approved brief into spec mode']"
    - label: "Revise existing work"
      description: "Reopen a previous artifact with new input or feedback"
    - label: "Start something different"
      description: "Set this aside and work on a new strategic problem"
```

If "Continue where I left off": route to the next logical skill. Skip Steps 1-3.
If "Revise existing work": ask which artifact, then route to that mode with the artifact loaded.
If "Start something different": proceed to Step 1.

**If no artifacts found:** Show a brief status line ("No existing strategy artifacts found. Starting fresh.") and proceed to Step 1.

### Step 1: Understand the Input

Julian might provide:
- A full brief with brand, audience, problem, and context
- A sentence or question
- A link or pasted document
- A request to iterate on previous work
- A vague "help me think through X"

Read whatever Julian provides and don't ask unnecessary questions.

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

**If the mode is obvious**, state it and proceed:
> "This reads like a brand positioning brief. Running narrative mode with Brand DNA vs Cultural Truth."

**If the mode is ambiguous**, use structured options:

```
AskUserQuestion:
  question: "I could approach this two ways. Which fits?"
  header: "Mode Selection"
  options:
    - label: "[Mode A name]"
      description: "[What it produces and how it approaches the problem]"
    - label: "[Mode B name]"
      description: "[What it produces and how it approaches the problem]"
```

### Step 3.5: Scope Posture (creative modes only)

**Skip this step if:**
- The mode is analytical (pressure-test, courtroom, research, distill, insight-distill, narrative-review)
- The input is a revision or continuation ("revise," "update," "continue," "iterate on," "tweak")
- Julian said something like "just do it" or gave very specific instructions

**For narrative, product, and brief modes**, ask:

```
AskUserQuestion:
  question: "How deep should this go?"
  header: "Scope"
  options:
    - label: "Full framework"
      description: "Cultural grounding, coined concept, expression territories, slide copy"
    - label: "Tight argument"
      description: "One tension, one insight, one strategy. No expressions."
    - label: "Just answer my question"
      description: "Skip the framework. Give me the strategic answer directly."
```

Pass the chosen posture as context when invoking the downstream skill.

### Step 4: Handoff

Once the mode is confirmed, invoke that mode's skill with Julian's full input carried forward. Don't make Julian repeat context. Include the scope posture if one was selected.

## Downstream: Build

Strategy-engine produces strategy, not software. When the strategic
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
