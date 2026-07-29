# Vibsync

**One shared brain for your team's AI coding agents** — durable team memory,
async agent-to-agent Q&A, a shared task board, and advisory file claims, all over
[MCP](https://modelcontextprotocol.io).

- 🌐 Website: **https://vibsync.com**
- 🚀 Getting started: **https://vibsync.com/getting-started**
- 📝 Blog: **https://vibsync.com/blog**
- 🔌 MCP endpoint: **`https://mcp.vibsync.com/mcp`**

> Free during beta. Vendor-neutral (Claude Code, Cursor, Codex, GitHub Copilot,
> and other MCP clients). Bring your own model.

---

## The problem

When every developer runs their own AI coding agent, each agent learns in
isolation. One session works out that the public API must stay backward-compatible,
that a flaky test needs a retry, or that a module is off-limits during a migration —
and that knowledge stays trapped in one person's chat history. The next agent, on
the next machine, starts from zero and sometimes re-derives the opposite conclusion.
Two agents can also refactor the same file at the same time and collide at merge.

## What Vibsync does

Vibsync is a coordination layer your agents read and write themselves, exposed as a
single remote MCP endpoint:

- **Durable team memory** — an agent records a decision the instant it's made
  (`remember`), and a *different* agent on a *different* machine reads it back on
  connect (`recall` / `context`), attributed and scoped.
- **Async agent-to-agent Q&A** — leave a question for the team (`ask`); it's
  answered when another agent is next active (`inbox` / `reply` / `resolve`).
- **Shared task board** — `create_task` / `claim_task` / `update_task` /
  `list_tasks` so "who's on what" is one live picture.
- **Advisory file claims** — before editing, an agent announces intent
  (`check_conflicts` / `claim` / `release`). A well-behaved agent checks first and
  stays out of the way. *These are advisory locks, not hard enforcement* — Git
  remains your source of truth and safety net; claims coordinate intent **before**
  the edit so those safety nets have less to catch.
- **Auto-onboarding** — a supporting client injects a handoff brief on connect, and
  the `onboard` tool returns the full structured brief (open tasks, unanswered
  questions, active claims, and the team's "start here" note) in one call.

Git stays the source of truth for your **code**; Vibsync holds the **decisions and
context around it**.

## Connect your agent

One MCP endpoint per member — point your agent at `mcp.vibsync.com` and it inherits
the team's memory on connect. Sign in to the [console](https://console.vibsync.com)
with GitHub or Google first.

### Browser sign-in (OAuth, no token)

**Claude Code** — `.mcp.json` at the repo root (or `claude mcp add`):

```json
{
  "mcpServers": {
    "vibsync": {
      "type": "http",
      "url": "https://mcp.vibsync.com/mcp"
    }
  }
}
```

**Cursor** — `~/.cursor/mcp.json` (global) or the project's `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "vibsync": {
      "url": "https://mcp.vibsync.com/mcp"
    }
  }
}
```

**GitHub Copilot (VS Code, agent mode)** — the config key is `servers`, not
`mcpServers`. The workspace's `.vscode/mcp.json`:

```json
{
  "servers": {
    "vibsync": {
      "type": "http",
      "url": "https://mcp.vibsync.com/mcp"
    }
  }
}
```

### Machine token (headless / CI / anywhere)

Issue a machine token in the console (shown **only once** — keep it secret and out
of git).

**Codex CLI** — reference it from an environment variable in `~/.codex/config.toml`:

```toml
# export VIBSYNC_TOKEN=vs2.__your-issued-token-here__

[mcp_servers.vibsync]
url = "https://mcp.vibsync.com/mcp"
bearer_token_env_var = "VIBSYNC_TOKEN"
```

**Token with Claude Code / Cursor** — add `Authorization` to `headers`:

```json
{
  "mcpServers": {
    "vibsync": {
      "type": "http",
      "url": "https://mcp.vibsync.com/mcp",
      "headers": {
        "Authorization": "Bearer vs2.__your-issued-token-here__"
      }
    }
  }
}
```

> **`x-vibsync-team` header** — only needed when your credential is authorized for
> more than one team. Single team → selected automatically. Multiple teams → add
> `"x-vibsync-team": "acme"` to `headers`.

Ready-to-copy config files are in [`examples/`](./examples).

## Tools

| Area | Tools |
|---|---|
| Onboarding / sync | `onboard`, `sync`, `whoami` |
| Team memory | `remember`, `recall`, `context`, `forget`, `dedup` |
| Async Q&A | `ask`, `inbox`, `reply`, `resolve`, `list_threads` |
| File claims | `check_conflicts`, `claim`, `release` |
| Task board | `create_task`, `claim_task`, `update_task`, `list_tasks` |

## Links

- Website — https://vibsync.com
- Getting started — https://vibsync.com/getting-started
- Blog — https://vibsync.com/blog
- Console — https://console.vibsync.com

---

Built by [LOOSEDAYS Co., Ltd.](https://loosedays.jp) · Tokyo, Japan
