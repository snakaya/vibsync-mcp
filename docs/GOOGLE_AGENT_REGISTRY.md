# Google Agent Registry

Google Agent Registry is a centralized catalog for agents, tools, and MCP
servers inside a Google Cloud project or organization. It is not a public global
marketplace like the Gemini CLI Extensions Gallery.

## Register Vibsync

Prerequisites:

- A Google Cloud project with Agent Registry enabled
- Permission to register MCP servers in the target project
- The Vibsync endpoint: `https://mcp.vibsync.com/mcp`
- The included [`google-agent-registry-toolspec.json`](../google-agent-registry-toolspec.json)

In the Agent Registry console, register an external MCP server with:

- Display name: **Vibsync**
- Description: **Long-term team memory and live work context for AI coding agents.**
- Endpoint: `https://mcp.vibsync.com/mcp`
- Tool specification: upload `google-agent-registry-toolspec.json`
- Authentication: configure OAuth or an organization-managed Vibsync machine
  token according to your security policy

After registration, search the registry for `Vibsync`, inspect the imported
tools, and test access with a member account. Keep credentials outside the
toolspec file.

- [Google Agent Registry overview](https://docs.cloud.google.com/agent-registry)
- [Register MCP servers](https://docs.cloud.google.com/agent-registry/register-mcp-servers)
- [Search agents and tools](https://docs.cloud.google.com/agent-registry/search-agents-and-tools)
