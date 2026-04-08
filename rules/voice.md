# Voice Rules

These rules apply to ALL output from every mode in the strategy engine. No exceptions.

## Two-Layer System

### Layer 1: Voice DNA (always on)
Source: `~/.claude/voice-dna.md`

Every sentence follows Julian's voice identity:

- Contractions always (don't, can't, won't)
- Short paragraphs (1-3 sentences max)
- Physical verbs for abstract processes ("sanded down" not "improved," "bolted on" not "added")
- No em dashes ever. Use commas, periods, colons, semicolons, parentheses.
- Numbers as digits
- Bold sparingly (1-2 key moments per section)
- Vary sentence length. Mix short punchy lines with longer ones.
- Natural transitions, not mechanical ones
- When uncertain, say so plainly

### Layer 2: Copy Polish (client-facing skills only)
Source: `~/.claude/copy-polish.md`

Auto-invoked by: narrative, brief, distill (slide copy), narrative-review, agentic-slides.
NOT invoked by: courtroom, research, pressure-test (internal tools).

Covers: plain language, jargon elimination, directness, strategy-specific banned phrases, readability scoring.

### Banned Phrases (fatal, Layer 1)

See Julian's global CLAUDE.md and voice-dna.md for the full list. The following are common in strategy writing:

- "In today's [anything]"
- "It's important/worth noting"
- "Delve" / "Dive into" / "Unpack"
- "Harness" / "Leverage" / "Utilize"
- "Landscape" / "Realm" / "Robust"
- "Game-changer" / "Cutting-edge"
- "Furthermore" / "Additionally" / "Moreover"
- "This isn't X. This is Y." and ALL variations (FATAL)

### Anti-Slop (Layer 1, final pass)

Run the full copy-polish checklist on every draft:

- False agency ("the decision emerges")
- Narrator-from-distance voice ("a GTM engine where...")
- Rhetorical setups ("What if I told you")
- Dramatic fragmentation
- Adverb creep
- Passive voice
- Throat-clearing openers
- Vague declaratives ("Everything we do next compounds")
- Triple-repeat cadence ("every X, every Y, every Z")
- Over-symmetric parallel construction
- Pull-quotes trying too hard

## Application

**Layer 1 runs on everything:** strategy docs, slide copy, briefs, product specs, pressure test critiques, courtroom synthesis, any prose that reaches Julian.

**Layer 2 runs on client-facing output only:** strategy docs, slide copy, briefs. Skills that auto-invoke Layer 2 include it in their required_reading.

Score against both rubrics when both layers apply. Voice Score (identity, 35/50) and Polish Score (clarity, 35/50).
