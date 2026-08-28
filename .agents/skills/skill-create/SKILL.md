---
name: skill-create
description: Create a focused repository-local Codex Skill from a user's capability request. Use when the user asks to create a new Skill; do not use to refine an existing Skill.
---

# Create a repository-local Skill

Create only the smallest native Skill that satisfies the requested capability. Work in the target repository and follow its applicable `AGENTS.md` instructions.

1. Establish the requested purpose, trigger conditions, expected outputs, exclusions, and narrow scope. Ask only for information needed to make those boundaries clear.
2. Inspect current repository authorities and only the repository evidence needed to ground the Skill. Do not copy volatile facts into the Skill.
3. Create the Skill at `.agents/skills/<skill-name>/SKILL.md` with `name` and a concise, trigger-oriented `description` front matter.
4. Keep its `SKILL.md` to applicability, purpose, boundaries, a high-level procedure, conditional reference routing, and an explicit self-improvement entry.
5. Create `references/self-improvement.md` in every generated Skill. Add other references only for actual complexity, including `references/repository/` only for stable repository-specific knowledge.
6. Report the created files, invocation, knowledge-placement decisions, and any repository-wide invariant candidate. Do not silently edit `AGENTS.md` for a candidate.

Read [the creation guide](references/creation-guide.md) when choosing the Skill shape, classifying knowledge, or writing the generated self-improvement path. Read [this Skill's self-improvement guidance](references/self-improvement.md) only when the user explicitly asks to improve, refine, evolve, review for improvement, or update `skill-create` itself.

Normal creation does not revise an existing Skill. Do not create Agents, a CLI, a registry, a service, automatic routing, or evaluation infrastructure.
