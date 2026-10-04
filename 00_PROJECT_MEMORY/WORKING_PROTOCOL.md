# NEWMODEL — Working Protocol
Version: 1.0
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
5. Obtain an explicit user gate.
6. Implement a small slice.
7. Test.
8. Review.
9. Record accepted learning.

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
- a new requirement conflicts with an accepted architectural decision;
- essential evidence is missing;
- a proposed feature depends on an unverified external capability;
- implementation would silently redefine the product;
- a major irreversible technical choice is being made without an approved decision.

## Output discipline
Prefer concise working artifacts over long speculative prose.
When research is requested, distinguish source evidence, inference and proposal.
