# NEWMODEL — M-204 SQL Schema Walkthrough v0.1.2

Status: PASSED / VALIDATED
Reference DBMS: PostgreSQL
Scope: Validation of PostgreSQL Physical Schema Specification v0.1.

| # | Test | Result | Enforcement / Evidence |
|---|---|---|---|
| 1 | Case → Decision 0..1 | PASS | UNIQUE(decision_case_id) |
| 2 | Same-Case Composite FK | PASS | Composite FK |
| 3 | NULL selected option for NO_ACCEPTABLE_OPTION | PASS | NULL is valid |
| 4 | Option belonging to another Case | PASS | Composite FK rejects |
| 5 | Current Feasibility uniqueness | PASS | Partial Unique Index |
| 6 | Re-evaluation history | PASS | Immutable versioned results |
| 7 | Impact → specific Feasibility Result | PASS | FK |
| 8 | Decision immutability | PASS | Domain / Trigger enforcement |
| 9 | DECISION_BLOCKED | PASS | Domain-enforced prohibition |
| 10 | REVIEW_REQUIRED | PASS | Acknowledgement required |
| 11 | Decision snapshot | PASS | Immutable historical state |
| 12 | Assumption versioning | PASS | Immutable + new record |
| 13 | Evidence versioning | PASS | Immutable + new record |
| 14 | Integrity status lifecycle | PASS | Materialized derived state |
| 15 | OPEN → DECISION_REQUIRED | PASS | OPEN removed; Case created directly in DECISION_REQUIRED |
| 16 | Post-Decision Change | PASS | Append-only |
| 17 | M-204 complete lifecycle | PASS | No model contradiction |

## Key Decisions Confirmed

### Integrity status on immutable objects
EVIDENCE and ASSUMPTION remain immutable in business content. Their integrity_status is a materialized derived state. It is not a source-of-truth business attribute. The Domain Engine may refresh this derived state without changing the underlying content.

### Lifecycle
OPEN is removed. A Decision Case is created directly as lifecycle_status = DECISION_REQUIRED.

Final lifecycle domain:
- DECISION_REQUIRED
- DECIDED
- OVERDUE
- CLOSED

### Decision enforcement
DECISION_BLOCKED prevents Decision INSERT through Domain/Application enforcement or Trigger.
DECISION is immutable after INSERT.

## Validation Verdict
17/17 tests passed.
No conceptual, relational, or enforcement-model gap remains within the current scope.

Therefore:
PostgreSQL Physical Schema Specification v0.1 — VALIDATED.

Next implementation stage:
PostgreSQL DDL v0.1 — executable CREATE TABLE / Index / Constraint / Trigger design.
