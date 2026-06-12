---
name: scope-change-impact
description: Assesses the impact of requested scope changes across timeline, budget, dependencies, risk, and delivery outcomes, and provides decision-ready options with tradeoffs.
---

# Scope Change Impact Skill

## Goal
Turn scope change requests into clear, decision-ready impact analysis with options, tradeoffs, and recommended path.

## Inputs
- Scope change request(s) and rationale.
- Current plan baseline (scope, schedule, budget, staffing, milestones).
- Optional context:
  - Constraints and fixed commitments
  - Priority tiers (must/should/could)
  - Contract/SOW boundaries
  - Release deadlines

## Output
Create or update:
- scope-change-impact-{topic-or-date}.md

Use this structure:

```markdown
# Scope Change Impact: [Change Request]
**Date:** [date]
**Requested By:** [name/team]
**Decision Deadline:** [date]

## Change Summary
- Requested change:
- Business rationale:
- Urgency:

## Baseline vs Proposed Scope
| Area | Baseline | Proposed | Delta |
| --- | --- | --- | --- |

## Impact Analysis
| Dimension | Impact (Low/Medium/High/Critical) | Detail |
| --- | --- | --- |
| Timeline |  |  |
| Budget |  |  |
| Staffing/Capacity |  |  |
| Dependencies |  |  |
| Technical Risk |  |  |
| Quality/Testing |  |  |
| Release Scope |  |  |

## Options and Tradeoffs
| Option | Description | Pros | Cons | Timeline Impact | Budget Impact | Risk |
| --- | --- | --- | --- | --- | --- | --- |

## Recommended Option
- Recommendation:
- Why:
- Conditions/assumptions:

## Required Decisions
- ...

## Action Plan (If Approved)
| Action | Owner | Due Date | Status |
| --- | --- | --- | --- |
```

## Workflow
1. Capture the request clearly
- Normalize the scope change into explicit in/out statements.
- Identify whether it is additive, substitutive, or defers existing scope.

2. Compare against baseline
- Measure deltas across milestones, estimates, and delivery commitments.

3. Assess impacts by dimension
- Evaluate timeline, budget, staffing, dependencies, risk, and quality effects.
- Mark each dimension with impact level.

4. Generate options
- Option A: Approve as requested.
- Option B: Approve with tradeoff (de-scope/defer something else).
- Option C: Defer/reject with rationale.

5. Recommend and operationalize
- Recommend one option based on objectives and constraints.
- Provide required decisions and action plan.

## Impact Rating Rubric
- **Critical:** jeopardizes fixed commitments, release viability, or major contractual obligations.
- **High:** significant shift to timeline/budget/risk requiring leadership decision.
- **Medium:** manageable change with moderate replanning.
- **Low:** minor adjustment with limited downstream effect.

## Guardrails
- Do not invent estimates, capacity, or budget numbers.
- Use `TBD` where evidence is missing and flag assumptions.
- Make tradeoffs explicit; avoid hidden scope shifts.
- Keep recommendations tied to business priorities and constraints.

## Example Invocation
Use the scope-change-impact skill to analyze adding feature X in Q3 and produce decision options with timeline/budget tradeoffs.
