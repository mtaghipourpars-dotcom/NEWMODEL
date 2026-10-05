# NEWMODEL — Current State
Version: 1.1
Status: ACCEPTED
Date: 2026-10-05

## Confirmed
- Development Manual v1.0 exists and governs collaboration.
- Human–AI collaboration is explicit and challenge-oriented.
- Development is visual-first and iterative.
- Architecture is versioned and may evolve.
- Product Map and Current Build State are separate.
- GitHub is the engineering record.
- Small validated vertical slices are preferred.

## Product direction currently established
- NEWMODEL is being developed as a management/decision-oriented enterprise web product.
- The product is not defined as Railway.
- Railway may be used as a visualization metaphor, not as the product boundary.
- Existing enterprise systems such as SAP, APS, MES, P6, PLM and SCADA should be consumed rather than unnecessarily rebuilt.
- A decision shell/layer is the current architectural direction.
- Current/future resource constraints and project/activity prioritization are central problem candidates.

## Validated decision-model state
- Conceptual Model: VALIDATED
- Logical Data Model v0.3: VALIDATED
- Dependency Graph v0.1: VALIDATED
- Integrity Rules v0.1.1: VALIDATED
- Physical Data Model Core: VALIDATED
- Constraint & Integrity Specification: VALIDATED
- SQL Schema Design v0.1.1: VALIDATED
- PostgreSQL Physical Schema Specification v0.1: VALIDATED
- M-204 SQL Schema Walkthrough v0.1.2: 17/17 PASS
- Reference DBMS: PostgreSQL (D-017)

## Current implementation stage
The next stage is executable PostgreSQL DDL v0.1:
CREATE TABLE, indexes, constraints and explicitly required triggers, followed by SQL execution and validation.

## Explicitly unresolved
- Final product name/brand.
- Final product vision wording.
- Exact MVP decision scenario.
- Final integration contracts.
- Final UI information architecture.
- Exact first customer/user and buying model.
- Production architecture.

## Status discipline
Nothing listed as unresolved may be treated as an accepted requirement without a new decision record.
