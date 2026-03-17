# Step 2: Generate Presentation

## Purpose
Invoke the sprantic-html skill with a structured slide outline derived from the scan data.

## Procedure

1. **Build the presentation outline** from the collected scan data. The deck follows this fixed narrative arc:

   | # | Slide Type | Key Message |
   |---|-----------|-------------|
   | 1 | title-slide | "Codebase Quick Scan — {repo_name}" with subtitle "{analysis_period}" |
   | 2 | agenda-slide | Three-part structure: Headline Numbers → What the Patterns Mean → Next Step |
   | 3 | content-slide | **Headline Numbers** — the three metrics in a table with benchmarks and severity colours |
   | 4 | content-slide | **Rework Analysis** — rework rate with top churn files table, name the Amnesia Tax if elevated |
   | 5 | content-slide | **Coordination Overhead** — merge ratio, branch lifetime, cross-dir ratio, author overlap; name Synchronisation Tax if elevated |
   | 6 | content-slide | **Requirements Gap** — specs, code-to-docs ratio, issue templates; name Telephone Game if elevated |
   | 7 | statement-slide | **The Cost** — translate the worst metric into a business cost statement (e.g. "~X engineer-months/year lost to rework") |
   | 8 | content-slide | **What These Numbers Mean** — brief business implication, referencing the Agentic Enterprise research |
   | 9 | closing-slide | **The one thing to remember:** the single most impactful finding + "Book an Assessment Discovery Call → sprantic.ai/bookings/assessment-discovery" |

   **Adjust the outline based on findings:**
   - If a metric is healthy (green), keep its slide but frame it positively — "Your rework rate is healthy at X%"
   - If all three metrics are healthy, replace the Cost slide (7) with a statement-slide: "Your codebase fundamentals are solid — the Assessment maps where to invest next"
   - If Jira data was included, add relevant details (epic staleness, sprint health) to the appropriate slides

2. **Present the outline to the user** for approval (OK Point), following the sprantic-html skill's Phase 1 format:

   ```
   Proposed presentation structure:

   1. Codebase Quick Scan — {repo_name}
   2. Agenda: Headline Numbers → Patterns → Next Step
   3. Three headline metrics with benchmarks
   4. Rework analysis: {rework_rate}% — {pattern if elevated}
   5. Coordination overhead: {merge_ratio}% merge ratio — {pattern if elevated}
   6. Requirements gap: {summary} — {pattern if elevated}
   7. The cost: {business cost statement}
   8. What these numbers mean for your engineering capacity
   9. The one thing to remember: {key finding}

   Does this structure work for you, or would you like to change anything?
   ```

3. **Once approved**, invoke the `sprantic-html` skill to generate the deck. Pass the approved structure and all scan data as context. The sprantic-html skill handles:
   - Reading its own style references (CSS, JS, slide types, brand assets)
   - Generating the single-file HTML
   - Fine-tuning iterations with the user

   Invoke it by calling: `/sprantic-html` with the full outline and data.

4. **After the HTML is generated**, remind the user:
   - They can open the file directly in a browser
   - They can request PDF export, and you should mention it
   - All data stays local — safe to share the deck with stakeholders

## Slide Content Guidelines

- **Use severity colours** in the headline numbers table:
  - Red metrics: highlight with a visual indicator (e.g. red dot or "⚠" prefix)
  - Green metrics: highlight positively (e.g. "✓" prefix)
- **Top churn files**: show max 5 rows in the rework slide
- **Patterns**: use the exact pattern names — "Amnesia Tax", "Synchronisation Tax", "Telephone Game"
- **Gate slide**: the closing slide must include the booking URL
- **Never prescribe fixes** — the deck diagnoses, the Assessment cures

## Done
Presentation generated. The user has a branded HTML deck of their scan findings.
