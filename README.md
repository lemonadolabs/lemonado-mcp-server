![Lemonado logo](https://storage.googleapis.com/lemonado-public-upload/lemonado_logo.png)

# Lemonado MCP server

Connect an external AI app to the data you have connected to Lemonado. Your connection determines which companies, sources, and tools the app can access.

- [Connect an app](https://docs.lemonado.io/external-ai)
- [MCP reference: addresses, tools, permissions, and examples](https://docs.lemonado.io/mcp-reference)

## Connect

1. Open your company in [Lemonado](https://app.lemonado.io).
2. Click the gear beside its name and choose **External access**.
3. Turn the connection on, select your AI app, and follow the setup instructions.
4. Ask the app to list the sources or accounts available through the connection.

A workspace owner or admin enables access. Follow the guide for OAuth or, where offered, a generated bearer token. Check the token's selected expiry and keep it private.

## Server addresses

| Address | Use |
| --- | --- |
| `https://mcp.lemonado.io/mcp` | General MCP tools for data discovery, SQL queries, and enabled connector actions. |
| `https://mcp.lemonado.io/chatgpt/mcp` | Read-only marketing-data discovery and analysis for ChatGPT. |
| `https://mcp.lemonado.io/claude/mcp` | The same read-only discovery and analysis tools, with results presented for Claude. |

Use the address shown in your setup guide. Claude and ChatGPT can also have existing connections to the general `/mcp` address, so check the configured URL rather than assuming from the app name. Changing addresses requires a new OAuth authorization for that address.

All three use **Streamable HTTP**. Configure a remote HTTP MCP server in your client, not a local stdio command or a web-fetch server.

## Tools

The general `/mcp` address provides:

- `list_objects`, `get_object_details`, and `execute_sql` for discovering and querying data.
- `get_google_ads_resource_metadata` for Google Ads schema discovery.
- Company discovery and connector-action tools where the connection's scope and features allow them.

The `/chatgpt/mcp` and `/claude/mcp` addresses each provide:

- `list_projects`
- `list_project_sources`
- `answer_data_question`
- `explain_metric_change`

See the [MCP reference](https://docs.lemonado.io/mcp-reference) for inputs, aliases, execution policies, and result limitations. Your client's tool list reflects the tools available to your connection; clients may add a prefix to their displayed names.

## AI, memory, and permissions

- **SQL calls:** Lemonado executes the query and returns data. The external AI app interprets it.
- **Analysis calls:** `answer_data_question` and `explain_metric_change` use AI inside Lemonado to plan data queries. Lemonado calculates comparisons from query results and can use AI to summarize data questions. The discovery tools do not run that analysis.
- **Memory:** These tools do not load or edit the memory files or instructions saved in Lemonado. Give the external AI app the relevant context separately, and include it in analysis questions when needed.
- **Writes:** SQL and the four analysis/discovery tools are read-only. The general endpoint can also expose `execute_action`, which may perform writes allowed by a connector's policy. Actions requiring approval return an error instead of running through an external MCP client.
- **Scope:** Requests remain subject to the connection's allowed companies, sources, and permissions. A supplied account ID does not grant access.

To stop access, turn off the connection in the company's **External access** settings.

## Troubleshooting and support

For missing tools, verify the server address and refresh tool discovery. For missing data, check the selected company, account, dates, and returned warnings. A partial result or query failure is not a measured zero.

See [access and troubleshooting](https://docs.lemonado.io/mcp-reference#access-and-troubleshooting), or contact [support@lemonado.io](mailto:support@lemonado.io). Include the server address, tool name, and error message, but never your token.
