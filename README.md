# workload.zero MCP server

Let Claude and other AI agents work in your [workload.zero](https://workloadzero.de/en/) account: tasks and goals, time tracking, contacts and deals, quotes and invoices. workload.zero is a business suite by Get IT Done GmbH, hosted in the EU (servers in Germany, file storage in Sweden).

- Endpoint: `https://mcp.workloadzero.de/mcp` (Streamable HTTP)
- Sign-in: OAuth 2.1 with PKCE and dynamic client registration, using your workload.zero account
- Discovery: `initialize` and `tools/list` answer without sign-in, so you can see every tool first. Tool calls need sign-in.
- Registry name: `de.workloadzero/mcp` in the [official MCP Registry](https://registry.modelcontextprotocol.io)

## What your agent can do

| Area | Tools |
| --- | --- |
| Tasks and goals | `list_tasks`, `get_task`, `create_task`, `update_task`, `add_task_comment`, `list_goals`, `get_todays_goals`, `get_week_goals`, `create_goal`, `update_goal`, `complete_goal` |
| Projects | `list_projects`, `get_project`, `create_project`, `update_project` |
| Time | `log_time`, `list_time_entries`, `get_my_time_entries`, `get_unbilled_hours` |
| CRM | `list_companies`, `upsert_company`, `list_contacts`, `upsert_contact`, `list_deals`, `upsert_deal`, `update_deal`, `convert_deal`, `find_deal_by_ref`, `list_pipelines`, `create_pipeline`, `update_pipeline`, `set_default_pipeline`, `get_sales_report` |
| Quotes and invoices | `list_quotes`, `get_quote`, `create_quote`, `estimate_quote`, `send_quote`, `convert_quote_to_invoice`, `list_invoices`, `get_invoice`, `create_invoice_from_time`, `get_revenue` |
| Team and chat | `get_my_profile`, `update_my_profile`, `get_my_colleagues`, `list_users`, `list_chats`, `get_chat_messages`, `send_message`, `get_unread_counts` |
| Files and search | `search`, `list_files`, `list_recent_files`, `search_files` |
| Privacy | `list_suppressions`, `add_suppression`, `check_suppression`, `mark_gdpr_answered` |

## Connect

### Claude Code

```sh
claude mcp add --transport http workload-zero https://mcp.workloadzero.de/mcp
```

Then run `/mcp` in Claude Code and sign in.

### Claude Desktop and claude.ai

Settings, Connectors, Add custom connector, URL `https://mcp.workloadzero.de/mcp`.

### Cursor

`~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "workload-zero": { "url": "https://mcp.workloadzero.de/mcp" }
  }
}
```

## Try it

> Show my goals for today and log two hours on the task I worked on this morning.

## Links

- Website: https://workloadzero.de/en/
- App: https://app.workloadzero.de
- Contact: info@itdone.de

This repository only describes the hosted server. It does not contain its source code.
