---
name: project-dashboard
description: Resume project work from an existing root STATUS.md, or update that file when explicitly requested. Use for project handoffs and continuation, not every new conversation.
---

Save tokens across threads with one file.

When resuming project work, read `STATUS.md` in the repo root if it exists.
State your understanding briefly. Ask a question only when a missing or conflicting fact prevents progress.
If there is no status file, proceed with normal, scoped investigation. Do not create one unless asked.

Treat the status file as a handoff, not proof of the current state. Verify relevant facts against the code and available evidence. Reuse its context to avoid unnecessary full-codebase scans, but inspect whatever the task requires.

To save work, rewrite `STATUS.md` only when the human asks or runs this skill. Write these four sections:

1. Last state: what was true before this thread.
2. Changed: what changed in this thread, with file paths.
3. Next: what remains.
4. Human: last human decision and open request.

Keep each section under 5 lines. Write facts, not summaries.

