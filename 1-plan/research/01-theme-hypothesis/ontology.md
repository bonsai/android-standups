# Prior Research Ontology

## Purpose

Organize computational humor research by concepts, methods, evaluation, datasets, and unresolved areas.

## Research Ontology

```text
COMPUTATIONAL HUMOR
├── THEORY
│   ├── Incongruity
│   ├── Resolution
│   ├── Script / Domain
│   └── Expectation
├── REPRESENTATION
│   ├── Semantic Domain
│   ├── Script
│   ├── Context
│   ├── Word / Phrase
│   └── Text
├── HUMOR MECHANISM
│   ├── Deviation
│   ├── Incongruity
│   ├── Distance
│   ├── Resolution
│   └── Surprise
├── GENERATION
│   ├── Text Editing
│   ├── Joke Generation
│   ├── LLM Generation
│   └── Creative Generation
├── EXPLANATION
│   ├── Why Funny?
│   ├── Incongruity Explanation
│   └── Resolution Explanation
├── EVALUATION
│   ├── Human Rating
│   ├── Pairwise Preference
│   ├── LLM Judge
│   ├── Humor Score
│   └── Agreement
└── DATASET
    ├── Jokes
    ├── Headlines
    ├── Edited Text
    └── Generated Text
```

## Existing Research vs Project Gap

| Concept | Prior research | Project direction |
|---|---|---|
| Incongruity | established | retain |
| Resolution | established | retain |
| Semantic distance | studied | extend |
| Human evaluation | established | retain as ground truth |
| Controlled deviation | Humicroedit etc. | extend to scripts/dialogue |
| LLM generation | current research | engine |
| LLM explanation | current research | structured explanation |
| World knowledge | partial | explicit model |
| Premise | partial | explicit node |
| Expectation | partial | explicit node |
| Deviation vector | gap | core candidate |
| Ontology-based evaluator | gap | core candidate |
| Human/AI interpretation gap | gap | benchmark candidate |

## Proposed Project Ontology

```text
WORLD KNOWLEDGE
      │
      ├── Entity
      ├── Role
      ├── Relation
      ├── Rule
      ├── Norm
      └── Convention
             ↓
           ORDER
             ↓
          PREMISE
             ↓
        EXPECTATION
             ↓
     ┌───────┴───────┐
     ↓               ↓
 EXPECTED          ACTUAL
     │               │
     └───────┬───────┘
             ↓
      DEVIATION DETECTOR
             ↓
      DEVIATION VECTOR
             ↓
          RESOLUTION
             ↓
            HUMOR
```

## Deviation dimensions

```text
semantic
role
social
logical
contextual
emotional
physical
linguistic
cultural_convention
expectation
```

## Research Hypothesis

> Humor may arise when a recognizable expectation is violated by a measurable deviation that remains interpretable.

The stronger philosophical formulation is retained separately:

> Humor may function as a detector of the boundary of an established order.

This is a hypothesis to support, refute, or revise through experiments.

## Evaluator Position

```text
World Model
  ↓
Ontology
  ↓
Order
  ↓
Premise
  ↓
Expectation
  ↓
Expected / Actual
  ↓
Deviation Vector
  ↓
Resolution
  ↓
Why-Funny Evaluator
```

## Versioning

Ontology is experimental and must evolve through evidence and counterexamples.
