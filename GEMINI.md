# Vibsync team context

Vibsync is the team's long-term memory and live work context for AI coding
agents. It is not an agent orchestrator, and Git remains the source of truth for
code.

When starting work:

1. Call `onboard` before planning or editing. If it is unavailable, call
   `recall` with the query `handoff` and read the team's `START HERE` memory.
2. Before editing shared files, call `check_conflicts`, then `claim` the files
   you intend to change. Claims coordinate intent; they are advisory, not hard
   locks.
3. Release claims when the work is complete.

While working:

- Use `remember` for durable decisions, discoveries, constraints, and gotchas.
- Use `ask`, `inbox`, `reply`, and `resolve` for asynchronous team questions.
- Use the task tools to coordinate ownership and status.
- Never store credentials, secrets, personal data, or other sensitive material
  in shared memory.
