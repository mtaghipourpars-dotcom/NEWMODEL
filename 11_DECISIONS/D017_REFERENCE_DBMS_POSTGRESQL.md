# D-017 — Reference DBMS Selection

Status: ACCEPTED
Date: 2026-10-05

## Decision
PostgreSQL is selected as the Reference Implementation DBMS for the first executable NEWMODEL / MDCRL physical schema.

## Rationale
The current physical model requires:
- Composite Foreign Keys
- Partial Unique Index for current Feasibility Result
- UUID identifiers
- JSONB evidence values
- CHECK constraints
- Transactional version replacement
- Trigger support where Domain enforcement is intentionally implemented at database level

PostgreSQL provides these capabilities cleanly for the current reference implementation.

## Boundary
This decision does not define PostgreSQL as the only future production DBMS. The logical model and business invariants remain DBMS-neutral. PostgreSQL is the first physical reference implementation.

## Enforcement Architecture
DATABASE-ENFORCED: PK / FK / UNIQUE / CHECK / Partial Unique Index / Composite FK

DOMAIN-ENFORCED: Decision immutability, DECISION_BLOCKED prohibition and other cross-row/business invariants where explicitly required

DOMAIN ENGINE: Dependency-aware recalculation, affected-option detection and derived integrity behavior

## Consequence
The next implementation step is PostgreSQL DDL v0.1.
