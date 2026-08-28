# Creation guide

Use this guide only while creating a new repository-local Skill or when its detail is needed to interpret a creation request.

## Establish the capability

Before writing files, identify:

- the user problem the Skill addresses;
- when it should and should not trigger;
- the expected outcome or artifact;
- boundaries that keep it from becoming a general-purpose workbench; and
- the target repository root and its applicable `AGENTS.md` instructions.

Inspect only the authorities and repository evidence required to make the Skill useful. Do not persist branch state, issue state, current module layouts, or other facts that can become stale.

Choose a lowercase, hyphenated directory and `name` that represent the established capability. Write a concise `description` that begins with its primary use case and includes clear trigger words and a boundary. The description is used for Skill discovery, so do not make it a long specification.

## Start with the smallest native shape

Create:

```text
.agents/skills/<skill-name>/
├── SKILL.md
└── references/
    └── self-improvement.md
```

`SKILL.md` must have YAML front matter with `name` and `description`, followed by compact instructions. It should contain only:

- applicability, purpose, and boundaries;
- high-level execution steps;
- explicit conditions for reading each reference; and
- the explicit-only self-improvement entry.

Add a general reference for a long procedure, domain rule, or example only when the current capability needs it. Do not add scripts, assets, `agents/openai.yaml`, a CLI, or empty directories merely for future use.

## Classify each item before storing it

| Item | Destination | Required behavior |
| --- | --- | --- |
| Repository-wide stable invariant | `AGENTS.md` candidate | Report it; do not silently edit `AGENTS.md`. Only edit it if the user explicitly requested that repository-wide rule change. |
| Stable portable Skill behavior | `SKILL.md` when execution-critical, otherwise a general `references/` file | Keep `SKILL.md` concise. |
| Stable repository-specific Skill knowledge | `references/repository/<focused-topic>.md` | Create this directory and file only when the stable knowledge is needed by this Skill. |
| Volatile/current repository fact | Runtime discovery from the authoritative repository source | Do not persist a copy as Skill knowledge. |

## Give every generated Skill an improvement path

Create `references/self-improvement.md` from the first version. Its `SKILL.md` must state that normal execution does not mutate the Skill and route to that reference only after an explicit user request to improve, refine, evolve, review for improvement, or update the Skill.

The generated reference must instruct the Skill to:

1. establish its current purpose, scope, `SKILL.md`, and relevant references;
2. inspect only session logs explicitly selected by the user and only observable evidence in them;
3. inspect repository evidence only when needed to interpret the observation;
4. form an explicit, evidence-backed improvement hypothesis and classify each proposed knowledge change;
5. make the smallest Skill-local change, including adding, removing, merging, simplifying, rewriting, or relocating guidance;
6. check progressive disclosure, duplication, contradiction, stale facts, overfitting, and scope expansion; and
7. report changed files and the evidence that justified them.

The reference must preserve the Skill's established identity and scope. A template-wide or repository-wide invariant conflict is a proposal, not a silent mutation. It must never require hidden/private chain-of-thought, automatic session collection, scoring, benchmarks, a judge, CI evaluation, or autonomous mutation.

## Route to existing Skills only when compatible

Apply this procedure only when the generated Skill would explicitly name, link to, depend on, or instruct use or reading of an existing Skill. Inspect only that candidate target's entry contract and only the minimum needed to decide the exact proposed routing condition:

- its name and description;
- its applicability or use conditions;
- its explicit exclusions or do-not-use boundaries;
- its high-level responsibility; and
- entry-level routing guidance needed to resolve the question.

Compare that contract with the exact generated condition. A route is valid only when the condition is semantically permitted and does not contradict an exclusion or select an incompatible workflow phase. Related terminology, an adjacent owner, shared Issue/Contract context, historical neighboring work, or useful facts do not establish compatibility. Read a deeper target reference only if its entry contract leaves this concrete decision ambiguous; do not preload unrelated Skills or references.

For an invalid or materially unresolved candidate, use the first applicable outcome:

1. Do not route to it; use the repository's proper authority or source directly.
2. Route to another existing Skill whose entry contract permits the condition.
3. Add focused local guidance or a reference to the generated Skill when that is the narrowest valid design.
4. Report a material ownership or routing conflict for user decision when no valid route can be established.

Do not broaden or rewrite a target Skill as a creation side effect, invent cross-Skill ownership, or force an adjacent Skill outside its contract.

## Finish

Before completing, qualitatively validate every explicitly routed existing Skill: the target exists; its entry contract permits the condition; no target exclusion or generated instruction is contradicted; it is not an adjacent-only or incompatible-phase route; compatible existing guidance is not needlessly duplicated locally; and no required repository authority was replaced merely for routing convenience. Keep this validation targeted to the selected candidates, not a graph, repository-wide analyzer, registry, or CI check.

Report the native path, expected `$<skill-name>` invocation, created references, knowledge decisions, and any proposal left for the user. Do not claim repository-specific knowledge was stored when runtime discovery is the correct treatment.
