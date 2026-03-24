# Strategy Engine

A strategy engine for the full range of strategic work: brand positioning, creative briefs, product vision, GTM narratives, adversarial pressure testing, and multi-agent debate. Built to self-improve over time.

## Structure

```
strategy-engine/
├── .claude-plugin/
│   └── plugin.json          # Plugin metadata
├── commands/                 # Slash command routers
├── skills/                   # Each skill = one /strategy:* command
│   ├── using-strategy/       # Bootstrap control plane
│   ├── go/                   # Entry point: routes to right mode
│   ├── narrative/            # Strategy docs → slide-ready copy
│   ├── brief/                # Creative briefs
│   ├── product/              # Product specs, vision docs
│   ├── pressure-test/        # Single-agent adversarial critique
│   ├── courtroom/            # Multi-agent debate engine
│   ├── distill/              # Compress copy without losing meaning
│   ├── research/             # Deep desk research with verified sources
│   └── sharpen/              # Autoresearch self-improvement loop
├── agents/
│   ├── courtroom/            # Courtroom debate panel agents
│   └── research/             # Research panel agents (academic, quantitative, cultural)
├── rules/                    # Apply to ALL output across all modes
│   ├── voice.md              # Voice DNA + Stop-Slop enforcement
│   ├── quality-gates.md      # Scoring, anti-patterns, mandatory checks
│   ├── process.md            # Phase sequencing, approval gates
│   └── observation.md        # Structured logging after every run
├── references/               # Shared strategic knowledge
│   ├── narrative-engines.md  # Reusable narrative structures
│   ├── slide-conventions.md  # Layout types, eyebrow labels
│   ├── anti-patterns.md      # Hard failure patterns
│   └── quality-system.md     # Scoring rubric + quick checks
├── logs/
│   └── execution-log.md      # Structured observation history
├── feedback-log.md           # Julian's manual corrections (BINDING)
├── CLAUDE.md                 # This file
└── LICENSE
```

## Command Workflow

All commands use the `/strategy:` namespace prefix.

```
0. BOOTSTRAP   /strategy:using-strategy  → Control plane (auto-loaded)
1. ENTRY       /strategy:go              → Routes to right mode
2. NARRATIVE   /strategy:narrative       → Strategy docs → slide copy
3. BRIEF       /strategy:brief           → Creative briefs
4. PRODUCT     /strategy:product         → Product specs, vision docs
5. TEST        /strategy:pressure-test   → Single-agent adversarial critique
6. DEBATE      /strategy:courtroom       → Multi-agent debate engine
7. DISTILL     /strategy:distill        → Compress copy, merge slides, tighten
8. RESEARCH    /strategy:research        → Deep desk research, verified sources
9. IMPROVE     /strategy:sharpen         → Autoresearch self-improvement
```

## Key Principles

- **Lead agent orchestrates, Julian decides.** The engine routes, delegates, and quality-checks. Julian approves architectures, picks concepts, and gives final sign-off.
- **Quality gates are mandatory, not decorative.** Voice DNA + Stop-Slop run line-by-line on every piece of prose before it reaches Julian. The Phase 4 quality gate scores everything. Below 35/50 gets revised internally.
- **Feedback log outranks everything.** Julian's manual corrections are binding. They override automated improvements, default rules, and the engine's own judgment.
- **Observation compounds.** Every run logs structured data. Over time, the system learns which modes underperform and where.
- **Strategy makes choices.** If output could be endorsed by every brand in the category, it fails. Name what you're choosing NOT to do.
