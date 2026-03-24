# Process Rules

How the strategy engine sequences work, enforces approvals, and prevents drift.

## Phase Sequencing

Every mode follows a version of this flow:

```
INTAKE → STRUCTURE → WRITE → QUALITY GATE → PRESENT
```

Some modes add or skip phases:

| Mode | Phases |
|------|--------|
| Narrative | Intake → Structure (pause for approval) → Write doc → Quality gate → Distill to slides → Quality gate → Present |
| Brief | Intake → Structure (pause for approval) → Write brief → Quality gate → Present |
| Product | Intake → Structure (pause for approval) → Write spec → Quality gate → Present |
| Pressure Test | Intake → Critique → Quality gate → Present |
| Courtroom | Intake → Round 1 (parallel critique) → Round 2 (agents argue) → Synthesis → Quality gate → Present |
| Research | Intake → Research brief (pause for approval) → Parallel research (3 agents) → Score → Synthesize → Present dossier |
| Sharpen | Select target → Baseline score → Mutation loop → Evaluate → Present changelog |

## Approval Gates

The lead agent MUST pause for Julian's approval at these points:

1. **After Structure phase**: Present the narrative architecture, coined concept candidates, and expression depth. Do not proceed until confirmed.
2. **After concept selection**: If multiple concepts were proposed, Julian picks. Don't pick for him.
3. **Before delivering final output**: Quality gate runs internally, but the scored output is what Julian sees.

## Drift Prevention

The lead agent checks for drift at these intervals:

- **Every mode invocation**: Read `feedback-log.md` first. Always.
- **Every quality gate**: Check output against `rules/voice.md` and `rules/quality-gates.md`.
- **Every 3rd run (tracked in execution log)**: Re-read the feedback log and check if any new patterns are emerging in the execution log that suggest systematic underperformance.

## Handoff Rules

- The lead agent can suggest mode transitions: "This positioning could become a brief. Want me to run /strategy:brief on it?"
- Julian decides. The engine never auto-chains modes.
- When handing off between modes, the lead agent carries forward: the brief summary, the approved concept, and any Julian feedback from the current session.

## Feedback Log Protocol

Julian's corrections go into `feedback-log.md`. The protocol:

1. Julian flags a problem in the output
2. The lead agent writes a structured entry: what happened, what was wrong (with specific examples), what the fixes looked like, and the rule going forward
3. The entry is binding on all future runs across all modes
4. Automated improvements (from /strategy:sharpen) NEVER override feedback log entries

## Observation Protocol

After every run, the lead agent writes a structured observation to `logs/execution-log.md`. See `rules/observation.md` for the format.
