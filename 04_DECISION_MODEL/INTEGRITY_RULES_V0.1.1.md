# NEWMODEL — Integrity Calculation Rules v0.1.1

Status: VALIDATED

## Four Independent Concepts
Integrity ≠ Feasibility ≠ Impact ≠ Decision State

| Concept | Core Question | Status / Result |
|---|---|---|
| Integrity | Is the decision basis reliable? | CURRENT / REVIEW_REQUIRED / DECISION_BLOCKED |
| Feasibility | Can the Option be executed? | FEASIBLE / PARTIALLY / NOT_FEASIBLE |
| Impact | What are expected consequences? | Time / Financial / Customer / Risk / NOT_AVAILABLE |
| Decision State | What is the state of the decision process? | DECISION_REQUIRED / NO_ACCEPTABLE_OPTION / DECIDED / OVERDUE / ... |

These concepts must never be collapsed into one status.

## Option Integrity
CURRENT when all relevant Evidence and Assumptions are current and no unresolved Conflict exists.
STALE when at least one relevant dependency changed but remains valid.
INVALID when at least one relevant dependency is explicitly invalid.
UNKNOWN when freshness or validity cannot be confirmed.
CONFLICT when valid Evidence for the same Business Meaning and Decision-Relevant Context is inconsistent and unresolved.

## Case Integrity
CURRENT when all Options are reliable.
REVIEW_REQUIRED when at least one Option is affected but at least one reliable Option remains.
DECISION_BLOCKED when no reliable Option remains.

Feasibility alone does not change Case Integrity.
NOT_AVAILABLE Impact data alone does not change Case Integrity.

## Decision Rules
- CURRENT → Decision allowed.
- REVIEW_REQUIRED → Decision allowed only with explicit warning and acknowledgement.
- DECISION_BLOCKED → Decision not allowed.

## Feasibility / Decision State Separation
If Case Integrity is CURRENT but no Option is feasible, Decision State = NO_ACCEPTABLE_OPTION.
This is not an Integrity failure.

If some Options are stale/conflicted while the only CURRENT Option is not feasible:
Case Integrity = REVIEW_REQUIRED; Decision State = NO_ACCEPTABLE_OPTION.
Decision remains technically allowed because the Case is not DECISION_BLOCKED, subject to warning/acknowledgement.

## M-204 Combined Failure Test
O-01: STALE + FEASIBLE + Financial Impact NOT_AVAILABLE
O-02: CONFLICT + NOT_FEASIBLE
O-03: CURRENT + NOT_FEASIBLE + Impacts AVAILABLE

Expected:
- Case Integrity = REVIEW_REQUIRED
- Feasibility = No currently acceptable Option
- Impact = Partial
- Decision State = NO_ACCEPTABLE_OPTION
- Decision allowed with warning

Result: PASSED.

## Architectural Invariant
Integrity ≠ Feasibility ≠ Impact ≠ Decision State
