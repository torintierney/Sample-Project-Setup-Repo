---
name: executive-brief
description: Produces concise one-page executive briefs from long project artifacts, highlighting outcomes, risk posture, decisions needed, and next steps. Use when leadership needs fast, decision-oriented context.
---

# Executive Brief Skill

## Goal
Transform detailed project material into a one-page leadership brief that is concise, decision-ready, and outcome-focused.

## Inputs
- One or more source artifacts (status reports, PRDs, plans, meeting notes, RAID logs, dashboards).
- Optional context:
  - Target audience (exec sponsor, steering committee, PMO)
  - Tone preference (neutral, urgent, optimistic)
  - Page/length limit
  - Decision deadline

## Output
Create or update:
- executive-brief-{topic-or-date}.md

Use this structure:

```markdown
# Executive Brief: [Topic]
**Date:** [date]
**Audience:** [audience]

## 1. Situation Summary
- 3-5 bullets on current state and context.

## 2. Key Outcomes Since Last Update
- ...

## 3. Current Status
- Overall: Green | Yellow | Red
- Schedule: Green | Yellow | Red
- Budget: Green | Yellow | Red
- Scope: Green | Yellow | Red
- One-paragraph interpretation of status.

## 4. Top Risks and Mitigations
| Risk | Severity | Mitigation | Owner | Timing |
| --- | --- | --- | --- | --- |

## 5. Decisions Required
| Decision | Why It Matters | Options | Recommended Option | Decision By | Owner |
| --- | --- | --- | --- | --- | --- |

## 6. Next 2-4 Week Plan
- ...

## 7. Executive Ask
- Clear support needed from leadership.
```

## Workflow
1. Synthesize source material
- Extract outcomes, status indicators, blockers, dependencies, and decision points.

2. Prioritize for executive relevance
- Keep only items that materially affect delivery, risk, cost, timeline, scope, or strategic value.

3. Build status narrative
- Convert raw data into concise interpretation, not just metric repetition.

4. Structure decisions and asks
- Turn unresolved questions into explicit decisions with options and recommendation.
- Make leadership support requests concrete and time-bound.

5. Tighten for brevity
- Remove operational detail that does not affect executive action.
- Keep wording direct and scannable.

## Quality Rules
- Lead with outcomes and implications, not activity lists.
- Every major risk should have an owner and mitigation.
- Every decision request should include options and recommendation.
- Keep the brief to one page equivalent unless user asks otherwise.

## Guardrails
- Do not invent data, dates, owners, or status.
- Use `TBD` where evidence is missing and flag it.
- Keep tone objective and non-defensive.
- Avoid jargon unless common to leadership audience.

## Example Invocation
Use the executive-brief skill to synthesize this week's status pack into a one-page leadership brief with decisions required by Friday.
