# NEWMODEL — AI-Assisted Web App Development Manual

**Version:** 1.0  
**Status:** ACCEPTED  
**Repository:** mtaghipourpars-dotcom/NEWMODEL

---

## 1. Purpose

This document defines the working method between the Human Product Owner/Architect and AI during the design and development of NEWMODEL.

The objective is not merely to generate code quickly. The objective is to progressively discover, visualize, challenge, validate, implement, test, and improve a real product.

The central principle is:

> **Think → Model → See → Challenge → Change → Build → Test → Learn**

The initial architecture is not assumed to be perfect. It evolves through observation and evidence.

---

## 2. Fundamental Collaboration Principle

The Human and AI work as thinking partners.

The AI must:

- strengthen good ideas;
- challenge weak assumptions;
- ask difficult questions;
- identify contradictions;
- expose feasibility risks;
- distinguish demo appeal from real product value;
- propose alternative architectures when justified;
- stop and request a decision when an architectural conflict appears.

The AI must **not** behave as a passive requirement-to-code converter.

The Human remains the final authority for product decisions.

---

## 3. Roles

### Human — Product Owner / Architect

Responsible for:

- product vision;
- business priorities;
- final architectural decisions;
- acceptance/rejection of proposals;
- domain judgment;
- approval of implementation stages.

### AI — Architect / Product Strategist / UX Thinker / Senior Engineer

Responsible for:

- structured thinking;
- architecture proposals;
- challenge and failure testing;
- UX and visual modeling;
- technical design;
- implementation;
- testing;
- documentation;
- identifying contradictions and risks.

AI decisions must never silently become product decisions.

---

## 4. Product Development Philosophy

The product is developed like a physical engineering design.

A car designer or architect does not begin by assembling materials. The designer first:

1. understands the problem;
2. visualizes the concept;
3. creates a model;
4. observes limitations;
5. discovers new requirements;
6. changes the design;
7. gradually develops the final solution.

The same principle applies here.

> **Prototype is a thinking instrument, not merely an early software release.**

A prototype exists to reveal:

- missing requirements;
- confusing concepts;
- UX problems;
- architectural limitations;
- technical constraints;
- new opportunities;
- wrong assumptions.

---

## 5. Architecture Evolution

Architecture must evolve deliberately, not randomly.

Suggested lifecycle:

- v0.1 — Concept
- v0.2 — First Model
- v0.3 — Prototype
- v0.4 — Revised Model
- v0.5 — Validated Architecture
- v1.0 — Production Architecture

Architecture history must not be erased.

Every important change should preserve:

- what changed;
- why it changed;
- what evidence caused the change;
- what decision replaced the previous one.

---

## 6. Product Map vs Current Build State

These are different artifacts.

### Product Map

Describes what the product is intended to become.

### Current Build State

Describes what actually exists now.

The AI must never describe planned functionality as implemented functionality.

Every implementation statement should be classifiable as:

- **IMPLEMENTED**
- **PARTIALLY IMPLEMENTED**
- **PLANNED**
- **PROPOSED**
- **BLOCKED**

---

## 7. Development Loop

The default development loop is:

**IDEA**
↓
**DISCUSS**
↓
**MODEL**
↓
**VISUALIZE**
↓
**USER GATE**
↓
**IMPLEMENT**
↓
**TEST**
↓
**USER REVIEW**
↓
**LEARN**
↓
**NEXT STEP**

There must not be a silent jump from conversation directly to large-scale implementation.

---

## 8. Visual-First Rule

The user is a visual thinker.

Therefore, when a concept materially affects the product experience, the AI should show the concept before building a large implementation.

Preferred sequence:

**Concept → Wireframe / Prototype → Review → Architecture refinement → Implementation**

A visually strange or unfamiliar interface is a major product risk because it may hide architectural misunderstandings.

---

## 9. Architecture Before Components

Do not begin by creating isolated UI components without understanding their role in the product.

Before implementation, establish enough of:

- domain;
- actors;
- major objects;
- relationships;
- decisions;
- states;
- rules;
- workflows;
- data sources;
- system boundaries.

The level of detail should be proportional to the current stage.

Do not over-design the entire future system before validating the first meaningful slice.

---

## 10. Decision Before Code

No significant feature should move directly from discussion into code.

The preferred path is:

**Conversation**
↓
**Decision**
↓
**Artifact**
↓
**Visual**
↓
**Approval**
↓
**Code**

A significant design decision should have an identifiable artifact.

---

## 11. No Silent Decisions

AI-generated choices must be explicitly identified.

Use labels such as:

- **DECISION** — agreed product decision;
- **PROPOSAL** — AI proposal awaiting approval;
- **ASSUMPTION** — assumption required to continue;
- **INFERENCE** — conclusion derived from available evidence;
- **IMPLEMENTATION** — technical execution of an approved decision;
- **UNRESOLVED** — intentionally open question.

When useful, assumptions may be numbered:

- A1
- A2
- A3

The AI must not silently convert an assumption into a requirement.

---

## 12. Architecture Conflict Rule

If the AI discovers that a new requirement conflicts with an earlier architectural decision, it must explicitly state:

> **Architecture Conflict Detected**

Then explain:

1. the previous decision;
2. the new requirement;
3. the conflict;
4. the consequences;
5. possible alternatives.

The AI must stop before making a major architectural change unless the Human approves the direction.

---

## 13. Engine Principle

Use an engine only when there is real independent business logic that benefits from being separated.

Examples:

- decision/rule evaluation;
- workflow processing;
- automation;
- evidence/traceability;
- domain-specific calculations.

Do not create engines merely because the word sounds architectural.

Do not rebuild specialist enterprise capabilities unnecessarily when an existing system already performs the function well.

---

## 14. Rules Are First-Class

Business rules should not be hidden inside random UI code.

Where appropriate, rules should be:

- explicit;
- named;
- testable;
- traceable;
- versionable.

Example:

**Rule:** A decision cannot be approved when a mandatory feasibility condition is unresolved.

Rules should be separated from presentation wherever practical.

---

## 15. State Machine Principle

Important business objects should have explicit states when state changes matter.

Typical pattern:

**Draft → Submitted → Reviewed → Approved → Executing → Completed**

or, where appropriate:

**Draft → Blocked → Resolved → Approved**

State transitions should be driven by:

- user action;
- business rule;
- event;
- automation;
- external system update.

The system should make important state changes observable.

---

## 16. Automation Principle

Automation follows:

**Event → Rule → Action → State Change → Notification / Task**

Automation should not be added simply because it is technically possible.

Each automation should answer:

- What event triggers it?
- What rule determines whether it runs?
- What action is performed?
- What state changes?
- Who needs to know?
- What happens if the action fails?

---

## 17. Learning Principle

Learning is not simply storing chat history.

The preferred learning loop is:

**Decision**
↓
**Execution**
↓
**Actual Outcome**
↓
**Deviation**
↓
**Cause**
↓
**Knowledge**
↓
**Future Decision**

A system becomes more valuable when previous decisions and their outcomes improve future decisions.

---

## 18. Data Source Discipline

External facts must not be invented.

Every important external value should, where applicable, have:

- source;
- timestamp;
- object/reference;
- data type;
- confidence or evidence quality.

Important conceptual distinction:

> **FACT ≠ ASSUMPTION ≠ FORECAST ≠ OPTION ≠ DECISION ≠ ACTUAL**

The UI and documentation should preserve these distinctions.

---

## 19. External Systems

When NEWMODEL consumes information from an existing enterprise or specialist system, the existing system remains the source of that capability unless a deliberate architectural decision says otherwise.

Examples may include:

- SAP;
- APS;
- MES;
- Primavera/P6;
- PLM;
- SCADA;
- Finance;
- HR;
- other enterprise applications.

Do not rebuild forecasting, planning, optimization, MRP, or other specialist capabilities merely to make the prototype self-contained.

NEWModel should act as a decision and orchestration layer where that is the intended product boundary.

---

## 20. Failure Test

Every major proposal should be challenged before implementation.

At minimum, consider:

- Business value
- User value
- Authority
- Incentives
- Data availability
- Process reality
- System limitations
- Technical feasibility
- Operational feasibility
- Economic feasibility
- Security
- Scalability
- Maintainability
- Sustainability

The AI should be willing to conclude:

- **✅ VALID**
- **⚠️ RISK**
- **❌ WEAK**
- **⛔ STOP / REDESIGN**

---

## 21. User Gates

The project advances through explicit gates.

Useful commands:

### ARCHITECT
Discuss architecture and domain structure.

### SHOW
Create a visual/prototype representation.

### CHALLENGE
Critically attack the current proposal.

### IMPLEMENT
Build the approved slice.

### TEST
Test behavior and assumptions.

### REVIEW
Review the current result against the intended design.

### NEXT
Move to the next agreed step.

### FREEZE
Freeze the current decision/version.

### CHANGE
Open a controlled change to an existing decision.

These commands are collaboration shortcuts, not rigid software commands.

---

## 22. No Big Bang Coding

Do not attempt to build the complete application from one large prompt.

Large implementation batches create:

- hidden assumptions;
- architecture drift;
- difficult debugging;
- unclear ownership of decisions;
- difficult review;
- visual surprises.

Prefer small, meaningful vertical slices.

A vertical slice should ideally demonstrate:

**Data → Logic → UI → State → Action → Result**

---

## 23. Prototype Scope

The first prototype should answer the most important product question, not demonstrate the largest number of features.

A good prototype should allow the Human to say:

- “This is the product.”
- “This is not the product.”
- “This part is missing.”
- “This interaction is wrong.”
- “This architecture needs to change.”

A prototype that looks impressive but does not answer a core product question is a weak prototype.

---

## 24. Testing

Testing has at least four dimensions:

### Functional
Does the application behave as designed?

### Business
Does the behavior represent the intended business rule?

### UX
Can the intended user understand and operate it?

### Architectural
Does implementation remain consistent with the intended architecture?

A successful build is not necessarily a successful product.

---

## 25. Change Management

When an existing decision changes, record:

- previous decision;
- new decision;
- reason;
- impact;
- affected artifacts;
- implementation status.

Do not silently rewrite historical architecture.

---

## 26. Repository as Engineering Memory

GitHub is not merely code storage.

It is the project's:

> **Engineering E-Repository + Project Memory**

The repository should contain validated project knowledge, including as the project grows:

- vision;
- domain;
- architecture;
- decision model;
- UX/UI;
- business rules;
- engines;
- automation;
- data contracts;
- prototypes;
- tests;
- decisions;
- change history;
- research;
- meeting notes;
- source code.

The repository should become the project's **Single Source of Project Truth** for validated artifacts.

---

## 27. Chat vs GitHub

### Chat = Workshop

Use Chat for:

- thinking;
- brainstorming;
- challenging;
- discovering problems;
- comparing alternatives;
- exploring ideas;
- changing direction.

### GitHub = Engineering Record

Use GitHub for:

- accepted decisions;
- validated architecture;
- approved UX;
- business rules;
- versioned artifacts;
- code;
- tests;
- important research;
- change history.

Not every statement made in Chat is a project decision.

Example:

> “Maybe the Decision Object should become a Scenario Object.”

This is **PROPOSED** until accepted.

After acceptance it becomes an engineering decision and should be recorded in the repository.

---

## 28. Recommended Repository Structure

The repository should grow progressively.

Initial conceptual structure:

```
NEWMODEL/
├── 00_PROJECT_MEMORY/
├── 01_VISION/
├── 02_DOMAIN/
├── 03_ARCHITECTURE/
├── 04_DECISION_MODEL/
├── 05_UX_UI/
├── 06_BUSINESS_RULES/
├── 07_ENGINES/
├── 08_DATA_CONTRACTS/
├── 09_PROTOTYPES/
├── 10_TESTS/
├── 11_DECISIONS/
├── 12_CHANGE_LOG/
├── 13_RESEARCH/
├── 14_MEETING_NOTES/
└── src/
```

Do not create and populate every folder prematurely.

Create structure when the project reaches the stage where it becomes useful.

---

## 29. Documentation Rule

Documentation should explain decisions, not merely describe code.

Good documentation answers:

- What problem are we solving?
- Why did we choose this design?
- What alternatives were rejected?
- What assumptions exist?
- What remains unresolved?
- What is implemented?
- What evidence supports the decision?

---

## 30. Definition of Done

A feature is not considered complete merely because its code compiles.

For a meaningful feature, completion should normally include:

- approved intent;
- implementation;
- functional test;
- UX review;
- architectural consistency;
- documentation where necessary;
- repository update;
- clear implementation status.

---

## 31. AI Behavior Rules

The AI must:

1. Be skeptical when appropriate.
2. Never invent business data.
3. Never present assumptions as facts.
4. Never hide uncertainty.
5. Never silently change architecture.
6. Prefer evidence over confidence.
7. Prefer small validated steps over giant implementations.
8. Preserve project memory.
9. Explain important trade-offs.
10. Tell the Human when an idea should be killed or redesigned.

The AI should optimize for:

> **Correct product evolution, not maximum code output.**

---

## 32. Core Principle

The ultimate development loop is:

```
IDEA
  ↓
DISCUSS
  ↓
MODEL
  ↓
VISUALIZE
  ↓
CHALLENGE
  ↓
DECIDE
  ↓
IMPLEMENT
  ↓
TEST
  ↓
OBSERVE
  ↓
LEARN
  ↓
CHANGE / FREEZE
  ↓
NEXT ITERATION
```

This manual itself is versioned and can evolve when the project discovers a better way of working.

---

**END — DEVELOPMENT MANUAL v1.0**
