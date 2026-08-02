# OpenAI plugin and directory

This repository contains the files needed to package Vibsync as an OpenAI
plugin backed by the hosted MCP server:

- `.codex-plugin/plugin.json` — product metadata and presentation
- `.mcp.json` — remote MCP endpoint configuration
- `assets/` — light, dark, and composer icon assets

Vibsync provides shared long-term memory and live work context for AI coding
agents. It does not choose, schedule, or run agents, so the listing copy avoids
presenting it as an agent orchestrator.

## Test before submission

1. Connect `https://mcp.vibsync.com/mcp` as a custom MCP server in the relevant
   OpenAI developer surface.
2. Complete OAuth sign-in and select a team.
3. Verify that `onboard`, `recall`, `remember`, task, Q&A, and file-claim tools
   are visible.
4. Confirm that read and write actions are described accurately and that no
   credentials or private team context appear in listing screenshots.
5. Validate the plugin manifest with the Codex plugin validator.

## Directory submission

Publishing an MCP server does not automatically create a public directory
listing. Submit the plugin/app through OpenAI's current review workflow, using:

- Name: **Vibsync**
- One-line description: **Long-term team memory and live work context for AI coding agents.**
- Developer: **LOOSEDAYS Co., Ltd.**
- Website: <https://vibsync.com>
- Privacy policy: <https://vibsync.com/privacy>
- Terms: <https://vibsync.com/terms>
- Support: <support@vibsync.com>
- MCP endpoint: `https://mcp.vibsync.com/mcp`
- Source: <https://github.com/loosedays/vibsync-mcp>

Approval is required before an app or plugin appears publicly in the Plugins
Directory.

- [Apps in ChatGPT](https://help.openai.com/en/articles/11487775-apps-in-chatgpt)
- [OpenAI app submission announcement](https://openai.com/index/developers-can-now-submit-apps-to-chatgpt/)
