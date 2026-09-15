---
name: analytics-mcp
description: Connect to and use a project-scoped, read-only Analytics MCP server for product analytics.
---

# Statelio Analytics MCP

Use this skill when the user wants to connect Statelio MCP or analyze their
Statelio product data through it.

## Connect a project

The bundled MCP server uses `https://statelio.com/api/v1/mcp`. On first use,
Codex opens Statelio's secure consent screen. The user signs in if needed,
chooses one project, and grants read-only access. Statelio returns the user to
Codex with a short-lived OAuth token; no project ID or `sk_live_*` key belongs
in the plugin configuration.

The endpoint already pins the selected project in the OAuth grant; do not
supply a project ID in tool arguments.

## Analytics available after connection

The server is read-only and can expose event discovery, schema inspection,
aggregates, time series, funnels, retention, anomalies, errors, revenue, path
analysis, period comparisons, cohorts, and cohort users.

Start analysis by confirming the event names and properties with schema or event
listing tools. State the time range, segment, and success event for every
funnel or retention question. Use a comparison period where it would make a
trend more meaningful.

## Security and troubleshooting

A 403 normally means the user no longer has access to the selected project. A
401 usually means the connection needs to be reauthorized. Do not suggest
write operations: the MCP surface is intentionally read-only.
