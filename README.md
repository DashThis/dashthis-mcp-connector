<p align="center">
  <img src="https://blob.dashthis.com/cdn/dashthis-static/images/dashthis-icon-dark.png" alt="DashThis" width="96" height="96">
</p>

# DashThis MCP connector

Work with your marketing reports and turn the numbers into client-ready updates.

> **This repository holds documentation only.** The DashThis MCP server is hosted by DashThis at
> `https://mcp.dashthis.com`. There is nothing to install, build or self-host.

[DashThis](https://dashthis.com) is a marketing reporting platform. Its MCP connector lets an AI
assistant work with the dashboards in your DashThis account, so you can prepare a client meeting,
draft a recap or explain a change without copying numbers by hand.

## Example prompts

- "Which of my DashThis dashboards are for Acme Co?"
- "Summarize September on the Acme dashboard as a short recap I can email the client."
- "Help me prepare tomorrow's meeting with Acme: what went well last month, what dropped, and what
  should I bring up?"
- "Compare conversions on the Acme Google Ads dashboard with the previous month and explain the change
  in plain language."
- "Export the Acme dashboard for September as a PDF."
- "Write this month's commentary in the Acme dashboard's comment box."

What the assistant can do depends on your DashThis account and plan.

## Connection details

| | |
|---|---|
| Server URL | `https://mcp.dashthis.com` |
| Transport | Streamable HTTP |
| Authentication | OAuth 2.1. Sign in with your DashThis account; no API key needed. |
| Requirements | A DashThis account |
| Registry name | `com.dashthis/mcp` in the [official MCP Registry](https://registry.modelcontextprotocol.io/v0.1/servers?search=dashthis) |

## Connect your assistant

### Claude

Add [DashThis from Claude's connector directory](https://claude.ai/directory/dashthis), or add a
custom connector with the URL `https://mcp.dashthis.com`. Sign in to DashThis when prompted.

### ChatGPT

Add [DashThis from ChatGPT's apps directory](https://chatgpt.com/plugins/plugin_asdk_app_6a7e00f905a88191a46f1d211beeafd0).
See [How to connect with MCP in ChatGPT](https://help.dashthis.com/how-to-connect-with-mcp-in-chatgpt)
for step-by-step instructions.

### Claude Code

```bash
claude mcp add --transport http dashthis https://mcp.dashthis.com
```

Then run `/mcp` in Claude Code and choose DashThis to sign in.

### Cursor

Add this to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "dashthis": {
      "url": "https://mcp.dashthis.com"
    }
  }
}
```

### VS Code

Add this to `.vscode/mcp.json`:

```json
{
  "servers": {
    "dashthis": {
      "type": "http",
      "url": "https://mcp.dashthis.com"
    }
  }
}
```

### Cline

Add this to `cline_mcp_settings.json` (MCP Servers → Configure → Configure MCP Servers):

```json
{
  "mcpServers": {
    "dashthis": {
      "type": "streamableHttp",
      "url": "https://mcp.dashthis.com"
    }
  }
}
```

Then choose **Authorize OAuth** on the DashThis server and sign in to DashThis.

### Other clients

Any MCP client that supports remote servers over Streamable HTTP with OAuth can connect to
`https://mcp.dashthis.com`. Clients that support dynamic client registration register themselves.

## Help and support

- Documentation: [help.dashthis.com/mcp](https://help.dashthis.com/mcp)
- Contact support: [help.dashthis.com/kb-tickets/new](https://help.dashthis.com/kb-tickets/new)
