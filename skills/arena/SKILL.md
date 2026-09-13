---
name: arena
description: "Compare two independent candidates for the same task, choose a base, combine useful improvements, and verify the result. Use for /arena, 'arena this', 'throw it in the arena', or an explicit request to compare alternative solutions."
disable-model-invocation: true
---

# Arena

Produce two candidates for the same task. Compare their results against the user's requirements, choose a base, and incorporate useful improvements from the other candidate. Verify the final result.

## Phase A: Define the task

1. State the artifact each candidate should produce and the permitted scope of changes.
2. Define a few concrete comparison criteria based on the user's requirements. Give both candidates the same task, requirements, and source material.
3. Use two candidates by default. Add more only when the user requests them.
4. Give each candidate its own output location. For code changes, use separate worktrees when available or separate working copies. For standalone artifacts, use separate folders in the environment's temporary directory. Do not let candidates write to the same files, branch, or external resource.

Candidate setup:

- Agent role: independent solution candidate.
- Preferred model: `gpt-5.6-terra` for ordinary tasks; `gpt-5.6-sol` for complex tasks involving multiple components or difficult constraints.
- Reasoning effort: `medium`.
- Fast mode: disabled.
- Use the environment's supported configuration or tool parameters. Report any model, reasoning, or fast-mode setting that cannot be applied or verified. When working directly, use the current session and disclose any difference from the preferred setup.
- If this model is unavailable, report that before using another model.
- Modify only the candidate's assigned files within the user's authorized scope. Do not publish or modify external state unless explicitly authorized.

## Phase B: Produce candidates

Launch the candidates in parallel using the environment's available delegation tool. Give each the shared task, its output location, and instructions to return the artifact plus a short explanation of its decisions. Keep candidates from reading each other's results before they finish.

If parallel execution is unavailable, run separate candidate agents sequentially. If delegation is unavailable, produce two alternatives directly and disclose that they are not independent agent attempts.

If a candidate fails, inspect the cause before retrying. With one usable candidate, report that the comparison is incomplete; do not present it as a winning consensus. With no usable candidates, report the failure rather than selecting a base.

## Phase C: Compare and choose

The main agent reads both candidates and compares them against the criteria. Check concrete behavior and relevant test results, not just the candidates' descriptions of their work. When candidates meet the requirements equally well, prefer the simpler result that is easier to maintain.

Use a separate judge only when the user requests one or a consequential, unresolved tradeoff would benefit from independent review. Explain that reason before launching it. Wait until candidates finish writing, then give the judge both artifacts and the comparison criteria.

Optional judge setup:

- Agent role: independent reviewer of completed candidates.
- Preferred model: `gpt-5.6-sol`.
- Reasoning effort: `medium`.
- Fast mode: disabled.
- Use the environment's supported configuration or tool parameters. Report any model, reasoning, or fast-mode setting that cannot be applied or verified. When working directly, use the current session and disclose any difference from the preferred setup.
- If this model is unavailable, report that before using another model.
- Do not modify files or external state. Use enforced read-only permissions when supported.

Agreement is supporting evidence, not proof of correctness. Disagreement can reflect legitimate tradeoffs, missing evidence, or different interpretations. Inspect the reasons and verify decisive claims before choosing.

Different solutions do not by themselves mean the task was underspecified. Clarify or rerun only when a specific missing requirement or failure justifies it.

## Phase D: Combine useful improvements

Choose one candidate as the base. Incorporate improvements from the other only when they help meet the requirements without unnecessary complexity. Keeping the base unchanged is valid when nothing else improves it.

Record the choice and any incorporated or rejected ideas in a short note. Include the judge's reasoning if a judge was used.

## Phase E: Verify

Verify the final artifact against the original requirements using appropriate tests, direct inspection, or an actual feature run. Candidate agreement does not replace verification. Recheck affected behavior after combining changes.

If verification fails, diagnose the actual cause. It may be an implementation bug, a problem introduced while combining candidates, a mistaken requirement, or a faulty check. Fix the cause and repeat the affected verification. Do not restart the entire comparison without a concrete reason.

## Output

Return the final artifact and a short comparison note explaining the choice, incorporated improvements, verification results, and any remaining limitations. Keep the note in the response unless the user requests a file or the project requires one.
