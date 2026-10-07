# NEWMODEL — Test Strategy
Version: 0.2
Status: ACCEPTED AS WORKING METHOD

## Test layers
1. Functional
2. Business
3. UX
4. Architectural
5. Integration
6. Data lineage
7. Security
8. Failure/recovery

## Vertical-slice acceptance
A meaningful slice should demonstrate:
Data → Logic → UI → State → Action → Result.

### Product-value acceptance
A vertical slice is not successful merely because the technical flow works.

It must also demonstrate:
Problem → Decision Journey → MDCRL Intervention → Decision → Outcome → Measurable Value.

Before deep technical implementation, the team should be able to explain what management behavior or outcome the slice improves.

## Business test
Ask:
- Is this decision painful enough to justify intervention?
- Who is accountable for the decision?
- What happens today without MDCRL?
- What changes with MDCRL?
- What measurable value can be demonstrated?


- Does the result answer the intended management question?
- Are infeasible options excluded or clearly marked?
- Are facts and assumptions distinguishable?
- Is the decision owner clear?
- Can the user explain why the decision was made?

## Data lineage test
For each critical value:
Source → Object → Timestamp → Transformation → Display → Decision use.

## Integration test
Verify actual source-system contracts rather than assuming fields or relationships exist.

## Failure test
Intentionally test:
- missing data;
- stale data;
- conflicting data;
- unavailable source;
- delayed source;
- infeasible alternative;
- simultaneous competing demands;
- changed constraint after decision;
- automation failure.

## UX test
A manager should be able to understand:
- what is happening;
- why it matters;
- what choices exist;
- what is feasible;
- what happens if nothing is decided;
- what action is expected.

## Product validation test
A Product Validation Test should record:
- current decision journey;
- decision owner;
- decision latency or effort where measurable;
- MDCRL-assisted journey;
- measurable improvement or defensible qualitative evidence;
- remaining gaps;
- verdict.

## Technical test checkpoint
The six DDL v0.1.2 re-evaluation tests are implementation validation, not product validation:
1. Normal re-evaluation
2. Failed re-evaluation
3. Concurrent re-evaluation
4. Pointer integrity
5. Decision → historical feasibility linkage
6. Rollback behavior

## Definition of test completion
A test is complete only when expected behavior, observed behavior and verdict are recorded.
