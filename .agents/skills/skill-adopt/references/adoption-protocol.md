# Adoption protocol

Use this procedure only to inspect or explicitly adopt the Issue #1 Skill-development loop into an existing active repository. It is a user-driven procedure, not an installer, migration framework, synchronizer, update system, version tracker, ownership system, Agent framework, or bulk Skill converter.

## 1. Inspect before proposing or mutating

Establish the repository root and active working scope. Read the applicable root and nested `AGENTS.md` hierarchy before inspecting or proposing changes. Then inspect only the artifacts needed for adoption compatibility:

1. Find the native Skill location actually used by the repository, its existing Skill names, and its local terminology.
2. Read only Skills relevant to Skill creation, improvement, or adoption. Determine whether `skill-create`, `skill-improve`, or equivalent capabilities already exist, and whether the repository has its own authoring or improvement mechanism.
3. Inspect `.gitignore` only enough to determine whether `.skill-lab/` is effectively ignored, including through a broader matching rule.
4. Compare applicable repository authority and every relevant `skill-create` / `skill-improve` capability to the required behavioral contract below. This comparison is about behavior, not copied template text.

Do not mutate during this inspection, crawl unrelated source or domain files, search or collect `.skill-lab/` sessions, or persist adoption state or metadata. Treat current repository facts as runtime discoveries.

## 2. Form a concrete adoption proposal

Before any mutation, report a repository-specific proposal with:

- classification: `clean`, `partial`, or `conflict`;
- files to add;
- exact files and focused sections to modify;
- files intentionally left unchanged, including existing authorities;
- existing rules and capabilities to reuse;
- the exact smallest `AGENTS.md` addition, if one is genuinely required;
- the exact smallest `.gitignore` addition, if one is genuinely required;
- conflicts, concrete alternatives, and any user decision required; and
- preservation checks and post-application validation.

When an existing capability is not contract-equivalent, name each missing required behavior and the smallest compatible adaptation needed. Do not describe a capability as equivalent merely because it is useful at a high level.

This is a procedural report, not persisted metadata or a generalized planning artifact. For inspection-only intent, stop after it and make no repository changes.

## 3. Assess required behavioral-contract equivalence

Keep these findings distinct:

- **Same name:** a local Skill uses `skill-create` or `skill-improve` as its name.
- **Same high-level purpose:** it appears to create or improve Skills.
- **Full required behavioral-contract equivalence:** it preserves every applicable requirement in this section.

Only full required behavioral-contract equivalence permits reuse or acceptance as equivalent. Template wording, organization, terminology, and reference splitting may follow target-native conventions; byte equality is not required. **Adapt structure when needed; do not adapt away required behavior.** A capability that omits any required invariant is `partial` or `conflict` according to its impact, never equivalent.

### Downstream `skill-create` checklist

An accepted or adapted `skill-create` equivalent must ensure every newly generated Skill, from version one:

- is created in the repository's native Skill location with valid native `SKILL.md` metadata and concise instructions;
- uses `references/` for progressive disclosure when detail is needed;
- has an explicit self-improvement path, normally `references/self-improvement.md` or a semantically equivalent progressively disclosed reference;
- permits self-improvement only after an explicit request, using only user-selected observable session evidence plus repository evidence necessary to interpret it;
- classifies knowledge correctly: repository-wide stable rules as proposals, stable portable behavior in concise instructions or general references, stable repository-specific knowledge in focused repository references only when needed, and volatile facts through runtime discovery from authoritative sources;
- preserves the generated Skill's established identity and scope during refinement; and
- treats repository-wide or template-wide policy changes as proposals rather than incidental Skill mutations.

Generated-Skill self-improvement is mandatory, not optional, deferred, or added after an observed failure. The downstream `skill-create` itself must also retain an explicit self-improvement path.

### Downstream `skill-improve` checklist

An accepted or adapted `skill-improve` equivalent must require an explicit target Skill and explicit improvement request, then:

- uses only user-selected evidence; never automatically discovers, collects, or indexes logs;
- evaluates observable evidence rather than hidden/private reasoning, and reads only repository evidence necessary to interpret it;
- forms an explicit hypothesis and applies the smallest supported Skill-local mutation;
- permits adding, removing, merging, simplifying, rewriting, or relocating guidance;
- checks for contradiction, duplication, stale facts, overfitting, and scope drift;
- treats repository-wide or template-wide policy changes as proposals; and
- retains an explicit self-improvement path for `skill-improve` itself.

### Development-Skill self-hosting

The adopted loop remains self-hosting: `skill-improve` can refine downstream `skill-create`, `skill-improve`, and retained `skill-adopt` from user-selected observable creation, improvement, or adoption sessions under these same rules. When retained or installed, `skill-adopt` must remain progressively disclosed and explicitly self-improvable. Normal execution of each Skill remains non-mutating.

Classify the inspected state lightly:

- **Clean:** no material conflict. On explicit `adopt`, `install`, or `apply`, add only the necessary compatible behavior.
- **Partial:** compatible rules or superficially similar capabilities already exist but one or more required behaviors are missing. Identify each omission explicitly. Reuse only the already contract-equivalent behavior; add only the genuinely missing compatible behavior when the result remains consistent.
- **Conflict:** a same-name Skill has a different responsibility, a required invariant conflicts with repository authority, the local Skill architecture is materially incompatible, or required behavior would materially change established practice. Identify the incompatible part and concrete alternatives. Do not overwrite, silently rename, replace, or reinterpret existing authority. Apply non-conflicting work only when it cannot create an inconsistent partial adoption; otherwise stop before mutation.

A differing template version alone is not a conflict. Missing any required invariant is explicitly `partial` or `conflict`, never equivalent.

## 4. Apply only an explicitly authorized compatible minimum

An explicit `adopt`, `install`, or `apply` request authorizes application after the required inspection and proposal. Do not request another confirmation unless a material conflict needs the user's decision.

When handling existing `AGENTS.md`:

1. Never replace it.
2. Decide semantic equivalence before proposing wording.
3. Do not duplicate equivalent rules; add only missing invariants actually required by the adopted behavior.
4. Preserve existing terminology, structure, and hierarchy, and keep Skill procedures in Skills rather than moving them into `AGENTS.md`.
5. Return a material policy conflict to the user rather than rewriting it by assumption.

When handling Skills:

- Never overwrite a Skill directory, silently rename a Skill, bulk-migrate Skills, bulk-retrofit progressive disclosure, or bulk-add self-improvement paths.
- Reuse a `skill-create` or `skill-improve` capability only when it passes the applicable full behavioral-contract checklist. With explicit authorization, adapt only the missing behavior and only by the smallest target-repository-compatible change that reaches contract equivalence.
- For a same-name Skill with a materially different responsibility, require a user-approved alternate name or explicit replacement decision.
- When needed and compatible, install only the missing current `skill-create` / `skill-improve` behavior into the repository's own native Skill location. Prefer current template structure when no local adaptation is needed. Installed Skills are target-repository-owned: add no template runtime dependency, synchronization, update check, version or registry data, lockfile, or ownership marker.

If restoring a required behavior would materially conflict with existing repository authority, surface that conflict for user resolution. Do not weaken the contract, request an extra approval when adoption is already explicit and no material conflict exists, or leave an inconsistent partial adoption.

If the improvement workflow is adopted, ensure `.skill-lab/` is effectively ignored. Preserve `.gitignore`; treat broader coverage as sufficient and otherwise add only the smallest missing rule. Do not create the directory, placeholders, session contents, a schema, collector, or indexer.

## 5. Validate and report

Perform focused, manual, qualitative validation; do not add a harness, benchmark, numerical score, CI evaluator, LLM judge, synchronizer, registry, or automatic repair. Confirm the proposal preceded mutation; no existing `AGENTS.md`, `.gitignore`, or Skill was wholesale overwritten; no contract-equivalent rule or capability was duplicated; and no template dependency or prohibited infrastructure was introduced. Verify native Skill discovery and effective `.skill-lab/` ignore coverage when the improvement workflow is installed.

Where a capability is installed, adapted, or reused, verify its applicable contract explicitly:

- **`skill-create`:** native discovery and progressive-disclosure routing; every generated Skill gets its explicit self-improvement path from version one; that path preserves explicit-only mutation, selected-evidence boundaries, scope preservation, and knowledge classification; and `skill-create` itself is explicitly self-improvable.
- **`skill-improve`:** selected evidence only; no hidden/private reasoning; valid simplifying, removing, merging, rewriting, or relocating actions; target identity and scope preservation; and `skill-improve` itself is explicitly self-improvable.
- **Retained `skill-adopt`:** progressive-disclosure routing; explicit self-improvement; and validation based on behavioral-contract equivalence rather than name or purpose similarity.

Use the ASTER-640 PR #753-shaped state as a regression check: a downstream `skill-create` that creates Skills and routes detail through references but does not require generated-Skill self-improvement from version one, and whose `skill-create` and `skill-improve` lack their own explicit self-improvement paths, is incomplete/partial and must not be declared equivalent or adoption-complete.

Report applied files, preserved files, reused behavior, missing requirements, validation results, conflicts or limitations, and any decision still required.
