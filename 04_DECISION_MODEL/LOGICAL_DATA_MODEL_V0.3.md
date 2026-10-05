# NEWMODEL — Logical Data Model v0.3

Status: VALIDATED
Scope: Current MDCRL decision model

## Ownership Classification
Persistent: Evidence/Snapshot, Assumption, Option, Feasibility Result, Impact, Decision Case, Decision, Outcome, Post-Decision Change.
External / Referenced: operational data owned by authoritative systems; MDCRL references it. Example: Fact such as capacity, priority and contract terms.
Derived: Option Integrity, Case Integrity, Current Feasibility Result, Affected Options and Deadline Status.

## Critical Pattern
Derived → Snapshot → Persistent

A derived result becomes persistent when its exact state is historically relevant to a decision:
- Decision Required Because
- Integrity Status at Decision
- Decision Context Snapshot

## Ownership Principles
1. MDCRL owns decision memory, not operational data.
2. Anything used at decision time must either be Persistent or Snapshot into the Decision record/context.
3. MDCRL does not calculate specialist Feasibility or Impact; it receives and persists their results.
4. Integrity is Derived except for the historical snapshot captured at Decision time.
5. Human owns the decision; MDCRL owns the immutable decision record.
6. Execution systems are the source of actual outcomes; MDCRL persists decision-relevant outcomes.
