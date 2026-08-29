# Codex Skill Creator

A small, repository-portable template for creating and explicitly improving repository-local Codex Skills from real usage evidence. It provides only the Skill lifecycle; it is not a workbench, Agent framework, or evaluation platform.

## Hands-on: choose the repository path

### Empty or new repository

Direct template use or copying the template Skills into the repository-native `.agents/skills/` location may be appropriate. Then use the loop below. This repository can also use it to improve its own template Skills.

1. Invoke `$skill-create` for a focused component capability. For example: “Create a repository-local Skill that checks release notes against changed public APIs. It should identify missing or unsupported claims, but must not write release notes.” Invoke `$workflow-skill-create` when the request instead needs a Workflow Skill to connect existing capabilities through explicit phases, handoffs, routing, and stop conditions.
2. Inspect the created Skill. Its `SKILL.md` is concise, `references/self-improvement.md` is present from the first version, and `references/repository/` exists only if stable repository-specific knowledge was actually needed.
3. Use the new Skill on a real release-note task. Normal use never changes the Skill.
4. Manually place selected, observable session logs under `.skill-lab/sessions/` in the target repository. This template does not create the directories, collect logs, or impose a log format. You may also keep transient local analysis material in `.skill-lab/work/`.
5. Explicitly invoke `$skill-improve`, name the target Skill, and provide the selected log paths. It analyzes only those paths plus repository evidence needed to interpret them.
6. Inspect the reported, evidence-backed minimal change. Use the revised Skill on a later real task, then repeat when the user explicitly requests another improvement.

### Existing active repository

Start with `$skill-adopt`; do not wholesale copy this template repository's `AGENTS.md` into an active repository. That is unsupported because the active repository's authorities, Skills, and ignore rules come first.

```text
existing repository
→ $skill-adopt
→ inspect authorities / Skills / ignore state
→ concrete minimal proposal
→ resolve only material conflicts
→ reuse or install only compatible missing capabilities
→ verify Skill discovery and .skill-lab ignore coverage
```

`inspect`, `assess`, and `show adoption plan` produce that proposal and make no changes. Explicit `adopt`, `install`, or `apply` requests inspect and propose first, then apply compatible minimum changes without an extra approval gate unless a material conflict needs a decision. Existing `AGENTS.md`, `.gitignore`, and Skills are preserved; only full behavioral-contract equivalents are reused rather than duplicated or replaced. That contract includes generated-Skill self-improvement from version one and self-hosting of the adopted development Skills; the adoption protocol holds the detail.

Conceptual local workspace (entirely ignored by Git):

```text
.skill-lab/
├── sessions/
└── work/
```

## What is included

- `.agents/skills/skill-create/`: creates a focused repository-local native Codex Skill from a capability request.
- `.agents/skills/workflow-skill-create/`: creates a minimal repository-local Workflow Skill from a natural-language orchestration request.
- `.agents/skills/skill-improve/`: explicitly improves a selected Skill from user-provided observable session evidence.
- `.agents/skills/skill-adopt/`: inspects and safely adopts the Skill-development loop into an existing active repository through a concrete minimal proposal.
- `AGENTS.md`: concise stable invariants for the template and generated Skills.

Codex discovers repository Skills under `.agents/skills/`. Each Skill has a `SKILL.md` with `name` and `description` front matter; the description supports discovery, while detailed instructions live in conditionally read `references/`. See the [official OpenAI Skill documentation](https://learn.chatgpt.com/docs/build-skills).

`$skill-create` creates a component capability; `$workflow-skill-create` creates the orchestration that connects components. Workflow Skills own phase order, routing, handoffs, transitions, and stops, while component Skills own their behavior. When a workflow needs a missing capability, it reports the gap rather than assigning it to a neighboring Skill or creating it automatically; a separate explicit `$skill-create` request may add that capability.

## Knowledge placement

| Classification | Where it belongs |
| --- | --- |
| Repository-wide stable invariant | An `AGENTS.md` candidate. Report it; do not change it as a side effect of Skill improvement. |
| Stable portable Skill behavior | Concise `SKILL.md` guidance if execution-critical; otherwise a general `references/` document. |
| Stable repository-specific Skill knowledge | `references/repository/<focused-topic>.md`, only when genuinely stable and needed. |
| Volatile/current repository fact | Runtime discovery from its authoritative source; do not copy it into Skill knowledge. |

Stable guidance may be referenced; current facts are discovered.

## Evidence and self-improvement

Session evidence is user-owned. The template never searches `.skill-lab/` or Codex-internal locations, harvests or indexes sessions, uploads logs, or commits raw logs. It can use user requests, visible actions/output, tool results, commands, validation, repository changes, and available PR/review/test evidence. It never requires hidden/private chain-of-thought.

Every Skill created by `$skill-create` or `$workflow-skill-create` includes an explicit self-improvement path. Improvement is available only after an explicit request to improve, refine, evolve, review for improvement, or update the Skill. It may add, remove, merge, simplify, rewrite, or relocate guidance, but it preserves the Skill's identity and scope. A proposed change to a template-wide invariant is reported rather than silently applied.

An explicitly requested evaluation, shadow, or historical comparison may create a distinct same-purpose Workflow Skill. It is evaluation-only, leaves the production Workflow Skill unchanged, and must state that it cannot participate in normal implicit production routing. It remains non-production until a later explicit promotion or replacement decision; this template supplies no router, resolver, or comparison harness.

The template Skills are self-hosting: invoke `$skill-improve` with `skill-create`, `workflow-skill-create`, `skill-improve`, or `skill-adopt` as the target and user-selected sessions to refine that template Skill under the same rules.

## Lightweight checks

After copying or changing the template, verify:

- the Skills are under `.agents/skills/` and each `SKILL.md` has `name` and `description` front matter;
- `SKILL.md` files route detailed work and explicit self-improvement to `references/`;
- `git check-ignore -v .skill-lab/sessions/example.log` confirms the local workspace is ignored;
- no raw `.skill-lab/` files are tracked; and
- an active-repository adoption proposal precedes mutation, preserves existing authorities and Skills, and handles material conflicts before partial change; and
- the hands-on flow, `AGENTS.md`, and all four Skills use the same knowledge-placement and explicit-improvement rules.

Codex detects Skill changes automatically; restart it if a newly added or changed Skill does not appear.

## Out of scope

This template does not provide Agents, a CLI, a service, registry, marketplace, database, capability/update graph, cross-repository learning or synchronization, telemetry, automatic routing or session collection/discovery/indexing, benchmarks, numerical scoring, LLM judges, CI evaluation, or autonomous self-modification.
