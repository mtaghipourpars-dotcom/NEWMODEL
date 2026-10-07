# NEWMODEL — Architecture Principles
Version: 0.2
Status: WORKING ARCHITECTURE — VALIDATION CONTINUES

## 1. Decision shell, not system replacement
NEWMODEL sits above existing systems and organizes decision context.

## 2. Source-system respect
A specialist capability should remain in its authoritative system unless there is an explicit decision to replace it.

## 3. Traceability
Every important external value should be traceable to source, object/reference, timestamp and semantic type where available.

## 4. Decision-centric model
The central architectural artifact is expected to be a Decision Object, subject to validation.

Candidate structure:
- Decision
- Decision Owner
- Decision Deadline
- Context
- Facts
- Plans
- Forecasts
- Constraints
- Assumptions
- Risks
- Options
- Feasibility
- Expected Consequences
- Selected Option
- Decision Rationale
- Execution
- Actual Outcome
- Deviation
- Learning

## 5. Feasibility before preference
A manager should not rank infeasible alternatives as if they were executable options.

## 6. Current and future resources
Where future capacity matters, future-resource confidence and time-phased feasibility should be visible rather than hidden inside a single number.

## 7. Human accountability
The system supports decisions; the accountable manager remains the decision authority.

## 8. Evidence before confidence
Confidence must derive from evidence quality, freshness, completeness and explicit assumptions.

## 9. Evolution
Architecture versions must preserve history and reasons for change.

## 10. Integration resilience
The product should minimize dependency on a single enterprise vendor or implementation detail.

## 11. Business value before technical depth
Architecture maturity must not be confused with product maturity.

The project must validate that the Decision Layer materially improves a real management decision before investing in deep implementation details.

## 12. Technical baseline is not product boundary
PostgreSQL, DDL, triggers, transaction handling, concurrency control and similar mechanisms are implementation choices. They must support the validated decision architecture rather than drive the product definition.

## 13. Decision memory is the architectural differentiator
Existing systems remain authoritative for operational and specialist capabilities. MDCRL's distinctive responsibility is to preserve the context, alternatives, rationale, decision basis and outcome of management decisions.

## 14. Minimal vertical proof
The first implementation should prove one meaningful decision journey end-to-end rather than maximize technical model completeness.

## Open architectural questions
- canonical domain objects;
- event model;
- integration pattern;
- data synchronization strategy;
- decision lifecycle;
- rules architecture;
- identity/authorization;
- audit model;
- deployment model;
- offline/local-network requirements;
- AI boundary.
