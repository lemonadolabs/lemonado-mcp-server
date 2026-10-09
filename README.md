![Lemonado logo](https://storage.googleapis.com/lemonado-public-upload/lemonado_logo.png)

# Lemonado MCP server

Connect an external AI app to the data you have connected to Lemonado. Your connection determines which companies, sources, and tools the app can access.

- [Connect an app](https://docs.lemonado.io/external-ai)
- [MCP reference: tools, permissions, and examples](https://docs.lemonado.io/mcp-reference)

## Connect

1. Open your company in [Lemonado](https://app.lemonado.io).
2. Click the gear beside its name and choose **External access**.
3. Turn the connection on, select your AI app, and follow the setup instructions.
4. Ask the app to list the sources or accounts available through the connection.

A workspace owner or admin enables access. Follow the guide for OAuth or, where offered, a generated bearer token. Check the token's selected expiry and keep it private.

## MCP server address

For a custom MCP connection, use:

```text
https://mcp.lemonado.io/mcp
```

Configure a remote **Streamable HTTP** server in your client.

For ChatGPT or Claude, select your app in Lemonado's **External access** settings and follow its guide. Directory connections are available once Lemonado is published in the app's directory.

## Tools

The general `/mcp` address provides:

- `list_objects`, `get_object_details`, and `execute_sql` for discovering and querying data.
- `get_google_ads_resource_metadata` for Google Ads schema discovery.
- Company discovery and connector-action tools where the connection's scope and features allow them.

See the [MCP reference](https://docs.lemonado.io/mcp-reference) for inputs, aliases, execution policies, and result limitations. Your client's tool list reflects the tools available to your connection; clients may add a prefix to their displayed names.

## AI, memory, and permissions

- **SQL calls:** Lemonado executes the query and returns data. The external AI app interprets it.
- **Dedicated integrations:** The ChatGPT and Claude integrations offer read-only analysis tools that run AI inside Lemonado. See [integration details](https://docs.lemonado.io/mcp-reference#integration-details) for their separate tool catalog and technical addresses.
- **Memory:** These tools do not load or edit the memory files or instructions saved in Lemonado. Give the external AI app the relevant context separately, and include it in analysis questions when needed.
- **Writes:** SQL queries are read-only. The general MCP connection can also expose `execute_action`, which may perform writes allowed by a connector's policy. Actions requiring approval return an error instead of running through an external MCP client.
- **Scope:** Requests remain subject to the connection's allowed companies, sources, and permissions. A supplied account ID does not grant access.

To stop access, turn off the connection in the company's **External access** settings.

## Troubleshooting and support

For missing tools, verify the server address and refresh tool discovery. For missing data, check the selected company, account, dates, and returned warnings. A partial result or query failure is not a measured zero.

See [access and troubleshooting](https://docs.lemonado.io/mcp-reference#access-and-troubleshooting), or contact [support@lemonado.io](mailto:support@lemonado.io). Include the server address, tool name, and error message, but never your token.
