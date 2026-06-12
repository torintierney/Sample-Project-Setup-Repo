---
name: roadmap-generator
description: Creates structured Roadmap documents from PRDs, epics, stories, and team composition using the canonical Roadmap Template. Analyzes dependencies for sequencing, estimates team capacity, and produces phase-based delivery roadmaps with critical path identification.
---

# Roadmap Generator Skill

## Goal
Generate a complete, delivery-ready Roadmap document that sequences phases based on epic/story dependencies, team capacity, and business priorities. Produces a resource-aware timeline with critical path analysis.

## Required Inputs
- PRD document (for business objectives and phasing intent)
- Epic list (with priority, estimated effort, dependencies, and phase assignment)
- Story list (with story points, dependencies, parent epic, and phase assignment)
- Team composition:
  - Total team members (count)
  - Role breakdown (if available: engineers, QA, product, design, etc.)
  - Allocation % for this project
  - Sprint velocity (story points per sprint, or calculate from historical data)
- Timeline constraints (target launch dates, regulatory deadlines, or dependencies on external teams)

If critical inputs are missing, ask targeted follow-up questions before finalizing.

## Template Source
Use this file as the canonical structure:
- output/project-docs/templates/Discovery/roadmap-template.md

Do not reorder or remove template sections.

## Output Location
Save generated roadmaps to:
- output/project-docs/

Use this filename format unless the user specifies a different name:
- roadmap-{project-slug}-{yyyy-mm-dd}.md

## Workflow

### Step 1: Extract Phase and Dependency Data
1. Parse the PRD for phasing strategy (Phase 1/Now, Phase 2/Next, Phase 3/Later) and business rationale.
2. Parse epics for:
   - Assigned phase (Phase 1, 2, 3, etc.)
   - Priority (Must-Have, Should-Have, Could-Have)
   - Estimated effort (story points or person-days)
   - Dependencies (upstream epics, systems, approvals)
   - Out-of-scope items
3. Parse stories for:
   - Parent epic
   - Story points
   - Dependencies (upstream stories, external systems)
   - Phase assignment
4. Identify team members and capacity:
   - Calculate available capacity per sprint: (team members × allocation %) × sprint velocity
   - Note any resource constraints, shared resources, or capacity variations by phase

### Step 2: Build Dependency Graph
1. Create a dependency map for all epics and stories (e.g., "Phase 2 EPIC-A depends on Phase 1 EPIC-B completing").
2. Identify critical path (longest chain of dependent items).
3. Find parallel work opportunities (items that can run simultaneously without blocking each other).
4. Flag external dependencies (vendor, regulatory, third-party teams) with owner and required-by date.

### Step 3: Sequence Phases
1. Assign epics/stories to phases based on:
   - Business priorities from PRD
   - Dependency chain constraints
   - Team capacity (ensure phase effort ≤ available capacity)
   - Must-Have items first, then Should-Have, then Could-Have
2. Identify critical path items that must complete on time to unblock downstream phases.
3. Estimate phase duration:
   - Calculate total effort per phase (sum story points)
   - Divide by available capacity per sprint
   - Round up to nearest sprint and apply buffer for unknowns (~20%)
4. Assign target dates based on capacity plan.

### Step 4: Populate Roadmap Sections
1. **Phasing Strategy and Rationale**: Explain why each phase exists and what business outcome it delivers.
2. **Phase Details**: For each phase, populate:
   - Objective and business value
   - Requirements/epics in scope with effort estimates
   - Success metrics
   - Critical path items
   - Resource allocation and capacity plan
   - Known risks and mitigations
3. **Cross-Phase Dependencies**: Document which items in Phase N depend on Phase N-1.
4. **Resource and Budget Summary**: Show effort allocation, team capacity vs. planned effort, confidence level.
5. **Timeline and Go-Live Milestones**: Calculate milestone dates based on phase effort and team capacity.
6. **Risks and Contingency**: Flag high-risk items, external dependencies, and fallback scenarios.
7. **Stakeholder Sign-Off**: Prepare for review by sponsor, product owner, and engineering lead.

### Step 5: Quality Validation
1. Verify every epic/story is assigned to exactly one phase.
2. Verify no phase exceeds available team capacity.
3. Verify all dependencies are documented and own-ers/target dates assigned.
4. Verify phase sequencing respects critical path constraints.
5. Verify timeline is realistic given team capacity and complexity.

### Step 6: Save and Confirm
1. Save the completed roadmap to output/project-docs/.
2. Summarize:
   - Number of phases and target go-live dates
   - Total effort by phase vs. team capacity
   - High-risk items and dependencies
   - Any TBD items requiring follow-up

## Section Quality Rules
- **Phasing Strategy**: One clear rationale per phase (why now, not later).
- **Phase Objectives**: One objective statement per phase tied to business outcome.
- **Requirements in Scope**: Each epic/story must show effort (story points or FTE-days), priority, and owner.
- **Critical Path Items**: List prerequisites and target completion dates.
- **Resource Allocation**: Show FTE, allocation %, and velocity assumptions; reconcile planned effort vs. available capacity.
- **Timeline**: Show all milestones with realistic dates based on phase effort ÷ team capacity.
- **Risks**: Every high-risk item must have mitigation and owner.
- **Dependencies**: Every phase-to-phase dependency must show owner, status, and target date.

## Guardrails
- Do not invent facts, dates, team members, or effort estimates; use provided data from PRDs, epics, and stories.
- If effort or team capacity data is missing, mark as [TBD] and list in Risks.
- If dependencies are circular or impossible to resolve, flag explicitly with recommended scope trim.
- Use realistic buffer (15-20%) for unknowns; do not assume best-case scenarios.
- If phase effort exceeds available capacity, recommend scope reduction or timeline extension (not speed-up).
- Preserve template structure and section order.
- Keep language concise and decision-focused.

## Example Invocation
Create a roadmap for the NexTitle project using output/project-docs/PRD-nextitle.md, output/epics/*.md, output/stories/*.md, and a team of 6 engineers (4 FTE allocated) with sprint velocity of 40 points. Identify critical path and produce roadmap-nextitle-2026-06-11.md in output/project-docs/.
