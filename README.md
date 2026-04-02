# Strategy Engine

<div align="center">

<img src="assets/hero-v2.svg" alt="Strategy Engine - Multi-agent strategic reasoning system for Claude Code" width="100%">

<br>

**A strategic reasoning system that turns vague ideas into sharp strategy.**<br>
**Research. Distill. Argue. Write. Ship.**

[![Claude Code Plugin](https://img.shields.io/badge/Claude_Code-Plugin-6366f1?style=flat-square)](https://docs.anthropic.com/en/docs/claude-code)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

</div>

---

## What This Is

Strategy Engine is a Claude Code plugin that gives you a full strategic practice inside your terminal. It runs 16 specialized agents across research, synthesis, critique, and writing to produce strategy that's specific, grounded, and ready for stakeholders.

It's not a chatbot that writes marketing copy. It's a multi-agent system where researchers find evidence, a distiller extracts tensions, debaters pressure-test every claim, and a writer produces documents that sound like a human strategist wrote them.

**Built for:** Brand strategists, product leads, innovation consultants, anyone who writes briefs, positioning docs, or GTM narratives and wants AI that argues back instead of agreeing with everything.

## What It Does

| Mode | Command | What you get |
|------|---------|-------------|
| **Go** | `/strategy:go` | Routes you to the right mode based on what you describe |
| **Research** | `/strategy:research` | 3 parallel agents (academic, quantitative, cultural) with scored, sourced findings |
| **Insight Distill** | `/strategy:insight-distill` | Tensions, audience truths, hypotheses, white space extracted from research |
| **Brief** | `/strategy:brief` | One-page creative brief using the Sacred Six framework |
| **Product** | `/strategy:product` | Product vision, capability spec, or component map (3 sub-modes) |
| **Narrative** | `/strategy:narrative` | Full strategy document + slide-ready copy from 4 narrative engines |
| **Pressure Test** | `/strategy:pressure-test` | Fast adversarial critique from 7 angles. Verdict: STRONG / HAS GAPS / WEAK |
| **Courtroom** | `/strategy:courtroom` | 10 agents debate your idea across 2 rounds until it's bulletproof |
| **Distill** | `/strategy:distill` | Compress copy without losing meaning. 4 words where the draft used 8 |
| **Narrative Review** | `/strategy:narrative-review` | Score narrative against brief on 7 dimensions before showing stakeholders |
| **Pipeline** | `/strategy:pipeline` | Full 7-step sequence: intake → research → distill → brief → spec → map → build |

## The Pipeline

Strategy Engine follows a deliberate sequence. Each step feeds the next. But not every project needs every step.

```
 INTAKE          What are we doing and why?
   ↓
 RESEARCH        What's true? 3 agents find evidence in parallel.
   ↓
 DISTILL         What's the tension? The insight? The way in?
   ↓
 BRIEF           The core document. 2-4 pages at every scale.
   │
   ├── DONE      Brand strategy, positioning, creative briefs stop here.
   │              The brief IS the deliverable.
   │
   ↓              Product work continues:
 SPEC            Capabilities, requirements, success metrics.
   ↓
 MAP             Components, zones, user flows. Dual-audience format.
   ↓
 BUILD           Hand off to your build system or team.
```

**Brand projects** (positioning, GTM, creative strategy) run Intake → Research → Distill → Brief. The brief is the output. Hand it to your creative team or use `/strategy:narrative` to produce a full strategy doc with slide-ready copy.

**Product projects** run the full sequence through Spec and Map, then hand off to a build system.

You can enter at any step. Most people start with `/strategy:go` and it figures out where you are.

## The Courtroom

The signature feature. 10 specialized agents, each with a different strategic lens, argue about your idea across 2 rounds.

**Round 1:** Each agent critiques independently (hidden from each other).
**Round 2:** Agents respond to each other's arguments. Alliances form. Bad arguments die.
**Synthesis:** The Synthesizer listens to everything, finds the surviving thread, writes the refined version.

The 10 lenses:

| Agent | Lens | Question it asks |
|-------|------|-----------------|
| Reductionist | Simplicity | "What's the one sentence?" |
| Contrarian | Inversion | "What if the opposite is true?" |
| Empiricist | Evidence | "Where's the proof?" |
| Competitor | Category | "Three other brands could say this. What makes it yours?" |
| Cynic | Org reality | "The CMO nods, then nothing changes." |
| Culture Editor | Cultural specificity | "Is this actually happening in culture, or a strategist's projection?" |
| Creative | Expressibility | "Can I make an ad from this?" |
| Audience | Real person | "I'm the target. Say this to my face. Do I care?" |
| Historian | Patterns | "This has been tried. Here's what happened." |
| Synthesizer | Integration | Doesn't argue. Listens, then writes the refined version. |

What comes out: a **Courtroom Verdict** with the surviving idea (refined), what held up, what got killed, the strongest surviving objection, and a debate map.

## Research Agents

Three parallel researchers, each scored on Recency, Cogency, Accuracy, and Verifiability.

- **Academic**: Published research, peer-reviewed studies, named frameworks, cited authors
- **Quantitative**: Market data, financial results, survey findings, growth metrics
- **Cultural**: Real human discourse, cultural signals, qualitative evidence from forums, interviews, social media

Every finding has a composite score. You see the scores. No "studies show" without naming the study.

## Narrative Engines

Four reusable strategic structures that create different kinds of tension:

1. **Brand DNA vs Cultural Truth** — When brand heritage meets a changed world. (Example: Bumble's evolution from dating app to women's lifestyle platform)
2. **False Choice → Reframe** — When the industry operates on a limiting binary. (Example: Suntory choosing both scale AND cultural relevance)
3. **Subculture → Mobilization** — When reaching new audiences through community. (Example: Brooks reaching Gen Z via running crews)
4. **Audience Tension → Platform Expansion** — When audience needs have outgrown the product frame.

## Quality System

Every piece of output passes through quality gates before you see it.

### Voice System (Two Layers)

- **Layer 1: Voice DNA** — Always on. Controls rhythm, word choice, physical verbs, banned phrases. Makes output sound like a human strategist, not a language model.
- **Layer 2: Copy Polish** — Client-facing only. Plain language, directness, jargon elimination. Auto-invoked by narrative, brief, distill, and review modes.

### Scoring (5 dimensions, 35/50 threshold)

| Dimension | What it measures |
|-----------|-----------------|
| Tension | Does the strategy create a problem worth solving before solving it? |
| Specificity | Is every claim grounded in THIS brand, audience, and moment? |
| Narrative Arc | Does the argument build, or just list? |
| Cultural Grounding | Is the cultural context real, current, and load-bearing? |
| Persuasion | Would this change someone's mind? |

Below 35/50 gets revised internally before it reaches you. Scores between 35-40 are presented with flagged weak dimensions. Above 40 ships clean.

### Anti-Patterns (Hard Failures)

The system catches and rejects these automatically:

- **Generic Cultural Take** — "Gen Z values authenticity." Could apply to any brand.
- **Strategy Without Tension** — Solution arrives before the argument earns it.
- **Consultant-Speak** — "360 omnichannel experience ecosystem." Every word correct, collectively meaningless.
- **The Insight That Isn't** — An observation dressed up as an insight. Real insights contain tension.
- **Strategy by Adjective** — "Bold, authentic, innovative." Adjectives aren't choices.
- **Mood Board as Strategy** — Beautiful visuals without strategic grounding.
- **The Recycled Framework** — Jobs to Be Done, Blue Ocean, etc. used as a substitute for thinking.

## Installation

Strategy Engine is a local Claude Code plugin. Clone it into your plugins directory:

```bash
git clone https://github.com/Julianlapis/strategy-engine.git ~/.claude/plugins/local/strategy-engine
```

The `.claude-plugin/plugin.json` manifest tells Claude Code how to load skills and commands. Once cloned, restart Claude Code (or start a new session) and the `/strategy:*` commands become available.

### Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI or Desktop app
- Claude Opus or Sonnet (the courtroom and research modes run multiple agents in parallel, so a capable model matters)

## Project Structure

```
strategy-engine/
├── .claude-plugin/
│   └── plugin.json           # Plugin manifest (name, version, entry points)
├── skills/                   # 11 executable modes, each with a SKILL.md
│   ├── go/                   # Entry point router
│   ├── narrative/            # Strategy docs + slide copy
│   ├── brief/                # Creative briefs (Sacred Six)
│   ├── product/              # Vision / spec / map (3 sub-modes)
│   ├── research/             # 3 parallel research agents
│   ├── insight-distill/      # Research → insights + tensions
│   ├── courtroom/            # 10-agent debate engine
│   ├── pressure-test/        # Fast adversarial critique
│   ├── distill/              # Compress without losing meaning
│   ├── narrative-review/     # Score narrative before stakeholders
│   ├── pipeline/             # Full 7-step sequence
│   └── using-strategy/       # Bootstrap control plane
├── agents/                   # One .md file per agent (lens + instructions)
│   ├── courtroom/            # 10 debate agents (reductionist, contrarian, etc.)
│   ├── research/             # 3 research agents (academic, quantitative, cultural)
│   ├── distill/              # Research distillation agent
│   └── review/               # Narrative review agent
├── rules/                    # Apply to ALL output across all modes
│   ├── voice.md              # Voice DNA + banned phrases
│   ├── quality-gates.md      # Scoring rubrics, anti-patterns, checks
│   ├── process.md            # Phase sequencing, approval gates
│   └── observation.md        # Post-run logging format
├── references/               # Shared strategic knowledge
│   ├── narrative-engines.md  # 4 reusable story structures
│   ├── sacred-six.md         # Universal brief framework (6 sections)
│   ├── anti-patterns.md      # 8 hard failure modes
│   ├── the-pipeline.md       # Full pipeline documentation
│   ├── specs-format.md       # Product spec structure
│   └── slide-conventions.md  # Deck layout types + patterns
├── commands/                 # Slash command routers (one per mode)
├── logs/
│   └── execution-log.md      # Structured observation history
├── feedback-log.md           # YOUR corrections (binding, overrides everything)
├── CLAUDE.md                 # System overview + architecture
└── LICENSE                   # MIT
```

## Customization

### Make It Yours

The system is designed to be forked and reshaped. Every file is a lever.

**Voice and quality:**

1. **`feedback-log.md`** — The ground truth. Your corrections go here and they override everything: automated improvements, default rules, the engine's own judgment. When it makes a mistake, write it down and it won't repeat it.

2. **`rules/voice.md`** — Replace the voice DNA with your own writing rules. Banned phrases, preferred rhythm, formatting constraints. This controls how every piece of output sounds.

3. **`rules/quality-gates.md`** — Adjust scoring dimensions, thresholds, and anti-pattern definitions. If you care more about cultural grounding than persuasion, weight it accordingly.

4. **`rules/process.md`** — Controls phase sequencing and approval gates. Change how many approval checkpoints each mode requires, or which phases pause for human input.

**Strategic knowledge:**

5. **`references/`** — Add your own narrative engines, brief formats, slide conventions. The engine loads whatever's here. Key files: `narrative-engines.md` (the 4 story structures), `sacred-six.md` (brief framework), `anti-patterns.md` (hard failure modes).

6. **`agents/`** — Each agent is a standalone `.md` file with its lens, instructions, and scoring criteria. Modify existing courtroom panelists, swap in new research specialists, or add entirely new agents. The courtroom runs whatever agents are in `agents/courtroom/`.

**Observation and learning:**

7. **`rules/observation.md`** — Controls how the system logs its own performance after every run. Scores on 5 dimensions, tracks patterns over time. This is how the engine learns which modes underperform.

8. **`logs/execution-log.md`** — The observation history. The system scans recent entries to flag recurring weak dimensions.

### Self-Improvement

The engine improves itself automatically via the universal `/sharpen` skill and auto-sharpen hooks. Scores drift? Auto-sharpen detects weak dimensions after sessions and runs background improvement loops. Want to steer it manually? Use `/sharpen` and point it at any strategy-engine skill.

## Usage Examples

### Quick pressure test before a meeting

```
/strategy:pressure-test

"Our positioning is that we're the only platform that combines
AI-powered recommendations with human curation."
```

Returns a verdict (STRONG / HAS GAPS / WEAK) with what holds, what breaks, and the kill shot.

### Full research sprint

```
/strategy:research

"I need to understand how luxury brands are using AI in customer
experience. Focus on LVMH, Kering, and Richemont specifically."
```

Three agents run in parallel. You get scored findings with named sources, dates, and composite quality scores.

### Brand positioning from scratch

```
/strategy:pipeline

"We're repositioning a legacy athletic brand for Gen Z
without alienating the core 35-55 audience."
```

Runs the full 7-step sequence: intake → research → distill → brief → spec → map → handoff.

### Debate an idea until it's sharp

```
/strategy:courtroom

"The future of retail banking is invisible. Banks should disappear
into the platforms where financial decisions actually happen."
```

10 agents argue across 2 rounds. The Reductionist strips it to one sentence. The Empiricist demands evidence. The Cynic asks who in the org will actually build this. The Synthesizer writes the version that survived.

## How It's Different

**From ChatGPT/Claude chat:** Strategy Engine doesn't agree with you. It runs adversarial critique, scores its own output, and rejects work that doesn't meet quality thresholds. Chat is a yes-machine. This argues back.

**From strategy frameworks (JTBD, Blue Ocean, etc.):** Those are templates. Strategy Engine produces custom thinking specific to your brand, audience, and moment. Using a recycled framework is one of the 8 hard failure modes.

**From AI writing tools:** This isn't about generating text faster. It's about generating *better strategic thinking* through multi-agent debate, parallel research, and quality gates that catch consultant-speak before it reaches stakeholders.

## License

MIT. Fork it, adapt it, make it yours.

---

<div align="center">

Built by [Julian Alexander](https://github.com/Julianlapis). Sharpened through hundreds of strategy sessions.

</div>
