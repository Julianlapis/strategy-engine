---
name: product
description: |
  Product specs, product vision, and service design documents.
  Use for "product spec," "product vision," "product strategy," "service design."
  PLACEHOLDER: Needs Julian's example product docs to fully calibrate format and quality bar.
---

<required_reading>
Read before doing ANY work:
1. `feedback-log.md` — Binding corrections
2. `rules/voice.md` — Voice rules
3. `rules/quality-gates.md` — Quality gates (adapted for product format)
</required_reading>

# /strategy:product

Product strategy documents. A different brain than brand strategy: user problems, capabilities, positioning against alternatives, success metrics.

## Two Modes

### Product Vision
The "why this should exist" document. Written before building. Answers:
- What problem does this solve, for whom, and why now?
- What's the current alternative and why does it fail?
- What does success look like in 6 months? 2 years?
- What are we choosing NOT to build?

### Product Spec
The "what to build" document. Written after the vision is clear. Answers:
- What are the capabilities (not features, capabilities)?
- How does the user experience it?
- What are the success metrics?
- What are the constraints (technical, legal, budget, timeline)?

## Product Vision Format

```markdown
# [Product Name]: Vision
*[Date]*

---

## The Problem
[2-3 paragraphs. Who has this problem, how it manifests, and why existing solutions fail. Be specific about the failure mode, not just "it's not good enough."]

## Why Now
[1-2 paragraphs. What changed (technology, behavior, market, regulation) that makes this solvable now when it wasn't before?]

## The Thesis
[One paragraph. The core bet. "We believe [X] because [Y], which means [Z]." This is the product's reason to exist.]

## What It Does
[3-5 capabilities described from the user's perspective. Not features ("AI-powered search") but outcomes ("find the answer in 3 seconds instead of 30 minutes").]

## What It Doesn't Do
[2-3 explicit exclusions. What you're choosing NOT to build and why. This is where product strategy makes choices.]

## Success Looks Like
[6-month and 2-year picture. Measurable where possible. Qualitative where measurement doesn't capture the value.]

## The Risk
[The single biggest reason this could fail. Not a list. The one thing.]

---

*Quality score: [X/50]*
```

## Product Spec Format

```markdown
# [Product Name]: Spec
*[Date] — v[X.X]*

---

## Context
[Link to or summary of the vision doc. 2-3 sentences.]

## User
[Who uses this. Behavior-based, not demographic. What they're trying to do when they reach for this product.]

## Capabilities
[Numbered list. Each capability:]
1. **[Capability name]** — [What the user can do, described from their perspective]
   - *How it works:* [Brief technical/UX description]
   - *Success metric:* [How we measure this capability is working]

## Constraints
[Numbered list of real constraints: technical limitations, legal requirements, budget, timeline, dependencies.]

## Out of Scope
[What's explicitly excluded from this version and why.]

## Open Questions
[Things that need answers before or during build. Each with who needs to answer it.]

---

*Quality score: [X/50]*
```

## Process

Same phase sequence as other modes:
1. Intake (accept whatever Julian provides)
2. Structure (PAUSE for approval: vision or spec? thesis direction?)
3. Write
4. Quality gate (adapted: specificity of problem, clarity of thesis, measurability of success)
5. Observation

## Quality Gate Adaptations

Product strategy has its own failure modes beyond the universal anti-patterns:
- **Solution looking for a problem**: The product is described before the problem is felt. Fix: spend more time on the problem.
- **Feature list as strategy**: A list of features isn't a product strategy. What's the thesis?
- **Unmeasurable success**: "Users love it" isn't a metric. What specific behavior indicates success?
- **Everything-for-everyone**: No explicit exclusions means no strategic choices. What does this NOT do?

## Status: PLACEHOLDER

This mode needs calibration. Julian: provide 1-2 product specs or vision docs you've written. I'll extract the format and patterns.
