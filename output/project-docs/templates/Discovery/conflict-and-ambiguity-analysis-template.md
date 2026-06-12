# Conflict and Ambiguity Analysis

## Purpose
Identify conflicts, ambiguities, implied requirements, and missing requirements before a PRD or backlog is finalized. Use during discovery synthesis, after requirements extraction, or before sprint planning when gaps could affect delivery decisions.

---

## 1. Conflicting Requirements Across Stakeholders

| Issue | Why It Is a Problem | Questions to Ask to Resolve It | Potential Impact If Not Addressed |
|---|---|---|---|
| [Name the conflict clearly, e.g., "Speed goal vs. accuracy threshold"] | [Explain the tension — who holds each position and why they conflict] | [List 2–3 specific questions that would force a resolution] | [Describe the downstream consequence if the conflict is left open] |
| [Conflict] | [Why it is a problem] | [Resolution questions] | [Impact] |
| [Conflict] | [Why it is a problem] | [Resolution questions] | [Impact] |

**Common conflict patterns to look for:**
- Quality target vs. cost target
- High-automation goal vs. mandatory human review requirements
- Role model implied by users vs. role model implied by security/ops
- UI-based configuration vs. code-controlled configuration
- File-based export vs. direct system integration
- Single review queue vs. multi-stage review workflows
- Pre-built reference data vs. incrementally built reference data
- Short retention goal vs. audit/troubleshooting needs

---

## 2. Ambiguous Requirements That Could Be Interpreted Multiple Ways

| Issue | Why It Is a Problem | Questions to Ask to Resolve It | Potential Impact If Not Addressed |
|---|---|---|---|
| [Name the ambiguous term or requirement, e.g., "'Production ready'"] | [Explain how different stakeholders or contexts interpret it differently] | [Questions that force a single agreed definition] | [What breaks if teams use different interpretations] |
| [Ambiguity] | [Why it is a problem] | [Resolution questions] | [Impact] |
| [Ambiguity] | [Why it is a problem] | [Resolution questions] | [Impact] |

**Common ambiguous terms to check in your project:**
- "Done" or "production ready" — is it measurable?
- Key performance metrics — are formulas agreed and shared?
- Terms with multiple meanings in context (e.g., "configuration", "export", "integration")
- Feature names used loosely across teams
- Scope boundaries: what is "in" vs. "adjacent but out"

---

## 3. Implied Requirements That Were Not Explicitly Stated But Are Necessary

| Issue | Why It Is a Problem | Questions to Ask to Resolve It | Potential Impact If Not Addressed |
|---|---|---|---|
| [Name the implied requirement, e.g., "Role-based authentication model"] | [Explain why it must exist even though no one said it explicitly] | [Questions to surface and confirm the implicit need] | [Risk if this is discovered late in delivery] |
| [Implied requirement] | [Why it is a problem] | [Resolution questions] | [Impact] |
| [Implied requirement] | [Why it is a problem] | [Resolution questions] | [Impact] |

**Common implied requirements to check:**
- Authentication and authorization model
- Audit trail and event logging
- Data retention and purge rules
- Benchmark and test-data strategy
- Status/state model for core entities
- Reference-data governance and ownership
- Monitoring, alerting, and reporting
- Post-processing or transformation contract

---

## 4. Missing Requirements Based on Standard Patterns for This Type of Project

| Issue | Why It Is a Problem | Questions to Ask to Resolve It | Potential Impact If Not Addressed |
|---|---|---|---|
| [Name the missing requirement, e.g., "Security and privacy controls"] | [Explain why it is typically required and why its absence is a risk] | [Questions to define the requirement before it is too late] | [What happens if it is discovered after build begins] |
| [Missing requirement] | [Why it is a problem] | [Resolution questions] | [Impact] |
| [Missing requirement] | [Why it is a problem] | [Resolution questions] | [Impact] |

**Standard missing-requirement categories to audit:**
- Security, privacy, and access controls
- Compliance, audit, and regulatory requirements
- Availability, backup, and recovery
- User acceptance testing and release signoff
- Training and change-management requirements
- Environment and deployment strategy
- SLAs for key operations or workflows
- Ownership model for post-launch maintenance

---

## Highest-Priority Follow-Up Questions

Use this section to consolidate the most decision-critical open items from all four sections above. These should be tabled with stakeholders before the PRD is finalized.

1. [Question 1 — most critical unresolved conflict or ambiguity]
2. [Question 2]
3. [Question 3]
4. [Question 4]
5. [Question 5]
6. [Add as needed]

---

## Resolution Tracker

| Question / Issue | Owner | Status | Resolution Summary | Date Resolved |
|---|---|---|---|---|
| [Question or conflict description] | [Name or role] | Open / In Progress / Resolved | [How it was resolved] | [yyyy-mm-dd] |
