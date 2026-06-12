# Roadmap Template

## Purpose
This roadmap defines the phasing strategy for requirements and epics across the project timeline. It maps requirements to phases, documents the rationale for sequencing, and shows cross-phase dependencies, resource allocation, and critical path items.

---

## Project Overview
- **Project:** [Project Name]
- **Owner:** [Owner Name/Role]
- **Created:** [YYYY-MM-DD]
- **Last Updated:** [YYYY-MM-DD]
- **Status:** [Draft | In Review | Approved | Active]

---

## Phasing Strategy and Rationale

### Phase Structure
- **Phase 1 (Now):** [Time range, e.g., Q2 2024] — [Primary objective]
- **Phase 2 (Next):** [Time range] — [Primary objective]
- **Phase 3 (Later):** [Time range] — [Primary objective]
- **Phase 4+ (Future):** [Time range] — [Primary objective, if applicable]

### Phasing Rationale
- [Reason for Phase 1 focus, e.g., "MVP market entry, customer acquisition"]
- [Reason for Phase 2, e.g., "Core operational capability, efficiency gains"]
- [Reason for Phase 3, e.g., "Optimization, advanced features, scale"]
- [Phasing constraints, e.g., "Dependent on vendor product roadmap", "Regulatory approval required"]

---

## Phase 1: [Phase Name] — [Timeline]

### Objective
[One clear objective and business value for Phase 1]

### Requirements and Epics in Scope
| ID | Requirement / Epic | Type | Priority | Effort (Est.) | Owner | Status |
| --- | --- | --- | --- | --- | --- | --- |
| FR-1 | [Functional requirement title] | Story | Must-Have | 8 pts | [Team] | Not Started |
| NFR-2 | [Non-functional requirement] | Story | Must-Have | 5 pts | [Team] | Not Started |
| EPIC-1 | [Epic title] | Epic | Must-Have | 21 pts | [Lead] | Not Started |

### Key Success Metrics
- [Metric 1, e.g., "Deliver MVP with core workflows in production"]
- [Metric 2, e.g., "Achieve 95% uptime SLA in pilot group"]
- [Metric 3, e.g., "Reduce processing time by 30% vs. baseline"]

### Critical Path and Dependencies
- **Critical Item 1:** [What must be done first] — Owner: [Name] — Target: [Date]
- **Critical Item 2:** [What blocks Phase 2 work] — Owner: [Name] — Target: [Date]
- **Upstream Dependency:** [If blocked by external team/vendor] — Owner: [External contact] — Needed by: [Date]

### Resources and Capacity
- **Team:** [Team name/composition]
- **FTE Allocation:** [% or headcount]
- **Known Constraints:** [Shared resources, vacations, capacity limits]

### Risk and Contingency
- **High Risk:** [Risk description] — Mitigation: [Plan] — Owner: [Name]
- **Fallback Plan:** [If critical path item slips, what is plan B?]

---

## Phase 2: [Phase Name] — [Timeline]

### Objective
[One clear objective and business value for Phase 2]

### Requirements and Epics in Scope
| ID | Requirement / Epic | Type | Priority | Effort (Est.) | Owner | Status |
| --- | --- | --- | --- | --- | --- | --- |
| FR-3 | [Functional requirement title] | Story | Should-Have | 8 pts | [Team] | Not Started |
| EPIC-2 | [Epic title] | Epic | Should-Have | 13 pts | [Lead] | Not Started |

### What Phase 1 Must Complete to Unblock Phase 2
- [Requirement or capability from Phase 1 that Phase 2 depends on]
- [Architecture or integration that Phase 2 relies on]

### Key Success Metrics
- [Metric 1]
- [Metric 2]

### Critical Path and Dependencies
- **Critical Item 1:** [Description] — Owner: [Name] — Target: [Date]

### Resources and Capacity
- **Team:** [Team name/composition]
- **FTE Allocation:** [% or headcount]

---

## Phase 3: [Phase Name] — [Timeline]

### Objective
[One clear objective and business value for Phase 3]

### Requirements and Epics in Scope
| ID | Requirement / Epic | Type | Priority | Effort (Est.) | Owner | Status |
| --- | --- | --- | --- | --- | --- | --- |
| FR-4 | [Functional requirement title] | Story | Could-Have | 5 pts | [Team] | Not Started |
| EPIC-3 | [Epic title] | Epic | Could-Have | 8 pts | [Lead] | Not Started |

### What Phases 1 & 2 Must Complete to Unblock Phase 3
- [Capability or integration from prior phases]

### Key Success Metrics
- [Metric 1]
- [Metric 2]

---

## Cross-Phase Dependencies and Critical Path

### Dependency Map
| Dependent Phase | Blocks | Reason | Owner | Target Date |
| --- | --- | --- | --- | --- |
| Phase 2 | Phase 1: FR-1, EPIC-1 | Requires MVP authentication and core workflow | [Name] | [Date] |
| Phase 3 | Phase 2: EPIC-2 | Depends on analytics platform ready | [Name] | [Date] |

### Critical Path Items (Phase 1 → Phase 2 → Phase 3)
1. [Phase 1 item that unblocks everything downstream] — Critical by [Date]
2. [Phase 2 item that Phase 3 cannot start without] — Critical by [Date]
3. [External dependency] — Critical by [Date]

### Parallel vs. Sequential Work
- [Work that can run in parallel, e.g., "Phase 2 infrastructure can start week N of Phase 1"]
- [Work that must be sequential, e.g., "Cannot start Phase 3 until Phase 2 validation complete"]

---

## Resource and Budget Summary

### Effort Allocation by Phase
| Phase | Estimated Total Effort | Team Capacity Available | Confidence | Notes |
| --- | --- | --- | --- | --- |
| Phase 1 | [X story points or person-months] | [Y] | High / Medium / Low | [Any constraints] |
| Phase 2 | [X] | [Y] | High / Medium / Low | [Any constraints] |
| Phase 3 | [X] | [Y] | High / Medium / Low | [Any constraints] |

### Budget and Cost Considerations
- **Phase 1 Cost:** [Estimate or range]
- **Phase 2 Cost:** [Estimate or range]
- **Phase 3 Cost:** [Estimate or range]
- **Contingency:** [% reserve]

---

## Timeline and Go-Live Milestones

### Milestone Schedule
| Milestone | Target Date | Owner | Status | Notes |
| --- | --- | --- | --- | --- |
| Phase 1 Requirements Finalized | [Date] | [Name] | Not Started | All PRD sign-offs complete |
| Phase 1 Development Complete | [Date] | [Name] | Not Started | All acceptance criteria met |
| Phase 1 UAT and Pilot | [Date] | [Name] | Not Started | Validate with 5-10 power users |
| Phase 1 Production Launch | [Date] | [Name] | Not Started | Go-live approval given |
| Phase 2 Requirements Finalized | [Date] | [Name] | Not Started | |
| Phase 2 Production Launch | [Date] | [Name] | Not Started | |
| Phase 3 Production Launch | [Date] | [Name] | Not Started | |

### Timeline Visualization
```
Phase 1        |----[Dev]----[UAT]----[Launch]
Phase 2                           |----[Dev]----[UAT]----[Launch]
Phase 3                                              |----[Dev]----[Launch]
                                 ↑ Dependency point
```

---

## Scope Changes and Decision Log

### Scope Trade-Offs
| Trade-Off | Recommendation | Decision | Owner | Date |
| --- | --- | --- | --- | --- |
| [Requirement A into Phase 1 vs Phase 2?] | [Recommendation] | [Approved/Rejected] | [Name] | [Date] |
| [Resource shift from Phase 1 to Phase 2?] | [Recommendation] | [Approved/Rejected] | [Name] | [Date] |

### Out of Scope (Explicitly Not Planned)
- [Feature or requirement that is intentionally not in roadmap]
- [Future consideration after Phase 3]

---

## Risks, Assumptions, and Constraints

### Key Assumptions
- [Assumption 1, e.g., "Phase 2 depends on vendor releasing API by Q3"]
- [Assumption 2, e.g., "Team capacity remains stable; no turnover"]
- [Assumption 3, e.g., "Customer feedback from Phase 1 validates Phase 2 direction"]

### Risks and Mitigation
| Risk | Impact | Likelihood | Mitigation | Owner |
| --- | --- | --- | --- | --- |
| [High-risk item, e.g., "Key engineer leaves"] | [High] | [Medium] | [Cross-train team member] | [Name] |
| [Regulatory delay, e.g., "Compliance review takes longer"] | [High] | [Medium] | [Start early; pre-submission] | [Name] |
| [Dependency risk, e.g., "Vendor API delayed"] | [Medium] | [Medium] | [Plan fallback integration] | [Name] |

### Constraints
- [Technical constraint, e.g., "Legacy system can only handle 1000 TPS"]
- [Organizational constraint, e.g., "Cannot hire for Phase 2"]
- [Regulatory constraint, e.g., "Compliance approval required before Phase 1 launch"]

---

## Stakeholder Communication and Sign-Off

### Roadmap Review Schedule
- **Planned Review Cadence:** [Monthly / Quarterly / As-needed]
- **Next Review Date:** [Date]
- **Stakeholders:** [List of executives, product, engineering, ops]

### Approval and Sign-Off
| Role | Name | Approval | Date | Notes |
| --- | --- | --- | --- | --- |
| Executive Sponsor | [Name] | Approved / Hold | [Date] | |
| Product Owner | [Name] | Approved / Hold | [Date] | |
| Engineering Lead | [Name] | Approved / Hold | [Date] | |
| Finance / Budget Owner | [Name] | Approved / Hold | [Date] | |

---

## Related Documents
- PRD: [Link to PRD]
- Epic List: [Link or reference]
- Risk Register: [Link]
- Capacity Plan: [Link]
- Decision Log: [Link]
