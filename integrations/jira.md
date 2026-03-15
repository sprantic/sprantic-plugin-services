# Jira Integration

## Overview

The services plugin can optionally connect to the customer's Jira instance to enrich diagnostics with real board data — epic quality, staleness, traceability, sprint health.

This is always opt-in. The customer is asked upfront whether they want Jira included, and guided through setup if needed.

## Flow

### Step 1: Ask the Customer

At the start of any skill (scan, epic-demo, consult), ask:

> "Would you also like me to include your Jira board in this analysis? It adds requirements quality scoring, epic staleness, and ticket traceability to the results. If not, I'll work from your git history and local files — that's plenty for a solid baseline."

If they say no → proceed with git/file-only analysis. No further mention of Jira.

### Step 2: Check MCP Availability

If they say yes, check whether Jira MCP tools are already available in the session (look for `mcp__atlassian__*` or `mcp__jira__*` tool prefixes).

- **If available** → proceed to Step 3 (project selection).
- **If not available** → guide them through setup (Step 2b).

### Step 2b: Guide MCP Setup

Tell the customer:

> "To connect Jira, we'll need to add an MCP server to your Claude Code settings. I recommend the MCP Atlassian server — it covers both Jira and Confluence."
>
> "You'll need three things:"
> 1. Your Atlassian URL (e.g., `https://your-company.atlassian.net`)
> 2. Your email address (the one you log into Jira with)
> 3. An API token — you can create one at https://id.atlassian.com/manage-profile/security/api-tokens
>
> "Once you have those, add this to your Claude Code settings file (`~/.claude/settings.json` or `.claude/settings.local.json` in your project):"

```json
{
  "mcpServers": {
    "atlassian": {
      "command": "uvx",
      "args": ["mcp-atlassian"],
      "env": {
        "JIRA_URL": "https://your-company.atlassian.net",
        "JIRA_USERNAME": "your-email@company.com",
        "JIRA_API_TOKEN": "your-api-token"
      }
    }
  }
}
```

> "After saving, restart Claude Code so the MCP server connects. Then run the skill again and I'll pick up the Jira data."

Wait for the customer to confirm setup is done. Do not proceed with Jira queries until the MCP tools are confirmed available.

### Step 3: Project Selection

Once Jira MCP is connected, ask:

> "Which Jira project should I scan? Please give me the project key (e.g., `PROJ`, `ENG`, `PLATFORM`)."

Use the provided project key for all JQL queries. Store it for the duration of the skill so the customer doesn't have to repeat it.

## What Each Skill Gets from Jira

| Skill | Without Jira | With Jira |
|-------|-------------|-----------|
| **scan** | Git-only metrics: rework, coordination, file-level analysis | + Epic quality scoring, issue staleness, ticket-to-commit traceability |
| **epic-demo** | Searches local files for specs, READMEs, PR descriptions | + Pulls actual epics from the board, selects the best demo candidate |
| **consult** | Conversation based on what customer describes | + Concrete board state: open epics, stale items, sprint health |

## Useful JQL Queries

### For scan (requirements gap analysis)
```
# Epics without acceptance criteria
project = {{KEY}} AND issuetype = Epic AND description !~ "acceptance criteria"

# Stale epics (no updates in 30+ days)
project = {{KEY}} AND issuetype = Epic AND updated <= -30d AND status != Done

# Issues without linked commits (traceability gap)
project = {{KEY}} AND issuetype in (Story, Task) AND status = Done AND development[commits].all = 0
```

### For epic-demo (find a good candidate)
```
# Recent, medium-complexity epics
project = {{KEY}} AND issuetype = Epic AND created >= -90d AND status != Done
ORDER BY priority DESC

# Epics currently in progress
project = {{KEY}} AND issuetype = Epic AND status = "In Progress"
```

### For consult (board health snapshot)
```
# Current sprint state
project = {{KEY}} AND sprint in openSprints()

# Recently completed (cycle time)
project = {{KEY}} AND status changed to Done AFTER -30d
```

## Privacy Note

All Jira queries run through the customer's own credentials on their own machine. The plugin never stores, transmits, or caches Jira data. The MCP server handles authentication — the plugin just asks questions.
