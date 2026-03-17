---
name: scan-deck
description: Generate a sprantic-branded HTML presentation from Quick Scan findings. Requires a completed scan in the current conversation.
---

# Scan Deck

Turn Quick Scan findings into a polished sprantic-branded slide deck. The presentation visualises the three headline numbers, names the patterns, and ends with a gate slide pointing to the Assessment booking.

## When to Use
- After a Quick Scan has been completed in the current conversation
- Customer asks for a "deck", "slides", or "presentation" of the scan results
- Preparing a leave-behind for a prospect meeting

## When NOT to Use
- No scan data available in the conversation — run `/sprantic-services:scan` first
- Customer wants a full assessment report (that's the paid engagement)

## Prerequisites
- Quick Scan must have been completed in this conversation (rework rate, coordination overhead, requirements gap data available)
- The `sprantic-html` plugin must be active

## Step Sequence
1. → `steps/collect.md` — Gather scan data from conversation context
2. → `steps/generate.md` — Invoke sprantic-html skill with structured content

Begin with step 1.

## What This Produces
- One `.html` file: a self-contained slide deck openable in any browser
- Optional PDF export on request

## Privacy
Same as Quick Scan — all data stays local. The presentation contains only aggregate numbers, never source code.
