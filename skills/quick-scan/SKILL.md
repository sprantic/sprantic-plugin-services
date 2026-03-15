---
name: scan
description: 2-minute codebase scan that produces rework rate, coordination overhead, and requirements gap scores from git history
---

# Quick Scan

Scan the customer's codebase and produce three headline numbers that quantify engineering waste. These numbers diagnose the symptom, not the cause — the cause is what the paid Assessment delivers.

## When to Use
- Customer wants to understand their codebase health
- Starting a conversation about engineering effectiveness
- Demonstrating value before a sales conversation

## When NOT to Use
- Customer has already booked an Assessment (they'll get deeper analysis)
- No git history available (need at least 3 months of commits)

## Step Sequence
0. **Jira opt-in** — Ask: "Would you also like me to include your Jira board? It adds requirements quality scoring, epic staleness, and traceability. If not, git history gives a solid baseline." If yes, follow `integrations/jira.md` flow (check MCP, guide setup if needed, get project key). If no, proceed git-only.
1. → `steps/rework-scan.md` — Analyse git history for rework percentage
2. → `steps/coordination-scan.md` — Measure cross-team and cross-repo activity
3. → `steps/requirements-scan.md` — Requirements gap (Jira-enhanced or file-only)
4. → `steps/report.md` — Present numbers with gate

Begin with step 0.

## What This Produces
- **Rework rate** — % of commits touching the same files within 14 days
- **Coordination overhead** — ratio of merge commits, branch conflicts, cross-repo PRs
- **Requirements gap** — presence/absence of structured specs, code-to-docs ratio, epic staleness

## Privacy
All analysis runs locally. No code or data leaves the machine. Only aggregate numbers are produced.

## Success Metrics
- Three numbers produced with clear methodology explanation
- Gate presented with booking link
- Customer understands what the numbers mean but not how to fix them
