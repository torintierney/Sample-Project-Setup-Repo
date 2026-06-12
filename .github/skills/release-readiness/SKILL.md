---
name: release-readiness
description: Evaluates go/no-go readiness for releases by checking quality, testing, deployment safety, risk posture, and stakeholder approvals. Use when preparing a release decision.
---

# Release Readiness Skill

## Goal
Produce a clear go/no-go recommendation with auditable evidence and explicit blockers before release.

## Inputs
- Release candidate artifacts (release notes, test reports, defect list, change log, deployment plan).
- Optional context:
  - Environment and deployment window
  - SLO/SLA targets
  - Rollback requirements
  - Approval policy

## Output
Create or update:
- release-readiness-{release-name-or-date}.md

Use this structure:

```markdown
# Release Readiness: [Release Name]
**Target Window:** [date/time]
**Environment:** [env]
**Last Updated:** [date]

## Recommendation
- Decision: Go | Conditional Go | No-Go
- Confidence: High | Medium | Low
- Decision Rationale: [short summary]

## Readiness Scorecard
| Area | Status (Green/Yellow/Red) | Evidence | Owner | Blocker? |
| --- | --- | --- | --- | --- |
| Feature Completion |  |  |  |  |
| Test Coverage & Pass Rate |  |  |  |  |
| Defect Risk |  |  |  |  |
| Security & Compliance |  |  |  |  |
| Performance & Reliability |  |  |  |  |
| Deployment Plan |  |  |  |  |
| Rollback/Recovery |  |  |  |  |
| Monitoring & Alerting |  |  |  |  |
| Stakeholder Approvals |  |  |  |  |

## Blocking Issues
| ID | Issue | Severity | Owner | Required Action | Due By |
| --- | --- | --- | --- | --- | --- |

## Conditional Go Criteria (if applicable)
- [ ] ...
- [ ] ...

## Release-Day Checklist
- [ ] Final artifact/tag verified
- [ ] DB migrations validated
- [ ] Feature flags/config validated
- [ ] Monitoring dashboards active
- [ ] Incident response contacts confirmed
- [ ] Rollback runbook confirmed

## Post-Release Validation Plan
- Success metrics to verify:
- Validation checkpoints and timing:
- Rollback trigger thresholds:
```

## Workflow
1. Collect evidence by readiness area
- Validate completeness of artifacts and map evidence into scorecard areas.

2. Evaluate risk and blockers
- Identify high/critical defects, unresolved dependencies, and deployment hazards.
- Classify each blocker with owner and due-by date.

3. Assess deployment safety
- Verify runbook, rollback strategy, and incident ownership.
- Confirm monitoring/alerting coverage for key user journeys and platform health.

4. Determine release recommendation
- Go: no blocking red items and acceptable risk profile.
- Conditional Go: limited unresolved items with explicit pre-release closure criteria.
- No-Go: one or more blocking critical/high conditions without safe mitigation.

5. Publish decision package
- Output recommendation, scorecard, blockers, and release-day checklist.

## Scoring Rules
- Green: Evidence complete, risk acceptable, no blocker.
- Yellow: Partial evidence or manageable risk, requires follow-up.
- Red: Missing critical evidence, unacceptable risk, or active blocker.

## Guardrails
- Do not mark Go when unresolved blocking red items exist.
- Do not assume sign-off, testing, or rollback readiness without evidence.
- Use TBD for unknowns and assign owner follow-up.
- Keep decisions traceable to concrete artifacts.

## Example Invocation
Use the release-readiness skill to evaluate release-candidate-2 and generate release-readiness-rc2.md with go or no-go recommendation.
