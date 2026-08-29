# Self-improvement guidance

Use this guidance only after the user explicitly asks to improve, refine, evolve, review for improvement, or update `workflow-skill-create`. Normal use never mutates this Skill.

1. Establish this Skill's current purpose, scope, `SKILL.md`, and relevant references.
2. Use only session logs or other observable evidence the user selected. Inspect repository evidence only when needed to interpret that observation; do not search or collect `.skill-lab/`, internal sessions, or hidden reasoning.
3. Form an explicit, evidence-backed hypothesis. Classify each proposed knowledge change as portable Skill behavior, stable repository-specific knowledge, a repository-wide invariant candidate, or a volatile fact to rediscover at runtime.
4. Make the smallest Skill-local, scope-preserving update: add, remove, merge, simplify, rewrite, or relocate guidance. A template-wide or repository-wide invariant conflict is a proposal, not a silent change.
5. Check progressive disclosure, duplication, contradiction, stale facts, overfitting, scope expansion, and the workflow failure lenses below. Report selected evidence, hypothesis, changed files, knowledge decisions, validation, and limits.

Use workflow-specific observations when relevant: incorrect phase order; invalid component routing; incomplete, ambiguous, or wrongly owned handoff; repeated authority discovery; premature transition; missing stop; unnecessary approval or gate; duplicated component responsibility; over-orchestration; unnecessary reference loading; unclear entry or exit; evaluation-only activation that could compete with production; or transition semantics imported without target authority.

Do not add automatic session collection, scoring, benchmarks, judges, CI evaluation, Agents, routers, registries, execution engines, or autonomous mutation.
