---
name: weekly-status-report
description: Generates a structured weekly project status report from files and transcripts uploaded or modified during the current week. Accepts meeting notes, transcripts, PPTX decks, PRDs, epics, stories, or any combination. Use when you need a consistent, leadership-ready weekly status report synthesized from the week's project activity. Produces a formatted markdown report and an email-ready summary.
---

# Weekly Status Report Skill

## Goal
Generate a weekly executive status report using the provided PowerPoint template structure.

## Approved Master Template (Current)
Default template path for weekly runs:
- `output/project-docs/templates/Weekly Status Reports - Template.pptx`

Use this as the master template unless the user explicitly provides a different approved template.

## Inputs Required
- Meeting transcripts
- Notes
- Optional: style reference deck (.pptx) for visual fidelity

If no source materials are provided, ask the user to supply them before proceeding.

## Repeatability Contract (Required)
To make output formatting repeatable, treat weekly report generation as a locked-template process.

Required artifacts:
1. A single approved master template deck (source of truth), including slide master/theme.
2. A fixed slide map that binds each required section to a specific slide index/layout.
3. Placeholder-based content zones in the template (title/body/table placeholders), not free-form text boxes.

Rules:
- Use the same approved master template every run unless user explicitly requests a template change.
- Do not create new slide layouts, free-form visual blocks, or ad-hoc typography.
- Populate placeholders only; avoid manual object placement when a placeholder exists.
- Keep section-to-slide mapping stable across runs.

If any required artifact is missing, stop and request it before producing `.pptx`.

## Formatting Fidelity Mode (Required for PPTX)
When creating the PowerPoint, formatting must match the style reference deck as closely as possible.

Use these rules in order:
1. Treat the reference deck as a template, not just a color/font hint.
2. Reuse existing slide layouts from the template deck; do not switch to default layouts.
3. Preserve theme, palette, font families, font weights, title/body hierarchy, spacing, and alignment.
4. Prefer replacing placeholder text in existing template-like slides over creating brand-new visual patterns.
5. Keep bullet density, line length, and section ordering aligned to the sample deck style.
6. Do not introduce new chart styles, icon sets, shapes, or decorative elements not present in the template.
7. If a required section has no direct visual counterpart in the template, use the closest existing layout.

If exact style fidelity cannot be achieved from available inputs, explicitly state what could not be matched.

## Signal Extraction
Read all provided materials and extract the following signals:

| Signal | Look For |
|--------|----------|
| Accomplishments | Completed work, delivered outputs, closed items |
| Schedule status | Milestone hits/misses, delay indicators, date changes |
| Budget status | Spend notes, variance references, burn rate mentions |
| Scope status | Scope changes, added/removed work, out-of-scope discussions |
| Risks and issues | Blockers, concerns, flagged risks, open escalations |
| Mitigations | Actions taken or planned to address risks/issues |
| Decisions needed | Open decisions, pending approvals, unresolved questions |
| Next week plan | Committed activities, upcoming milestones, owner commitments |
| Action items | Named owners and due dates from meetings or discussions |

## Workflow

### Step 1 — Gather and Read Materials
Read all provided meeting transcripts and notes.

Also validate required formatting assets for repeatability:
- Confirm the approved master template deck path.
- Confirm a fixed section-to-slide mapping.
- Confirm placeholders exist for title/body/table content.

If these are not available, stop and request them.

### Step 2 — Extract Signals
Extract only the signals needed for the required output sections.

### Step 3 — Resolve Gaps
For any required section with no supporting evidence in the source materials:
- Mark explicitly as: `Not explicitly stated in source materials`
- Do not invent status, metrics, or outcomes.

### Step 4 — Determine RAG Status
For each health dimension (Overall, Schedule, Budget, Scope), assign:
- **Green** — On track, no significant concerns.
- **Yellow** — At risk, needs monitoring or action.
- **Red** — Off track, escalation or intervention required.

Base RAG only on signals found in the provided materials. If insufficient signal exists, mark as `Not enough information`.

### Step 5 — Draft Report Using Required Template
Use the exact section order and naming specified in `Output Format`.

### Step 6 — Build Presentation with Inherited Formatting
Create a PowerPoint version of the report and inherit style from the provided reference deck:
- Start from the reference deck and preserve template styling decisions.
- Reuse theme colors, fonts, slide master/layouts, and spacing patterns from the style reference deck.
- Preserve section order and naming from the report structure.
- Keep slide titles and bullet structure consistent with the reference look and feel.
- Use concise bullets (prefer 4-6 bullets max per slide, no paragraph blocks unless summary slide).
- Include a title slide, health summary slide, accomplishments, risks/issues, mitigations, decisions, next-week plan, and sources.
- Prefer text substitution in template placeholders instead of free-form object placement.

Deterministic build behavior:
- Use fixed slide mapping for required sections (same section -> same slide each run).
- Preserve all existing font names, font sizes, line spacing, paragraph spacing, and bullet indentation levels.
- Preserve original placeholder geometry (x/y/width/height); only replace text.
- For tables, update cell text only; do not restyle table borders, fills, or text styles.
- If content overflows a placeholder, shorten text rather than resizing or restyling the placeholder.
- If a section has no mapped slide, duplicate the closest approved slide from the template and keep its formatting unchanged.

Save PowerPoint to:
- `output/project-docs/weekly-status-{project-slug}-{YYYY-MM-DD}.pptx`

### Step 7 — Quality Check
Before finalizing:
- Confirm all accomplishments use past-tense action verbs.
- Confirm each mitigation is tied to a specific risk or issue.
- Confirm RAG statuses are supported by source signals.
- Confirm no section is fabricated.
- Confirm the week label matches the reporting period.
- Confirm slide formatting matches the reference deck style profile.
- Confirm slide-by-slide visual parity for title treatment, body text hierarchy, and spacing rhythm.
- Confirm executive tone, concise wording, and no repetition.
- Confirm all slides use theme fonts only (no fallback fonts).
- Confirm no new layouts, shape styles, or colors were introduced.
- Confirm section titles exactly match required section names.
- Confirm no text box was manually inserted where a placeholder existed.

### Step 8 — Save Output
Write report to:
- `output/project-docs/weekly-status-{project-slug}-{YYYY-MM-DD}.md`

## Output Format

Match exactly these sections and order:

1. `Key Activities Completed This Week`
- Bullet points (max 6-8), concise and outcome-focused.

2. `Key Activities Planned for Next Week`
- Forward-looking, specific actions.

3. `Critical Open Questions / Issues`
- Clear, decision-oriented or blocker-oriented.

4. `Risks / Issues Table`
For each item include:
- Description
- Impact
- Mitigation
- Severity (Low/Med/High)
- Owner (if known)
- Target resolution (if known)

5. `Status:`
- Overall (G/Y/R)
- Schedule (G/Y/R)
- Budget (G/Y/R)
- Scope (G/Y/R)

6. `Scope Summary`
- 2-3 sentences max, business-focused.

7. `Status Overview`
- Executive summary (2-3 sentences).
- Call out key risks or inflection points.

## Report Structure (Markdown)

```markdown
# Weekly Status Report: [Project / Program Name]
**Week of:** [YYYY-MM-DD]
**Prepared by:** [Name or role if known]
**Audience:** [Leadership | Team | Stakeholders]

---

## Key Activities Completed This Week
- [Past-tense bullet: Completed X, Delivered Y, Finalized Z]
- ...

---

## Key Activities Planned for Next Week
- [Specific forward-looking action 1]
- [Specific forward-looking action 2]
- ...

---

## Critical Open Questions / Issues
- [Decision-oriented question or blocker]
- ...

---

## Risks / Issues Table
| # | Description | Impact | Mitigation | Severity | Owner | Target Resolution |
|---|-------------|--------|------------|----------|-------|-------------------|
| 1 |             |        |            | Low/Med/High |       |                   |

---

## Status
- Overall: [G/Y/R + one-line rationale]
- Schedule: [G/Y/R + one-line rationale]
- Budget: [G/Y/R + one-line rationale]
- Scope: [G/Y/R + one-line rationale]

---

## Scope Summary
[2-3 business-focused sentences]

---

## Status Overview
[2-3 executive sentences with key risks or inflection points]

---

## Source Materials
- [List of files used to generate this report]
```

## Email Summary (Optional)
After the report, generate a condensed email version using the stakeholder-update format:

```markdown
Hi [audience],

## Accomplishments
- ...

## Overall Status (Overall, Schedule, Budget, Scope)
- Overall: [RAG + rationale]
- Schedule: [RAG + rationale]
- Budget: [RAG + rationale]
- Scope: [RAG + rationale]

## Status Summary for (Week [date])
[Single paragraph.]

## Impacts
- ...

## Mitigations
- ...

## Upcoming Decisions
- ...

## Next Week Planned Activities
- ...
```

## Guardrails
- Do not reorder or rename required sections.
- Do not fabricate accomplishments, RAG status, budget, or schedule details.
- Do not skip a section — mark missing data explicitly.
- Keep `Key Activities Completed This Week` to 6-8 bullets max.
- Keep `Scope Summary` and `Status Overview` to 2-3 sentences each.
- Each risk row must include mitigation and severity.
- Source materials must be listed at the bottom of the report.
- Do not invent formatting styles; always inherit from the provided reference deck.
- If reference deck is missing, stop and request it before generating `.pptx` output.
- Use concise, executive-ready consulting tone.
- No fluff. No repetition.
- Use a single approved master template deck for all weekly runs.
- Keep a fixed section-to-slide mapping and do not rotate sections across layouts.
- Replace placeholder text only; do not manually redesign slides during report generation.

## Section-to-Slide Map (Default)
Use this map unless the user provides a different approved map.

1. Title / Week metadata
2. Key Activities Completed This Week
3. Key Activities Planned for Next Week
4. Critical Open Questions / Issues
5. Risks / Issues Table
6. Status
7. Scope Summary
8. Status Overview
9. Source Materials

If the master template has a different approved sequence, follow that sequence consistently on every run.

## Example Invocations
- "Use weekly-status-report to generate a status report for the NexTitle project from this week's meeting notes in NexTitle Test case/ and use output/project-docs/templates/Weekly Status Reports - Template.pptx for slide formatting."
- "Use weekly-status-report on the files I've uploaded this week for the FinOps Data Platform project, generate the markdown report and PowerPoint, and apply the formatting from [path/to/current-status-template.pptx]."
