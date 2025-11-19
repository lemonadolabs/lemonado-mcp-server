![Lemonado Logo](https://storage.googleapis.com/lemonado-public-upload/lemonado_logo.png)

# Lemonado MCP Server

The Lemonado Model Context Protocol (MCP) server at `mcp.lemonado.io/mcp` enables your AI agents to query data from marketing platforms, payment processors, and productivity tools such as Google Ads, Meta Ads, LinkedIn Ads, Google Analytics, Stripe, Google Sheets, and CSV files. The MCP can run SQL across these data sources.

## Our Integrations

-   **Google Ads**
-   **Meta Ads** (Facebook/Instagram)
-   **LinkedIn Ads**
-   **Google Analytics**
-   **Stripe**
-   **Google Sheets**
-   **CSV files**
-   ...and more!

We continuously add new integrations to expand your data access capabilities.

[View all integrations →](https://docs.lemonado.io/data-connectors)

## What You Can Ask Your AI

With Lemonado MCP, you can ask complex cross-platform questions like:

-   "Compare this week's Google Ads spend to our 30-day average"
-   "Which Meta Ads campaigns drove the most conversions last month?"
-   "Show me the top performing LinkedIn Ads by click-through rate"
-   "Calculate ROI for each marketing channel"
-   "What are the trends in cost per click across all ad platforms?"

## Authentication

Lemonado MCP supports two authentication methods:

### Bearer Token Authentication

Get a bearer token by registering at [data.lemonado.io/signup](https://data.lemonado.io/signup). This method is ideal for:

-   Desktop applications (Claude Desktop, Cursor)
-   Direct API access
-   Testing and development

### OAuth 2.0

Secure OAuth authentication is available for:

-   Web-based AI tools (ChatGPT, Claude Web)
-   Enterprise deployments
-   Multi-user environments

## Installation

### Requirements

-   A Lemonado account ([Create free account →](https://data.lemonado.io/signup))
-   At least one data source connected in Lemonado
-   Claude, ChatGPT, n8n, or another MCP-compatible client

<details>
<summary><b>Install in Claude</b></summary>

Connect your Lemonado data to Claude using the Model Context Protocol (MCP). Choose your preferred Claude platform below.

### Claude.ai (Web) - Browser-based

**Prerequisites:**

-   A Claude.ai account
-   Access to Lemonado ([Create a Lemonado account](https://data.lemonado.io/signup))

**Setup Instructions:**

1. Go to [claude.ai](https://claude.ai) in your browser
2. Click on **Settings** (usually found in the bottom left or profile menu)
3. Navigate to the **Connectors** section
4. Click **Add custom connector**
5. Fill in the connector details:
    - **Name**: Lemonado
    - **Remote MCP Server URL**: `https://mcp.lemonado.io/mcp`
6. Click **Add** to save the connector
7. Click **Connect** to initiate the authentication process
8. Follow the OAuth flow - a new browser tab will open for you to log in to Lemonado
9. Once authenticated, return to Claude.ai - your connector should show as connected
10. You can now use MCP tools in your Claude conversations

### Claude Desktop - Native app

**Prerequisites:**

-   Claude Desktop application installed
-   Access to Lemonado ([Create a Lemonado account](https://data.lemonado.io/signup))

**Setup Instructions:**

1. Open **Claude Desktop** application
2. Click on your **profile avatar** in the bottom left corner
3. Select **Settings** from the menu
4. Navigate to the **Connectors** section
5. Click **Add custom connector**
6. Fill in the connector configuration:
    - **Name**: Lemonado
    - **Remote MCP Server URL**: `https://mcp.lemonado.io/mcp`
7. Click **Add** to save the connector
8. Click **Connect** to initiate authentication
9. A new browser tab will open - log in to Lemonado if prompted
10. Authorize the connection and return to Claude Desktop
11. You can now use MCP tools in your Claude conversations

### Claude Code - Terminal-based

**Prerequisites:**

-   Claude Code installed from the official Anthropic website
-   Access to Lemonado ([Create a Lemonado account](https://data.lemonado.io/signup))

**Setup Instructions:**

1. **Install Claude Code** from the official Anthropic website if you haven't already
2. **Open Claude Code** in your terminal:
    ```bash
    claude
    ```
3. **Open the configuration file** by running:
    ```bash
    claude config edit
    ```
4. **Add the following MCP server configuration** to your config file:
    ```json
    {
        "mcpServers": {
            "lemonado": {
                "command": "npx",
                "args": ["-y", "@modelcontextprotocol/server-fetch", "https://mcp.lemonado.io/mcp"],
                "env": {
                    "MCP_AUTH_TYPE": "oauth",
                    "MCP_OAUTH_PROVIDER": "lemonado"
                }
            }
        }
    }
    ```
5. **Save the configuration file** and restart Claude Code
6. **Start a new conversation** - Claude Code will prompt you to authenticate
7. **Follow the OAuth flow** in your browser to connect to Lemonado
8. Once authenticated, you can **query your Lemonado data** directly in Claude Code

**Troubleshooting:**

-   **Authentication Issues**: If OAuth fails, try running `claude config edit` again and ensure the configuration is correct
-   **Connection Problems**: Verify that `https://mcp.lemonado.io/mcp` is accessible
-   **No Data Available**: Check that your Lemonado account has the necessary permissions and data sources connected
-   **Configuration Not Loading**: Restart Claude Code after saving the configuration file

[Full Claude setup guide →](https://docs.lemonado.io/ai-connectors/claude-setup)

</details>

<details>
<summary><b>Install in ChatGPT Developer Mode</b></summary>

**New in September 2025:** OpenAI has released MCP support in ChatGPT Developer Mode, enabling direct access to your Lemonado data.

### Overview

ChatGPT now supports the Model Context Protocol (MCP) through Developer Mode, allowing direct connection to your Lemonado AI Connectors.

### Prerequisites

-   **ChatGPT Plus or Pro subscription** (required for Developer Mode)
-   **Developer Mode enabled** in ChatGPT settings
-   **Lemonado account** with at least one data source connected

### Setup Instructions

**Step 1: Enable Developer Mode**

1. Open ChatGPT in your web browser
2. Click your profile picture → **Settings**
3. Navigate to **Connectors** → **Advanced**
4. Toggle on **Developer mode (beta)**

**Step 2: Add Lemonado MCP Connector**

1. In the Connectors section, click **Add custom connector**
2. Enter the connector details:
    - **Name**: Lemonado
    - **Remote MCP Server URL**: `https://mcp.lemonado.io/mcp`
3. Click **Connect**
4. You'll be redirected to Lemonado to authenticate
5. Log in to your Lemonado account
6. Select which AI Connector you want to use
7. Authorize ChatGPT to access your data

**Step 3: Verify Connection**

After OAuth authentication completes, ChatGPT will have access to your selected AI Connector.

**Step 4: Test the Connection**

1. Start a new chat in ChatGPT
2. Click the paperclip icon or connectors button in the message box
3. Select **Lemonado** from the list of available connectors
4. Test with a query like:
    ```
    "Show me a list of available data sources"
    ```

If successful, you'll see ChatGPT accessing your Lemonado data directly.

### Capabilities

With MCP in Developer Mode, ChatGPT can:

**Data Access:**

-   Query any connected database or SaaS tool
-   Search and filter records
-   Generate reports and analytics
-   Access real-time synchronized data

**Analysis & Insights:**

-   Perform complex data analysis
-   Generate visualizations
-   Identify trends and patterns
-   Create custom reports

### Example Usage

**Data Analysis:**

```
"Analyze campaign performance across Google Ads and Meta Ads for the last quarter"
```

**Marketing Insights:**

```
"Show me cost per click trends across all ad platforms"
```

**Report Generation:**

```
"Create a monthly marketing report comparing this month to last month, broken down by channel"
```

**Trend Analysis:**

```
"Identify seasonal patterns in our ad spend and predict next month's budget needs"
```

### Security & Privacy

**OAuth Authentication:**

Lemonado uses OAuth for secure authentication:

-   No API keys to manage or expose
-   Credentials are never shared with ChatGPT
-   You control which AI Connector ChatGPT can access
-   Disable the connector anytime from your Lemonado dashboard

**Data Access Control:**

-   Configure permissions in your AI Connector settings
-   All access is read-only for security
-   Use data filtering to limit exposed information
-   Monitor all queries in your Lemonado audit logs

### Troubleshooting

**Connection Failed:**

1. Verify Developer Mode is enabled
2. Ensure you completed OAuth authentication
3. Check your AI Connector is active in Lemonado
4. Try removing and re-adding the connector

**Authentication Issues:**

-   Clear browser cookies and try again
-   Ensure you're logged into the correct Lemonado account
-   Check if your AI Connector has been deleted or disabled

**No Data Returned:**

-   Verify your data sources are connected in Lemonado
-   Check if data sync has completed
-   Ensure your AI Connector has access to the data sources
-   Review query syntax and filters

[Full ChatGPT setup guide →](https://docs.lemonado.io/ai-connectors/chatgpt-mcp)

</details>

<details>
<summary><b>Install in OpenAI Agent Builder</b></summary>

**Secure MCP Integration:** OpenAI Agent Builder now supports Model Context Protocol through secure token authentication, enabling direct access to your Lemonado data.

### Overview

OpenAI Agent Builder allows you to create custom AI agents with access to external tools and data sources. By connecting Lemonado via MCP, your agents can query databases, SaaS tools, and analytics platforms in real-time.

### Prerequisites

-   OpenAI account with access to Agent Builder
-   Active Lemonado AI Connector with MCP endpoint configured
-   API access token (generated from Lemonado)

### Setup Instructions

**Step 1: Generate Lemonado Access Token**

1. Log in to your Lemonado dashboard
2. Navigate to your AI Connector settings
3. Click **Generate Access Token**
4. Copy the bearer token (it will only be shown once)
5. Save it securely - this token never expires unless regenerated

> **Important:** Store your access token securely. If compromised, regenerate it immediately from your Lemonado dashboard.

**Step 2: Configure OpenAI Agent Builder**

1. Go to your agent in OpenAI Agent Builder
2. Click **Add Tool** → **MCP Server**
3. Choose **+ Server** in the top right
4. Fill in the server details:
    - **URL**: `https://mcp.lemonado.io/mcp`
    - **Name**: Lemonado
    - **Description**: Access your Lemonado data and analytics through MCP
    - **Authentication**: Access Token / API Key
5. Paste your Lemonado bearer token in the authentication field
6. Click **Connect** to save the configuration

**Step 3: Test the Connection**

In your agent's chat interface, try a test query:

```
"List all available data sources from Lemonado"
```

If successful, your agent will return information from your Lemonado AI Connector.

### Capabilities

With Lemonado connected to your OpenAI agent, you can:

**Data Access:**

-   Query any connected database or SaaS platform
-   Access real-time synchronized data
-   Filter and search across multiple data sources
-   Retrieve specific records and datasets

**Analytics & Reporting:**

-   Generate custom reports from your data
-   Perform aggregations and calculations
-   Analyze trends and patterns
-   Create data visualizations

**Multi-Source Queries:**

-   Combine data from multiple sources
-   Cross-reference information
-   Build comprehensive dashboards
-   Track metrics across platforms

### Security & Best Practices

**Token Management:**

> **Security Notice:** Access tokens provide full access to your AI Connector data. Treat them like passwords.

-   Never share your access token publicly or commit it to version control
-   Regenerate tokens immediately if compromised
-   Use separate tokens for different agents or environments
-   Monitor usage in your Lemonado audit logs
-   Revoke access by regenerating the token

**Access Control:**

-   Configure data permissions in your Lemonado AI Connector settings
-   Use data filtering to limit what data your agents can access
-   Set up read-only access for security
-   Monitor all agent queries in real-time

**Rate Limiting:**

-   OpenAI enforces rate limits on API calls
-   Plan your agent's query patterns accordingly
-   Consider caching frequently accessed data
-   Monitor your Lemonado usage dashboard

### Advanced Configuration

**Multiple AI Connectors:**

You can add multiple Lemonado AI Connectors to a single agent:

1. Create separate AI Connectors in Lemonado for different data sources
2. Generate a unique access token for each connector
3. Add each as a separate MCP server in OpenAI Agent Builder
4. Give each a descriptive name (e.g., "Lemonado-Sales", "Lemonado-Analytics")

**Custom Agent Instructions:**

Optimize your agent's data access by including specific instructions:

```
When querying Lemonado:
1. Always specify date ranges for time-series data
2. Use filters to limit result sets
3. Request only the fields you need
4. Handle empty results gracefully
```

### Troubleshooting

**Authentication Failed:**

_Verify token is correct:_

-   Check for extra spaces or characters
-   Ensure you copied the complete token
-   Regenerate if unsure

_Token expired or revoked:_

-   Generate a new token in Lemonado
-   Update the token in OpenAI Agent Builder
-   Note: Tokens don't expire unless manually regenerated

**Connection Issues:**

-   **Check MCP server URL**: Ensure `https://mcp.lemonado.io/mcp` is entered correctly
-   **Verify AI Connector status**: Confirm your AI Connector is active in Lemonado
-   **Test from Lemonado**: Try querying your data directly in Lemonado first

**No Data Returned:**

-   Verify data sources are connected in your Lemonado AI Connector
-   Check data sync status - ensure recent sync was successful
-   Review permissions - confirm the AI Connector has access to required data
-   Test query syntax - verify your agent is using correct query format

[Full OpenAI Agent Builder setup guide →](https://docs.lemonado.io/ai-connectors/openai-agent-builder)

</details>

<details>
<summary><b>Install in n8n Automation</b></summary>

> **Important:** Make sure you are on the latest stable version of n8n for the best compatibility with MCP.

### Overview

n8n is a powerful workflow automation tool that can connect to Lemonado through the Model Context Protocol (MCP) using the MCP Client Tool node. This enables you to query and analyze your Lemonado data within automated workflows.

### Prerequisites

-   n8n instance (latest version with MCP support)
-   Lemonado account with at least one data source connected
-   Active AI Connector in Lemonado

### Setup Instructions

**Step 1: Create an AI Connector in Lemonado**

1. Go to your Lemonado dashboard
2. Navigate to **AI Connectors**
3. Create a new AI Connector or select an existing one
4. Choose which data sources the connector can access

**Step 2: Generate Bearer Token in Lemonado**

1. In your AI Connector settings, click on the **n8n** tab in the left sidebar
2. At the bottom of the page, select **Expires in: 1 Year** (recommended)
3. Click **Generate Token**
4. Copy the generated bearer token

**Step 3: Configure n8n Workflow**

1. Open your n8n workflow editor
2. Add an **HTTP Request** node or **MCP** node (if available)
3. Configure the node with these settings:
    - **Method**: POST
    - **URL**: `https://mcp.lemonado.io/mcp`
    - **Authentication**: Bearer Token
4. Add your generated bearer token to the Authorization header
5. Test the connection and save your workflow

**Step 4: Use MCP Tools**

Once connected, you can use Lemonado's MCP tools:

-   **`execute_sql`** - Run SQL queries on your connected data sources
-   **`list_objects`** - List available tables and data objects
-   **`get_object_details`** - Get schema information for tables

**Step 5: Build Your Workflow**

Example workflow components:

-   **Trigger**: Schedule, webhook, or manual trigger
-   **MCP Client Tool**: Query Lemonado data using `execute_sql`
-   **Process**: Transform or filter the data
-   **Output**: Send to Slack, email, or another service

### Example Workflows

**Daily Sales Report:**

1. **Schedule Trigger**: Run daily at 9 AM
2. **MCP Client Tool**: Execute SQL query
    ```sql
    SELECT
      DATE(created_at) as date,
      COUNT(*) as orders,
      SUM(amount) as total_revenue
    FROM orders
    WHERE created_at >= CURRENT_DATE - INTERVAL '1 day'
    GROUP BY DATE(created_at)
    ```
3. **Format**: Convert to table or chart
4. **Email**: Send report to team

**Customer Data Monitoring:**

1. **Schedule Trigger**: Every hour
2. **MCP Client Tool**: List new customers
    ```sql
    SELECT * FROM customers
    WHERE created_at > NOW() - INTERVAL '1 hour'
    ```
3. **IF Node**: Check if new customers exist
4. **Slack**: Notify sales team of new signups

**Inventory Alerts:**

1. **Schedule Trigger**: Every 30 minutes
2. **MCP Client Tool**: Check inventory levels
    ```sql
    SELECT product_name, quantity, reorder_point
    FROM inventory
    WHERE quantity < reorder_point
    ```
3. **IF Node**: Check if any items are low
4. **Create Task**: Generate purchase orders

### Using MCP Tools in n8n

**`execute_sql` Tool:**

-   Supports SELECT queries (read-only)
-   Returns results as JSON
-   Can query any connected data source

**`list_objects` Tool:**

-   Lists all tables and views
-   Shows data source information
-   Useful for discovery and documentation

**`get_object_details` Tool:**

-   Returns column names and types
-   Shows relationships and constraints
-   Helps with query building

### Integration with AI Agents

n8n can combine MCP with AI agents:

1. **MCP Client Tool**: Fetch data from Lemonado
2. **AI Agent**: Analyze data with Claude, GPT, etc.
3. **Decision Node**: Route based on AI analysis
4. **Action Nodes**: Trigger appropriate actions

### Best Practices

**Performance Optimization:**

-   Cache frequently accessed data
-   Use specific queries with filters
-   Implement pagination for large datasets
-   Schedule heavy queries during off-peak hours

**Error Handling:**

-   Add error trigger nodes to workflows
-   Implement retry logic for failed queries
-   Log errors for debugging
-   Set up alerting for critical failures

**Security:**

-   Use n8n's credential management
-   Enable workflow execution logging
-   Restrict access to sensitive workflows
-   Regularly review workflow permissions

### Troubleshooting

**Connection Issues:**

-   Verify n8n is on the latest version
-   Check bearer token authentication is complete
-   Ensure AI Connector is active in Lemonado
-   Test with simple queries first

**Query Errors:**

-   Verify SQL syntax is correct
-   Check table and column names exist
-   Ensure you have permission to access the data
-   Use `list_objects` to discover available tables

**Performance Issues:**

-   Optimize SQL queries with indexes
-   Reduce data volume with filters
-   Use pagination for large results
-   Consider caching for repeated queries

### Advanced Features

**Workflow Variables:**

Use n8n variables in your queries:

```sql
SELECT * FROM orders
WHERE customer_id = {{ $json.customerId }}
AND created_at > '{{ $json.startDate }}'
```

**Dynamic Queries:**

Build queries based on conditions:

```javascript
const table = $json.dataSource;
const limit = $json.limit || 100;
return {
    tool: "execute_sql",
    query: `SELECT * FROM ${table} LIMIT ${limit}`,
};
```

**Parallel Processing:**

Run multiple MCP queries concurrently:

1. Use **Split In Batches** node
2. Execute MCP queries in parallel
3. Merge results with **Merge** node
4. Process combined data

> **Pro Tip:** Use n8n's built-in variables and expressions to make your MCP queries dynamic and responsive to workflow context.

[Full n8n setup guide →](https://docs.lemonado.io/ai-connectors/n8n-automation)

</details>

[View all installation guides →](https://docs.lemonado.io/ai-connectors)

## Available Tools

Once connected, your AI assistant will have access to three powerful MCP tools:

-   **`lemonado_execute_sql`** - Execute SQL queries across all your connected data sources
-   **`lemonado_list_objects`** - List all available tables, views, and data sources
-   **`lemonado_get_object_details`** - Get detailed schema information for specific tables

## Key Features

![Query Multiple Data Sources](https://storage.googleapis.com/lemonado-public-upload/ads_one_query.png)

-   **Unified Data Access**: Connect and query multiple data sources through a single SQL interface

-   **AI-Powered Analytics**: Integrate with AI assistants like Claude, ChatGPT, and n8n for natural language data analysis

-   **Real-time Integration**: Access live data from platforms including Stripe, Google Ads, Meta Ads, and databases

-   **Secure Authentication**: OAuth 2.0 authentication and bearer token support for production deployments

## Documentation

Full documentation available at: [https://docs.lemonado.io/](https://docs.lemonado.io/)

## Support

Need help? Visit [data.lemonado.io](https://data.lemonado.io) or check our documentation for setup guides and troubleshooting.

---

**Empower your AI assistant with unified SQL access to all your marketing data.**

[Create Free Account →](https://data.lemonado.io)
