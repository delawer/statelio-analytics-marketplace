# Private Statelio Analytics MCP marketplace

This repository is a private Codex marketplace containing the read-only
`analytics-mcp` Statelio plugin. It intentionally contains no API keys,
OAuth tokens, project IDs, or Statelio data.

## Share it privately

1. Create a **private** GitHub repository.
2. Upload this directory's contents to the repository root, keeping
   `.agents/plugins/marketplace.json` and `plugins/analytics-mcp/` intact.
3. Invite your friend to the private repository with read access.

## Install in Codex (friend)

The friend needs Codex CLI and a GitHub account that can read the private
repository. In a terminal, run the following, replacing the repository URL:

```sh
codex plugin marketplace add git@github.com:OWNER/statelio-analytics-marketplace.git --ref main
codex plugin add analytics-mcp@statelio-private
```

Then start a **new** Codex chat or CLI session and say:

```text
Help me connect this Statelio project to MCP.
```

Codex will open Statelio's OAuth consent screen. The friend signs in with their
own Statelio account, selects a project they can access, and approves the
read-only grant.

## Important

- Installing the plugin does **not** share your Statelio project or login.
- Never commit or send OAuth tokens, `sk_live_*` keys, or project secrets.
- The MCP service is read-only: it can inspect analytics but cannot change
  Statelio data or settings.

## Local-folder alternative

Instead of GitHub, the friend can receive this folder and run:

```sh
codex plugin marketplace add /absolute/path/to/statelio-analytics-marketplace
codex plugin add analytics-mcp@statelio-private
```

