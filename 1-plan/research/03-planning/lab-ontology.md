# Research Lab Ontology

## Purpose
Define the research-lab structure triggered by a human hypothesis and evolved through research, seminar critique, planning, experiments, evaluation, and revision.

## Core structure

```text
RESEARCH_LAB
├── THEME_HYPOTHESIS
├── SEMINAR
├── PLANNING
├── EXPERIMENT
├── EVALUATION
├── EVOLUTION
└── OUTPUT
```

## Core relations

```text
Human --proposes--> Hypothesis
Hypothesis --triggers--> Research_Cycle
Paper --provides--> Evidence
Claim --supported_by--> Evidence
Claim --challenged_by--> Objection
Objection --answered_by--> Counterargument
Seminar --produces--> Decision
Decision --changes--> Hypothesis
Seminar --requests--> Planning
Planning --defines--> Experiment
Experiment --produces--> Result
Result --evaluated_by--> Evaluator
Result --causes--> Hypothesis_Revision
Hypothesis_Revision --creates--> Hypothesis_Version
```

## Research state machine

```text
PROPOSED
  ↓
RESEARCHING
  ↓
SEMINAR
  ↓
PLANNED
  ↓
EXPERIMENTING
  ↓
EVALUATING
  ↓
REVIEWING
  ↓
REVISED
  └────────→ PROPOSED
```

Alternative states:

```text
BLOCKED
NEEDS_EVIDENCE
REJECTED
ABANDONED
```

## Automatic trigger

```text
Human writes Hypothesis
        ↓
Theme / Hypothesis stage
        ↓
Seminar stage
        ↓
Planning stage
        ↓
Experiment
        ↓
Evaluation
        ↓
Revision
        ↓
New Hypothesis
```

## Human / LLM separation

LLM layer: English-only Markdown.

Human layer: Japanese meeting minutes / HTML-oriented outputs.

Do not duplicate internal reasoning unnecessarily. Convert research state into concise human-readable decisions.

## Versioning

Version major research objects:

```text
Hypothesis_V1
Ontology_V1
Plan_V1
Evaluator_V1
Experiment_V1
```

Never silently erase a material research decision.

## Domain module

The current domain is humor. The lab ontology itself remains domain-independent so future research domains can be attached without redesigning the research cycle.
