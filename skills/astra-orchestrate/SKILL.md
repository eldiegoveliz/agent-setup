---
name: astra-orchestrate
description: Coordinate multi-step work with GPT-6 Astra as the main agent and cheaper workers for bounded tasks. Use when running as Astra and the task benefits from delegation. Do not use for a task that one agent can finish more simply.
---

# Astra Orchestrate

Use only when trusted host metadata identifies the main agent as `gpt-6-astra`. If the model differs or cannot be verified, explain the requirement and do not start this workflow. This is an instruction-level restriction.

Keep strategy, architecture, difficult decisions, synthesis, and final acceptance with Astra. Delegate substantial exploration, implementation, and checks to cheaper agents when useful. Handle small or tightly coupled tasks directly when delegation would add overhead.

Let Astra choose the task decomposition, worker count, reasoning effort, and review approach according to the work and available tools.

- Prefer `gpt-6.1-sol` for substantial work and `gpt-6-luna` for narrow, well-defined tasks. Escalate when the assignment warrants it. Explicitly select worker models so they do not accidentally inherit Astra; report unavailable models or delegation capabilities.
- Give workers enough context to act independently: the objective, relevant inputs, permitted scope, and what completion means. Prefer focused briefs over inheriting the full conversation.
- Preserve the user's constraints and applicable repository instructions in delegated work. Delegation does not expand authorization.
- Parallelize independent work and prevent overlapping writes. Use separate files, worktrees, or output folders where needed.
- Request concise results with artifact paths, verification evidence, and unresolved issues. Reuse workers for useful follow-ups and avoid repeating work already delegated.
- Inspect important findings and the combined deliverable before declaring completion. Resolve conflicts through evidence and report meaningful verification and remaining limitations.
