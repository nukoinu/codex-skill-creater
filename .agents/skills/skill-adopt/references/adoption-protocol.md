# Adoption protocol

Use this procedure only to inspect or explicitly adopt the Issue #1 Skill-development loop into an existing active repository. It is a user-driven procedure, not an installer, migration framework, synchronizer, update system, version tracker, ownership system, Agent framework, or bulk Skill converter.

## 1. Inspect before proposing or mutating

Establish the repository root and active working scope. Read the applicable root and nested `AGENTS.md` hierarchy before inspecting or proposing changes. Then inspect only the artifacts needed for adoption compatibility:

1. Find the native Skill location actually used by the repository, its existing Skill names, and its local terminology.
2. Read only Skills relevant to Skill creation, improvement, or adoption. Determine whether `skill-create`, `skill-improve`, or equivalent capabilities already exist, and whether the repository has its own authoring or improvement mechanism.
3. Inspect `.gitignore` only enough to determine whether `.skill-lab/` is effectively ignored, including through a broader matching rule.
4. Compare the applicable repository authority to the minimum Issue #1 invariants: progressive disclosure; explicit-only Skill mutation; user-owned, uncommitted local session evidence; smallest evidence-backed change; and repository-wide policy changes as proposals rather than incidental Skill mutations.

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

This is a procedural report, not persisted metadata or a generalized planning artifact. For inspection-only intent, stop after it and make no repository changes.

## 3. Assess compatibility

Classify the inspected state lightly:

- **Clean:** no material conflict. On explicit `adopt`, `install`, or `apply`, add only the necessary compatible behavior.
- **Partial:** compatible rules or equivalent capabilities already exist. Reuse them unchanged when they provide the required behavior; add only genuinely missing behavior when the result remains consistent.
- **Conflict:** a same-name Skill has a different responsibility, a required invariant conflicts with repository authority, the local Skill architecture is materially incompatible, or required behavior would materially change established practice. Identify the incompatible part and concrete alternatives. Do not overwrite, silently rename, replace, or reinterpret existing authority. Apply non-conflicting work only when it cannot create an inconsistent partial adoption; otherwise stop before mutation.

Semantic and behavioral equivalence, not byte-for-byte template text, determines reuse. A differing template version alone is not a conflict.

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
- Reuse an equivalent `skill-create` or `skill-improve` capability as-is. Adapt it only when explicitly authorized and compatible.
- For a same-name Skill with a materially different responsibility, require a user-approved alternate name or explicit replacement decision.
- When needed and compatible, install only the missing current `skill-create` / `skill-improve` behavior into the repository's own native Skill location. Installed Skills are target-repository-owned: add no template runtime dependency, synchronization, update check, version or registry data, lockfile, or ownership marker.

If the improvement workflow is adopted, ensure `.skill-lab/` is effectively ignored. Preserve `.gitignore`; treat broader coverage as sufficient and otherwise add only the smallest missing rule. Do not create the directory, placeholders, session contents, a schema, collector, or indexer.

## 5. Validate and report

Confirm the proposal preceded mutation; no existing `AGENTS.md`, `.gitignore`, or Skill was wholesale overwritten; no equivalent rule or capability was duplicated; and no template dependency or prohibited infrastructure was introduced. Verify native Skill discovery and effective `.skill-lab/` ignore coverage when the improvement workflow is installed. Report applied files, preserved files, reused behavior, validation results, conflicts or limitations, and any decision still required.
