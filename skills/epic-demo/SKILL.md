---
name: epic-demo
description: Transform ONE of the customer's epics/issues into Epic as Code format, showing before/after to demonstrate the methodology
---

# Epic as Code Demo

Transform a single epic or issue from the customer's codebase into the Epic as Code format. Show the before/after. Explain why it matters. This teaches the concept but doesn't transfer the skill — they can't apply it across their portfolio without the discipline, templates, governance, and training that come with the engagement.

## When to Use
- Customer is interested in requirements discipline
- After a scan shows a requirements gap
- Customer asks about Epic as Code or structured requirements

## When NOT to Use
- Customer wants multiple epics transformed (that's the paid engagement)
- No epics/issues available in the codebase

## Step Sequence
0. **Jira opt-in** — Ask: "Would you like me to pull epics from your Jira board? I can find the best candidate for the demo directly. Otherwise I'll work from specs and docs in your repo." If yes, follow `integrations/jira.md` flow (check MCP, guide setup if needed, get project key). If no, proceed file-only.
1. → `steps/find-epic.md` — Find a suitable epic (from Jira or local files)
2. → `steps/transform.md` — Show before/after transformation
3. → `steps/gate.md` — Present the value and booking link

Begin with step 0.

## What This Produces
- One epic transformed from current format to Epic as Code
- Clear before/after comparison
- Explanation of what changed and why it matters

## The One-Taste Principle
One example teaches the concept but doesn't transfer the skill. It's like showing someone one yoga pose — useful, but not a practice. The implementation engagement covers their entire pipeline.

## Success Metrics
- Customer sees a clear improvement in their epic's clarity
- Customer understands the concept of executable requirements
- Gate presented naturally as "this for your whole pipeline"
