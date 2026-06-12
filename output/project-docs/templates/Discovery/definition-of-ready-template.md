# Definition of Ready (DoR) Template

## Purpose
Use this checklist to validate that a backlog item (Epic or Story) is sufficiently clear, complete, and testable before entering the sprint. Ensures all stakeholders have acknowledged the requirement, ambiguities are resolved, and the team can commit with confidence.

---

## Story or Epic Title
- [Title]

## Requirement Clarity and Completeness

### Requirement Acknowledgment
- [ ] Requirement has been reviewed and acknowledged by sponsor/product owner
- [ ] Source stakeholder(s) confirmed (who requested this?)
- [ ] Meeting notes or discovery artifact linked: [link]
- [ ] Any conflicting stakeholder feedback recorded and resolved

### Functional Requirements Clear
- [ ] All required functionality is described in acceptance criteria
- [ ] Edge cases and boundary conditions are specified
- [ ] User workflows are documented (happy path and error paths)
- [ ] Integration points with other systems are identified
- [ ] Input/output formats and data contracts are defined

### Non-Functional Requirements Clear
- [ ] Performance expectations are quantified (latency, throughput, scale)
- [ ] Availability and SLA targets are defined
- [ ] Security and compliance requirements are documented
- [ ] Data handling and privacy requirements are clear
- [ ] Scalability constraints are understood

### Ambiguities Resolved
- [ ] All ambiguities from discovery have been addressed or explicitly noted
- [ ] Unclear terminology has been defined
- [ ] Ownership and decision rights are clear (who decides X?)
- [ ] Remaining ambiguities are documented with owner and target resolution date

---

## Dependencies and Scope

### Dependencies Understood
- [ ] Upstream dependencies identified and scheduled
- [ ] Downstream consumers identified
- [ ] External constraints (vendor, regulatory, contract) documented
- [ ] Dependency owners have confirmed feasibility and timing
- [ ] Blockers or risks from dependencies are documented

### Scope Clearly Bounded
- [ ] In-scope items are explicit
- [ ] Out-of-scope items are explicit
- [ ] Phasing (Phase 1, 2, 3) is assigned
- [ ] Phase sequencing rationale is documented (why Phase 1 vs later?)
- [ ] Trade-offs between scope, cost, and timeline are recorded

### Interdependency and Conflict Questions Answered
- [ ] This requirement's relationship to other requirements is mapped
- [ ] Any scope conflicts with other work are identified and resolved
- [ ] Cost or resource trade-offs are understood
- [ ] Decision on trade-offs is recorded with owner and date

---

## Acceptance Criteria and Testability

### Acceptance Criteria Quality
- [ ] Acceptance criteria are written in Gherkin (Given/When/Then) format
- [ ] Each criterion is testable (can be verified objectively)
- [ ] Criteria cover happy path, error cases, and boundary conditions
- [ ] Each criterion is traceable to PRD section or requirement ID
- [ ] Criterion ownership (who validates?) is clear

### Test Readiness
- [ ] Test cases can be written from acceptance criteria
- [ ] Data requirements for testing are defined
- [ ] Test environment and prerequisites are identified
- [ ] Acceptance criteria are linked to PRD sections and requirement numbers

### Success Metrics Defined
- [ ] Business success metrics are quantifiable
- [ ] Operational metrics (if applicable) are defined
- [ ] Measurement method is documented
- [ ] Baseline and target values are set
- [ ] Owner for reporting is assigned

---

## Stakeholder Sign-Off and Capacity

### Stakeholder Review Complete
- [ ] Product owner has reviewed and approved
- [ ] Engineering lead has reviewed for feasibility
- [ ] Security/compliance has reviewed (if applicable)
- [ ] Affected teams have reviewed for dependencies
- [ ] All stakeholder sign-offs are documented (name, date, approval)

### Capacity and Commitment
- [ ] Story size is estimated in story points
- [ ] Estimated effort is reasonable for planned sprint
- [ ] Required skills are identified
- [ ] Team capacity for this work is confirmed
- [ ] Owner is assigned (who will drive implementation?)

---

## Documentation and Traceability

### Source Documentation Linked
- [ ] PRD linked (if from PRD discovery)
- [ ] Parent epic linked (if applicable)
- [ ] Related stories/epics linked
- [ ] Meeting notes or discovery artifacts linked
- [ ] Any supporting documentation (architecture, runbooks) referenced

### Requirement Traceability
- [ ] Each acceptance criterion maps back to PRD section or requirement ID
- [ ] Requirement-to-objective mapping is recorded (if in PRD)
- [ ] Requirements that affect roadmap/phase are marked

---

## Known Risks and Assumptions

### Risks Documented
- [ ] Any implementation risks are identified
- [ ] Risk mitigation plan is outlined
- [ ] Risk owner is assigned
- [ ] Contingency plan exists (if high-risk item)

### Assumptions Documented
- [ ] Key assumptions are documented
- [ ] Assumption validity is verified or flagged for validation
- [ ] Assumption owner is assigned

---

## Definition of Ready Sign-Off

| Role | Name | Approval | Date | Notes |
| --- | --- | --- | --- | --- |
| Product Owner | [Name] | Approved / Hold | [YYYY-MM-DD] | [Any conditions] |
| Engineering Lead | [Name] | Approved / Hold | [YYYY-MM-DD] | [Any conditions] |
| Architecture / Technical Lead | [Name] | Approved / Hold | [YYYY-MM-DD] | [Any conditions] |
| Other Stakeholder | [Name] | Approved / Hold | [YYYY-MM-DD] | [Any conditions] |

---

## Ready to Commit?
- [ ] All checkboxes above are marked complete
- [ ] All stakeholder sign-offs are captured
- [ ] No high-risk items are unmitigated
- [ ] Team has capacity and skills for this sprint

**Status:** Ready for Sprint / Needs Refinement  
**Date:** [YYYY-MM-DD]
