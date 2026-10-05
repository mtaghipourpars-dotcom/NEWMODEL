# NEWMODEL — Physical Data Model v0.1 Core Draft

Status: APPROVED AS DRAFT
Purpose: Minimal relational core derived from validated logical concepts. No advanced indexing or auxiliary capabilities yet.

## Core Tables
FACT_REFERENCE: fact_id PK; business_meaning; domain; external_source_system.
EVIDENCE: evidence_id PK; fact_id FK; source_system; source_reference; timestamp; value; integrity_status.
ASSUMPTION: assumption_id PK; description; source; confidence; current_value; impact_if_false; integrity_status.
OPTION: option_id PK; decision_case_id FK; description; source; integrity_status.
FEASIBILITY_RESULT: feasibility_result_id PK; option_id FK; result; provider; evaluation_timestamp; reference; is_current.
IMPACT: impact_id PK; feasibility_result_id FK; impact_family; description_or_value; availability; source.
DECISION_CASE: decision_case_id PK; title; lifecycle_status; integrity_status; deadline; decision_required_because.
DECISION: decision_id PK; decision_case_id FK; selected_option_id FK; decision_maker; decision_time; rationale; conditions; integrity_status_at_decision; integrity_warning_acknowledged.
POST_DECISION_CHANGE: post_decision_change_id PK; decision_id FK; changed_object_type; changed_object_id; detected_at; change_type; impact_on_decision_context.

## Graph Relationship Tables
EVIDENCE_OPTION: evidence_id FK; option_id FK.
ASSUMPTION_OPTION: assumption_id FK; option_id FK.

## Constraints
1. Integrity status fields are derived/materialized representations, not independent sources of truth.
2. Feasibility Result is versioned; is_current identifies the current result.
3. Impact belongs to a specific Feasibility Result.
4. Decision preserves historical Integrity state at decision time.
5. Decision is immutable.
6. Snapshot is not yet a separate table; M-204 Physical Walkthrough will validate whether an independent snapshot entity is necessary.
7. The model is intentionally minimal and may be revised after walkthrough findings.
