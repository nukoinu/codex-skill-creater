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

## Finish

Report the native path, expected `$<skill-name>` invocation, created references, knowledge decisions, and any proposal left for the user. Do not claim repository-specific knowledge was stored when runtime discovery is the correct treatment.
