# Installing the Truthifi MCP server (for AI agents such as Cline)

Truthifi is a **remote** MCP server. Do not clone, build, install packages or run anything.

1. Add a remote MCP server named `truthifi` with URL `https://api.truthifi.com/mcp` and transport Streamable HTTP (`"type": "streamableHttp"` in Cline).
2. Leave client ID, client secret and API key empty. The server supports OAuth Dynamic Client Registration.
3. On first connection a browser window opens; the user signs in to Truthifi and approves access. Wait for them.
4. Verify with `get_subscription_info` (free, 0 credits). It returns the user's plan and the tools it includes.

```json
{
  "mcpServers": {
    "truthifi": {
      "type": "streamableHttp",
      "url": "https://api.truthifi.com/mcp"
    }
  }
}
```

No Truthifi account yet? The user can start free at https://truthifi.com (limits apply).
