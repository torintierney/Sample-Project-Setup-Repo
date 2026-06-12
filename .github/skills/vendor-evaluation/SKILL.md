---
name: vendor-evaluation
description: Evaluates vendors or tools using weighted criteria, evidence scoring, and tradeoff analysis to produce a recommendation memo with clear rationale and decision risk.
---

# Vendor Evaluation Skill

## Goal
Provide an objective, evidence-based vendor/tool recommendation with transparent scoring and clear tradeoffs.

## Inputs
- Candidate vendor/tool list.
- Evaluation criteria and optional weights.
- Supporting artifacts (RFP responses, demos, pricing docs, security/compliance answers, references).
- Optional context:
  - Budget guardrails
  - Timeline constraints
  - Mandatory requirements
  - Procurement policy

## Output
Create or update:
- vendor-evaluation-{topic-or-date}.md

Use this structure:

```markdown
# Vendor Evaluation: [Topic]
**Date:** [date]
**Decision Window:** [date range]

## Executive Recommendation
- Recommended Option: [Vendor/Tool]
- Confidence: High | Medium | Low
- Why: [3 concise reasons]
- Key Risk: [top risk to monitor]

## Evaluation Criteria
| Criterion | Weight (%) | Must-Have? |
| --- | --- | --- |

## Scoring Matrix
| Vendor | Criterion 1 | Criterion 2 | Criterion 3 | Weighted Score | Rank |
| --- | --- | --- | --- | --- | --- |

## Cost and Commercial Summary
| Vendor | One-Time Cost | Recurring Cost | Contract Risks | Notes |
| --- | --- | --- | --- | --- |

## Risk and Constraint Analysis
| Vendor | Top Risks | Mitigation | Residual Risk |
| --- | --- | --- | --- |

## Tradeoff Analysis
- [Vendor A vs Vendor B key tradeoffs]

## Decision Conditions
- Conditions required before final sign-off.

## Next Steps
- Procurement/technical/legal actions with owners and dates.
```

## Workflow
1. Define criteria and thresholds
- Confirm must-haves vs preferences.
- Normalize weights to total 100%.

2. Gather evidence
- Extract comparable evidence across all vendors.
- Flag missing evidence explicitly as `TBD`.

3. Score each criterion
- Use a consistent scale (1-5 or 1-10).
- Separate score from confidence in evidence quality.

4. Calculate weighted results
- Compute weighted total for each vendor.
- Rank vendors and identify close-score scenarios.

5. Analyze tradeoffs and risk
- Explain why highest score may not always be best option (risk, lock-in, timeline).
- Identify decision conditions and mitigation actions.

6. Publish recommendation memo
- Provide recommendation, confidence, risks, and next actions.

## Scoring Rules
- Use only evidence-backed scoring.
- If evidence is missing, assign provisional score and mark `Low Confidence`.
- For must-have failures, mark vendor as `Conditionally Disqualified` unless exception is explicitly approved.

## Guardrails
- Do not invent pricing, legal terms, certifications, or security claims.
- Avoid biased language; keep assessment neutral and auditable.
- Highlight assumptions that materially affect ranking.
- Make uncertainty visible rather than hidden.

## Example Invocation
Use the vendor-evaluation skill to compare Vendor A, Vendor B, and Vendor C using our weighted criteria and generate a recommendation memo for steering committee review.
