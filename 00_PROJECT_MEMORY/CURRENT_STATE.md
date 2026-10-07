# NEWMODEL — Current State
Version: 1.2
Status: ACCEPTED
Date: 2026-10-07

## Confirmed
- Development Manual v1.0 exists and governs collaboration.
- Human–AI collaboration is explicit and challenge-oriented.
- Development is visual-first and iterative.
- Architecture is versioned and may evolve.
- Product Map and Current Build State are separate.
- GitHub is the engineering record.
- Small validated vertical slices are preferred.
- Business/product validation must precede deep technical implementation when product value is not yet proven.

## Product direction currently established
- NEWMODEL is being developed as a management/decision-oriented enterprise web product.
- The product is not defined as Railway.
- Railway may be used as a visualization metaphor, not as the product boundary.
- Existing enterprise systems such as SAP, APS, MES, P6, PLM and SCADA should be consumed rather than unnecessarily rebuilt.
- A decision shell/layer is the current architectural direction.
- Current/future resource constraints and project/activity prioritization are central problem candidates.
- The current product hypothesis is that MDCRL creates value by making decision context, trade-offs, feasibility, integrity and decision history traceable.

## Validated decision-model state
- Conceptual Model: VALIDATED
- Logical Data Model v0.3: VALIDATED
- Dependency Graph v0.1: VALIDATED
- Integrity Rules v0.1.1: VALIDATED
- Physical Data Model Core: VALIDATED
- Constraint & Integrity Specification: VALIDATED
- SQL Schema Design v0.1.1: VALIDATED
- PostgreSQL Physical Schema Specification v0.1: VALIDATED
- Reference DBMS: PostgreSQL (D-017)
- D-019: Feasibility Current Representation — ACCEPTED
- D-020: Decision → Historical Feasibility Linkage — ACCEPTED

## Technical implementation status
- PostgreSQL DDL v0.1.1 identified a real historical-linkage gap.
- DDL v0.1.2 is the intended next technical revision, adding DECISION.selected_feasibility_result_id.
- DDL v0.1.2 is NOT YET VALIDATED.
- M-204 Re-evaluation Walkthrough has not yet been accepted as passed.
- The six re-evaluation tests are the next technical validation only after the product-value checkpoint.

## Architecture / product validation status
The project has intentionally paused deeper technical implementation.

The current priority is BUSINESS / PRODUCT VALIDATION:
1. Identify the real management decision journey.
2. Compare current decision-making without MDCRL against the MDCRL-assisted journey.
3. Establish measurable value: decision latency, decision quality/traceability, avoidable loss/risk, or other defensible business consequence.
4. Validate the human accountability boundary.
5. Test MDCRL against multiple high-value decision scenarios.
6. Identify the smallest vertical slice that proves product value.

## Technical baseline / freeze
The current technical architecture is sufficient as a baseline for product validation.

Technical deepening is temporarily FROZEN except where required to resolve a validated architectural gap or support a minimal product-validation prototype.

PostgreSQL, DDL, triggers, concurrency and transaction details are implementation mechanisms, not the product definition.

## Explicitly unresolved
- Final product name/brand.
- Final product vision wording.
- Exact MVP decision scenario.
- Final integration contracts.
- Final UI information architecture.
- Exact first customer/user and buying model.
- Production architecture.
- Demonstrated business value / killer use case.
- Quantified before/after value case for MDCRL.

## Status discipline
Nothing listed as unresolved may be treated as an accepted requirement without a new decision record.

## Current next step
Product / Business Validation of MDCRL before further technical deepening.
