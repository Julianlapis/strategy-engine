# Observation Rules

After every run of any mode, the lead agent writes a structured observation to `logs/execution-log.md`. This is the cognee-inspired memory layer that lets the system learn from its own performance over time.

## What Gets Logged

```markdown
---
run_id: YYYY-MM-DD-NNN
date: YYYY-MM-DD
mode: [narrative | brief | product | pressure-test | courtroom | sharpen]
brief_summary: [1-2 sentence summary of the input]
---

### Scores
| Dimension | Score |
|-----------|-------|
| Tension | /10 |
| Specificity | /10 |
| Narrative Arc | /10 |
| Cultural Grounding | /10 |
| Persuasion | /10 |
| **Total** | **/50** |

### Weak Dimensions
[List any dimension below 7 with the specific section and what was weak]

### Failure Patterns
[What went wrong, if anything. Which anti-patterns appeared. Which quality checks failed initially.]

### Self-Corrections
[What the engine caught and fixed before presenting. E.g., "Rewrote 3 slides after stop-slop caught triple-repeat cadence"]

### User Feedback
[Julian's reaction, corrections, or redirects. Updated after the run if Julian gives feedback.]

### Agent Performance (courtroom only)
[Which agents produced the strongest critiques. Which were weakest. Any agents that consistently underperform.]
```

## When to Log

- **Always.** Every mode invocation gets an entry. No exceptions.
- Log AFTER the quality gate but BEFORE presenting to Julian.
- Update the "User Feedback" section after Julian responds.

## How to Use the Log

The log serves three purposes:

1. **Pattern detection**: After 5+ runs, look for recurring weak dimensions. If cultural grounding is consistently below 7, that's a signal the engine needs better cultural research habits.
2. **Agent improvement**: In courtroom mode, track which agents consistently produce weak critiques. Feed that into /strategy:sharpen.
3. **Mode comparison**: Track which modes score highest/lowest over time. If briefs consistently outscore narratives, that's worth investigating.

## Log Maintenance

- Keep the most recent 20 entries in the main log file
- Archive older entries to `logs/archive/YYYY-MM.md` monthly
- The lead agent should reference recent log entries when planning improvements
