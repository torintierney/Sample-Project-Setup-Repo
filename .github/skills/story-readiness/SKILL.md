---
name: story-readiness
description: Evaluates backlog stories against Definition of Ready (DoR), identifies gaps, and rewrites weak stories into implementation-ready format with clear acceptance criteria and dependencies.
---

# Story Readiness Skill

## Goal
Ensure stories are truly ready for engineering by checking quality, completeness, and testability before sprint commitment.

## Inputs
- One or more backlog items (story text, epic context, linked tasks).
- Optional context:
  - Team-specific DoR checklist
  - Story point sizing guidance
  - Non-functional requirements (security, performance, compliance)
  - Existing sprint goal

## Output
Create or update:
- `story-readiness-{project-or-date}.md`

Use this structure:

```markdown
# Story Readiness Report: [Project Name]
**Sprint/Period:** [name or date range]
**Last Updated:** [date]

## Summary
- Stories reviewed: [count]
- Ready: [count]
- Conditionally Ready: [count]
- Not Ready: [count]

## Readiness Results
| Story ID | Title | Status (Ready/Conditional/Not Ready) | Key Gaps | Recommended Fixes | Owner |
| --- | --- | --- | --- | --- | --- |

## Rewritten Stories (If Needed)
### [Story ID] [Title]
**User Story**
As a [persona], I want [capability], so that [outcome].

**Acceptance Criteria**
- [ ] ...
- [ ] ...

**Dependencies**
- ...

**Assumptions**
- ...

**Test Notes**
- ...

## Cross-Cutting Risks
- ...

## Sprint Entry Recommendation
- Ready to pull: [IDs]
- Pull with conditions: [IDs + condition]
- Do not pull yet: [IDs]
```

## Workflow
1. Evaluate each story against core DoR checks
- Clear user value and outcome
- Explicit scope boundaries
- Testable acceptance criteria
- Identified dependencies
- NFRs called out where relevant
- No unresolved blockers for sprint start

2. Classify readiness
- `Ready`: Can be implemented without clarification risk.
- `Conditional`: Implementable if specific small fixes are completed first.
- `Not Ready`: Significant ambiguity or missing core elements.

3. Rewrite where needed
- Convert vague stories into standard user-story format.
- Replace ambiguous criteria with concrete, testable acceptance criteria.
- Add explicit dependency and assumption notes.

4. Add implementation context
- Include test notes and edge cases.
- Call out integration/data/security considerations where applicable.

5. Publish sprint recommendation
- Separate stories into pull-now, pull-with-conditions, and hold.

## Readiness Rubric
- **Ready**
  - Story intent is clear, bounded, and testable.
  - Acceptance criteria are objective and verifiable.
  - Dependencies are known and manageable.
- **Conditional**
  - Core intent is clear, but one or two fixable gaps remain.
  - Team can proceed after minor edits.
- **Not Ready**
  - Missing user value, unclear scope, untestable criteria, or major unresolved dependencies.

## Guardrails
- Do not invent architecture details, owners, or external commitments.
- If info is missing, flag explicitly as `TBD` and mark impact.
- Keep rewrites faithful to original intent; do not alter business goals.
- Avoid over-specification that should remain implementation design.

## Example Invocation
"Use the story-readiness skill to review these backlog items for sprint planning and produce a readiness report with rewrites for non-ready stories."
