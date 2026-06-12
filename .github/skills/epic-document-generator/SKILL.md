---
name: epic-document-generator
description: Creates structured Epic documents from PRDs, notes, and project context using the canonical Epic Template. Use when you need to draft a new epic, standardize epic quality, or keep epics aligned to delivery outcomes, dependencies, risk, and acceptance criteria.
---

# Epic Document Generator Skill

## Goal
Generate a complete, implementation-ready Epic document using the approved epic template and save it in the project output folder.

## Required Inputs
- Epic title
- Epic summary (2-3 sentences)
- Owner
- Priority
- Phase
- Personas impacted
- Objective and key results
- Business value
- Success metrics
- Regulatory requirements (if any)
- Security considerations
- Dependencies
- Estimated effort
- Monitoring metrics
- Acceptance criteria
- Ambiguities and clarification needs (including dependency questions and conflict/tradeoff questions)
- Out of scope items
- Stakeholders
- Source links (PRD, related epics, related stories)

If any critical input is missing, ask targeted follow-up questions before finalizing.

## Template Source
Use this file as the canonical structure:
- output/project-docs/templates/Delivery/Epic Template.md

Do not reorder or remove template sections.

## Output Location
Save generated epics to:
- output/epics/

Use this filename format unless the user specifies a different name:
- epic-{project-slug}-{epic-slug}-{yyyy-mm-dd}.md

## Workflow
1. Gather source context from user inputs, PRD(s), meeting notes, and other related artifacts.
2. Populate the frontmatter first with concise, decision-useful values.
3. Fill every body section in template order.
4. Convert high-level goals into measurable key results and clear acceptance criteria.
5. Populate Ambiguities and Clarification Needs with ownership/boundary questions and explicit dependency and conflict/tradeoff questions.
6. Ensure dependencies include owner, status, and needed-by date where known.
7. Keep out-of-scope boundaries explicit to control scope creep.
8. Add assumptions, risks, and mitigations in Notes and Links when uncertainty exists.
9. Save the completed epic to output/epics/ and summarize any TBD items.

## Section Quality Rules
- Human-readable Summary: exactly 2-3 sentences, outcome-focused.
- Objective: one clear delivery objective.
- Key Results: 3-5 measurable outcomes with targets when available.
- Business Value: explain impact on cost, speed, quality, risk, or customer outcomes.
- Personas Impacted: describe how each persona is affected.
- Acceptance Criteria: write testable pass/fail checks.
- Ambiguities and Clarification Needs: include unresolved boundaries, prerequisite dependencies, and conflict/tradeoff decisions.
- Validation/QA Plan: specify test scope, test types, evidence, and exit criteria.
- Monitoring and Metrics: include operational, quality, reliability, and compliance metrics.
- Dependencies: include owner, status, and needed-by date, or mark as TBD.

## Guardrails
- Do not invent facts, dates, owners, or metrics.
- If details are unknown, mark as [TBD] and list in Notes and Links assumptions/risks.
- Keep wording concise and execution-oriented.
- Preserve template structure and section order.
- Ensure every major risk has a mitigation path.
- Ensure acceptance criteria and key results are aligned with the objective.
- Do not add standalone interdependency/conflict/tradeoff sections unless explicitly present in the template.

## Example Invocation
Create an epic for NexTitle geolocation generalization using output/project-docs/templates/Delivery/Epic Template.md and save it to output/epics/.
