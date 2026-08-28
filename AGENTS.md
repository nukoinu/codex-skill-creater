# Template invariants

- Keep every Skill progressively disclosed: keep `SKILL.md` concise and read detailed `references/` only when relevant.
- Classify knowledge before persisting it:
  - repository-wide stable invariant: an `AGENTS.md` candidate;
  - stable portable Skill behavior: concise `SKILL.md` guidance or a general reference;
  - stable repository-specific Skill knowledge: `references/repository/<focused-topic>.md` only when needed;
  - volatile/current fact: discover it at runtime from its authoritative source; do not persist it as Skill knowledge.
- A Skill may mutate only for an explicit user request to improve, refine, evolve, review for improvement, or update it. Normal use never mutates the Skill.
- `.skill-lab/` is a user-owned, Git-ignored local workspace. Do not collect, discover, index, upload, or commit sessions automatically.
- Make the smallest evidence-backed change that preserves the Skill's established identity and scope. Simplify, merge, remove, or relocate guidance when evidence supports it.
- Never silently change these template-wide invariants. Report a conflicting policy or `AGENTS.md` change as a proposal unless the user explicitly requests that change.
