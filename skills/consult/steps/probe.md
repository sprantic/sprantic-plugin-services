# Step 2: Probe

## Purpose
Ask specific follow-up questions based on the pain areas identified. These questions sharpen the diagnosis and help the customer see the problem more clearly.

## Procedure

Choose probes based on the pain signals from Step 1:

### If Rework / Amnesia Tax
- "When something gets rebuilt, is it usually because the team didn't know it existed, or because the original wasn't documented well enough to reuse?"
- "How do teams discover what's already been built?"
- "If I ran a scan on your git history, what rework rate would you guess? 10%? 30%?"

### If Coordination Overhead
- "How do cross-team changes get coordinated? Meetings? Slack? PRs?"
- "How long does a typical PR stay open before merge?"
- "When two teams need to change the same service, how is that handled?"

### If AI Tool Disappointment
- "Which AI tools are you using? Copilot, Cursor, Claude Code?"
- "Where do they work well? Where do they fall short?"
- "How much context does a typical repo give the AI? Is it self-contained or does it depend on 10 other repos?"

### If Requirements Problems
- "Walk me through how a feature request becomes a deployed feature. How many handoffs?"
- "What does an epic or user story look like in your system? Is it a Jira ticket? A doc? A conversation?"
- "How often does a developer start work on something and discover mid-sprint that the requirements were ambiguous?"

### If Architecture Misalignment
- "How did your current repo structure emerge? Was it designed or did it grow?"
- "Do your repo boundaries align with team boundaries? With business capabilities?"
- "If you had to explain your architecture to a new engineer, how long would it take?"

## Rules
- Ask 2-3 probes maximum. Don't interrogate.
- After each answer, name the pattern if you recognise it.
- If they mention specific numbers, remember them for the gate.

## Next
→ `steps/relate.md`
