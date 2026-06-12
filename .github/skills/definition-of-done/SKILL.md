---
name: definition-of-done
description: Defines and validates Definition of Done (DoD) criteria to ensure completed work meets quality, testing, documentation, and release standards before closure.
---

# Definition of Done Skill

## Goal
Create and apply a clear Definition of Done so teams close work only when quality and release expectations are met.

## Inputs
- Completed or near-complete stories/tasks.
- Optional context:
  - Team release model and environments
  - CI/CD and testing standards
  - Compliance and documentation requirements
  - Existing DoD policy to compare against

## Output
Create or update:
- dod-checklist-{project-or-team}.md
- dod-validation-{date-or-sprint}.md

## Core DoD Checklist
A story is Done only when all required checks pass.

1. Acceptance criteria fully met
- All criteria are implemented and verified.
- No unresolved requirement gaps remain.

2. Code quality standards met
- Code review completed and approved.
- Linting/static analysis thresholds pass.
- No critical or high-severity defects introduced.

3. Testing complete
- Unit and integration tests are added/updated and passing.
- Regression impact evaluated and covered.
- UAT/business validation completed where required.

4. Security and compliance checks complete when applicable
- Required security scans/checks pass.
- Compliance controls and evidence are recorded.

5. Documentation updated
- Technical and user-facing documentation updated where required.
- Runbooks/support notes updated for operational impact.

6. Observability and operability ready
- Logging, metrics, and alerts added/updated where needed.
- Failure modes and recovery approach considered.

7. Deployment readiness confirmed
- Feature flags/configuration documented.
- Migration/backfill steps prepared and validated if needed.
- Rollback or remediation plan defined.

8. Defect and risk posture acceptable
- Remaining defects are triaged and explicitly accepted if deferred.
- Residual risks are documented with owner and mitigation.

9. Product and stakeholder sign-off completed where required
- Required approvals captured.

10. Closure metadata complete
- Story status, links, and artifacts are updated in tracking tools.

## Completion Scoring
- Done: all required checks pass.
- Conditionally Done: minor non-blocking admin/documentation tasks remain with explicit owner/date.
- Not Done: one or more critical checks fail.

## Workflow
1. Validate each completed item against DoD checklist.
2. Record evidence for each criterion.
3. Flag gaps and required remediation.
4. Assign final closure status.
5. Publish closure report and carry-over actions.

## Guardrails
- Do not mark Done when critical checks fail.
- Do not infer sign-off or test completion without evidence.
- Use explicit residual risk statements for accepted exceptions.
- Keep closure decisions auditable and traceable.

## Example Invocation
Use the definition-of-done skill to validate completed stories in sprint-12-closeout.md and produce dod-validation-sprint-12.md.
