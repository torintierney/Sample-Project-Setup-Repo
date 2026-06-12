---
name: postmortem
description: Produces blameless postmortems for incidents and delivery failures, including timeline reconstruction, root cause analysis, impact assessment, and corrective actions.
---

# Postmortem Skill

## Goal
Create a blameless, action-oriented postmortem that improves system and process reliability after incidents or failures.

## Inputs
- Incident artifacts (alerts, logs, timeline notes, tickets, chat transcripts, deployment history, customer reports).
- Optional context:
  - Incident severity model
  - SLO/SLA targets
  - Team escalation policy
  - Prior similar incidents

## Output
Create or update:
- postmortem-{incident-name-or-date}.md

Use this structure:

```markdown
# Postmortem: [Incident Name]
**Date:** [date]
**Severity:** [Sev]
**Status:** Draft | Final

## Executive Summary
- What happened:
- Customer/business impact:
- Duration:
- Current risk level:

## Timeline (UTC)
| Time | Event | Source |
| --- | --- | --- |

## Impact Assessment
- Affected users/systems:
- Functional impact:
- Financial/operational impact:
- Detection-to-resolution timings:

## Root Cause Analysis
### Primary Root Cause
- ...

### Contributing Factors
- ...

### What Worked
- ...

### What Didn’t Work
- ...

## Corrective and Preventive Actions (CAPA)
| ID | Action | Type (Corrective/Preventive) | Owner | Priority (Critical/High/Medium/Low) | Due Date | Status |
| --- | --- | --- | --- | --- | --- | --- |

## Follow-Up Validation
- Success metrics to confirm fixes:
- Validation window:
- Rollback/contingency if fixes fail:

## Lessons Learned
- ...
```

## Workflow
1. Build factual timeline
- Reconstruct events from first signal to full recovery.
- Include source evidence for each major event.

2. Quantify impact
- Measure user, system, and business impact.
- Capture detection, triage, mitigation, and recovery durations.

3. Perform root cause analysis
- Identify primary root cause and contributing factors.
- Use structured reasoning (5 Whys/fault chain) where possible.

4. Define actions
- Add corrective actions for immediate gaps.
- Add preventive actions to reduce recurrence risk.
- Assign owners, priority, and due dates.

5. Publish and track
- Mark postmortem status and required review audience.
- Track completion of CAPA actions.

## Analysis Rules
- Blameless language: focus on system/process conditions, not individual fault.
- Distinguish facts from hypotheses.
- Treat unknowns explicitly as `TBD` with follow-up owner.

## Guardrails
- Do not invent timeline events, causes, or impacts.
- Do not close postmortem without named owners for high/critical actions.
- Keep recommendations concrete and measurable.
- Ensure at least one preventive action for recurrence reduction.

## Example Invocation
Use the postmortem skill on incident-2026-06-04 artifacts and generate a final postmortem with CAPA actions and owners.
