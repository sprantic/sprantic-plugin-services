# Step 1: Find a Suitable Epic

## Purpose
Find one epic, user story, or feature specification that would benefit most from the Epic as Code transformation. Choose one that clearly demonstrates the value of structured requirements.

## Path A: With Jira (customer opted in, MCP connected, project key provided)

1. **Query recent epics:**
   ```
   project = {{KEY}} AND issuetype = Epic AND created >= -90d AND status != Done
   ORDER BY priority DESC
   ```

2. **Score candidates.** Prefer epics that:
   - Have a description but lack structured acceptance criteria
   - Have multiple sub-tasks (shows coordination complexity)
   - Are actively in progress (relevant to the customer)
   - Have visible ambiguity (vague description, no definition of done)

3. **Pull the full epic** — description, sub-tasks, comments, linked issues. Preserve original formatting for the before/after comparison.

## Path B: File-Only (customer declined Jira or MCP not available)

1. **Search for requirements artifacts.** Look for:
   - Issue templates, epic descriptions, feature specs
   - Files matching patterns: `*.epic`, `*.story`, `*requirements*`, `*spec*`, `*epic*`
   - Markdown files in `docs/`, `specs/`, `requirements/`, `.github/ISSUE_TEMPLATE/`

2. **If no formal specs exist**, look for:
   - README sections describing planned features
   - TODO comments in code referencing features
   - PR descriptions that contain implicit requirements
   - Commit messages that reference tickets

## For Both Paths

3. **Select the best candidate.** Prefer epics that:
   - Are medium complexity (not trivial, not massive)
   - Have visible ambiguity or missing acceptance criteria
   - Touch multiple components (shows coordination value)
   - Are recent or active (relevant to the customer)

4. **Present the selection** to the customer:
   - Show what you found
   - Explain why this epic is a good demo candidate
   - Ask for confirmation before transforming

## If Nothing Found
If no requirements artifacts exist at all (neither in Jira nor locally), note this as a significant finding — the absence of structured requirements is itself a diagnosis. Proceed to the gate with this observation.

## Next
→ `steps/transform.md`
