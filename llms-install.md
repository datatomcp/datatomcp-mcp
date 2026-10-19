# Installing datatomcp (for AI agents)

datatomcp is a **remote** MCP server. There is nothing to clone, build or run locally.

1. Add this server to the MCP client configuration:
   - URL: `https://app.datatomcp.com/mcp`
   - Transport: Streamable HTTP (in Cline: `"type": "streamableHttp"`)
   - No API key or headers. Authentication is OAuth: on first connection the client opens a browser window where the user signs in to datatomcp and allows access.

   Cline example (`cline_mcp_settings.json`):

   ```json
   {
     "mcpServers": {
       "datatomcp": { "type": "streamableHttp", "url": "https://app.datatomcp.com/mcp" }
     }
   }
   ```

2. Ask the user to sign in when the browser opens. If they don't have an account yet, signing in creates one (free plan, no card).
3. The user needs at least one dataset. If `list_datasets` returns nothing, tell them to add a CSV or Google Sheet at https://app.datatomcp.com/app/new.
4. To confirm the setup, call `list_datasets`, then `describe_dataset` on one result.

Tools: `list_datasets`, `describe_dataset`, `query_rows`, `aggregate`, `distinct_values`. All are read-only.
