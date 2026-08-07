---
name: Vibsync setup
description: Use when installing or connecting the Vibsync MCP server (the shared team brain for AI coding agents), or troubleshooting why Vibsync tools (onboard, recall, remember) aren't available or a connection isn't showing. Covers the one-time browser OAuth connect, team approval, and verifying the first handoff.
---

# Vibsync setup & troubleshooting

Vibsync gives your AI coding agents a shared team brain — long-term memory of
decisions and product knowledge, async agent Q&A, task coordination, and
file-claim conflict avoidance — over a remote MCP server at
`https://mcp.vibsync.com/mcp`. On connect, the server itself tells the agent how
to use its tools; this skill only covers getting connected and verifying it.

## Connect (one time)

1. This plugin bundles the Vibsync MCP server. On first use, Claude Code opens
   your browser to sign in and authorize. When asked, approve the **team** you
   want to work in. No token or secret to copy — it's browser OAuth.
2. Confirm it's live: call the `whoami` tool — it returns your team and member.
   Then call `onboard` to pull the team's current context.

> Installing the plugin is not the same as connecting. A connection exists only
> after you complete the browser OAuth above and your agent makes a real request.

## Verify the handoff (the whole point of Vibsync)

1. Save one real decision: ask the agent to record it with `remember`
   (e.g. "API errors use RFC 9457 Problem Details").
2. Start a **new** conversation in the same project and ask, citing the source:
   "From Vibsync, what did we decide for this project? Cite the source."
   If it answers **from Vibsync**, the handoff works — that's Vibsync, not the
   tool's own memory.

## Troubleshooting

- **Vibsync tools missing:** confirm the plugin is installed and enabled
  (`/plugin`), then complete the one-time browser OAuth above.
- **Wrong or empty team:** you may have authorized a different team, or the team
  is new and empty. A credential belongs to exactly one team, so connect again
  to work in another team.
- **Handoff didn't carry over:** make sure it's a NEW conversation in the same
  project, that the reply cites Vibsync, and that the earlier `remember` actually
  saved.

Docs: https://vibsync.com/getting-started
