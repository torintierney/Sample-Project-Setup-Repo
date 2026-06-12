---
name: definition-of-ready
description: Evaluates and defines Definition of Ready (DoR) criteria for backlog items so stories can enter sprint planning with sufficient clarity, scope boundaries, dependencies, and testability.
---

# Definition of Ready Skill

## Goal
Establish and apply a clear Definition of Ready checklist so stories are implementation-ready before sprint commitment.

## Inputs
- Candidate stories or backlog items.
- Optional context:
  - Team conventions and estimation model
  - Epic and roadmap context
  - Non-functional requirements
  - Existing DoR policy to compare against

## Output
Create or update:
- dor-checklist-{project-or-team}.md
- dor-assessment-{date-or-sprint}.md

## Template Source
When available, align checklist content with:
- output/project-docs/templates/Discovery/definition-of-ready-template.md

## Core DoR Checklist
A story is Ready only when all required checks pass.

1. Problem and user value are clear
- Story states who needs what and why.
- Business/user outcome is explicit.

2. Scope boundaries are clear
- In-scope and out-of-scope are stated.
- No hidden expansion in acceptance criteria.

3. Acceptance criteria are testable
- Criteria are objective and verifiable.
- Edge conditions are addressed where relevant.

4. Dependencies are identified
- Upstream/downstream teams, systems, and approvals are listed.
- Blocking dependencies have an owner and target date.

5. Data and integration needs are known
- Required inputs, outputs, contracts, and integration points are identified.

6. Non-functional requirements are defined when applicable
- Security, performance, compliance, reliability, accessibility, and observability are captured where relevant.

7. Design and UX references are available when applicable
- Wireframes, copy, interaction notes, or design decisions are linked or captured.

8. Test approach is feasible
- Unit/integration/UAT expectations are known.
- Required test environments or test data are available or planned.

9. Estimation readiness
- Story has enough detail for sizing.
- Unknowns that prevent realistic sizing are explicitly flagged.

10. Ownership and accountability are clear
- Story owner and implementation owner are known.
- Open questions have assigned owners.

11. Ambiguity, dependency, and conflict/tradeoff questions are answered
- Key ambiguities are documented and assigned.
- Dependency questions are answered with owner and target timing.
- Scope/cost/timeline tradeoff conflicts are recorded with decision owner.

## Readiness Scoring
- Ready: all required checks pass.
- Conditional: minor gaps exist, fixable before sprint start.
- Not Ready: one or more critical checks fail.

## Workflow
1. Evaluate each story against checklist.
2. Record pass/fail evidence for each check.
3. Flag gaps with exact fix actions and owners.
4. Return status: Ready, Conditional, or Not Ready.
5. Produce sprint-entry recommendation list.

## Guardrails
- Do not invent missing details.
- Use TBD for unknowns and assign follow-up owners.
- Keep recommendations practical and specific.
- Avoid forcing implementation design details into DoR unless necessary for readiness.

## Example Invocation
Use the definition-of-ready skill to evaluate stories in sprint-backlog.md and generate dor-assessment-sprint-12.md.
