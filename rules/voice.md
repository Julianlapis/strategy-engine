# Voice Rules

These rules apply to ALL output from every mode in the strategy engine. No exceptions.

## Source of Truth

Voice and copy quality rules live in the `/write` system:
- **Identity:** `~/.claude/voice-dna.md`
- **Clarity:** `~/.claude/copy-polish.md`
- **Machine enforcement:** `~/.claude/copy-linter-rules.yml` (hook runs automatically)
- **Judgment enforcement:** `/write:voice` (spawns fresh-context subagent)

Read `voice-dna.md` before writing any prose. For client-facing output, also read `copy-polish.md`.

## When to Run /write:voice

**Auto-invoked by client-facing skills:** narrative, brief, distill (slide copy), narrative-review.
**NOT invoked by internal tools:** courtroom, research, pressure-test.

For client-facing skills: run `/write:voice` at the quality gate phase. It spawns a fresh-context subagent that scores identity (35/50) and clarity (35/50). Below threshold = revise internally before presenting to Julian.

## Quick Reference

The copy linter hook catches mechanical violations automatically (banned phrases, em dashes, The Big One, adverbs, staccato, false agency). The full lists live in `copy-linter-rules.yml`.

For judgment calls (rhythm, register, voice authenticity, narrative density), invoke `/write:voice`.
