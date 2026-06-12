# Requirements Extraction Table

## Purpose
Consolidate requirements from discovery notes, interviews, and workshops into a single working table before PRD finalization and backlog decomposition.

Use this template before drafting the PRD. Treat it as a short-lived discovery synthesis artifact: update it only until open clarification questions are resolved, then freeze it and carry decisions into the PRD.

Use this table to:
- De-duplicate repeated requirements
- Capture stakeholder attribution
- Surface dependencies and constraints early
- Flag open clarification questions before planning

---

## Priority Definitions

- Must-Have: Required for planned release scope or core viability.
- Should-Have: Important but can be phased if constrained.
- Could-Have: Valuable enhancement, not required for current release.
- Won't-Have (This Phase): Explicitly deferred.

---

## Requirements Table

| Requirement | Category | Priority | Stakeholder(s) | Constraints or Dependencies | Needs Clarification? |
|---|---|---|---|---|---|
| [Requirement statement in clear action language] | [Business / Functional / Non-Functional / Technical] | [Must-Have / Should-Have / Could-Have / Won't-Have] | [Names or roles] | [Known constraints, assumptions, or external dependencies] | [Open question that must be resolved] |
| [Requirement] | [Category] | [Priority] | [Stakeholder(s)] | [Constraints/dependencies] | [Clarification] |
| [Requirement] | [Category] | [Priority] | [Stakeholder(s)] | [Constraints/dependencies] | [Clarification] |
| [Requirement] | [Category] | [Priority] | [Stakeholder(s)] | [Constraints/dependencies] | [Clarification] |
| [Requirement] | [Category] | [Priority] | [Stakeholder(s)] | [Constraints/dependencies] | [Clarification] |
| [Requirement] | [Category] | [Priority] | [Stakeholder(s)] | [Constraints/dependencies] | [Clarification] |

---

## Optional Release-Phase Notation

Use this if requirements are split by phase:
- Example: Must-Have (Phase 1)
- Example: Must-Have (Phase 2)
- Example: Should-Have (Post-MVP)

If phase notation is used, ensure roadmap milestones and PRD scope match it.

---

## Clarification Backlog

Track unresolved items from the table and assign owners.

| Requirement Reference | Clarification Needed | Owner | Due Date | Status |
|---|---|---|---|---|
| [Row or requirement ID] | [Question to resolve] | [Name or role] | [yyyy-mm-dd] | Open / In Progress / Resolved |
| [Row or requirement ID] | [Question to resolve] | [Name or role] | [yyyy-mm-dd] | Open / In Progress / Resolved |

---

## Quality Checks Before PRD Draft

- Each requirement is testable and written in observable language.
- Priority is explicit and consistent with phase scope.
- Dependencies are clear enough to drive sequencing and risk assessment.
- Clarification items have owners and dates.
- Duplicates are merged so each requirement appears once.

---

## Update Cadence and Freeze Rule

- Create this table before the first PRD draft.
- Update only during clarification (while questions are Open or In Progress).
- Once clarification items are Resolved and PRD drafting begins, mark this table as Frozen.
- After freeze, make changes in the PRD and linked delivery artifacts instead of revisiting this table.

---

## Notes

- This is a synthesis artifact, not a final signed-off requirements specification.
- Priority reflects current discovery signal until stakeholder approval is complete.
- Rows with unresolved clarification should be treated as blockers for backlog decomposition where relevant.
- After the table is Frozen, keep it as historical traceability and avoid reopening unless discovery scope materially changes.
