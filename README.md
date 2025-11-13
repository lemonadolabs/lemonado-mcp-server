# Lemonado MCP Server

Remote MCP Server that securely connects Lemonado with your LLM, IDE, or agent platform of choice.

## Overview

Lemonado MCP transforms your AI assistant into a powerful data analyst by providing unified SQL access to all your data sources. Query databases, spreadsheets, and APIs through natural language, with sub-second responses on millions of rows.

**Unified SQL: query databases, sheets, and APIs as one.**

Create a separate MCP for each agent or use case, ensuring that each one has access to only the relevant data and context.

## What is Lemonado MCP?

The Lemonado data layer acts as a unified interface, allowing seamless integration and querying of diverse data sources through a single, coherent framework.

Connect your data sources (Stripe, Google Ads, Sheets, Postgres, etc.), run SQL queries across all of them simultaneously, and get sub-second responses — all through natural language.

## Key Features

### 🚀 Universal SQL Engine

Query 30+ data sources with standard SQL. Sub-second responses on millions of rows with joins, aggregations, and complex analytics.

### 🔌 Multi-Connector Architecture

Create multiple connectors with specific data sources for different agents or use cases. Each connector can access only the data it needs.

### 🔒 Remote MCP Server

Production-ready remote server supporting HTTP transport, Bearer authentication, and OAuth 2.0 for secure enterprise deployments.

### 🤖 AI-Native Integration

Works with Claude, ChatGPT, Cursor, Windsurf, Cody, and any MCP-compatible assistant. Natural language queries automatically converted to optimized SQL.

## What You Can Ask Your AI

With Lemonado MCP, you can ask complex cross-platform questions like:

- "Show me customers who spent >$1000 on Google Ads but haven't converted in Stripe"
- "Compare this week's revenue across all channels to our 30-day average"
- "Which Instagram campaigns drove the most Stripe subscriptions last month?"
- "Find enterprise customers from HubSpot who haven't been contacted in 30 days"
- "Match Stripe transactions with Google Ads orders and flag any discrepancies"
- "Calculate ROI for each marketing channel using actual purchase data"

## Available MCP Tools

Lemonado MCP provides three core tools that your AI assistant can use:

### 1. Execute SQL
Run SQL queries across your connected data sources with sub-second response times.

### 2. List Objects
Discover available tables, views, and data sources in your Lemonado instance.

### 3. Get Object Details
Inspect schema, columns, and metadata for specific data objects.

## Available Integrations

Connect 30+ data sources including:

### Marketing & Ads
- **Google Ads**
- **Meta Ads** (Facebook/Instagram)
- **LinkedIn Ads**
- **Google Analytics**

### Business & Finance
- **Stripe**
- **HubSpot**

### Databases
- **PostgreSQL**
- **MySQL**
- **Microsoft SQL Server**

### Productivity
- **Google Sheets**
- **CSV files**

...and many more.

[View all integrations →](https://docs.lemonado.io/)

## Supported AI Tools

Lemonado MCP works seamlessly with:

- **Claude Desktop** - Anthropic's AI assistant
- **ChatGPT Developer Mode** - OpenAI's ChatGPT with custom tools
- **OpenAI Agent Builder** - Build custom agents
- **Cursor IDE** - AI-powered code editor
- **Windsurf IDE** - AI development environment
- **Cody AI Assistant** - Sourcegraph's AI coding assistant
- **n8n Automation** - Workflow automation platform

## Getting Started

### 1. Create Your Account

Create a free account on [data.lemonado.io](https://data.lemonado.io) to get started.

### 2. Connect Your Data Sources

Add the data sources you need - from Stripe and Google Ads to Postgres and Google Sheets.

### 3. Configure Your AI Tool

Follow the setup guides for your AI assistant:

- [Claude Setup](https://docs.lemonado.io/claude-setup)
- [ChatGPT Developer Mode](https://docs.lemonado.io/chatgpt-developer-mode)
- [OpenAI Agent Builder](https://docs.lemonado.io/openai-agent-builder)
- [Cursor IDE](https://docs.lemonado.io/cursor-ide)
- [Windsurf IDE](https://docs.lemonado.io/windsurf-ide)
- [Cody AI Assistant](https://docs.lemonado.io/cody-ai-assistant)
- [n8n Automation](https://docs.lemonado.io/n8n-automation)

### 4. Start Querying

Ask your AI assistant natural language questions about your data. It will automatically:
- Convert your question to optimized SQL
- Query the relevant data sources
- Return results with insights

## Use Cases

### Marketing Analytics
Analyze campaign performance across Google Ads, Meta Ads, and LinkedIn. Connect to Stripe or your CRM to measure true ROI.

### Business Intelligence
Build dashboards, generate reports, and analyze trends across all your business data in one place.

### Customer Analysis
Segment customers, track behavior patterns, and identify opportunities by combining data from multiple sources.

### Financial Reporting
Reconcile transactions, track revenue, and generate financial reports by querying accounting and payment platforms.

### Agent Automation
Build autonomous agents that can access and analyze your data to make decisions or trigger actions.

## Security & Enterprise

- **Bearer Authentication** - Secure API access with token-based auth
- **OAuth 2.0** - Enterprise-grade authentication
- **Data Isolation** - Each connector accesses only permitted data sources
- **Production-Ready** - Built for enterprise deployments

## Documentation

Full documentation available at: [https://docs.lemonado.io/](https://docs.lemonado.io/)

## Support

Need help? Visit [data.lemonado.io](https://data.lemonado.io) or check our documentation for setup guides and troubleshooting.

---

**Empower your AI assistant to make smarter decisions, accelerate your business processes, and build better agents.**

[Create Free Account →](https://data.lemonado.io)
