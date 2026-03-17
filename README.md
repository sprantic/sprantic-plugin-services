# sprantic-services

A Claude Code plugin that analyses your codebase and gives you hard numbers on engineering health — rework, coordination overhead, and requirements maturity.

All analysis runs locally on your machine. No code or data leaves your environment.

Brought to you by sprantic GmbH

## What You Get

### Quick Scan (`/sprantic-services:scan`)

A 2-minute scan of your git history that produces three headline metrics:

- **Rework Rate** — percentage of commits touching the same files within 14 days, benchmarked against industry norms
- **Coordination Overhead** — merge frequency, branch lifetimes, cross-repo coupling patterns
- **Requirements Gap** — presence and quality of structured specifications, code-to-docs ratio

Each metric comes with context: what the number means, what pattern it indicates, and how it compares to teams of similar size.

### Scan Deck (`/sprantic-services:scan-deck`)

Generates a presentation-ready HTML slide deck from your scan results — useful for sharing findings with your team or leadership. Runs after a completed scan.

### Epic Demo (`/sprantic-services:epic-demo`)

Takes one real epic or issue from your project and transforms it into structured, executable format using the Epic as Code discipline. Shows a concrete before/after comparison so you can see what higher-fidelity requirements look like in practice.

### Consultation (`/sprantic-services:consult`)

A guided diagnostic conversation. Helps you articulate engineering pain points, maps them to known patterns, and identifies which areas would benefit most from deeper analysis.

## Optional: Jira Integration

Each skill can optionally pull data from your Jira board to enrich the analysis — epic quality, ticket staleness, sprint health, and traceability from tickets to commits. The plugin asks upfront whether you want Jira included and walks you through setup if needed. All queries run through your own Atlassian credentials on your own machine.

## What Happens Next

The scan produces real numbers from your codebase. If the findings point to structural issues — high rework, coordination bottlenecks, weak requirements — sprantic offers three engagements to address them:

| Engagement | For | Outcome |
|---|---|---|
| **Agentic Readiness Assessment** | Engineering leaders evaluating codebase health | Prioritised action plan with quantified impact |
| **Federation Workshop** | Platform teams with 50+ engineers and growing AI adoption | Concrete restructuring plan with pilot scope |
| **Agentic Domain Flows** | Organisations ready to implement at scale | Running infrastructure and trained teams |

Details and booking: [sprantic.ai](https://sprantic.ai)

## Background

sprantic builds on the **Agentic Enterprise** thesis — a set of principles for organisations where AI agents work alongside humans as first-class participants. The methodology and thinking behind it are published on [Substack](https://sprantic.substack.com).

## Privacy

- All codebase analysis runs locally via git commands
- No source code, metrics, or project data is transmitted anywhere
- Jira integration (if opted in) uses your own credentials and runs on your machine
- Diagnostic reports are generated locally for your review

## Installation

Add this plugin to your Claude Code environment:

```bash
claude plugin add /path/to/sprantic-plugin-services
```

Then use any of the skills directly in conversation with Claude Code.
