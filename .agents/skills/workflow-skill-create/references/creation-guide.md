# Workflow Skill creation guide

Use this guide when creating a repository-local Workflow Skill. It records portable authoring behavior, not current repository facts. Discover current facts from their authoritative sources.

## Establish the workflow boundary

State the requested outcome, activation boundary, expected artifact, exclusions, and whether the request is production or an explicit evaluation-only comparison. Separate the requested work into:

- **workflow-owned orchestration:** ordering, phase entry and exit, routing, handoff relationships, conditions, and stops; and
- **component-owned behavior:** domain procedures, capability-specific decisions, and execution details.

A Workflow Skill may hold workflow-specific policy with no existing owner. It must not copy a component's procedure merely to make the workflow self-contained. If an existing production Workflow Skill has the same or materially overlapping purpose, inspect it as focused evidence and surface a material ownership or activation conflict rather than silently making ordinary production competitors.

## Discover only what the workflow needs

Inspect the applicable `AGENTS.md` hierarchy, native Skill location and conventions, existing same/overlapping Workflow Skills, and only the candidate component Skills actually considered. For each proposed edge that names, invokes, links to, or instructs reading a Skill, inspect its entry contract:

- name and description;
- applicability or use conditions;
- explicit exclusions;
- high-level responsibility; and
- only entry-level routing guidance needed for that edge.

Compare the exact proposed phase condition with that contract. Related terms, adjacent ownership, shared history, or useful information do not make a route valid. Read a deeper reference only when the entry contract leaves a concrete routing or handoff decision ambiguous. Do not preload unrelated Skills or construct a dependency graph.

For an invalid or unresolved edge, use the first applicable outcome:

1. Use direct repository authority or source when that is sufficient.
2. Use another existing component Skill whose entry contract permits the exact condition.
3. Keep narrow local orchestration guidance only when it is genuinely workflow-owned.
4. Report a missing capability or material ownership conflict for a user decision.

Never assign the gap to a neighboring Skill, broaden an existing Skill, reproduce component behavior to bypass its boundary, or automatically create a missing component. A user may separately and explicitly request `$skill-create` for that capability.

## Write material phases and handoffs

Use concise natural language. For every material phase, state enough of the following to prevent transition guesswork; omit fields that genuinely do not apply:

- purpose and entry condition;
- required input and responsible component Skill or direct authority;
- expected output and exit condition;
- handoff artifact or value and whether it is fixed authority or advisory context;
- which phase may modify or reinterpret it and what other authority the next phase must independently reacquire;
- conditional next step; and
- stop, retry, or user-return condition.

The Workflow Skill owns the relationship between one phase's output and the next phase's input. It does not invent the contents of a component's output. Derive any fresh or same-instance boundary, approval, validation gate, fixed input, authority reacquisition, or stop-on-conflict behavior from the target repository and component contracts. Do not encode example transitions from another repository as a general rule.

Make branches and stops plain: an ambiguous authority, missing required handoff, validation failure, missing capability, or repository-defined conflict must not silently advance. Do not introduce a DSL, formal state machine, engine, scheduler, runtime, or Agent/session execution model.

## Use progressive disclosure

Start with the smallest useful native shape:

```text
.agents/skills/<workflow-skill>/
├── SKILL.md
└── references/
    └── self-improvement.md
```

Keep `SKILL.md` to trigger conditions, scope, high-level phases and routing, material boundaries, conditional references, and explicit self-improvement. Add `references/workflow.md` only when detailed phase, handoff, or branch material would make the entry file unclear. Do not create empty directories or speculative references.

Every generated Workflow Skill must say that normal execution does not mutate it and link to its self-improvement path for an explicit request to improve, refine, evolve, review, or update it. That path uses only user-selected observable evidence, preserves identity and scope, and makes the smallest evidence-backed Skill-local change.

## Create an evaluation-only alternative only explicitly

For an explicit same-purpose evaluation, shadow, or historical-comparison request, an alternative Workflow Skill may coexist with production. It must have a distinct name and explicit evaluation-only activation language in both its description and body, so it cannot be implicitly selected for ordinary production work. Preserve the requested high-level outcome, inspect the production workflow as comparison evidence without mechanically copying it, leave production unchanged, and make promotion or replacement a later explicit choice.

Do not create resolver metadata, automatic routing, experiment assignment, a harness, a runner, a scheduler, a benchmark, or an experiment database. If equivalent tasks are later executed for comparison, the responsible repository workflow must isolate sessions, worktrees, or state as needed; this Skill does not execute that comparison.

## Validate and report

Qualitatively verify the new Workflow Skill against the request: its routes are contract-compatible, material handoffs and authority are clear, conditions and stops do not guess, component behavior is not duplicated, missing capabilities remain surfaced, and no framework machinery was introduced. Report created files and invocation, chosen routes and rejected candidates, phase/handoff semantics, knowledge-placement decisions, validation results, gaps, and conflicts or overlap left for the user.
