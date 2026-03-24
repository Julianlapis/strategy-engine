# Strategy Engine Feedback Log

**CANONICAL LOCATION: `~/.claude/feedback/strategy/general.md`**

Read the canonical file above. It contains all corrections from Julian, migrated from this file.
Also read: `~/.claude/feedback/global.md` (cross-cutting rules for all skills).

Automated improvements from /strategy:sharpen NEVER override entries in the canonical feedback file.

---

## 2026-03-18: Skipped Voice DNA + Stop-Slop quality gate on slide copy

**What happened:** Wrote the strategy doc and scored it (Phase 4), but treated the score as a rubber stamp instead of doing a real line-by-line audit. Then wrote 28 slides of slide-ready copy and presented it without running either quality layer. Julian caught it.

**What was wrong (examples from the slide copy):**

| Slide | Problem | Rule violated |
|-------|---------|---------------|
| Slide 4 | "operational advantage" | Voice DNA: consultant-speak, dead language |
| Slide 24 | "every campaign, every conversation, every market shift" | Stop-Slop: triple-repeat cadence is a classic AI tell |
| Slide 6 | "Research without deployment creates... Advisor tools without validated research creates..." | Stop-Slop: over-symmetric parallel construction reads as generated |
| Slide 6 | "creates" (plural subject) | Grammar: should be "create" |
| Slide 22 | "Everything we do next compounds" | Stop-Slop: vague declarative that sounds smart but says nothing |
| Slide 3 | "shared language" | Voice DNA: cliche-adjacent, vague |
| Slide 16 | "A beautifully designed tool that sits in a folder is worthless" | Stop-Slop: pull-quote trying too hard for a slide |
| Slide 24 | "A GTM engine where audience intelligence gets sharper..." | Stop-Slop: narrator-from-distance voice, reads like a brochure |
| Slide 2 | Symmetrically stacked questions | Stop-Slop: too-tidy setup, feels constructed |

**What the fixes looked like:**

Slide 4 before: "How do we turn strategic understanding into operational advantage?"
Slide 4 after: "How do we turn what we know about these audiences into something UBS teams can act on?"

Slide 16 before: "We won't design the kit in a vacuum. A beautifully designed tool that sits in a folder is worthless."
Slide 16 after: "We won't design the kit without talking to the people who'll use it. The format has to survive contact with an FA's actual Tuesday."

Slide 22 before: "Everything we do next compounds."
Slide 22 after: "Every interview, validated trigger, and verbatim quote we collect feeds the system that comes after this."

Slide 24 before: "A GTM engine where audience intelligence gets sharper with every campaign, every conversation, every market shift."
Slide 24 after: "Audience intelligence that gets sharper with use. Where the next campaign starts smarter than the last one ended."

**The rule:** Both quality layers (Voice DNA + Stop-Slop) must be run line-by-line on every piece of prose BEFORE presenting to Julian. The Phase 4 quality gate in the skill is mandatory, not decorative. This applies to strategy docs AND slide copy. No exceptions.

---

## 2026-03-20: Statement and belief slides had too much body copy

**What happened:** Slides 02 (The Opportunity, red bg) and 03 (The Belief, white bg) each had 3+ sentences of body copy beneath the headline. Julian flagged them as too dense for the slide type. These are statement slides where the headline carries the argument. The body should support, not repeat or expand.

**The rule:** For statement slides (red bg, dark bg) and belief slides (white bg with a single declarative headline): **max 2 sentences of body copy.** The headline does the work. The body adds one layer of context or evidence. If you're writing a third sentence, the slide is doing too much. Move the extra content to the next slide or cut it.

**How to apply:** Before writing body copy for any L1 (title), L2 (red statement), or belief/declaration slide, ask: can the headline stand alone? If yes, the body is optional. If no, write 1-2 sentences max. Three sentences means the slide needs restructuring.
