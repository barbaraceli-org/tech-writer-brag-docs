# Setup

## Atlassian (Jira)

The project includes `mcp.json` in the root with Atlassian MCP. Cursor loads it automatically for this workspace.

- Ensure **Settings → Features → Model Context Protocol** has MCP enabled.
- Restart Cursor after changing `mcp.json`.
- On first use, you may be prompted to log in to Atlassian.

## GitHub (optional)

To include PRs and commits in brag docs, add the GitHub MCP to your **user** config:

- **Windows:** `%USERPROFILE%\.cursor\mcp.json`
- **macOS/Linux:** `~/.cursor/mcp.json`

Example:

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "<your-token>"
      }
    }
  }
}
```

Create a token at [GitHub → Settings → Developer settings → Personal access tokens](https://github.com/settings/tokens) with `repo` scope.

## Troubleshooting

- **Jira connection fails:** Confirm `mcp.json` is in the project root and Cursor was restarted. Check Cursor’s MCP panel for errors.
- **No GitHub data:** Verify GitHub MCP is in your user `mcp.json` and the token has `repo` access.
- **Wrong date range:** Use explicit dates (e.g. `2026-02-01 to 2026-02-28`) or standard terms (e.g. `Q1 2026`, `last week`).
