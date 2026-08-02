# Gemini CLI Extension

The Vibsync extension connects Gemini CLI to the hosted Vibsync MCP endpoint and
loads the recommended team-memory workflow from `GEMINI.md`.

## Install

```sh
gemini extensions install https://github.com/loosedays/vibsync-mcp
```

Restart Gemini CLI after installation. Authenticate in the browser and verify
the connection:

```text
/mcp auth vibsync
/mcp list
```

Then ask Gemini to onboard before it starts work:

```text
Use Vibsync to onboard me to the team's current context.
```

Vibsync uses MCP OAuth with dynamic client registration, so no token needs to be
stored in the extension. For headless environments, create a machine token in
the Vibsync console and follow the [Getting Started guide](https://vibsync.com/getting-started).

## Public gallery

The Gemini CLI Extensions Gallery indexes public GitHub repositories that have
a valid root `gemini-extension.json` and the `gemini-cli-extension` repository
topic. The gallery crawler validates eligible repositories daily.

- [Gemini CLI extension release documentation](https://geminicli.com/docs/extensions/releasing/)
- [Gemini CLI Extensions Gallery](https://geminicli.com/extensions/)
