# Research Lab Ontology

## Purpose

Define the complete research-lab structure that is triggered by a human hypothesis and evolves through research, critique, experiments, evaluation, and revision.

## Root ontology

```text
RESEARCH_LAB
├── HUMAN
│   ├── Researcher
│   ├── Student
│   ├── Senior
│   ├── Professor
│   └── Reviewer
├── KNOWLEDGE
│   ├── Hypothesis
│   ├── Paper
│   ├── Evidence
│   ├── Claim
│   ├── Concept
│   ├── Ontology
│   └── Research_Gap
├── REASONING
│   ├── Question
│   ├── Argument
│   ├── Objection
│   ├── Counterargument
│   ├── Critique
│   └── Decision
├── RESEARCH
│   ├── Research_Plan
│   ├── Experiment
│   ├── Dataset
│   ├── Annotation
│   ├── Baseline
│   ├── Measurement
│   ├── Result
│   └── Error_Analysis
├── EVOLUTION
│   ├── Hypothesis_Version
│   ├── Ontology_Version
│   ├── Experiment_Version
│   ├── Evaluator_Version
│   └── Research_State
└── OUTPUT
    ├── Meeting_Minutes
    ├── Research_Proposal
    ├── Paper
    └── Artifact
```

## Core relations

```text
Human --proposes--> Hypothesis
Hypothesis --triggers--> Research_Cycle
Paper --provides--> Evidence
Claim --supported_by--> Evidence
Claim --challenged_by--> Objection
Objection --answered_by--> Counterargument
Discussion --produces--> Decision
Decision --changes--> Hypothesis
Hypothesis --becomes--> Experiment
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
PLANNED
  ↓
DEBATING
  ↓
EXPERIMENTING
  ↓
EVALUATING
  ↓
REVIEWING
  ↓
REVISED
  │
  └────────→ PROPOSED
```

Alternative states:

```text
BLOCKED
NEEDS_EVIDENCE
REJECTED
ABANDONED
```

## Automatic lab trigger

```text
Human
  ↓ writes
Hypothesis
  ↓ triggers
Research_Lab
  ├── Search_Prior_Research
  ├── Build_Research_Gap
  ├── Generate_Research_Plan
  ├── Run_Seminar
  ├── Generate_Critique
  ├── Design_Experiment
  ├── Evaluate_Result
  └── Revise_Hypothesis
          ↓
      Hypothesis_V2
          ↓
      Research_Lab
```

## Research cycle

```text
HYPOTHESIS
 → PRIOR_RESEARCH
 → RESEARCH_GAP
 → RESEARCH_PLAN
 → SEMINAR
 → CRITIQUE
 → EXPERIMENT
 → RESULT
 → EVALUATION
 → HUMAN_REVIEW
 → REVISION
 → NEW_HYPOTHESIS
```

## Seminar ontology

```text
SEMINAR
├── Student
├── Theory_Senior
├── NLP_Senior
├── Cognitive_Science_Senior
├── Statistics_Senior
├── Comedy_Domain_Senior
├── Experimental_Senior
└── Professor
```

Each critic produces:

```text
Observation
 → Objection
 → Evidence
 → Counterargument
 → Decision
```

Decision values:

```text
ACCEPT
REVISE
REJECT
EXPERIMENT_REQUIRED
```

## Human / LLM separation

### LLM layer

English only.
Markdown only.

Contains:

```text
ontology
hypothesis
papers
claims
evidence
research_gap
research_plan
workflow
skills
experiments
results
evaluation_rules
```

### Human layer

Japanese.
Meeting-minutes / HTML oriented.

Contains:

```text
agenda
discussion
objections
decisions
unresolved_questions
action_items
research_history
```

Do not duplicate all internal reasoning into the human record. Summarize the discussion and decisions for human comprehension.

## Research domain ontology: humor

The current domain is computational humor.

```text
WORLD_KNOWLEDGE
  ↓
ORDER
  ↓
PREMISE
  ↓
EXPECTATION
  ↓
EXPECTED / ACTUAL
  ↓
DEVIATION_VECTOR
  ↓
RESOLUTION
  ↓
HUMOR
```

## Versioning

All major research objects are versioned:

```text
Hypothesis_V1
Ontology_V1
Evaluator_V1
Experiment_V1
```

Never silently rewrite a research decision that materially changes the model. Preserve the previous state and record the reason for revision.

## Human oversight

Human intervention is sparse but authoritative at major decision points:

- hypothesis creation or major revision
- ontology changes
- research-plan approval
- experiment approval
- unexpected results
- final interpretation
- paper submission

## Design principle

The Lab should optimize for discovery, criticism, falsification, and explanatory improvement rather than confirmation of the initial hypothesis.

## Future extensibility

The ontology must remain domain-independent above the humor layer. Humor-specific concepts are a domain module under the general Research Lab ontology.

Potential future domains:

```text
Humor
Education
Software Engineering
Creative Writing
Social Interaction
Cognitive Modeling
```
