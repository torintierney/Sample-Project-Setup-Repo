---
name: weekly-plan
description: Builds a realistic weekly execution plan from backlog, priorities, blockers, and team capacity, including owners, sequencing, and fallback options.
---

# Weekly Plan Skill

## Goal
Generate a clear, executable week plan that aligns priorities to available capacity, highlights risks, and provides fallback actions.

## Inputs
- Current backlog and priority list.
- Team capacity and availability (PTO, meetings, constraints).
- Open blockers/dependencies.
- Optional context:
  - Sprint goal or OKR
  - Required stakeholder milestones
  - Production/support obligations
  - Work-in-progress limits

## Output
Create or update:
- weekly-plan-{week-of-date}.md

Use this structure:

```markdown
# Weekly Plan: Week of [date]
**Planning Date:** [date]
**Team Capacity Summary:** [brief]

## 1. Weekly Objectives
- Objective 1
- Objective 2
- Objective 3

## 2. Priority Plan (Committed)
| Priority | Work Item | Owner | Estimate | Dependency | Target Date | Success Criteria |
| --- | --- | --- | --- | --- | --- | --- |

## 3. Sequencing and Critical Path
- Ordered execution notes
- Critical path items and why

## 4. Risks and Blockers
| Risk/Blocker | Impact | Owner | Mitigation | Escalation Trigger |
| --- | --- | --- | --- | --- |

## 5. Fallback Plan (If Blocked)
| Trigger | Fallback Work | Owner | Expected Outcome |
| --- | --- | --- | --- |

## 6. Stakeholder Touchpoints This Week
- [Date] [Audience] [Purpose]

## 7. End-of-Week Exit Criteria
- [ ] ...
- [ ] ...
- [ ] ...
```

## Workflow
1. Set weekly objectives
- Translate sprint/roadmap priorities into 2-4 concrete objectives.

2. Balance commitment with capacity
- Select committed items that fit realistic capacity.
- Avoid overcommitment; reserve contingency for unplanned work.

3. Sequence by dependency and risk
- Order work to unblock downstream tasks early.
- Identify critical path items and escalation points.

4. Add risk-aware fallback planning
- Define alternate productive tasks if key dependencies block progress.

5. Finalize accountability and checkpoints
- Ensure every committed item has owner, date, and success criteria.
- Include stakeholder touchpoints for decisions/visibility.

## Planning Rules
- Commit less than total theoretical capacity when uncertainty is high.
- Prioritize items that unlock multiple downstream tasks.
- Pair high-risk items with explicit early validation steps.
- Include at least one fallback path for top blockers.

## Guardrails
- Do not invent capacity numbers or dates without source input.
- If estimates are missing, mark `TBD` and include owner for follow-up.
- Keep objectives outcome-focused, not activity-only.
- Avoid plans that depend on unconfirmed external commitments.

## Example Invocation
Use the weekly-plan skill to build this week’s plan from backlog.md, team-capacity.md, and blockers.md, including fallback actions.
