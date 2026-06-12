# Inconsistency Analysis

## Purpose
Cross-check finalized project artifacts for structural conflicts — where two or more documents state different things about the same requirement, priority, risk, or scope boundary. Use this after a set of discovery or delivery documents has been produced to catch contradictions before backlog creation or sprint planning.

> **Distinction from Conflict and Ambiguity Analysis:** The Conflict and Ambiguity Analysis captures stakeholder-level tensions in raw requirements. This document captures structural inconsistencies between finalized artifacts.

---

## Priority Classifications

- **Blocking** — Will create scope misalignment, contradictory backlog items, or incorrect release criteria if left unresolved.
- **Informational** — A documentation gap or traceability issue that should be corrected but does not materially mislead planning decisions.

---

## Inconsistency Index

| ID | Short Description | Affected Documents | Priority |
|---|---|---|---|
| INC-01 | [Brief name of the inconsistency] | [Doc A], [Doc B], [Doc C] | Blocking / Informational |
| INC-02 | [Brief name] | [Doc A], [Doc B] | Blocking / Informational |
| INC-03 | [Brief name] | [Doc A], [Doc B] | Blocking / Informational |
| INC-04 | [Brief name] | [Doc A], [Doc B] | Blocking / Informational |
| INC-05 | [Brief name] | [Doc A], [Doc B] | Blocking / Informational |

---

## Detailed Findings

### INC-01 — [Short description]

**Affected documents:**
- [Document name and section or row]
- [Document name and section or row]
- [Document name and section or row]

**Nature of the conflict:**
[Describe what each document says and why the statements conflict. Be specific — quote or paraphrase the contradictory language and explain why a reader using only one document would be misled.]

**Recommended resolution:**
[Describe the concrete action needed to resolve this. Specify which document should change, what the update should say, and whether a stakeholder decision is needed before the fix can be made.]

---

### INC-02 — [Short description]

**Affected documents:**
- [Document name and section]
- [Document name and section]

**Nature of the conflict:**
[What each document says and why they conflict]

**Recommended resolution:**
[What to change and where]

---

*Add additional INC-## sections following the same format for each item in the index.*

---

## Common Inconsistency Patterns to Look For

Use these as a checklist when reviewing a document set:

- **Priority misalignment** — A requirement is Must-Have in one doc and Should-Have in another
- **Phase assignment conflicts** — A feature is in Phase 1 scope in one doc and out-of-scope or Phase 2+ in another
- **Role or access model differences** — Number of roles, permission boundaries, or admin model defined differently across docs
- **Metric definition drift** — The same KPI defined with different formulas, baselines, or targets in different docs
- **Risk coverage gaps** — A risk called out in one doc is absent from the Risk Register or vice versa
- **Scope boundary language** — One doc uses hard exclusions ("not in scope") while another uses soft language ("likely out of scope") for the same item
- **Traceability breaks** — An objective in a traceability matrix depends on a requirement that has a lower priority than the objective requires
- **Implied vs. explicit requirements** — A downstream doc treats something as decided that an upstream doc still marks as open

---

## Resolution Tracker

| ID | Resolution Action | Owner | Status | Date Resolved |
|---|---|---|---|---|
| INC-01 | [What was done] | [Name or role] | Open / In Progress / Resolved | [yyyy-mm-dd] |
| INC-02 | | | | |
| INC-03 | | | | |
