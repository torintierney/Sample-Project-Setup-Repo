---
name: raid-log
description: Extracts and maintains RAID (Risks, Assumptions, Issues, Dependencies) logs from project artifacts such as transcripts, notes, PRDs, and status reports. Use when you need a structured RAID register with owners, severity, due dates, and mitigations.
---

# RAID Log Skill

## Goal
Produce a clean, decision-ready RAID register from messy project inputs and keep it updated over time.

## Inputs
- One or more source files (meeting transcripts, weekly status reports, PRDs, notes, backlog docs).
- Optional context:
  - Current reporting period
  - Team roster for owner mapping
  - Severity scale preferences
  - Existing RAID log path to update

## Output
Create or update a file named:
- `raid-log-{project-or-date}.md`

Use this structure:

```markdown
# RAID Log: [Project Name]
**Reporting Period:** [date range]
**Last Updated:** [date]

## Summary
- Risks: [count]
- Assumptions: [count]
- Issues: [count]
- Dependencies: [count]
- Critical: [count]
- High: [count]

## Risks
| ID | Statement | Severity | Owner | Mitigation | Trigger/Indicator | Due Date | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |

## Assumptions
| ID | Statement | Owner | Validation Method | Due Date | Status |
| --- | --- | --- | --- | --- | --- |

## Issues
| ID | Statement | Severity | Owner | Action Plan | Blocked Area | Due Date | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |

## Dependencies
| ID | Dependency | Type (Internal/External) | Owner | Needed By | Impact if Missed | Status |
| --- | --- | --- | --- | --- | --- | --- |

## Changes Since Last Update
- Added:
- Updated:
- Closed:

## Open Decisions Needed
- ...
```

## Workflow
1. Ingest and classify signals
- Parse each source for statements that indicate uncertainty, blockers, required assumptions, or cross-team/vendor dependencies.
- Classify each item as Risk, Assumption, Issue, or Dependency.

2. Normalize and de-duplicate
- Merge duplicates across sources.
- Rewrite statements into concise, single-idea entries.
- Keep terminology consistent and actionable.

3. Assign metadata
- Assign owner where explicit; otherwise use `Unassigned`.
- Assign severity (`Critical`, `High`, `Medium`, `Low`) where applicable.
- Add due/needed dates if present; otherwise use `TBD`.
- Capture mitigation/action plan from source when available.

4. Validate for actionability
- Ensure each Risk/Issue has mitigation or action plan.
- Ensure each Dependency has impact if missed.
- Ensure each Assumption has validation method.

5. Publish and summarize
- Output full register and include a short summary and change log.

## Classification Rules
- **Risk:** Potential future problem that may impact delivery.
- **Assumption:** Belief accepted as true for planning, pending validation.
- **Issue:** Current problem already impacting delivery.
- **Dependency:** External or internal prerequisite needed to proceed.

## Severity Rubric
Use the highest applicable level based on impact and urgency.

- **Critical**
  - Immediate or near-immediate impact to delivery or operations.
  - Can cause major milestone miss, production outage, regulatory/compliance exposure, or material financial/reputational harm.
  - No viable workaround, or workaround is extremely limited and short-lived.
  - Action required now (same day to 48 hours).

- **High**
  - Significant impact likely if unresolved soon.
  - Can delay key milestones, reduce committed scope, or create major quality/performance degradation.
  - Workaround exists but is costly, unstable, or not sustainable.
  - Action required this week.

- **Medium**
  - Moderate impact to team efficiency, sequencing, or quality.
  - Does not immediately threaten major milestones if managed.
  - Workaround is available and reasonably sustainable in the short term.
  - Action required in current sprint/near-term window.

- **Low**
  - Limited localized impact with minimal effect on milestones or commitments.
  - Workaround is straightforward and sustainable.
  - Action can be planned into normal backlog prioritization.

### Scoring Guidance
- If evidence is incomplete, choose the lower of two plausible severities and flag for review.
- Escalate one level when both impact and likelihood are high.
- For dependencies, score based on impact if the dependency is missed by the `Needed By` date.

## Guardrails
- Do not invent facts, dates, owners, or statuses.
- If unknown, use explicit placeholders: `TBD` or `Unassigned`.
- Prefer direct evidence from source text; avoid speculative interpretation.
- Keep entries brief and operational.

## Example Invocation
"Use the raid-log skill to generate a RAID register from [file1], [file2], and [file3], and save it as raid-log-weekly.md."
