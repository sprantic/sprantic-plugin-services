---
name: consult
description: Guided conversation about the customer's situation — understand their pain, map it to offerings, and guide to a booking
---

# Guided Consultation

A structured conversation that helps the customer articulate their engineering challenges, connects their pain to specific Sprantic offerings, and guides them to the appropriate next step.

This is NOT primarily a sales pitch. It's a genuinely helpful diagnostic conversation that stays within the published-methodology boundary. The customer should feel understood and guided, not sold to.

## When to Use
- Customer describes pain but hasn't run a scan yet
- Customer asks "what do you do?" or "can you help with X?"
- General exploration of Sprantic's offerings
- Follow-up after a scan or epic demo

## Step Sequence
0. **Jira opt-in** — Ask: "Would you like me to look at your Jira board as part of this conversation? It helps me ground the discussion in your actual project state. Otherwise we'll work from what you tell me." If yes, follow `integrations/jira.md` flow (check MCP, guide setup if needed, get project key). If no, proceed conversation-only.
1. → `steps/understand.md` — Understand their situation and what's painful
2. → `steps/probe.md` — Ask specific questions per pain area
3. → `steps/relate.md` — Map their pain to specific offerings
4. → `steps/gate.md` — Summary with concrete next step

Begin with step 0.

## Conversation Principles
- **Listen first.** Don't jump to solutions.
- **Be specific.** "How many repos?" not "Tell me about your architecture."
- **Name patterns.** When you recognise something, name it — this builds credibility.
- **Stay in bounds.** Discuss freely, redirect at the protected line.
- **Offer the scan.** If they haven't run one, suggest it as a concrete next step.

## Success Metrics
- Customer feels understood (their specific situation, not a generic pitch)
- Pain connected to a specific offering (not "we can help with everything")
- Clear next step offered (scan, booking, or essay reference)
