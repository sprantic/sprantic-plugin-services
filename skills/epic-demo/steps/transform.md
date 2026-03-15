# Step 2: Transform Epic

## Purpose
Show the before/after of one epic transformed into Epic as Code format. The transformation should make the improvement undeniable — clearer acceptance criteria, testable outcomes, explicit dependencies, traceable to code.

## Procedure

1. **Present the "Before"** — Show the epic in its current format, exactly as found. Highlight:
   - Ambiguous acceptance criteria (or missing ones)
   - Implicit assumptions not stated
   - Missing dependency declarations
   - Untestable success conditions

2. **Present the "After"** — Transform into Epic as Code format:

```markdown
# Epic: [Title]

## Intent
[One sentence: what outcome does this epic produce?]

## Context
[Why this matters now. What changes if we don't do it?]

## Acceptance Criteria
- [ ] [Testable criterion 1 — measurable, specific]
- [ ] [Testable criterion 2]
- [ ] [Testable criterion 3]

## Dependencies
- Upstream: [What must exist before this can start]
- Downstream: [What depends on this being done]

## Bounded Context
- Primary: [Which domain/service owns this]
- Touches: [Which other domains are affected]

## Verification
[How do we know this is done? What test, metric, or demonstration?]
```

3. **Explain the differences:**
   - What was implicit is now explicit
   - What was ambiguous is now testable
   - What was disconnected is now traceable
   - Estimate how this format would have prevented rework on this specific epic

## Rules
- Transform ONE epic only. If the customer asks for more, that's the engagement.
- Be genuinely helpful — the transformation should be good enough that they learn the concept.
- Don't explain the full methodology. Show the format, explain why each section matters, but don't teach them how to roll this out across their organisation.

## Next
→ `steps/gate.md`
