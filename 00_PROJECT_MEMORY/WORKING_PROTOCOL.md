# NEWMODEL — Working Protocol
Version: 1.1
Status: ACCEPTED

## Conversation protocol
The AI should naturally distinguish:
- DECISION
- PROPOSAL
- ASSUMPTION
- INFERENCE
- IMPLEMENTATION
- UNRESOLVED

## Before major implementation
1. Clarify the problem.
2. Model the concept.
3. Show the concept when visual understanding matters.
4. Challenge it.
5. Validate business/product value.
6. Obtain an explicit user gate.
7. Implement a small slice.
8. Test.
9. Review.
10. Record accepted learning.

### Architecture stop rule
If technical detail is growing faster than evidence of product value, STOP technical deepening and move to Business/Product Validation.

A technically correct implementation is not evidence that the product should exist.

## User gates
ARCHITECT — architecture/domain discussion.
SHOW — visual/prototype.
CHALLENGE — adversarial review.
IMPLEMENT — execute approved scope.
TEST — test behavior and assumptions.
REVIEW — compare result with intent.
NEXT — move to the next agreed step.
FREEZE — freeze a decision/version.
CHANGE — intentionally reopen an accepted decision.

## Stop conditions
Stop and surface the issue when:
- technical elaboration is continuing without a clear product-value question;
- a new technical layer does not materially improve validation of the current business hypothesis;
- a new requirement conflicts with an accepted architectural decision;
- essential evidence is missing;
- a proposed feature depends on an unverified external capability;
- implementation would silently redefine the product;
- a major irreversible technical choice is being made without an approved decision.
- a new requirement conflicts with an accepted architectural decision;
- essential evidence is missing;
- a proposed feature depends on an unverified external capability;
- implementation would silently redefine the product;
- a major irreversible technical choice is being made without an approved decision.

## Output discipline
Prefer concise working artifacts over long speculative prose.
When research is requested, distinguish source evidence, inference and proposal.
