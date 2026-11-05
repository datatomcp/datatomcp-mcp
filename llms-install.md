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
3. A new account starts with an example dataset (`sample_sales`). To use their own data, the user adds a file, a Google Sheet or a database at https://app.datatomcp.com/app/new.
4. To confirm the setup, call `list_datasets`, then `describe_dataset` on one result.

Tools: `workspace_overview`, `list_datasets`, `describe_dataset`, `distinct_values`, `query_rows`, `aggregate` (read-only), `chart` (draws the answer in the chat), `create_dashboard`, `list_dashboards`, `refresh_dashboard` (dashboards, never changing data) and `report_issue`.
