---
title: <data-story-title>
parent_epic: <epic-id-or-filename>
summary: <1-2 sentence outcome-focused summary>
owner: <team-or-individual>
priority: <P0|P1|P2>
sprint: <sprint-name-or-date-range>
story_points: <1|2|3|5|8>
data_domain: <customer|product|finance|operations|other>
data_classification: <public|internal|confidential|restricted>
source_systems:
  - <system/table/file/api>
source_owners:
  - <team-or-owner>
target_datasets:
  - <warehouse.schema.table_or_data_product>
consumers:
  - <persona/team/use-case>
dependencies:
  - <dependency-1>
  - <dependency-2>
transformations:
  - <short label, example: source_to_target_mapping>
  - <short label, example: deduplication_rules>
  - <short label, example: incremental_cdc_logic>
acceptance_criteria:
  - <short AC summary 1>
  - <short AC summary 2>
quality_thresholds:
  completeness: <target>
  accuracy: <target>
  timeliness: <target>
  uniqueness: <target>
privacy_and_security:
  pii_present: <yes|no>
  masking_required: <yes|no>
  access_policy: <rbac-policy-name>
links:
  - <related-epic-link-or-path>
  - <prd-link-or-path>
  - <data-contract-or-schema-link>
---

## Data User Story
As a <data consumer persona>, I need <data capability> so that <business decision or workflow outcome>.

## Scope
### In Scope
- <included transformation, metric, or data product update>
- <included source/target boundary>

### Out of Scope
- <explicit non-goal 1>
- <explicit non-goal 2>

## Data Contract and Schema Expectations
- Grain: <row-level grain definition>
- Required fields: <field-1>, <field-2>, <field-3>
- Data types and constraints: <required validations>
- Null handling/default rules: <rules>

## Transformations
- Source-to-target mapping: <source field -> target field>
- Business rules: <derivations, standardization, enrichment logic>
- Joins and keys: <join strategy and key assumptions>
- Aggregations/window logic: <grouping, rollups, window functions>
- Deduplication strategy: <survivorship or tie-break rules>
- Incremental logic: <CDC/watermark/upsert behavior>

## Acceptance Criteria (Given/When/Then)
1. Given <approved source data and schema>, when <pipeline/model runs>, then <target dataset is produced with expected grain and required fields>.
2. Given <quality rules>, when <validation checks execute>, then <thresholds are met or failures are quarantined and alerted>.
3. Given <authorized consumer role>, when <consumer queries/accesses data>, then <policy-compliant fields and rows are available within SLA>.

## Ambiguities and Clarification Needs
- <Ambiguity 1: Is source system API stable? Who owns upstream data quality?>
- <Ambiguity 2: Which fields are truly required vs optional? Who decides schema?>
- <Ambiguity 3: What is acceptable data latency for different consumer use cases?>
- <Dependency question: Which upstream source contracts, pipeline jobs, or access approvals are prerequisites?>
- <Conflict/tradeoff question: What freshness, quality, privacy, and cost tradeoffs must be decided?>

## Data Quality Validation
- Completeness rule(s): <rule + threshold>
- Accuracy rule(s): <rule + threshold>
- Timeliness SLA: <latency/freshness target>
- Reconciliation method: <source vs target comparison approach>

## Privacy, Security, and Compliance
- PII/PHI fields: <list or none>
- Masking/tokenization requirements: <rules>
- Access control checks: <roles and least-privilege expectations>
- Audit requirements: <logging/tracing requirements>

## Observability and Alerting
- Pipeline signals: <job success/failure, run duration, throughput>
- Data signals: <freshness, null rates, distribution drift>
- Alerts and owners: <alert condition -> owner/escalation path>

## Test Plan
- Unit tests: <transformation/business-rule tests>
- Integration tests: <source-to-target contract tests>
- Backfill/replay test: <historical data validation strategy>
- UAT validation: <consumer sign-off criteria>

## Rollout and Backout
- Rollout plan: <phased, canary, or full release>
- Backout plan: <rollback/revert strategy>
- Communication plan: <stakeholder notifications>

## Definition of Done
- [ ] Acceptance criteria verified with evidence.
- [ ] Quality thresholds met and monitored.
- [ ] Data catalog/documentation updated.
- [ ] Access controls and compliance checks completed.
- [ ] Consumer validation/sign-off captured.
