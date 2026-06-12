---
name: story-document-generator
description: Creates implementation-ready user stories from PRDs and parent epics using the canonical Story Template, including acceptance criteria traceability and rollout validation. Use when you need to break epics into executable stories with clear PRD citations.
---

# Story Document Generator Skill

## Goal
Generate complete user story documents that are traceable to both the parent epic and PRD, and save them in a consistent format for delivery teams.

## Required Inputs
- Story title
- Parent epic path or identifier
- Source PRD path
- Story summary (1-2 sentences)
- Owner
- Priority (P0, P1, P2)
- Sprint or target date range
- Story points
- Primary and secondary personas
- Dependencies
- Acceptance criteria (Given/When/Then)
- Ambiguities and clarification needs (including dependency questions and conflict/tradeoff questions)
- Implementation and QA tasks
- Non-functional and compliance requirements
- Telemetry and reporting requirements
- Risks and mitigations

If critical inputs are missing, ask targeted follow-up questions before finalizing.

## Source Requirements
Use these as mandatory source artifacts:
- Parent epic document(s)
- PRD document

Story content must align with epic scope and PRD requirements. If epic and PRD conflict, prefer the latest dated source and flag the conflict in Risks and Mitigations.

## Template Source
Use this file as the canonical story structure:
- output/project-docs/templates/Delivery/Story Template.md

Do not reorder, remove, or rename template sections.

## Output Location
Save generated stories to:
- output/stories/

Use this filename format unless the user specifies a different name:
- story-{project-slug}-{epic-slug}-{story-slug}-{yyyy-mm-dd}.md

## Workflow
1. Gather source context from parent epic, PRD, and user-provided constraints.
2. Identify the exact epic slice and related PRD sections this story should deliver.
3. Populate YAML frontmatter fields first, including parent_epic and links.
4. Write the User Story sentence in persona-action-benefit format.
5. Build Acceptance Criteria in Gherkin style with PRD citations for each AC.
6. Fill Ambiguities and Clarification Needs, including boundary, dependency, and conflict/tradeoff questions.
7. Fill non-functional, compliance, telemetry, dependency, and risk sections using source evidence.
8. Complete rollout/validation checklist with explicit completion markers.
9. Save the story file to output/stories/ and summarize any TBD items.

## Section Quality Rules
- Summary: 1-2 sentences, outcome-focused.
- User Story: must follow "As a <persona>, I can <action> so that <benefit>".
- Acceptance Criteria: each AC row must include Given, When, Then, and PRD Citation.
- PRD Citation: include section reference and requirement identifier when available.
- Ambiguities and Clarification Needs: include unresolved boundary questions plus dependency and conflict/tradeoff prompts.
- Non-Functional Notes: include performance, security, compliance, accessibility, and data handling constraints.
- Telemetry: specify events, KPI targets, and dashboard/alert ownership.
- Dependencies: split upstream, downstream, and external constraints.
- Risks: each risk must have impact, likelihood, mitigation, and owner.

## Guardrails
- Do not invent facts, owners, dates, requirements, or citations.
- Use [TBD] for unknowns and list them in Risks and Mitigations or Source References.
- Every acceptance criterion must map to the PRD.
- Every story must reference its parent epic in both frontmatter and Source References.
- Keep language concise and implementation-ready.
- Do not add standalone tradeoff sections unless explicitly present in the template.

## Example Invocation
Create a story for NexTitle geolocation fallback handling using the parent epic in output/epics and PRD in output/project-docs, and format it with output/project-docs/templates/Delivery/Story Template.md.
