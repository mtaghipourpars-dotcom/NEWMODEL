# NEWMODEL — Dependency Graph Model v0.1

Status: VALIDATED
Purpose: Traceability and change-impact detection only.

## Nodes
Fact, Evidence, Assumption, Option, Feasibility Result, Impact, Decision Case, Decision, Post-Decision Change.

## Relationships
- Fact 1:N Evidence
- Evidence N:N Option
- Assumption N:N Option
- Option 1:N Feasibility Result
- Feasibility Result 1:N Impact
- Option N:1 Decision Case
- Decision Case 1:0..1 Decision
- Decision 1:0..N Post-Decision Change

## Semantics
Fact is an external Business Meaning. The Fact itself is not versioned by MDCRL. External Fact State change is observed through new or updated Evidence.
Option depends on Evidence and Assumption, never directly on Fact.
Evidence, Feasibility Result and Impact are versioned/snapshotted.
The graph is bidirectionally traversable: forward traversal supports Integrity propagation; reverse traversal supports audit and decision reconstruction.

## Integrity Propagation
External Fact State Change → new/updated Evidence → affected Options → affected Feasibility Results → affected Impacts → affected Decision Case → Integrity recalculation.

## Integrity Semantics
STALE: a relevant Evidence or Assumption changed relative to the snapshot used for evaluation while remaining valid.
INVALID: a dependent Evidence or Assumption is explicitly invalid.
CONFLICT: valid Evidence for the same Business Meaning and Decision-Relevant Context contains inconsistent values and no existing rule resolves the conflict.
Change Over Time is not automatically Conflict.
UNKNOWN: freshness or validity cannot be verified.

## Post-Decision Change
Preserves Changed Object, Detected At, Change Type and Impact on Decision Context.
Decision is immutable; later changes do not rewrite the historical Decision.

## Boundary
The graph is never used for Scheduling, Optimization, Resource Allocation or Option Generation. It exists only for Traceability, change-impact detection and Integrity support.
