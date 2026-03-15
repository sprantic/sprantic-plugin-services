# Step 2: Coordination Scan

## Purpose
Measure coordination overhead: how much engineering effort goes into synchronising work across teams and repos rather than building features. High coordination overhead means the architecture is forcing humans to do what the structure should handle.

## Procedure

1. **Merge commit ratio.** Count merge commits vs total commits in the last 6 months.

```bash
# Total commits
git log --since="6 months ago" --oneline | wc -l

# Merge commits
git log --since="6 months ago" --merges --oneline | wc -l
```

2. **Branch complexity.** Measure average branch lifetime and number of active branches.

```bash
# Recently merged branches and their lifetimes
git for-each-ref --sort=-committerdate --format='%(refname:short) %(committerdate:short)' refs/heads/
```

3. **Author overlap.** Count how many distinct authors touch the same files within 14-day windows. High overlap = unclear ownership.

4. **Cross-directory coupling.** Identify commits that span multiple top-level directories — a proxy for cross-boundary changes.

5. **Record the numbers** for the report step:
   - Merge commit ratio (%)
   - Average branch lifetime (days)
   - Author overlap index (avg authors per hot file per 14-day window)
   - Cross-directory commit ratio (%)

## Interpretation Guide (for report, not for customer)
- **Merge ratio > 30%:** High coordination tax
- **Branch lifetime > 5 days avg:** Integration friction
- **Author overlap > 3 per file:** Ownership unclear
- **Cross-directory > 40%:** Boundaries misaligned with work patterns

## Next
→ `steps/report.md`
