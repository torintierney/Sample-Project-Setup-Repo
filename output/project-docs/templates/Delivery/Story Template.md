---
title: <story-title>
parent_epic: <epic-id-or-filename>
summary: <1-2 sentence outcome-focused summary>
owner: <team-or-individual>
priority: <P0|P1|P2>
sprint: <sprint-name-or-date-range>
story_points: <1|2|3|5|8>
personas:
  - <primary-persona>
  - <secondary-persona>
dependencies:
  - <dependency-1>
  - <dependency-2>
acceptance_criteria:
  - <short AC summary 1>
  - <short AC summary 2>
tasks:
  - <implementation-task-1>
  - <qa-task-1>
links:
  - <related-epic-link-or-path>
  - <prd-link-or-path>
---

## Traceability Reminder
- Link every story to its parent epic in parent_epic and links.
- Cite the originating PRD section for each acceptance criterion (for example: PRD Section X.Y, FR-#, NFR-#).

## User Story
As a <persona>, I can <action> so that <benefit>.

## Acceptance Criteria (Gherkin-Style)

| ID | Given | When | Then | PRD Citation |
| --- | --- | --- | --- | --- |
| AC-1 | <context/precondition> | <user/system action> | <expected observable outcome> | <Section X.Y / FR-#> |
| AC-2 | <context/precondition> | <user/system action> | <expected observable outcome> | <Section X.Y / NFR-#> |
| AC-3 | <context/precondition> | <user/system action> | <expected observable outcome> | <Section X.Y> |

## Ambiguities and Clarification Needs
- <Ambiguity 1: What is the exact boundary condition for this story? Who decides edge cases?>
- <Ambiguity 2: Is this story required for all personas or specific roles?>
- <Dependency question: What upstream story, system, or approval must be complete before this work starts?>
- <Conflict/tradeoff question: What sprint scope, resource, or timeline tradeoff does this story create?>

## Non-Functional / Compliance Notes
- Performance: <latency/throughput target and source citation>
- Security: <authn/authz/data protection requirement>
- Compliance: <HIPAA/FDA/retention/audit requirement>
- Accessibility/Usability: <required standard or constraint>
- Data handling: <PHI/PII boundaries and storage policy>

## Telemetry and Reporting
- Events to capture:
  - <event-name-1>
  - <event-name-2>
- Metrics/KPIs:
  - <metric-1, target, source citation>
  - <metric-2, target, source citation>
- Dashboards/alerts:
  - <dashboard-name>
  - <alert-threshold and owner>

## Dependencies
- Upstream:
  - <service/team/system>
- Downstream:
  - <consumer/system/report>
- External constraints:
  - <regulatory/contract/vendor dependency>

## Risks and Mitigations
| Risk | Impact | Likelihood | Mitigation | Owner |
| --- | --- | --- | --- | --- |
| <risk-1> | <H/M/L> | <H/M/L> | <mitigation action> | <name/team> |
| <risk-2> | <H/M/L> | <H/M/L> | <mitigation action> | <name/team> |

## Rollout / Validation Checklist
- [ ] Parent epic linked and verified.
- [ ] Acceptance criteria map to PRD sections and requirement IDs.
- [ ] Test cases defined for all Given/When/Then criteria.
- [ ] Compliance and audit logging requirements validated.
- [ ] Telemetry events implemented and visible in reporting.
- [ ] Dependencies confirmed and tracked.
- [ ] Rollback plan documented.
- [ ] Stakeholder sign-off captured.

## Source References
- PRD: <path-or-link to source PRD in context (ingestion)>
- PRD Sections used:
  - <Section X.Y - title>
  - <Section A.B - title>
- Related epic:
  - <epic-id-or-path>
- Supporting docs:
  - <architecture/runbook/policy links>
