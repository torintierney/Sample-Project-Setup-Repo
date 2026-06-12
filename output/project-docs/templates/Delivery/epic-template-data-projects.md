# Epic Template - Data Projects

## Epic Name
- [Enter epic name]

## Epic Objective
- [One sentence describing the data outcome this epic should achieve]

## User Story
As a [data user role],
I want [data capability],
So that [business value and decision impact].

## Business Value
- [Why this data epic matters now]
- [Expected impact on decision quality, operational efficiency, or risk]

## Data Domain and Scope Boundary
- Data domain: [Example: Customer, Product, Finance, Operations]
- Included systems/domains: [List]
- Excluded systems/domains: [List]

## Data Sources and Producers
- Source 1: [System/table/file/API], owner: [Team], refresh: [Cadence]
- Source 2: [System/table/file/API], owner: [Team], refresh: [Cadence]
- Source 3: [System/table/file/API], owner: [Team], refresh: [Cadence]

## Data Consumers and Use Cases
- Consumer 1: [Team/persona], use case: [Decision/workflow]
- Consumer 2: [Team/persona], use case: [Decision/workflow]
- Consumer 3: [Team/persona], use case: [Decision/workflow]

## Data Definitions and Critical Fields
- Business definition(s): [Canonical definitions for key terms]
- Critical fields and grain: [List field names and grain]
- Source of truth: [Authoritative dataset/table]

## Data Quality Requirements
- Completeness: [Target threshold and rule]
- Accuracy: [Target threshold and rule]
- Timeliness: [Target threshold and rule]
- Uniqueness: [Target threshold and rule]
- Validity: [Target threshold and rule]

## Governance, Privacy, and Security
- Data classification: [Public/Internal/Confidential/Restricted]
- Privacy requirements: [PII handling, masking, retention]
- Access model: [Role-based access expectations]
- Compliance constraints: [Policy/regulatory requirements]

## Dependencies
- [Dependency on source system team]
- [Dependency on platform/infrastructure]
- [Dependency on governance/security review]

## Requirement Interdependencies and Conflicts
- [Dependency: This data epic depends on [source system] completing their API contract first]
- [Conflict: High data freshness (hourly) conflicts with cost; low-cost option is daily refresh]
- [Conflict: Masking sensitive fields may reduce analytics value; balancing privacy vs insight]

## Child Story Breakdown
- [Story 1 title]
- [Story 2 title]
- [Story 3 title]

## Acceptance Criteria
### Success Metrics
- [Metric 1 with target, example: Data freshness under 4 hours for 95% of loads]
- [Metric 2 with target, example: Completeness above 99% for critical fields]
- [Metric 3 with target, example: Reduce manual reconciliation time by 40%]

### Given/When/Then Criteria
1. Given [approved source systems and schema], when [pipeline runs], then [target dataset is populated with required fields and grain].
2. Given [data quality rules], when [validation executes], then [records outside thresholds are flagged and routed for remediation].
3. Given [authorized consumer role], when [consumer accesses dataset], then [only permitted data is visible according to policy].

## Ambiguities and Clarification Needs
- [Ambiguity 1: Is source system API stable? What is the SLA for upstream data availability?]
- [Ambiguity 2: Which fields are truly critical vs optional? Who decides schema changes?]
- [Ambiguity 3: What is acceptable data latency for different consumer use cases?]
- [Dependency question: Which source contracts, platform capabilities, or governance approvals are prerequisites?]
- [Conflict/tradeoff question: What privacy, freshness, quality, and cost tradeoffs need decisions?]

## Out of Scope
- [Excluded data source or domain]
- [Excluded advanced analytics/modeling work]

## Definition of Done
- [All committed child stories are completed and accepted]
- [Data quality checks are automated and passing within agreed thresholds]
- [Data catalog and lineage documentation are updated]
- [Access controls and governance approvals are complete]
- [Stakeholder sign-off is recorded]
