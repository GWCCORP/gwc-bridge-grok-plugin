# GWC Bridge for Grok Build

GWC Bridge connects Grok Build to your own computer. With it, Grok Build can read, search and edit files and documents in the folders you share, run commands, manage processes and hand tasks to the GWC agent, all within the permissions you set on that computer.

## Requirements

- A GWC account with an active Connect Pass: https://gwc-corp.com/pricing
- GWC Studio or GWC for VS Code on the computer you want to use, signed in with the same account, with Bridge switched on: https://gwc-corp.com/download
- The computer switched on and online, with at least one folder shared with Bridge.

## What this plugin contains

| Component | Details |
|---|---|
| MCP server | `gwc-bridge`, a remote HTTP server at `https://mcp.gwc-corp.com/mcp` |
| Skill | `get-started`: sets up GWC Bridge and confirms one harmless file read |

There are no hooks, scripts, commands, agents or local binaries. Nothing is downloaded or run on install.

## Network endpoints and sign-in

- `https://mcp.gwc-corp.com/mcp`: the GWC Bridge MCP server.
- `https://api.gwc-corp.com`: the OAuth authorization server. You sign in with your GWC account and approve the connection on GWC's consent page.

The plugin stores no API keys or passwords. The OAuth token is held by Grok Build, the MCP client. GWC relays each request to your computer through GWC's servers; see the privacy policy below.

## You stay in control

On your computer, GWC Studio or GWC for VS Code decides which folders are shared, whether each folder allows changes, and whether commands and agent tasks are allowed. Bridge cannot grant itself more access. Commands and agent tasks run with your own account rights on that computer, so allow them only where you intend to.

To stop access, turn Bridge off in the desktop app, or revoke the connection in your GWC account under Settings, Security, Connected apps.

## Links

- Product page: https://gwc-corp.com/bridge
- Support: https://gwc-corp.com/support (support@gwc-corp.com)
- Privacy policy: https://gwc-corp.com/privacy
- Terms of service: https://gwc-corp.com/terms

## Licence

The files in this repository are released under the MIT licence (see `LICENSE`). The licence covers only this plugin package. GWC services and apps are provided under the GWC Terms of Service.
