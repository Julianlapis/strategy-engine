---
name: pipeline
description: |
  Full strategy-to-build pipeline. 7 steps from written input to shipped product.
  Use when starting a new project, saying "let's build something," or when you need
  the full sequence: intake → research → distill → brief → spec → map → build.
  For stateful multi-session runs, use `lead pipeline` from terminal instead.
---

# /strategy:pipeline

The full strategy-to-build sequence. Every project hits every step.
The depth dial changes. The sequence does not.

## Quick Reference

```
1. INTAKE    → /strategy:go              What are we doing and why?
2. RESEARCH  → /strategy:research        What's true about the market, audience, category?
3. DISTILL   → /strategy:insight-distill What's the tension, insight, way in?
4. BRIEF     → /strategy:product vision  The core document. Clear. Unambiguous. Original.
5. SPEC      → /strategy:product spec    Capabilities, requirements, what we're building.
6. MAP       → /strategy:product map     Components, zones, flows — the buildable structure.
7. BUILD     → /arc:* or human process   Design and development.
```

## When to Use This vs. `lead pipeline`

| Use this (`/strategy:pipeline`) | Use `lead pipeline` |
|---|---|
| Quick reference for the sequence | Multi-day projects that span sessions |
| Running a single step manually | Need state tracking and resume |
| Already know which step you're on | Starting a new project from scratch |
| In a Claude Code conversation | From the terminal |

**For stateful execution**, tell Julian to run from terminal:
```bash
lead pipeline ~/Projects/my-project --size M --type product
lead pipeline ~/Projects/my-project --resume
```

## The Sequence

### Step 1: Intake
**Skill:** `/strategy:go`
**Input:** Written problem statement, client brief, or RFP
**Output:** `docs/strategy/01-intake.md`

### Step 2: Research
**Skill:** `/strategy:research`
**Input:** Intake doc
**Output:** `docs/strategy/02-research.md` (Punt-style dossier)

### Step 3: Distill
**Skill:** `/strategy:insight-distill`
**Input:** Research dossier
**Output:** `docs/strategy/03-distill.md` (core insight, tension, audience truth, way in)
At Large: also run `/strategy:pressure-test` or `/strategy:courtroom`

### Step 4: Brief (THE CORE DOCUMENT)
**Skill:** `/strategy:product` (vision mode)
**Input:** Distilled insights
**Output:** `docs/strategy/04-brief.md` + `docs/strategy/04-brief-handoff.yaml`
**Quality gate:** Three-layer scoring, all 35/50. Rallying cry below 7/10 = hard stop.
THE BRIEF DOES NOT GET LONGER AT LARGE.

### Step 5: Spec
**Skill:** `/strategy:product` (spec mode)
**Input:** Brief
**Output:** `docs/strategy/05-spec.md` + optional `.specs/` directory

### Step 6: Map
**Skill:** `/strategy:product` (map mode) + `/arc:vision`
**Input:** Spec
**Output:** `docs/map/` (components, zones, flows, open questions) + `docs/vision.md`
At Small: map mode is optional if designer works from spec directly.

### Step 7: Build
**Skill:** `/arc:*` (solo) or human process (team)
Solo: `arc:ideate → arc:build → arc:implement → arc:verify → arc:letsgo`
Team: design sprints + dev sprints, Julian reviews against brief.

## T-Shirt Sizes

| | Small | Medium | Large |
|---|---|---|---|
| **Team** | Julian + 1 designer | Small team | Full agency |
| **Research** | 1-2 hours | Half day | 1-2 days |
| **Brief** | 2-3 pages | 2-4 pages | 2-4 pages |
| **Map** | Optional | Required | Full Cenex-style |
| **Build** | Full Arc suite | Arc:vision only | Arc:vision only |

## The Rule

**Solo build triggers Arc. Team build stays in strategy-engine. Arc:vision is the only bridge.**
(Teams still use Arc for `vision.md` generation — but only that.)

**Arc without strategy-engine** is valid for small personal projects where the builder
already knows what they're building. Skip the pipeline, go straight to `/arc:vision`
or `/arc:ideate`. The pipeline exists for when the problem needs to be understood
before it's solved.
