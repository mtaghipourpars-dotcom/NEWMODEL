# NEWMODEL — Product Vision
Version: 0.2
Status: WORKING VISION — BUSINESS VALIDATION REQUIRED

## Vision
Create a management decision layer that helps an enterprise understand competing demands, constraints, commitments and available resources in one traceable context, so managers can make better prioritization and allocation decisions.

## Core management question
Given current projects, commitments, future demand and limited resources:
What should be advanced now, what should be delayed, what should be protected, and what must be prepared for?

## Current architectural hypothesis
NEWMODEL should act as a decision shell over existing enterprise and specialist systems.

Potential sources:
- SAP
- APS
- MES
- Primavera/P6
- PLM
- SCADA
- Finance
- HR
- Other enterprise systems

The product should consume facts, plans, forecasts, actuals, constraints, commitments and alternatives rather than unnecessarily recreating specialist planning/forecasting/optimization systems.

## Decision evidence principle
FACT ≠ ASSUMPTION ≠ FORECAST ≠ OPTION ≠ DECISION ≠ ACTUAL.

Important decision information should remain traceable to source, object and time.

## External conditions
External conditions may create changes; changes may create impacts; impacts may create constraints; constraints may create risks/opportunities; these may require decisions.

External condition → Change/Event → Impact → Constraint → Risk/Opportunity → Decision.

## Product value hypothesis
The product creates value when it reduces decision latency, makes trade-offs visible, exposes infeasibility before commitment, improves resource prioritization, and preserves the reasoning and outcome of decisions.

This remains a hypothesis until demonstrated against a real management decision journey.

### Required proof
The product must demonstrate a meaningful improvement over the existing decision process in at least one high-value scenario.

The proof should compare:
- decision journey before MDCRL;
- decision journey with MDCRL;
- decision latency;
- information completeness / traceability;
- visibility of trade-offs and feasibility;
- management accountability;
- measurable economic, customer, risk or capacity consequence where evidence is available.

## Out of scope for initial phase
- Rebuilding SAP.
- Rebuilding MRP.
- Rebuilding APS.
- Rebuilding specialist forecasting.
- Rebuilding enterprise optimization solely for the prototype.
- Treating dashboards as the product by themselves.

## Critical validation questions
- Which decision is painful enough to buy for?
- Who owns that decision?
- Which existing systems already contain the necessary evidence?
- What decision is currently made manually or inconsistently?
- What measurable economic consequence follows from a better decision?
- What is the smallest vertical slice that proves value?

## Product-validation checkpoint
Before deep implementation, validate:
1. a painful decision worth improving;
2. the accountable decision owner;
3. the existing decision process;
4. the incremental value created by MDCRL;
5. the smallest vertical slice that can demonstrate that value.

## Gate
This document is a working vision, not yet a frozen product specification.
