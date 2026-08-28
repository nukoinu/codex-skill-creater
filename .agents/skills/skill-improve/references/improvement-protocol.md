# Improvement protocol

Use this protocol only after the user explicitly requests improvement and supplies a target Skill plus selected session-log path or paths. It is qualitative and evidence-driven; it is not a scoring, benchmark, or judge system.

## 1. Establish the target and evidence boundary

Read the target Skill's `SKILL.md`, relevant references, and applicable `AGENTS.md` instructions. State its current purpose, boundaries, expected behavior, and the exact user-selected session logs to inspect.

Read no other session logs. Do not scan `.skill-lab/`, discover Codex-internal log locations, harvest sessions, build an index, upload evidence, or assume a fixed log representation.

Use only observable evidence that is available, such as:

- user requests;
- visible assistant actions and final output;
- tool calls and results;
- commands and validation results;
- resulting repository changes; and
- relevant PR, review, or test evidence.

Never make correctness depend on hidden/private model reasoning.

## 2. Analyze observed behavior

Use lenses relevant to the target Skill's purpose, as applicable: intent satisfaction, authority/context discovery, decision quality, scope discipline, tool use, unnecessary work, progressive disclosure, validation proportionality, error recovery, and outcome quality. For evaluative Skills, false positives and false negatives may also matter.

Identify strengths and material weaknesses, including failures, ambiguity, missing or over-guidance, poor reference routing, tool misuse, scope drift, or stale guidance. Separate what the session directly supports from an inference. One session may justify a change when a defect is clear and materially supported; when the conclusion is ambiguous or context-specific, request or rely on additional user-supplied evidence before generalizing.

Inspect repository authorities, state, diffs, tests, or reviews only when they are needed to interpret observed behavior correctly. Treat current repository facts as runtime discoveries, not new persistent Skill knowledge.

## 3. Hypothesize, classify, and change minimally

Write a concrete hypothesis in terms of the target Skill's established purpose, for example: "The Skill needs a conditional check for authoritative repository instructions because the selected session skipped them." Do not redefine the Skill's identity or broaden its responsibility.

Classify every proposed piece of knowledge:

| Classification | Action |
| --- | --- |
| Repository-wide stable invariant | Report an `AGENTS.md` candidate; do not change it unless the user explicitly requested that repository-wide policy change. |
| Stable portable Skill behavior | Keep concise execution-critical instruction in `SKILL.md`; otherwise use a general reference. |
| Stable repository-specific Skill knowledge | Add a focused `references/repository/<topic>.md` only if needed and stable. |
| Volatile/current repository fact | Do not persist it; use an authoritative runtime discovery step. |

Apply the smallest effective Skill-local change. Valid changes include adding, removing, merging, simplifying, rewriting, or relocating content to or from a reference. Prefer a smaller, clearer Skill over accumulated instructions. Create or remove references only when that improves progressive disclosure.

## 4. Review and report

Before completing, check that the edit:

- preserves the target Skill's established scope and boundaries;
- keeps `SKILL.md` concise with conditional reference routing;
- has no duplication, contradiction, stale facts, or obvious overfitting;
- leaves normal execution non-mutating; and
- does not add prohibited infrastructure or a silent template-wide policy change.

Report the selected evidence, observations, hypothesis, changed files, knowledge-placement decisions, and any unresolved uncertainty. If a template-wide invariant would need changing, report a proposal rather than applying it as an improvement side effect.
