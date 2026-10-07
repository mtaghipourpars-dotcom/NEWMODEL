# NEWMODEL — Decision Object
Version: 0.2
Status: WORKING MODEL — VALIDATION CONTINUES

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

## Product-validation rule
The Decision Object is an architectural means, not the product value itself.

Validation must demonstrate that structuring a decision into context, evidence, constraints, options, feasibility, decision and outcome materially improves a real management decision.

## Historical feasibility basis
Where an Option is selected, the Decision records the exact Feasibility Result used at decision time.

Three concepts remain distinct:
- History: immutable FEASIBILITY_RESULT records.
- Current: OPTION.current_feasibility_result_id.
- Decision basis: DECISION.selected_feasibility_result_id.

For a NO_ACCEPTABLE_OPTION decision, both selected option and selected feasibility result remain NULL.


## Product Validation Rule
The Decision Object is an architectural means, not the product value itself. Validation must demonstrate that structuring a real decision into context, evidence, constraints, options, feasibility, decision and outcome materially improves management decision-making.

## D-019 / D-020
History = immutable FEASIBILITY_RESULT. Current = OPTION.current_feasibility_result_id. Decision basis = DECISION.selected_feasibility_result_id. NO_ACCEPTABLE_OPTION leaves both selected fields NULL.
