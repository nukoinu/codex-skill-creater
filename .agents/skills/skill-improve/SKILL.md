---
name: skill-improve
description: Improve a specified repository-local Codex Skill from user-selected observable session logs and necessary repository evidence. Use only for an explicit request to improve, refine, evolve, review for improvement, or update a Skill.
---

# Improve a repository-local Skill

Use this Skill only after the user explicitly asks to improve a target Skill and identifies the selected session log path or paths. Do not search `.skill-lab/`, Codex-internal log locations, or other directories for sessions.

1. Establish the target Skill's current identity, scope, `SKILL.md`, and relevant references.
2. Read only the user-selected logs and assess observable behavior plus only the repository evidence needed to interpret it.
3. Form an explicit improvement hypothesis, classify the knowledge involved, and make the smallest effective Skill-local change.
4. Check progressive disclosure, duplication, contradiction, stale facts, overfitting, and accidental scope expansion.
5. Report the evidence, hypothesis, changed files, policy proposals, and limits.

Read [the improvement protocol](references/improvement-protocol.md) for the detailed evidence and mutation procedure. If the target is `skill-improve` itself, read [its self-improvement guidance](references/self-improvement.md) as well.

Never mutate a Skill during normal execution. Do not require hidden/private chain-of-thought or introduce scoring, benchmark, judge, CI, telemetry, automatic collection/indexing, Agents, a CLI, or orchestration machinery.
