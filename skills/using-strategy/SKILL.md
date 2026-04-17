---
name: using-strategy
description: Use when starting any conversation that involves strategy work. Establishes the strategy engine's routing, instruction priority, and bootstrap rules.
---

<SUBAGENT-STOP>
If you were dispatched as a subagent to execute a specific task, skip this skill.
</SUBAGENT-STOP>

# Using Strategy Engine

The strategy engine handles the full range of Julian's strategic work. Use this skill as the control plane that routes to the right mode.

## Instruction Priority

When instructions conflict, use this order:

1. Julian's instructions in the conversation
2. `feedback-log.md` (binding corrections from Julian)
3. Strategy engine rules (`rules/`)
4. Strategy engine skills and references
5. Default system behavior

Julian stays in control. The engine provides process and quality, not authority over Julian's intent.

## The Rule

Before starting strategy work, decide which mode applies:

- If Julian names a mode, use it.
- If the task clearly matches a mode, route to it.
- If unclear, use `/strategy:go` to determine the right mode.

## Mode Routing

| Signal | Mode |
|--------|------|
| "positioning," "brand strategy," "what should the brand stand for" | `/strategy:narrative` |
| "brief," "creative brief," "write a brief" | `/strategy:brief` |
| "product spec," "product vision," "product strategy" | `/strategy:product` |
| "pressure test," "poke holes," "what's wrong with this" | `/strategy:pressure-test` |
| "courtroom," "debate this," "argue about this," "stress test" | `/strategy:courtroom` |
| "research," "find evidence," "verify," "back this up," "find examples" | `/strategy:research` (redirects to standalone `/research` plugin) |
| "sharpen," "improve this skill," "autoresearch" | `/strategy:sharpen` |
| "strategy," "help me think through," vague strategic ask | `/strategy:go` (router) |

## Required Reading

Every mode invocation MUST read `feedback-log.md` before doing any work. This is non-negotiable.

## Quality Rules

All output from every mode passes through the quality gates in `rules/quality-gates.md` and the voice rules in `rules/voice.md`. Both layers (Voice DNA + Stop-Slop) apply to every piece of prose. See `rules/process.md` for phase sequencing.

## Progressive Disclosure

Don't preload all references. Load what the active mode needs:

- Narrative mode: `references/narrative-engines.md`, `references/slide-conventions.md`
- All modes: `rules/voice.md`, `rules/quality-gates.md`
- Courtroom: Agent definitions from `agents/courtroom/`
- Research: Agent definitions from `agents/research/`
- Sharpen: `logs/execution-log.md` for baseline data

## Version Control

The strategy engine is git-tracked at `~/.claude/plugins/local/strategy-engine/` with a remote at `github.com/Julianlapis/strategy-engine` (private).

**End-of-session habit:** Before Julian closes a session that involved strategy work, suggest committing and pushing any changes to the plugin (feedback log entries, sharpen mutations, new agents, rule updates). Use:

```bash
cd ~/.claude/plugins/local/strategy-engine
git add -A && git status --short
# Show Julian what changed, then commit and push if he confirms
```

This keeps the plugin versioned and recoverable. The sharpen mode commits after each accepted mutation (Step 7 in sharpen/SKILL.md), but feedback log entries and manual edits accumulate between sessions and need an explicit commit.
