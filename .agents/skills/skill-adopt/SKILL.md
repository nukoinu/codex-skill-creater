---
name: skill-adopt
description: Safely inspect or adopt repository-local Skill-development capabilities into an existing active repository. Use for adoption assessment, proposal, install, or apply requests; not for new-repository setup, migration, or general installation.
---

# Adopt the Skill-development loop

Use this Skill only for an existing active repository that needs the Issue #1 Skill-development loop. For an empty or new repository, direct template use may be appropriate instead.

Inspect applicable repository authority before proposing or changing anything. This Skill adopts only the focused `skill-create` / `skill-improve` capability and its necessary supporting invariants; it does not bootstrap, refactor, migrate, manage policy, synchronize, update, track versions or ownership, create Agents, or bulk-convert Skills.

- For `inspect`, `assess`, or `show adoption plan`, inspect, classify, report a concrete proposal, and stop without mutation.
- For explicit `adopt`, `install`, or `apply`, inspect and propose first, then apply the compatible minimum without a redundant confirmation when there is no material conflict.
- Handle a clean repository with the minimum additions; reuse equivalent behavior in a partial repository; and surface a material conflict for user choice. Do not make a non-conflicting change when it would leave an inconsistent partial adoption.

Read [the adoption protocol](references/adoption-protocol.md) for the focused inspection, required behavioral-contract equivalence, proposal, and application procedure. Normal use never changes this Skill. Read [self-improvement guidance](references/self-improvement.md) only after an explicit request to improve, refine, evolve, review for improvement, or update `skill-adopt` itself.
