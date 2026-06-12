# Cost and ROI Model

## Purpose
Estimate the cost, total cost of ownership (TCO), and return on investment (ROI) for a software or automation project. Use this as a planning tool during discovery — update all inputs with actual data before using in stakeholder review or budget decisions.

> **Note:** This model is structured as a spreadsheet workbook. Each section below maps to a recommended worksheet tab.

---

## Modeling Scope

Document what the model covers before filling in numbers.

- **Solution type:** [e.g., cloud-hosted application, SaaS platform, custom-built automation]
- **Infrastructure platform:** [e.g., AWS, Azure, GCP, on-prem]
- **Core services assumed:** [e.g., managed compute, managed database, document processing APIs, storage]
- **Application stack:** [e.g., frontend framework, backend language, worker/job layer]
- **Downstream integrations included in scope:** [e.g., CRM, ERP, export targets, third-party APIs]
- **Excluded from this model:** [List anything that affects cost but is not modeled here]

---

## Recommended Workbook Tabs

| Tab Name | Purpose |
|---|---|
| `Inputs_Assumptions` | All editable inputs in one place — single source of truth for the model |
| `Volume_Scenarios` | Low / medium / high volume assumptions |
| `Infrastructure_Model` | Monthly cloud or platform infrastructure cost by scenario |
| `Implementation_Model` | One-time delivery and setup costs |
| `Ongoing_Operations` | Recurring operational costs beyond infrastructure |
| `ROI_Model` | Savings vs. cost comparison and break-even analysis |
| `Sensitivity_Analysis` | Stress-test key variables |
| `Summary` | Executive-facing output for stakeholder review |

---

## Tab 1: Inputs_Assumptions

Populate with editable inputs only. All other tabs should reference these cells.

| Input | Symbol | Example Value | Notes |
|---|---|---:|---|
| Units processed per month | `UnitsPerMonth` | [number] | [e.g., documents, transactions, requests] |
| Average sub-units per unit | `SubUnitsPerUnit` | [number] | [e.g., pages per document, line items per order] |
| Total sub-units per month | `SubUnitsPerMonth` | `=UnitsPerMonth*SubUnitsPerUnit` | Derived |
| Processing rate (low tier) | `ProcessingRateLow` | [$/unit] | [Low-cost or simpler processing path] |
| Processing rate (high tier) | `ProcessingRateHigh` | [$/unit] | [Richer or more expensive processing path] |
| Percent using high tier | `HighTierMix` | [%] | [Estimated split between tiers] |
| Percent using low tier | `LowTierMix` | `=1-HighTierMix` | Derived |
| Average source file or payload size | `AvgSizeMB` | [MB] | [Used for storage sizing] |
| Retention period in months | `RetentionMonths` | [number] | [How long data is kept] |
| Database compute monthly cost | `DBComputeMonthly` | [$] | [Selected instance or tier cost] |
| Database storage in GB | `DBStorageGB` | [GB] | [Provisioned or estimated] |
| Database storage rate per GB-month | `DBStorageRate` | [$/GB] | [Replace with actual rate] |
| App compute monthly cost | `AppComputeMonthly` | [$] | [Web/API tier cost] |
| Worker or job compute monthly cost | `WorkerComputeMonthly` | [$] | [Background processing cost] |
| Object/blob storage rate per GB-month | `StorageRate` | [$/GB] | [Replace with actual rate] |
| Egress data per month in GB | `EgressGB` | [GB] | [Outbound traffic estimate] |
| Egress rate per GB | `EgressRate` | [$/GB] | [Replace with actual rate] |
| Network / shared infrastructure monthly | `NetworkFixedMonthly` | [$] | [Load balancers, VPN, DNS, etc.] |
| Monitoring and logging monthly cost | `ObservabilityMonthly` | [$] | [Alerting, log retention, dashboards] |
| Manual baseline cost per unit | `ManualCostPerUnit` | [$/unit] | [Current-state cost being replaced or reduced] |
| Straight-through / automation rate | `AutomationRate` | [%] | [Expected trusted automation with no human touch] |
| Accepted output rate | `AcceptanceRate` | [%] | [First-pass downstream acceptance rate] |
| Staff oversight monthly cost | `OversightMonthly` | [$] | [Reviewer, admin, triage labor] |
| Support and maintenance monthly cost | `SupportMonthly` | [$] | [Internal or vendor support] |
| Content, rules, or config update monthly cost | `ContentOpsMonthly` | [$] | [Ongoing tuning, mapping, rule updates] |
| Model or algorithm tuning monthly cost | `ModelOpsMonthly` | [$] | [Evaluation, retraining, adapter updates] |
| One-time: architecture and design | `ImplArchitecture` | [$] | |
| One-time: application development | `ImplAppDev` | [$] | |
| One-time: core integration / workflow | `ImplCore` | [$] | |
| One-time: external system integrations | `ImplIntegrations` | [$] | |
| One-time: testing and QA | `ImplQA` | [$] | |
| One-time: training and change management | `ImplTraining` | [$] | |

---

## Tab 2: Volume_Scenarios

| Scenario | Units per Month | Sub-units per Unit | Sub-units per Month |
|---|---:|---:|---:|
| Low | [number] | [number] | `=B2*C2` |
| Medium | [number] | [number] | `=B3*C3` |
| High | [number] | [number] | `=B4*C4` |

---

## Tab 3: Infrastructure_Model

### Processing Consumption

| Metric | Formula |
|---|---|
| Low-tier sub-units | `=SubUnitsPerMonth*LowTierMix` |
| High-tier sub-units | `=SubUnitsPerMonth*HighTierMix` |
| Low-tier processing cost | `=LowTierSubUnits*ProcessingRateLow` |
| High-tier processing cost | `=HighTierSubUnits*ProcessingRateHigh` |
| Total processing monthly cost | `=LowTierProcessingCost+HighTierProcessingCost` |

### Database Cost

| Metric | Formula |
|---|---|
| DB storage cost | `=DBStorageGB*DBStorageRate` |
| Total DB monthly cost | `=DBComputeMonthly+DBStorageCost` |

### Storage and Networking

| Metric | Formula |
|---|---|
| Object storage GB (steady state) | `=UnitsPerMonth*AvgSizeMB*RetentionMonths/1024` |
| Storage cost | `=StorageGB*StorageRate` |
| Egress cost | `=EgressGB*EgressRate` |
| Total network and storage cost | `=StorageCost+EgressCost+NetworkFixedMonthly+ObservabilityMonthly` |

### Application Compute

| Metric | Formula |
|---|---|
| Total app compute monthly cost | `=AppComputeMonthly+WorkerComputeMonthly` |

### Total Infrastructure

| Metric | Formula |
|---|---|
| Monthly infrastructure total | `=TotalProcessingCost+TotalDBCost+TotalNetworkAndStorageCost+TotalAppComputeCost` |
| Infrastructure cost per processed unit | `=MonthlyInfrastructureTotal/UnitsPerMonth` |
| Infrastructure cost per accepted unit | `=MonthlyInfrastructureTotal/(UnitsPerMonth*AcceptanceRate)` |

---

## Tab 4: Implementation_Model

| Cost Area | Formula |
|---|---|
| Architecture and design | `=ImplArchitecture` |
| Application development | `=ImplAppDev` |
| Core integration / workflow | `=ImplCore` |
| External integrations | `=ImplIntegrations` |
| Testing and QA | `=ImplQA` |
| Training and change management | `=ImplTraining` |
| **Total implementation cost** | `=SUM(B2:B7)` |

**Typical planning ranges (adjust for your context):**

| Deployment Shape | Typical Range |
|---|---:|
| Lean pilot | $100,000 – $250,000 |
| Production MVP | $250,000 – $600,000 |
| Enterprise rollout | $600,000 – $1,200,000+ |

---

## Tab 5: Ongoing_Operations

| Cost Area | Formula |
|---|---|
| Support and maintenance | `=SupportMonthly` |
| Content, rules, or config updates | `=ContentOpsMonthly` |
| Model or algorithm tuning | `=ModelOpsMonthly` |
| Staff oversight | `=OversightMonthly` |
| Total monthly operational overhead | `=SUM(B2:B5)` |
| Total monthly run cost | `=MonthlyInfrastructureTotal+TotalMonthlyOperationalOverhead` |
| Annual recurring run cost | `=TotalMonthlyRunCost*12` |

---

## Tab 6: ROI_Model

| Metric | Formula |
|---|---|
| Monthly manual baseline cost | `=UnitsPerMonth*ManualCostPerUnit` |
| Automated blended cost per accepted unit | `=TotalMonthlyRunCost/(UnitsPerMonth*AcceptanceRate)` |
| Monthly automated total cost | `=TotalMonthlyRunCost` |
| Monthly gross savings | `=MonthlyManualBaselineCost-MonthlyAutomatedTotalCost` |
| Net annual savings | `=MonthlyGrossSavings*12` |
| Break-even months | `=IF(MonthlyGrossSavings>0,TotalImplementationCost/MonthlyGrossSavings,"No payback")` |
| Year 1 total cost | `=TotalImplementationCost+AnnualRecurringRunCost` |
| Year 2 total cost | `=AnnualRecurringRunCost` |
| Year 3 total cost | `=AnnualRecurringRunCost` |
| Three-year TCO | `=Year1TotalCost+Year2TotalCost+Year3TotalCost` |
| Three-year manual baseline cost | `=MonthlyManualBaselineCost*36` |
| Three-year net savings | `=ThreeYearManualBaselineCost-ThreeYearTCO` |
| Three-year ROI | `=IF(ThreeYearTCO>0,ThreeYearNetSavings/ThreeYearTCO,0)` |

---

## Tab 7: Sensitivity_Analysis

Stress-test the variables that most affect TCO and payback.

| Variable | Low Case | Base Case | High Case |
|---|---:|---:|---:|
| Sub-units per unit | [low] | [base] | [high] |
| High-tier processing mix | [%] | [%] | [%] |
| Automation / straight-through rate | [%] | [%] | [%] |
| Acceptance rate | [%] | [%] | [%] |
| Manual baseline cost per unit | [$] | [$] | [$] |
| Integration scope multiplier | 0.8 | 1.0 | 1.5 |
| Staff oversight monthly cost | [$] | [$] | [$] |

| Metric | Formula |
|---|---|
| Adjusted implementation cost | `=TotalImplementationCost*IntegrationScopeMultiplier` |
| Adjusted monthly run cost | `=BaseMonthlyRunCost+AdditionalOversightDelta` |
| Sensitivity break-even months | `=IF(AdjustedMonthlySavings>0,AdjustedImplementationCost/AdjustedMonthlySavings,"No payback")` |

---

## Tab 8: Summary

Executive-facing output for stakeholder review.

| Output | Formula |
|---|---|
| Selected scenario | Manual input |
| Monthly units processed | `=UnitsPerMonth` |
| Monthly sub-units | `=SubUnitsPerMonth` |
| Monthly infrastructure cost | `=MonthlyInfrastructureTotal` |
| Monthly operating cost | `=TotalMonthlyOperationalOverhead` |
| Monthly total run cost | `=TotalMonthlyRunCost` |
| One-time implementation cost | `=TotalImplementationCost` |
| Year 1 total cost | `=Year1TotalCost` |
| Three-year TCO | `=ThreeYearTCO` |
| Break-even months | `=BreakEvenMonths` |
| Three-year ROI | `=ThreeYearROI` |
| Cost per accepted unit | `=AutomatedBlendedCostPerAcceptedUnit` |

---

## Key Assumptions and Caveats

Document the assumptions baked into this model before sharing with stakeholders.

| Assumption | Value or Basis | Confidence | Notes |
|---|---|---|---|
| [e.g., Average sub-units per unit] | [value] | High / Medium / Low | [Source or rationale] |
| [e.g., Manual baseline cost per unit] | [value] | High / Medium / Low | [Source or rationale] |
| [e.g., Automation rate at launch] | [value] | High / Medium / Low | [Source or rationale] |
