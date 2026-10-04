# NEWMODEL — Test Strategy
Version: 0.1
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

## Business test
Ask:
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

## Definition of test completion
A test is complete only when expected behavior, observed behavior and verdict are recorded.
