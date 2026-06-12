---
name: prd-document-generator
description: Creates simple Product Requirements Documents (PRDs) from project context, notes, and requirements using a consistent template. Use when you need to draft a new PRD, standardize PRD structure, or quickly convert discovery artifacts into a PRD with objective, context/problem statement, users, scope, phasing, non-functional requirements, and SLAs.
---

# PRD Document Generator Skill

## Goal
Generate a concise, structured PRD in a simple format and save it to the project docs output folder.

## Required Inputs
- Project title
- Objective / goal
- Context and problem statement
- Key users
- In scope requirements
- Out of scope requirements
- Phasing details for Now, Next, Later
- Non-functional requirements
- SLA requirements
- Ambiguities and clarification needs (including dependency questions and conflict/tradeoff questions)
- Open questions, assumptions, and risks

If any input is missing, ask targeted follow-up questions before finalizing.

## Template Source
Use this file as the canonical structure:
- output/project-docs/templates/Discovery/prd-template-simple.md

## Output Location
Save generated PRDs to:
- output/project-docs/

Use this filename format unless the user specifies a different name:
- prd-[project-slug]-[yyyy-mm-dd].md

## Workflow
1. Gather source context from user-provided notes, requirements, and relevant workspace files.
2. Populate each section in the template with concrete, testable statements.
3. Keep the PRD concise and plain language; avoid unnecessary filler.
4. Preserve required section order from the template.
5. Populate Ambiguities and Clarification Needs using requirement-level questions, including dependency and conflict/tradeoff prompts.
6. Add Open Questions, Assumptions, and Risks when uncertainty exists.
7. Write the final PRD markdown file to output/project-docs/.
8. Confirm file path and summarize any missing data or assumptions.

## Section Quality Rules
- Objective / Goal: one to three bullets with measurable outcomes when possible.
- Context and Problem Statement: separate context from explicit problem statements.
- Key Users: list primary and secondary users clearly.
- In Scope Requirements: use clear action language and concrete behavior.
- Ambiguities and Clarification Needs: include ownership, scope boundary, dependency, and conflict/tradeoff questions directly in this section.
- Out of Scope Requirements: explicitly exclude items to prevent scope creep.
- Phasing: assign items to Now, Next, Later based on delivery priority.
- Non-Functional Requirements: include performance, reliability, security, accessibility, and compliance where relevant.
- SLA Requirements: include availability, response, resolution, and support window when known.
- Open Questions: include unresolved dependency risks and architecture/timeline/budget conflicts.

## Guardrails
- Do not invent facts.
- If details are unknown, mark them as [TBD] and list them in Open Questions.
- Keep the format simple and consistent with the template.
- Do not reorder or remove required sections.
- Do not introduce standalone sections for interdependencies/conflicts/tradeoffs unless explicitly present in the template.

## Example Invocation
Create a PRD for [project name] using the PRD template and save it under output/project-docs/ with today's date.
