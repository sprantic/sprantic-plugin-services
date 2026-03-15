# Step 1: Rework Scan

## Purpose
Compute the rework rate: percentage of commits that touch files already modified within the past 14 days. This is a proxy for "built the wrong thing" — high rework means teams are revisiting recent work, often because requirements were unclear.

## Procedure

1. **Identify the analysis window.** Use the last 6 months of git history (or all available if less).

2. **Run the rework analysis.** For each commit, check if any file it modifies was also modified by a different commit within the preceding 14 days.

```bash
# Get all commits with files changed, last 6 months
git log --since="6 months ago" --name-only --pretty=format:"%H %ai" |
  # Process to find files touched multiple times within 14-day windows
```

3. **Compute the percentage.**
   - Numerator: commits where ≥1 file was modified within the prior 14 days
   - Denominator: total commits in the window
   - Rework rate = numerator / denominator × 100

4. **Identify hot files.** List the top 5 files by rework frequency — these are the "churn magnets."

5. **Record the numbers** for the report step:
   - Rework rate (%)
   - Total commits analysed
   - Analysis window
   - Top 5 churn files

## Interpretation Guide (for report, not for customer)
- **< 15%:** Healthy. Normal iteration.
- **15-25%:** Elevated. Likely some requirements gaps or unclear ownership.
- **25-35%:** High. Significant rework — probably structural causes.
- **> 35%:** Critical. Major requirements or architecture problems.

## Next
→ `steps/coordination-scan.md`
