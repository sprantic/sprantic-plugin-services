# Step 1: Understand

## Purpose
Understand the customer's situation before offering anything. What do they do, what's their scale, and what hurts?

## If Jira Was Connected
If the customer opted in to Jira and the MCP is connected, pull a board snapshot first:
- Count of open epics, in-progress stories, stale items (not updated in 30+ days)
- Sprint health: items in current sprint vs completed vs carried over

Use these numbers in the conversation to ground it in reality:
- "I can see you have 23 open epics, 7 of which haven't been updated in over a month — is that typical?"
- "Your current sprint has 15 items, 3 carried over from last sprint — does that feel about right?"

## Procedure

1. **Ask about their context** (pick what's relevant, don't interrogate):
   - "What does your engineering organisation look like? How many teams, repos, engineers?"
   - "What's the main thing that's not working as well as you'd like?"
   - "Have you started using AI coding tools? How's that going?"
   - "Where do requirements come from? How do they reach developers?"

2. **Listen for pain signals:**

| Signal | Likely Pattern | Relevant Offering |
|--------|---------------|-------------------|
| "We keep rebuilding things" | Amnesia Tax / rework | Assessment |
| "Teams step on each other" | Coordination overhead | Workshop |
| "AI tools aren't helping as much as expected" | Context fragmentation | Assessment |
| "Requirements get lost in translation" | Telephone Game | Workshop (Epic as Code) |
| "We have too many repos / too few repos" | Architecture misalignment | Assessment → Workshop |
| "Governance slows us down" | Strangling standards | Implementation |
| "We don't know what's deployed where" | Drift / observability gap | Implementation |

3. **Reflect back** what you heard in their language, not yours:
   - "So the main issue is that your 12 teams are stepping on each other across 30+ repos, and the AI tools you adopted aren't making things faster because the context is fragmented?"

4. **Check:** "Did I get that right? Anything I'm missing?"

## Next
→ `steps/probe.md`
