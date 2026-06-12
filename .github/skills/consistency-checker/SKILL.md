---
name: consistency-checker
description: Compares a set of project documents (PRDs, epics, stories, meeting notes, templates, or any combination) and identifies inconsistencies, contradictions, gaps, and misalignments across them. Use when you want to validate that a project's artifacts agree with each other before planning, sprint, or release. Works on any project — do not pass specific file paths; point to a folder or provide document contents directly.
---

# Consistency Checker Skill

## Goal
## Typical Workflow

1. Upload discovery or planning documents (DOCX, transcripts) to `input/` subdirectories
2. Run [doc-to-markdown](../../doc-to-markdown/SKILL.md) to convert to markdown:
  ```bash
  python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py input --delete-source
  ```
3. Run this skill (consistency-checker) to validate templates against each other:
  ```bash
  Use consistency-checker on output/project-docs/ or input/ (after doc-to-markdown conversion)
  ```

## Template Validation Phases

**Templates to validate BEFORE PRD finalization:**
- User personas
- Success metrics / Definition of Success
- Requirements extraction (vs. meeting notes)
- Cost & ROI model
- Risk-based requirement gaps

**Templates to validate AFTER PRD finalization but BEFORE story creation:**
- Traceability matrix (PRD → epics → stories)
- Risk register (against PRD scope)
- Definition of Ready (acceptance criteria clarity)
- Definition of Done (deliverable standards)

**Templates to validate AFTER story creation (FROZEN — do not change PRD or epics):**
- Story acceptance criteria (vs. epic acceptance criteria)
- Story-to-epic traceability
- Roadmap (final sequencing based on story estimates)
- Epic dependency matrix

**Templates that remain ACTIVE throughout (can be updated/added):**
- Meeting notes (from ongoing meetings)
- Risk register (new risks emerge continuously)
- Decision log (new decisions recorded)
- Stakeholder conversations log

## Goal
Scan a set of project documents provided by the user, detect cross-document inconsistencies, and return a prioritized, actionable findings report.

## Inputs Required
- A folder path or a set of documents to compare (for example: all files in output/project-docs/, or a PRD plus its epics plus its stories).
- Document types accepted: PRD, epic, story, meeting notes, Definition of Done, templates, decision logs, or any markdown artifact.
- Optional context:
  - Which dimension to focus on (scope, requirements, acceptance criteria, personas, dependencies, definitions, dates, owners).
  - Severity threshold (report all findings, or only High and Medium).

Do not hardcode file paths. Ask the user to provide a folder or paste document contents if no path is given.

## What to Check

### 1. Scope Consistency
- Does the scope defined in the PRD match what is included/excluded in each epic and story?
- Are any epics or stories delivering work that falls outside PRD scope?

### 2. Requirements Traceability
- Does every in-scope PRD requirement trace to at least one epic or story?
- Are there epics or stories with no clear PRD requirement driving them?

### 3. Acceptance Criteria Alignment
- Do story-level acceptance criteria logically implement the epic-level criteria?
- Do epic-level criteria trace back to PRD objectives and success metrics?

### 4. Persona Consistency
- Are the same user personas named consistently across PRD, epics, and stories?
- Do any documents introduce personas not defined in the PRD?

### 5. Dependency Consistency
- Are dependencies listed in one document also reflected in dependent documents?
- Are any blocking dependencies missing from the documents that require them?

### 6. Definition Consistency
- Are key terms, field names, and business definitions used consistently?
- Do any documents contradict each other on a shared definition?

### 7. Owner and Date Consistency
- Are owners and target dates consistent across documents?
- Do any documents have conflicting dates or unassigned owners for shared work?

### 8. Definition of Done Alignment
- Does each story and epic reference or meet the project's Definition of Done criteria?
- Are DoD criteria consistent across document types?

## Workflow

### Step 1 — Gather Documents
Ask the user to provide:
- A folder path containing the project documents, OR
- A list of specific documents to compare.

Read all provided documents before proceeding.

### Step 2 — Build a Consistency Map
For each shared concept (scope, requirements, personas, ACs, dependencies, terms, owners, dates), record what each document says.

### Step 3 — Detect Inconsistencies
Flag any case where two or more documents contradict, diverge, or are missing a reference the other requires.

Classify each finding:
- **High** — Contradicts another document directly or creates a delivery risk.
- **Medium** — Likely gap or misalignment that should be resolved before sprint.
- **Low** — Minor wording difference or non-critical inconsistency.

### Step 4 — Generate Report
Write findings to a file:
- `consistency-check-{project-name-or-date}.md`
- Save to the folder the user provides, or to `output/project-docs/` by default.

### Step 5 — Confirm and Iterate
After presenting findings, ask if the user wants to:
- Drill into a specific finding.
- Re-check after documents are updated.
- Focus on a specific document type or consistency dimension.

## Output Format

```markdown
# Consistency Check Report: [Project Name or Folder]
**Date:** [date]
**Documents reviewed:** [count and list]
**Dimensions checked:** [scope | requirements | ACs | personas | dependencies | definitions | owners/dates | DoD]

## Summary
- Total findings: [count]
- High: [count] | Medium: [count] | Low: [count]
- Overall consistency: Strong | Acceptable | Needs Attention | Critical Gaps

## Findings

### High Priority
| # | Dimension | Documents Involved | Inconsistency | Recommended Fix |
|---|-----------|-------------------|---------------|-----------------|
| 1 | | | | |

### Medium Priority
| # | Dimension | Documents Involved | Inconsistency | Recommended Fix |
|---|-----------|-------------------|---------------|-----------------|
| 1 | | | | |

### Low Priority
| # | Dimension | Documents Involved | Inconsistency | Recommended Fix |
|---|-----------|-------------------|---------------|-----------------|
| 1 | | | | |

## Traceability Coverage
| PRD Requirement | Traced to Epic | Traced to Story | Status |
|----------------|---------------|----------------|--------|
| | | | Covered / Gap |

## Next Steps
- [ ] [Recommended action 1]
- [ ] [Recommended action 2]
```

## Guardrails
- Do not assume documents are consistent because they use the same template.
- Do not fabricate requirements, personas, or definitions not present in the source documents.
- If a document is ambiguous, flag it as a Low finding rather than inferring intent.
- Do not modify any source document — only produce the report file.

## Example Invocation
"Use consistency-checker on all files in output/project-docs/ for the NexTitle project and report High and Medium findings only."
