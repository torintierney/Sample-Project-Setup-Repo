---
name: stakeholder-update
description: Generates stakeholder update emails from uploaded project artifacts. Use when you need a consistent executive or stakeholder status update with required sections and ordering.
---

# Stakeholder Update Skill

## Goal
Generate a polished stakeholder update email from an uploaded project file.

## Inputs Required
- A PowerPoint file (.ppt or .pptx) uploaded or available in the workspace.
- Audience name/team for the greeting.
- Optional context:
  - Reporting period (if different from current week)
  - Any known sensitive items to omit
  - Tone preference (executive, concise, detailed)

## Output Requirements
The email must:
- Start with: `Hi [insert person/team here],`
- Include these sections in this exact order:
  1. Accomplishments
  2. Overall Status (Overall, Schedule, Budget, Scope)
  3. Status Summary for (Week [current date])
  4. Impacts
  5. Mitigations
  6. Upcoming Decisions
  7. Next Week Planned Activities
- Write all `Accomplishments` bullets in past tense (for example: Completed, Delivered, Finalized, Submitted).

## Workflow
1. Read the PowerPoint and extract key signals:
- Delivered outcomes
- Current KPI or milestone status
- Timeline/schedule shifts
- Budget notes
- Scope changes
- Risks/issues and mitigations
- Decision requests
- Next-week plan

2. Resolve ambiguity before drafting:
- If a required section has no clear source in the deck, explicitly mark as:
  - `Not explicitly stated in source deck`
- Do not invent facts.

3. Draft email using required structure:
- Keep tone concise, professional, and leadership-ready.
- Prefer short bullets under each section.
- Keep language factual and action-oriented.
- Ensure `Accomplishments` uses past-tense action verbs.
- Ensure each `Mitigations` bullet is tied to a specific `Impact` or identified risk/issue.
- Write `Status Summary for (Week [current date])` as a single paragraph that combines overall weekly status and health details.

4. Final quality check:
- Confirm section order is exact.
- Confirm greeting format is exact.
- Confirm week label uses current date context unless user specifies otherwise.
- Confirm no unsupported claims were added.

## Email Template
```markdown
Hi [insert person/team here],

## Accomplishments
- ...

## Overall Status (Overall, Schedule, Budget, Scope)
- Overall: [Green/Yellow/Red + one-line rationale]
- Schedule: [Green/Yellow/Red + one-line rationale]
- Budget: [Green/Yellow/Red + one-line rationale]
- Scope: [Green/Yellow/Red + one-line rationale]

## Status Summary for (Week [current date])
- Single paragraph combining overall weekly status and health details.

## Impacts
- ...

## Mitigations
- ...

## Upcoming Decisions
- ...

## Next Week Planned Activities
- ...
```

## Guardrails
- Do not reorder sections.
- Do not skip required sections.
- Do not fabricate budget/schedule/scope details.
- If data is missing, call it out clearly and request follow-up input.

## Example Invocation
"Use stakeholder-update to create a stakeholder update email from [path/to/file.pptx] for [team name]."
