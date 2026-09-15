---
name: project-dashboard
description: Carry context across threads with one status file. Use when you start a thread, resume work, or want to skip re-reading the codebase.
---

Save tokens across threads with one file.

To start work, read `STATUS.md` in the repo root first.
State where you think you are in two lines.
Then ask the human one question: what is wrong or missing in that guess.

Do work from the answer. Do not rescan the codebase to rebuild context.

To save work, rewrite `STATUS.md` only when the human asks or runs this skill. Write these four sections:

1. Last state: what was true before this thread.
2. Changed: what changed in this thread, with file paths.
3. Next: what remains.
4. Human: last human decision and open request.

Keep each section under 5 lines. Write facts, not summaries.

