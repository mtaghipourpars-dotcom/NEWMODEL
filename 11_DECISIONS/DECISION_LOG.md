# NEWMODEL — Decision Log
Version: 1.0
Status: ACTIVE

## Decision register

| ID | Decision | Status | Date | Evidence / Reason |
|---|---|---|---|---|
| D-001 | Human is final Product Owner / Architect authority. | ACCEPTED | 2026-10-04 | Development Manual |
| D-002 | AI acts as thinking partner and must challenge assumptions. | ACCEPTED | 2026-10-04 | Development Manual |
| D-003 | Development follows Think → Model → See → Challenge → Change → Build → Test → Learn. | ACCEPTED | 2026-10-04 | Development Manual |
| D-004 | Prototype is a thinking instrument. | ACCEPTED | 2026-10-04 | Development Manual |
| D-005 | Product Map and Current Build State are separate. | ACCEPTED | 2026-10-04 | Development Manual |
| D-006 | GitHub is the engineering record; Chat is the workshop. | ACCEPTED | 2026-10-04 | Development Manual |
| D-007 | NEWMODEL is not Railway; Railway is only a possible visualization metaphor. | ACCEPTED | 2026-10-04 | Project discussion |
| D-008 | Existing specialist enterprise systems should not be unnecessarily rebuilt in the initial phase. | ACCEPTED | 2026-10-04 | Product architecture discussion |
| D-009 | A decision shell/layer over existing systems is the current product architecture direction. | ACCEPTED AS DIRECTION | 2026-10-04 | Product architecture discussion |
| D-010 | Dynamic prioritization/allocation under current and future resource constraints is a central problem candidate. | ACCEPTED AS HYPOTHESIS | 2026-10-04 | Product problem discussion |

## Unresolved decisions
- Final product vision.
- MVP decision scenario.
- Canonical domain model.
- Integration architecture.
- AI responsibility boundary.
- Security/authorization model.
- Production deployment architecture.

## D-011 — Ownership Classification
**Status:** ACCEPTED  
**Date:** 2026-10-05  
MDCRL owns decision memory, not operational data. Persistent / External-Referenced / Derived classification is the baseline for the decision model.

## D-012 — Derived → Snapshot → Persistent
**Status:** ACCEPTED  
**Date:** 2026-10-05  
Derived results become Persistent when their exact state is historically relevant to a decision, including Decision Required Because, Integrity at Decision and Decision Context Snapshot.

## D-013 — Dependency Graph Boundary
**Status:** ACCEPTED  
**Date:** 2026-10-05  
Dependency Graph is used only for Traceability, change-impact detection and Integrity support. It is not used for Scheduling, Optimization, Resource Allocation or Option Generation.

## D-014 — Integrity Invariant
**Status:** ACCEPTED  
**Date:** 2026-10-05  
Integrity ≠ Feasibility ≠ Impact ≠ Decision State. These four concepts must remain independent throughout subsequent architecture and implementation.

## D-015 — Integrity Rules v0.1.1
**Status:** VALIDATED  
**Date:** 2026-10-05  
Option and Case Integrity rules were validated, including CURRENT / REVIEW_REQUIRED / DECISION_BLOCKED and the M-204 combined failure test.

## D-016 — Physical Relational Core
**Status:** APPROVED AS DRAFT  
**Date:** 2026-10-05  
The minimal relational core is approved as the starting Physical Data Model.

## D-017 — Reference DBMS Selection
**Status:** ACCEPTED  
**Date:** 2026-10-05  
PostgreSQL is selected as the Reference Implementation DBMS for the first executable NEWMODEL / MDCRL physical schema. This does not lock future production deployment to PostgreSQL.

## D-018 — PostgreSQL Physical Schema Specification
**Status:** VALIDATED  
**Date:** 2026-10-05  
PostgreSQL Physical Schema Specification v0.1 and M-204 SQL Schema Walkthrough v0.1.2 were validated with 17/17 tests passed. The next implementation stage is executable PostgreSQL DDL.
