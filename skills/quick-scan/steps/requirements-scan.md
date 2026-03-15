# Step 3: Requirements Gap Scan

## Purpose
Assess requirements maturity. Uses Jira board data if the customer opted in during the skill intro, otherwise works from local files only.

## Path A: With Jira (customer opted in, MCP connected, project key provided)

1. **Epic quality audit.** Query recent epics:
   ```
   project = {{KEY}} AND issuetype = Epic AND created >= -90d
   ```
   For each epic, check:
   - Has acceptance criteria? (look for "acceptance criteria", "AC:", checklists in description)
   - Has linked sub-tasks?
   - Has been updated in the last 30 days?
   - Has a clear definition of done?

2. **Staleness check.** Query stale items:
   ```
   project = {{KEY}} AND issuetype = Epic AND updated <= -30d AND status != Done
   ```
   Count stale epics as % of total open epics.

3. **Traceability check.** For recently completed issues, check:
   - Do commits reference issue keys?
   - Are issues linked to PRs/branches?

4. **Record the numbers:**
   - Epic quality score (% with acceptance criteria)
   - Staleness rate (% of open epics not updated in 30+ days)
   - Traceability rate (% of done issues with linked commits)
   - Total open epics / in-progress / stale

## Path B: File-Only (customer declined Jira or MCP not available)

1. **Search for requirements artifacts:**
   - Files matching: `*spec*`, `*requirements*`, `*epic*`, `*story*`, `*.feature`
   - Directories: `docs/`, `specs/`, `requirements/`, `.github/ISSUE_TEMPLATE/`
   - README sections with feature descriptions

2. **Code-to-docs ratio.** Compare lines of code to lines of documentation/specs.

3. **Commit message quality.** Sample recent commit messages:
   - Do they reference tickets/issues? (e.g., `PROJ-123`, `#456`)
   - Are they descriptive or just "fix" / "update" / "wip"?

4. **Record the numbers:**
   - Spec files found (count and location)
   - Code-to-docs ratio
   - Commit traceability (% referencing tickets)
   - Issue templates present (yes/no)

## Interpretation Guide (internal)

| Indicator | Healthy | Concerning | Critical |
|-----------|---------|------------|----------|
| Epics with AC (Jira) | > 80% | 50-80% | < 50% |
| Staleness rate (Jira) | < 10% | 10-30% | > 30% |
| Traceability (either) | > 70% | 40-70% | < 40% |
| Code-to-docs ratio | > 1:10 | 1:20-1:50 | < 1:50 |

## Next
→ `steps/report.md`
