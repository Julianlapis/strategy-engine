---
name: research
description: |
  Deep desk research with verified, traceable sources. Three parallel researcher agents
  (academic, quantitative, cultural) scored on recency, cogency, accuracy, and verifiability.
  Use for bolstering strategy arguments, finding examples, comparing claims, discovering
  counterexamples, and grounding narrative in evidence.
  Trigger: "research this," "find evidence for," "verify this claim," "what does the data say,"
  "find examples of," "back this up," or any request for sourced evidence.
---

<required_reading>
Read `~/.claude/feedback/pre-flight.md` before any work.
Read before doing ANY work:
1. `feedback-log.md` — Binding corrections from Julian
2. `rules/voice.md` — Voice rules apply to synthesis output
3. `rules/quality-gates.md` — Quality gates apply to synthesis
</required_reading>

# /strategy:research

Deep desk research engine. Three specialized agents research in parallel, score findings on 4 dimensions, and deliver a verified research dossier with full citations.

## Philosophy

1. **Verified or flagged.** If a claim can't be traced to a specific source with a URL, DOI, or named publication, it gets flagged as unverified. Unverified claims can still be useful, but Julian sees the flag.
2. **Scored, not curated.** The agents don't hide weak findings. They score them and show the scores. Julian decides what's strong enough.
3. **Anti-slop research.** No "studies show" without naming the study. No "experts agree" without naming the expert. No "recent trends indicate" without naming the trend, the data, and the date.
4. **Recency matters.** A 2019 stat about Gen Z is a 2019 stat, not a current truth. All findings carry their date visibly.

## The Three Researchers

### 1. Academic Researcher
**Lens:** Published research, peer-reviewed studies, named frameworks, cited authors.
**Searches:** Google Scholar, university repositories, published books, named researchers' work, conference proceedings.
**Strength:** Theoretical grounding, established frameworks, longitudinal studies.
**Weakness:** Often 1-3 years behind current practice. Paywalled full-text access limited.
**Output:** Findings with author, title, publication, year, DOI/URL where available.

### 2. Quantitative Researcher
**Lens:** Numbers, market data, financial results, survey findings, growth metrics.
**Searches:** Public financial filings, industry reports (free/summary versions), government data, published surveys, earnings calls, press releases with numbers.
**Strength:** Hard evidence. Revenue, growth rates, market share, demographic data.
**Weakness:** Can't access proprietary databases (Statista premium, Bloomberg). Limited to public data.
**Output:** Findings with specific numbers, source, date, and URL.

### 3. Cultural Researcher
**Lens:** Real human discourse, cultural signals, qualitative evidence from existing sources.
**Searches:** Reddit threads, Twitter/X discourse, forum discussions, published interviews, journalistic accounts, ethnographic studies, cultural commentary, Substack/newsletter analysis.
**Strength:** What people are saying in their own words. Real sentiment, not survey sentiment. Cultural context that numbers miss.
**Weakness:** Can't conduct primary research (interviews, focus groups). Relies on what's published.
**Output:** Findings with direct quotes where possible, source platform, date, and URL.

## Process

### Phase 1: Research Brief
Julian provides one of:
- A **topic** to research broadly ("NBA's content strategy in the 2000s-2010s")
- A **claim** to verify or challenge ("70% of Gen Z buys dupes")
- An **argument** to bolster ("brand compounds under imitation")
- A **question** to answer ("did MLB's lockdown strategy hurt their cultural relevance?")
- A **comparison** to investigate ("NBA vs MLB audience growth trajectories")

The engine creates a research brief:
```
RESEARCH BRIEF
──────────────
Topic: [what we're researching]
Angle: [the strategic question driving the research]
For each researcher:
  Academic: [what to look for, which fields, which authors if known]
  Quantitative: [what numbers to find, what metrics matter]
  Cultural: [what discourse to scan, which communities, what signals]
```

**PAUSE for Julian's approval before launching researchers.**

### Phase 2: Parallel Research
All three researchers execute in parallel. Each uses firecrawl for web research and follows their specific lens.

Each researcher returns findings in this format:

```markdown
## Finding [N]

**Claim:** [The specific finding, stated as a concrete claim]
**Source:** [Author/Organization, Title, Publication, Date]
**URL:** [Full URL or DOI]
**Date of source:** [YYYY-MM-DD or YYYY-MM or YYYY]
**Excerpt:** [Direct quote or specific data point from source]

### Scores
| Dimension | Score (1-10) | Rationale |
|-----------|-------------|-----------|
| Recency | | How recent? Post-2023 = 8+. Pre-2020 = 5 or below unless historical. |
| Cogency | | How relevant to the research question? Does it advance the argument? |
| Accuracy | | Is the claim internally consistent? Cross-referenced? |
| Verifiability | | Can someone click the URL and find this claim? |

**Composite Score:** [Average of 4 dimensions]
**Confidence:** HIGH / MEDIUM / LOW
```

### Phase 3: Synthesis
After all three researchers return, the engine:

1. **Merges findings** across all three researchers, grouping by sub-topic.
2. **Flags conflicts** where researchers found contradictory evidence.
3. **Identifies gaps** where a claim lacks support from any researcher.
4. **Ranks by composite score** so the strongest evidence surfaces first.
5. **Creates a research dossier** with the structure below.

### Phase 4: Research Dossier
The deliverable:

```markdown
# Research Dossier: [Topic]

## Research Brief
[The brief from Phase 1]

## Key Findings (ranked by composite score)
[Top 5-10 findings, scored, with full citations]

## Supporting Evidence
[Additional findings that reinforce the key findings]

## Contradictions & Counter-Evidence
[Findings that challenge the argument, with scores]

## Gaps
[Claims that couldn't be verified or areas with no evidence found]

## Source Quality Summary
| Dimension | Average Score | Weakest Area |
|-----------|-------------|-------------|
| Recency | /10 | [which findings are dated] |
| Cogency | /10 | [which findings are tangential] |
| Accuracy | /10 | [which findings couldn't be cross-referenced] |
| Verifiability | /10 | [which findings lack traceable sources] |

## Full Citation List
[All sources in a consistent format: Author, Title, Publication, Date, URL/DOI]
```

### Phase 5: Present
Present the dossier to Julian. He decides:
- Which findings to incorporate into the narrative
- Which claims need more research
- Which contradictions to address
- Whether to run a follow-up pass on specific gaps

## Scoring Rubric

### Recency
| Score | Meaning |
|-------|---------|
| 10 | Published within last 3 months |
| 8-9 | Published within last year |
| 6-7 | Published within last 2 years |
| 4-5 | Published 3-5 years ago |
| 2-3 | Published 5-10 years ago |
| 1 | Published 10+ years ago |
| Exception | Historical claims (e.g., "A&F lost 90% of market cap 2011-2016") score on accuracy of the historical record, not recency of publication |

### Cogency
| Score | Meaning |
|-------|---------|
| 10 | Directly answers the research question with a specific, applicable finding |
| 8-9 | Closely related, provides strong supporting or challenging evidence |
| 6-7 | Related but requires interpretation to apply to the argument |
| 4-5 | Tangentially related, useful as context only |
| 2-3 | Loosely related, might be interesting but doesn't advance the argument |
| 1 | Not relevant |

### Accuracy
| Score | Meaning |
|-------|---------|
| 10 | Cross-referenced across multiple independent sources |
| 8-9 | Verified against one additional source |
| 6-7 | From a credible source but not independently verified |
| 4-5 | From a less authoritative source, not verified |
| 2-3 | Single source, potentially biased or promotional |
| 1 | Unverifiable or contradicted by other evidence |

### Verifiability
| Score | Meaning |
|-------|---------|
| 10 | Direct URL to the specific claim, publicly accessible |
| 8-9 | URL to the source document, claim is findable within it |
| 6-7 | URL to the organization/author, specific document requires search |
| 4-5 | Named source but no direct URL (e.g., a book, a paywalled paper) |
| 2-3 | Vague attribution ("according to industry reports") |
| 1 | No source provided |

## Integration with Other Modes

### Research → Narrative
Run research first, then hand the dossier to `/strategy:narrative` as input. The narrative mode uses scored findings as evidence, citing sources inline.

### Research → Courtroom
The courtroom agents can request research mid-debate. If an agent makes a claim that needs verification, the engine can spawn a targeted research query.

### Research → Pressure Test
Before pressure-testing, run research to find counterexamples and contradictory evidence. Feed the dossier into the pressure test so the critique is grounded in real data.

### Narrative → Research (backfill)
After writing a narrative, Julian can flag specific claims that need sourcing. Research mode runs targeted queries on flagged claims and returns evidence to insert.

## Anti-Slop Research Rules

1. **Never say "studies show" without naming the study.** Name: author, institution, year, title.
2. **Never say "experts agree" without naming the expert.** Name: person, role, organization, what they said, where they said it.
3. **Never say "data suggests" without showing the data.** Number, source, date.
4. **Never round aggressively.** "~$4.1B" is fine. "Several billion" is not.
5. **Never present a single data point as a trend.** One number is a snapshot. Two numbers with dates are a direction. Three or more are a trend.
6. **Flag the difference between correlation and causation.** "NBA viewership grew while highlights were open" is correlation. "NBA viewership grew because highlights were open" is a causal claim that needs more evidence.
7. **Date everything.** A stat without a date is a stat without context.
8. **Distinguish primary sources from secondary.** An earnings call transcript is primary. A TechCrunch article about the earnings call is secondary. Score accordingly.
9. **When a source is paywalled, say so.** Don't pretend you read the full paper if you only read the abstract.
10. **When you can't find evidence, say so.** "No evidence found" is a valid research finding. It's more useful than a manufactured source.

## Modes of Use

### Broad Research
`/strategy:research NBA content strategy evolution 2000-2024`
All three researchers run broad queries. Returns a comprehensive dossier.

### Claim Verification
`/strategy:research verify "70% of Gen Z buys dupes"`
Quantitative researcher leads. Finds the original source, checks methodology, cross-references.

### Example Discovery
`/strategy:research find examples of brands that grew by opening their IP`
All three researchers search for concrete examples with evidence.

### Counter-Research
`/strategy:research find counterexamples to "brand compounds under imitation"`
Researchers specifically look for cases where the thesis fails.

### Backfill
`/strategy:research backfill [file path]`
Reads the document, identifies unsourced claims, runs targeted research on each.

## Cleanup

After all research agents complete, kill orphaned subagent processes:
```bash
~/.claude/scripts/cleanup-agents.sh
```
