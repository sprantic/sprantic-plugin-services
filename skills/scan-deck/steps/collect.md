# Step 1: Collect Scan Data

## Purpose
Extract the scan findings from the current conversation and structure them for the presentation.

## Procedure

1. **Locate scan results** in the conversation. You need:
   - **Repository name** and analysis period
   - **Rework rate** (%) and top churn files
   - **Coordination overhead** — merge ratio, branch lifetime, cross-directory ratio, author overlap
   - **Requirements gap** — specs found, code-to-docs ratio, issue templates
   - **Patterns identified** — which of the three patterns are elevated (Amnesia Tax, Synchronisation Tax, Telephone Game)
   - **Business implication** text and gate message

2. **If any data is missing**, inform the user which metrics are unavailable and suggest running the full scan first. Do not fabricate numbers.

3. **Determine severity** for each metric:
   - **Red:** Rework > 25%, Merge ratio > 40%, No specs at all
   - **Amber:** Rework 15–25%, Merge ratio 30–40%, Minimal specs
   - **Green:** Rework < 15%, Merge ratio < 30%, Specs present

4. **Hold this data** for the next step. Do not present it to the user — proceed directly to step 2.

## Done
Scan data collected and severity levels assigned. Proceed to `steps/generate.md`.
