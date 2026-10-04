# NEWMODEL — Decision Object
Version: 0.1
Status: PROPOSED — REQUIRES USER GATE

## Purpose
Represent one management decision with enough context to make the decision traceable before, during and after execution.

## Candidate structure
### Identity
- Decision ID
- Title
- Decision Owner
- Organizational scope
- Created at
- Decision deadline
- Status

### Context
- Business situation
- Trigger/event
- Relevant projects/activities
- Commitments
- Current state

### Evidence
- Facts
- Plans
- Forecasts
- Actuals
- Source references
- Freshness
- Evidence quality

### Constraints
- Resource constraints
- Capacity constraints
- Material constraints
- Financial constraints
- Time constraints
- External constraints
- Regulatory/security constraints

### Assumptions
Explicit assumptions with owner and confidence.

### Options
For each option:
- description;
- feasibility;
- required resources;
- opportunity cost;
- timing;
- expected economic impact;
- risk;
- dependencies;
- evidence.

### Decision
- selected option;
- decision rationale;
- decision maker;
- decision timestamp.

### Execution
- actions;
- responsible parties;
- deadlines;
- state changes.

### Outcome
- actual result;
- deviation;
- cause;
- lesson;
- future rule/knowledge candidate.

## Core rule
The system must not blur evidence, prediction, option and decision into one undifferentiated value.
