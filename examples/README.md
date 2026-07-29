# Connection examples

Ready-to-copy MCP client configs for connecting to Vibsync at
`https://mcp.vibsync.com/mcp`.

| File | Client | Notes |
|---|---|---|
| `claude-code.mcp.json` | Claude Code | `.mcp.json` at the repo root (or `claude mcp add`) |
| `cursor.mcp.json` | Cursor | `~/.cursor/mcp.json` (global) or project `.cursor/mcp.json` |
| `vscode-copilot.mcp.json` | GitHub Copilot (VS Code, agent mode) | workspace `.vscode/mcp.json` — key is `servers` |
| `codex.config.toml` | Codex CLI | `~/.codex/config.toml`, uses a machine token via env var |

Browser sign-in (OAuth) needs no token; headless/CI uses a machine token issued in
the [console](https://console.vibsync.com). See the repo
[README](../README.md) for details.
