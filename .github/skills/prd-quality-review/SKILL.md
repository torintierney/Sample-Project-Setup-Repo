---
name: prd-quality-review
description: Reviews PRDs for completeness, clarity, and delivery-readiness by identifying gaps in scope, requirements, dependencies, metrics, risks, and acceptance criteria. Use when validating PRD quality before planning or build.
---

# PRD Quality Review Skill

## Goal
Evaluate a PRD against a practical quality rubric and return a prioritized, actionable gap list with recommended fixes.

## Inputs
- One PRD file (or multiple draft versions).
- Optional context:
  - Product strategy or goals
  - Target release window
  - Architecture constraints
  - Team-specific PRD standards

## Output
Create or update:
- prd-quality-review-{prd-name-or-date}.md

Use this structure:

```markdown
# PRD Quality Review: [PRD Name]
**Date:** [date]
**Reviewer Mode:** [strict/standard/light]

## Overall Assessment
- Quality Score: [0-100]
- Readiness: Ready | Conditional | Not Ready
- Top 3 Gaps:
  1. ...
  2. ...
  3. ...

## Section-by-Section Findings
| Section | Status (Pass/Partial/Fail) | Key Findings | Recommended Fix |
| --- | --- | --- | --- |
| Problem Statement |  |  |  |
| Goals and Non-Goals |  |  |  |
| Personas / Users |  |  |  |
| Requirements |  |  |  |
| Acceptance Criteria |  |  |  |
| Dependencies |  |  |  |
| Risks and Mitigations |  |  |  |
| Success Metrics |  |  |  |
| Rollout / Release Plan |  |  |  |

## Critical Issues (Must Fix Before Build)
- ...

## Important Improvements (Should Fix)
- ...

## Nice-to-Have Enhancements
- ...

## Suggested Rewrite Snippets
- [Section]: [improved draft text]
```

## Workflow
1. Parse and map PRD structure
- Detect whether each core section exists and evaluate depth/quality.

2. Score each quality dimension
- Clarity, testability, completeness, traceability, and execution readiness.

3. Identify and prioritize gaps
- Classify findings as Critical, Important, or Nice-to-Have.

4. Recommend concrete fixes
- Provide specific edits, not generic advice.
- Include rewrite snippets for weak sections.

5. Return readiness recommendation
- `Ready`: no critical gaps.
- `Conditional`: critical gaps resolved by explicit conditions.
- `Not Ready`: major unresolved gaps.

## Quality Rubric
- **Problem clarity:** Problem is explicit, evidence-backed, and time-relevant.
- **Scope discipline:** Goals/non-goals are clear; scope creep is constrained.
- **Requirement quality:** Requirements are specific and implementation-informative.
- **Acceptance testability:** Success criteria are measurable and verifiable.
- **Dependency visibility:** Cross-team/system dependencies are explicit with owners.
- **Risk posture:** Key risks have mitigations and triggers.
- **Metric rigor:** Outcome metrics include baselines/targets where possible.
- **Delivery readiness:** Rollout plan supports staged release and feedback.

## Guardrails
- Do not invent business facts or technical constraints not present in source.
- Use `TBD` placeholders for missing evidence and flag for author confirmation.
- Keep feedback direct, specific, and prioritized.
- Separate objective gaps from subjective style suggestions.

## Example Invocation
Use the prd-quality-review skill on prd-v3.md and generate a readiness review with must-fix gaps before sprint planning.
