# Sprantic Codebase Quick Scan — Report

**Repository:** {{repo_name}}
**Analysis period:** {{start_date}} — {{end_date}}
**Commits analysed:** {{total_commits}}

---

## Headline Numbers

| Metric | Value | Benchmark |
|--------|-------|-----------|
| **Rework Rate** | {{rework_rate}}% | Healthy: < 15% |
| **Coordination Overhead** | {{coordination_score}} | Healthy: < 30% merge ratio |
| **Requirements Gap** | {{requirements_score}} | Structured specs present: {{specs_present}} |

---

## Rework Analysis

**{{rework_rate}}%** of commits in the last {{period}} touched files that were already modified within the prior 14 days.

{{#if rework_high}}
This is the **Amnesia Tax** — teams rebuilding what was already built. At your commit volume, this represents approximately {{rework_capacity_estimate}} of engineering capacity per year spent on rework.
{{/if}}

### Top Churn Files
| File | Rework Touches | Last Modified |
|------|---------------|---------------|
{{#each churn_files}}
| {{this.path}} | {{this.count}} | {{this.date}} |
{{/each}}

---

## Coordination Overhead

| Indicator | Value |
|-----------|-------|
| Merge commit ratio | {{merge_ratio}}% |
| Avg branch lifetime | {{avg_branch_days}} days |
| Cross-directory commits | {{cross_dir_ratio}}% |
| Author overlap (hot files) | {{author_overlap}} avg |

{{#if coordination_high}}
This is the **Synchronisation Tax** — your architecture is forcing humans to coordinate what the structure should handle.
{{/if}}

---

## Requirements Gap

| Indicator | Found |
|-----------|-------|
| Structured spec files | {{specs_found}} |
| Code-to-docs ratio | {{code_docs_ratio}} |
| Issue templates | {{issue_templates}} |

{{#if requirements_gap}}
This is the **Telephone Game** — requirements losing fidelity through handoffs before reaching developers.
{{/if}}

---

## What These Numbers Mean

{{business_implication}}

---

## Next Step

{{gate_message}}

→ **Book an Assessment Discovery Call:** sprantic.ai/bookings/assessment-discovery

---

*All analysis ran locally. No code or data left your machine. These numbers are yours to keep.*
*Powered by Sprantic — the builder who consults.*
