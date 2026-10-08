# Installing the DashThis MCP connector (for AI agents)

The DashThis MCP server is hosted at `https://mcp.dashthis.com`. There is nothing to clone, build,
install or run. Setup is one entry in the client's MCP settings file, then a browser sign-in.

## Cline

1. Find Cline's MCP settings file. Check these paths in order and use the **first one that exists**.
   Do not search elsewhere, and do not create the file in any other location.

   | Order | Platform | Path |
   |---|---|---|
   | 1 | All | `~/.cline/data/settings/cline_mcp_settings.json` (Windows: `%USERPROFILE%\.cline\data\settings\cline_mcp_settings.json`) |
   | 2 | Windows | `%APPDATA%\Code\User\globalStorage\saoudrizwan.claude-dev\settings\cline_mcp_settings.json` |
   | 3 | macOS | `~/Library/Application Support/Code/User/globalStorage/saoudrizwan.claude-dev/settings/cline_mcp_settings.json` |
   | 4 | Linux | `~/.config/Code/User/globalStorage/saoudrizwan.claude-dev/settings/cline_mcp_settings.json` |

   If none exists, stop and ask the user to open Cline's **MCP** panel and choose
   **Edit Configuration**, which creates the file in the right place.

2. Add this entry under `mcpServers`, keeping any servers already there:

   ```json
   "dashthis": {
     "type": "streamableHttp",
     "url": "https://mcp.dashthis.com"
   }
   ```

3. Tell the user to open Cline's **MCP** panel, choose **Authorize OAuth** on `dashthis`, and sign in
   with their DashThis account. No API key or token goes in the settings file.

4. Once authorized, start a new task. "List my DashThis dashboards" confirms the connection.
