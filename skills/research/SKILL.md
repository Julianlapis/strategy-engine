---
name: research
description: |
  REDIRECT: Research has moved to the standalone /research plugin.
  This stub preserves /strategy:research for muscle memory.
  All modes, agents, and scoring work identically via /research.
---

# /strategy:research (Redirect)

Research is now a standalone plugin at `~/.claude/plugins/local/research/`.

**Use `/research` directly.** All modes work:
- `/research <topic>` (broad)
- `/research verify "<claim>"`
- `/research examples "<pattern>"`
- `/research counter "<thesis>"`
- `/research backfill <file>`
- `/research competitive <brand>`
- `/research audience <segment>`
- `/research reference <topic>`

If Julian invokes `/strategy:research`, run `/research` with the same arguments. The behavior is identical. The standalone plugin has the full SKILL.md, agents, and scoring rubric.

**Do not duplicate the research logic here.** Read and execute `~/.claude/plugins/local/research/skills/research/SKILL.md` instead.
