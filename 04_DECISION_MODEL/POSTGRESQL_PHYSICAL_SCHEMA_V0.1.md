# NEWMODEL — PostgreSQL Physical Schema Specification v0.2

Status: VALIDATED
Reference DBMS: PostgreSQL
Decision: D-017
Scope: Physical relational implementation of the validated MDCRL decision model.

## 1. Reference DBMS Decision
PostgreSQL is the reference implementation DBMS for the first executable physical schema. This is a reference implementation choice, not a product-level lock on PostgreSQL as the only future deployment DBMS.

## 2. Enforcement Model
DATABASE-ENFORCED: Primary keys, foreign keys, unique constraints/indexes, check constraints, partial unique index for current feasibility, and composite foreign key for same-case option selection.

DOMAIN-ENFORCED: Decision with DECISION_BLOCKED integrity cannot be inserted; DECISION is immutable after INSERT; EVIDENCE and ASSUMPTION business content is immutable; post-decision polymorphic reference integrity; domain lifecycle/state transition rules not expressible as row-local checks.

DOMAIN ENGINE: Dependency-aware integrity recalculation, affected-option detection, case integrity recalculation, and current derived integrity interpretation.

## 3. Tables

### FACT_REFERENCE
fact_id UUID PK DEFAULT gen_random_uuid()
business_meaning VARCHAR(255) NOT NULL
domain VARCHAR(100) NOT NULL
external_source_system VARCHAR(100) NULL
UNIQUE (business_meaning, domain)
External/reference object; identity is stable. Delete behavior is RESTRICT when dependent Evidence exists.

### EVIDENCE
evidence_id UUID PK
fact_id UUID NOT NULL FK to FACT_REFERENCE
source_system VARCHAR(100) NOT NULL
source_reference VARCHAR(255) NULL
timestamp TIMESTAMPTZ NOT NULL
value JSONB NOT NULL
integrity_status VARCHAR(30) NOT NULL DEFAULT CURRENT
Integrity check: CURRENT, STALE, INVALID, UNKNOWN, CONFLICT.
Business content is immutable. integrity_status is a materialized derived state, not an independent source of truth.

### ASSUMPTION
assumption_id UUID PK
description TEXT NOT NULL
source VARCHAR(100) NOT NULL
confidence VARCHAR(20) NULL
current_value TEXT NULL
impact_if_false TEXT NULL
integrity_status VARCHAR(30) NOT NULL DEFAULT CURRENT
Integrity check: CURRENT, STALE, INVALID, UNKNOWN, CONFLICT.
Business content is immutable; a changed assumption is a new record/version.

### DECISION_CASE
decision_case_id UUID PK
title VARCHAR(500) NOT NULL
lifecycle_status VARCHAR(30) NOT NULL DEFAULT DECISION_REQUIRED
decision_state VARCHAR(30) NOT NULL DEFAULT DECISION_REQUIRED
integrity_status VARCHAR(30) NOT NULL DEFAULT CURRENT
deadline TIMESTAMPTZ NULL
decision_required_because JSONB NULL; historical snapshot
Lifecycle: DECISION_REQUIRED, DECIDED, OVERDUE, CLOSED.
Decision state: DECISION_REQUIRED, NO_ACCEPTABLE_OPTION, DECIDED, OVERDUE.
Integrity: CURRENT, REVIEW_REQUIRED, DECISION_BLOCKED.
DECIDED lifecycle requires DECIDED decision_state.
NO_ACCEPTABLE_OPTION cannot coexist with DECIDED lifecycle.
A Case is created directly in DECISION_REQUIRED; OPEN is not a domain state.

### OPTION
option_id UUID PK
decision_case_id UUID NOT NULL FK to DECISION_CASE
description TEXT NOT NULL
source VARCHAR(100) NULL
integrity_status VARCHAR(30) NOT NULL DEFAULT CURRENT
UNIQUE (option_id, decision_case_id) to support same-case composite FK.
Integrity: CURRENT, STALE, INVALID, UNKNOWN, CONFLICT.

### FEASIBILITY_RESULT
feasibility_result_id UUID PK
option_id UUID NOT NULL FK to OPTION
result VARCHAR(30) NOT NULL
provider VARCHAR(100) NOT NULL
evaluation_timestamp TIMESTAMPTZ NOT NULL
reference VARCHAR(255) NULL
is_current BOOLEAN NOT NULL DEFAULT FALSE
Result: FEASIBLE, PARTIALLY_FEASIBLE, NOT_FEASIBLE.
Immutable/versioned. Partial unique index ensures at most one current result per option. Replacing current result must be atomic.

### IMPACT
impact_id UUID PK
feasibility_result_id UUID NOT NULL FK to FEASIBILITY_RESULT
impact_family VARCHAR(30) NOT NULL
description_or_value TEXT NULL
availability VARCHAR(20) NOT NULL DEFAULT Available
source VARCHAR(100) NULL
Impact family: Time, Financial, Customer, Risk.
Availability: Available, Not Available.
Immutable and belongs to a specific Feasibility Result version.

### DECISION
decision_id UUID PK
decision_case_id UUID NOT NULL UNIQUE FK to DECISION_CASE
selected_option_id UUID NULL
decision_maker VARCHAR(255) NOT NULL
decision_time TIMESTAMPTZ NOT NULL
rationale TEXT NOT NULL
conditions TEXT NULL
integrity_status_at_decision VARCHAR(30) NOT NULL
integrity_warning_acknowledged BOOLEAN NOT NULL DEFAULT FALSE
Integrity snapshot: CURRENT, REVIEW_REQUIRED, DECISION_BLOCKED.
REVIEW_REQUIRED requires acknowledgement.
DECISION_BLOCKED prohibits INSERT through Domain/Application enforcement or Trigger.
Decision is immutable: no UPDATE/DELETE after INSERT.
Composite FK (selected_option_id, decision_case_id) to OPTION(option_id, decision_case_id).

### POST_DECISION_CHANGE
post_decision_change_id UUID PK
decision_id UUID NOT NULL FK to DECISION
changed_object_type VARCHAR(50) NOT NULL
changed_object_id UUID NOT NULL
detected_at TIMESTAMPTZ NOT NULL
change_type VARCHAR(100) NOT NULL
impact_on_decision_context TEXT NULL
Append-only. changed_object_id is intentionally polymorphic and Domain-owned; no DB FK.

### EVIDENCE_OPTION
evidence_id UUID NOT NULL FK to EVIDENCE
option_id UUID NOT NULL FK to OPTION
Composite PK (evidence_id, option_id).

### ASSUMPTION_OPTION
assumption_id UUID NOT NULL FK to ASSUMPTION
option_id UUID NOT NULL FK to OPTION
Composite PK (assumption_id, option_id).

## 4. Integrity Semantics
Integrity ≠ Feasibility ≠ Impact ≠ Decision State.

Integrity: CURRENT, STALE, INVALID, UNKNOWN, CONFLICT.
Case integrity: CURRENT, REVIEW_REQUIRED, DECISION_BLOCKED.
Feasibility: FEASIBLE, PARTIALLY_FEASIBLE, NOT_FEASIBLE.
Decision state: DECISION_REQUIRED, NO_ACCEPTABLE_OPTION, DECIDED, OVERDUE.

## 5. Immutability and Derived State
EVIDENCE and ASSUMPTION business content is immutable. Their materialized integrity status is derived and may be refreshed by the Domain Engine without changing underlying observation/assumption content.

FEASIBILITY_RESULT and IMPACT are versioned/immutable.
DECISION is immutable and records historical integrity status at decision time.

## 6. D-019 — Feasibility Current Representation
FEASIBILITY_RESULT is fully immutable.

The current result is represented by:
OPTION.current_feasibility_result_id

The current pointer must reference a result belonging to the same Option through the composite relationship:
(current_feasibility_result_id, option_id)
→ FEASIBILITY_RESULT(feasibility_result_id, option_id)

Re-evaluation creates a new immutable FEASIBILITY_RESULT and atomically advances the Option pointer. Concurrent re-evaluation is serialized on the Option row.

The current pointer is materialized derived state; it is not historical truth.

## 7. D-020 — Decision → Historical Feasibility Linkage
DECISION contains:
selected_feasibility_result_id UUID NULL

For a normal Option Decision:
(selected_feasibility_result_id, selected_option_id)
→ FEASIBILITY_RESULT(feasibility_result_id, option_id)

Nullability consistency:
- selected_option_id NULL → selected_feasibility_result_id NULL.
- selected_option_id NOT NULL → selected_feasibility_result_id NOT NULL.

This preserves the exact historical Feasibility Result used at decision time even if the Option's current pointer later changes.

For NO_ACCEPTABLE_OPTION, both fields are NULL.

## 8. Implementation Status
PostgreSQL remains the Reference Implementation DBMS (D-017).

The current technical baseline is sufficient for Product/Business Validation. Further DDL implementation is temporarily frozen except for resolving validated architectural gaps.

DDL v0.1.1 is superseded for implementation purposes by the intended DDL v0.1.2 design.

DDL v0.1.2 is not yet validated.

Required technical walkthrough before implementation validation:
1. Normal re-evaluation.
2. Failed re-evaluation.
3. Concurrent re-evaluation.
4. Pointer integrity.
5. Decision → historical feasibility linkage.
6. Rollback behavior.

The six-test walkthrough must pass before DDL v0.1.2 is marked VALIDATED.

## Implementation Status — Product Validation Gate
D-019 and D-020 are accepted. DDL v0.1.2 is ready for walkthrough but is not validated. Deep technical implementation is paused while product value is validated.
