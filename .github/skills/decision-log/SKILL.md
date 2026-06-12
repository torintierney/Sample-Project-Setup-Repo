---
name: decision-log
description: Captures and maintains project decisions from meetings, docs, and status artifacts. Use when you need traceable decision records with options considered, rationale, owner, and follow-up actions.
---

# Decision Log Skill

## Goal
Create and maintain a clear, auditable decision register that explains what was decided, why, by whom, and what happens next.

## Inputs
- One or more source files (meeting transcripts, PRDs, status reports, notes, architecture docs).
- Optional context:
  - Project name
  - Reporting period
  - Existing decision log to update
  - Required governance format

## Output
Create or update:
- `decision-log-{project-or-date}.md`

Use this structure:

```markdown
# Decision Log: [Project Name]
**Reporting Period:** [date range]
**Last Updated:** [date]

## Summary
- New decisions this period: [count]
- Updated decisions: [count]
- Deferred decisions: [count]
- Open follow-ups: [count]

## Decision Register
| ID | Decision | Status | Owner | Date | Options Considered | Rationale | Impact | Follow-Up Actions | Review Date |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

## Deferred / Pending Decisions
| ID | Decision Topic | Current State | Blocking Factors | Owner | Target Decision Date |
| --- | --- | --- | --- | --- | --- |

## Changes Since Last Update
- Added:
- Updated:
- Closed:

## Escalations Needed
- ...
```

## Workflow
1. Identify decision candidates
- Find explicit decisions, implicit commitments, and major direction changes.
- Ignore minor operational chatter unless it changes scope, timeline, architecture, budget, governance, or ownership.

2. Track decision evolution
- Capture initial proposal, alternatives raised, concerns, and final state.
- Preserve important context and tradeoffs.

3. Normalize entries
- Convert to concise decision statements.
- Assign owner/date if explicit; otherwise use `Unassigned` and `TBD`.
- Set status as one of:
  - `Decided`
  - `Tentative`
  - `Deferred`
  - `Superseded`

4. Add actionability fields
- Document follow-up actions tied to each decision.
- Add review date for reversible or high-impact decisions.
- Record impact scope (team/process/architecture/customer/financial).

5. Publish and summarize
- Update summary counts and changes since last update.
- Surface escalations where decisions are blocked or overdue.

## Decision Quality Rules
- Every `Decided` entry must include rationale and at least one impact statement.
- `Tentative` and `Deferred` entries must include blocking factors and target decision date where possible.
- `Superseded` entries must reference the replacement decision in rationale or follow-up.

## Guardrails
- Do not invent options, rationale, owners, or dates.
- If evidence is unclear, mark fields as `TBD` and flag for confirmation.
- Keep language factual and neutral.
- Prefer direct traceability to source statements.

## Example Invocation
"Use the decision-log skill to extract and update project decisions from [transcript.md] and [status-report.md], and save to decision-log-weekly.md."
