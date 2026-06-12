# Risk Register

## Purpose
Capture, score, and action all project risks in one place. This register combines risk identification with mitigation planning, monitoring cadence, and requirement follow-through so teams have a single source of truth from discovery through delivery.

---

## Risk Register

| Risk ID | Risk Description | Category | Likelihood | Impact | Rationale | Owner |
|---|---|---|---|---|---|---|
| R001 | [Clear risk statement] | [Category] | High / Medium / Low | High / Medium / Low | [Why this risk exists in this project context] | [Role or name] |
| R002 | [Risk statement] | [Category] | High / Medium / Low | High / Medium / Low | [Rationale] | [Role or name] |
| R003 | [Risk statement] | [Category] | High / Medium / Low | High / Medium / Low | [Rationale] | [Role or name] |
| R004 | [Risk statement] | [Category] | High / Medium / Low | High / Medium / Low | [Rationale] | [Role or name] |
| R005 | [Risk statement] | [Category] | High / Medium / Low | High / Medium / Low | [Rationale] | [Role or name] |
| R006 | [Risk statement] | [Category] | High / Medium / Low | High / Medium / Low | [Rationale] | [Role or name] |

---

## Category Guide

Use categories consistently for grouping, reporting, and applying category-level guidance below.

- Technical
- Organizational
- Regulatory / Compliance
- Data / Security
- Vendor / Dependency
- Timeline / Budget
- [Add domain-specific categories as needed]

---

## Highest-Priority Risks

List the risks most likely to require executive attention or pre-project clarification.

| Risk ID | Why It Is Critical |
|---|---|
| [R0XX] | [What it can materially change: scope, approval, timeline, quality, or business case] |
| [R0XX] | [Criticality rationale] |
| [R0XX] | [Criticality rationale] |

---

## Core Mitigation Matrix

For each risk, define the type, controls, signals, and response plan.

| Risk ID | Risk Summary | Risk Type | Primary Owner | Preventive Controls | Detection Signals | Response Actions |
|---|---|---|---|---|---|---|
| R001 | [Risk statement] | [Threat / Uncertainty / Assumption] | [Role or name] | [What you do before it happens] | [Metrics or signals that indicate it is occurring] | [What to do if it occurs] |
| R002 | [Risk statement] | [Risk type] | [Role or name] | [Preventive controls] | [Detection signals] | [Response actions] |
| R003 | [Risk statement] | [Risk type] | [Role or name] | [Preventive controls] | [Detection signals] | [Response actions] |
| R004 | [Risk statement] | [Risk type] | [Role or name] | [Preventive controls] | [Detection signals] | [Response actions] |
| R005 | [Risk statement] | [Risk type] | [Role or name] | [Preventive controls] | [Detection signals] | [Response actions] |

**Risk Type Guide:**
- **Threat** — A known negative event that will damage delivery if it occurs (e.g., a vendor misses a deadline)
- **Uncertainty** — An unknown where the outcome could be positive or negative (e.g., regulatory ruling still pending)
- **Assumption** — A stated belief that has not been validated and could be wrong (e.g., "data quality is sufficient")

---

## Monitoring Cadence

| Risk ID | Review Cadence | Review Forum | RAG Status | Last Reviewed | Next Review |
|---|---|---|---|---|---|
| R001 | [Weekly / Biweekly / Milestone-based] | [Forum name] | Green / Amber / Red | [yyyy-mm-dd] | [yyyy-mm-dd] |
| R002 | [Cadence] | [Forum name] | Green / Amber / Red | [yyyy-mm-dd] | [yyyy-mm-dd] |
| R003 | [Cadence] | [Forum name] | Green / Amber / Red | [yyyy-mm-dd] | [yyyy-mm-dd] |

---

## Requirement Follow-Through

Convert mitigation actions into explicit PRD requirements, release gates, or operational controls so risk responses are traceable to delivery.

| Risk ID | Derived Requirement or Gate | PRD Section / Epic | Owner |
|---|---|---|---|
| [R0XX] | [Requirement, release gate, or acceptance criterion derived from mitigation] | [PRD Section or Epic ID] | [Role] |
| [R0XX] | [Requirement or gate] | [PRD Section or Epic ID] | [Role] |
| [R0XX] | [Requirement or gate] | [PRD Section or Epic ID] | [Role] |

---

## Risk Status Tracker

| Risk ID | Owner | RAG Status | Current Status | Last Reviewed | Next Action | Escalation Needed |
|---|---|---|---|---|---|---|
| [R0XX] | [Role or name] | Green / Amber / Red | Open / Monitoring / Mitigating / Closed | [yyyy-mm-dd] | [Action] | Yes / No |
| [R0XX] | [Role or name] | Green / Amber / Red | Open / Monitoring / Mitigating / Closed | [yyyy-mm-dd] | [Action] | Yes / No |
| [R0XX] | [Role or name] | Green / Amber / Red | Open / Monitoring / Mitigating / Closed | [yyyy-mm-dd] | [Action] | Yes / No |

---

## Category-Level Risk Guidance

Use the applicable sections below to ensure consistent identification, detection, and response patterns by risk category.

### Technical Risks

| Area | Guidance |
|---|---|
| What commonly goes wrong | [Design gaps, integration failures, performance degradation, technical debt accumulation] |
| Early detection methods | [Test coverage metrics, performance benchmarks, integration test failures, code review signals] |
| Preventive measures | [Architecture review gates, proof-of-concept spikes, non-functional requirements in DoR] |
| Mitigation if it occurs | [Scope reduction, technical debt sprint, architecture escalation, spike to unblock] |

### Organizational Risks

| Area | Guidance |
|---|---|
| What commonly goes wrong | [Unclear ownership, stakeholder misalignment, sponsor disengagement, competing priorities] |
| Early detection methods | [Missed decisions, low meeting attendance, delayed approvals, change-request volume] |
| Preventive measures | [RACI definition, decision log, regular steering cadence, explicit escalation path] |
| Mitigation if it occurs | [Escalate to sponsor, re-baseline scope, hold requirements review, re-align stakeholders] |

### Regulatory and Compliance Risks

| Area | Guidance |
|---|---|
| What commonly goes wrong | [Audit gaps, data retention violations, undocumented controls, late compliance review] |
| Early detection methods | [Compliance checkpoints, evidence review cadence, policy change notifications] |
| Preventive measures | [Involve compliance early, build audit logging into DoR, include compliance sign-off in release gates] |
| Mitigation if it occurs | [Hold release, execute rework/re-approval steps, document remediation evidence] |

### Data and Security Risks

| Area | Guidance |
|---|---|
| What commonly goes wrong | [Access control gaps, unencrypted data, missing audit logs, secrets in code, poor data quality] |
| Early detection methods | [Access audits, configuration scans, data quality dashboards, security monitoring alerts] |
| Preventive measures | [Least privilege, encryption at rest/transit, data classification, secret rotation policy] |
| Mitigation if it occurs | [Credential rotation, incident response activation, containment, re-approval before relaunch] |

### Vendor and Dependency Risks

| Area | Guidance |
|---|---|
| What commonly goes wrong | [External system constraints, late API delivery, changing vendor terms, undocumented contracts] |
| Early detection methods | [Dependency milestone tracking, contract test failures, vendor communication gaps] |
| Preventive measures | [Early acceptance criteria collection, formal dependency tracker, defined fallback path] |
| Mitigation if it occurs | [Execute fallback, replan affected epics, escalate to sponsor for timeline/scope decision] |

### Timeline and Budget Risks

| Area | Guidance |
|---|---|
| What commonly goes wrong | [Scope creep, hidden work, delivery gate slippage, cost drift, optimistic estimates] |
| Early detection methods | [Change-request volume, sprint velocity drops, milestone slippage, variance tracking] |
| Preventive measures | [Explicit non-goals, scope controls, milestone deliverables, baseline assumption documentation] |
| Mitigation if it occurs | [Rebaseline scope/timeline/budget, secure stakeholder approvals, remove Could-Have items] |

---

## Organizational Risk Deep-Dive

Use this for stakeholder dynamics, decision rights, ownership gaps, and adoption risks that need deeper analysis.

| Organizational Risk | Why This Is a Problem | Worst-Case Scenario | Proactive Mitigation | Early Warning Signs |
|---|---|---|---|---|
| [Risk description] | [Why it matters to delivery or outcomes] | [What failure looks like at its worst] | [Preventive actions before it escalates] | [Behavioral or process signals to watch for] |
| [Risk description] | [Why it matters] | [Worst case] | [Mitigation] | [Signals] |
| [Risk description] | [Why it matters] | [Worst case] | [Mitigation] | [Signals] |
