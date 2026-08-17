# Research Direction — Conversation-Derived Design

## Purpose

The project has three connected goals:

1. **Write funny scripts.**
2. **Evolve the engine that writes funny scripts.**
3. **Make the principles of humor understandable to both humans and AI.**

The project therefore spans philosophy → world knowledge → ontology → engineering → experiments → paper.

## Core hypothesis

> **Humor is a detector of the boundary of order.**

The working hypothesis is not treated as truth. Each generation of experiments may support, refute, branch, or revise it.

## Core mechanism

```text
World Knowledge
      ↓
Order
      ↓
Premise
      ↓
Expectation
      ↓
Actual Event / Utterance
      ↓
Deviation Detection
      ↓
Why Funny?
```

The engineering question is:

> **What is deviating from what, in which direction, and by how much?**

## World Knowledge Model

Before evaluating a deviation, the system needs a model of what is normally expected.

```text
World Knowledge
      ↓
Ontology
      ↓
Context
      ↓
Expected State
```

The ontology should represent entities, roles, relations, properties, rules, context, events, states, and expectations.

## Example: 「青りんご」

A literal interpretation can map:

```text
青 + りんご → blue apple
```

while human world knowledge may interpret the phrase as:

```text
青りんご → green apple
```

The interesting event is not simply an error. It exposes a mismatch between literal language interpretation and human conventional knowledge.

This becomes a useful benchmark for the evaluator:

```text
Human World Model
        ↕
   Interpretation Gap
        ↕
AI / Literal Model
```

## Why-Funny Evaluator

The first implementation target should be the evaluator, not the writer.

For every candidate, ask:

1. What happened?
2. What order is assumed?
3. What premise is constructed?
4. What would a human normally expect?
5. What did the candidate actually produce?
6. What is the deviation?
7. What type of deviation is it?
8. How large is the deviation?
9. Is the deviation recognizable?
10. Is it surprising?
11. Is it understandable?
12. Why might the deviation become humorous?

## Deviation model

Represent deviation as a vector rather than one score.

```yaml
Deviation:
  semantic: 0.00
  social: 0.00
  role: 0.00
  logical: 0.00
  contextual: 0.00
  emotional: 0.00
  physical: 0.00
  linguistic: 0.00
```

The project should investigate whether humor has an optimal deviation region rather than assuming that larger deviation means more humor.

```text
small deviation     → unnoticed / boring
moderate deviation  → "そう来たか" / potentially funny
large deviation     → incomprehensible / potentially not funny
```

## Comedy Knife

The evaluator is a knife for cutting a funny utterance into observable components:

```text
Utterance
 ↓
Meaning
 ↓
Context
 ↓
Order
 ↓
Premise
 ↓
Expectation
 ↓
Boundary
 ↓
Deviation
 ↓
MicroSkill
 ↓
Reaction
```

## Autonomous evolution

The system should operate as an agent graph:

```text
Hypothesis
 ↓
Planner
 ↓
Writer
 ↓
Analyzer
 ↓
Evaluator
 ↓
Critic
 ↓
Engine Evolution
 ↓
New Version
 └────────────→ Hypothesis
```

Humans do not need to watch and evaluate every generation. Human participation is sparse oversight: periodic viewing, evaluation, and opinion become evidence rather than continuous control.

## Versioned hypothesis evolution

Hypotheses must never simply be overwritten.

```text
H-001
  ↓
H-002
  ↓
H-003
 ├── H-003a
 ├── H-003b
 └── H-003c
```

Every generation should retain parent, evidence, counterexamples, status, and confidence so that the evolution of the engine is reproducible.

## Human + AI teaching goal

The system should answer both:

> **Why is this funny?**

and

> **How can I make something like this funny?**

The same explanation should be convertible into human-readable principles and machine-readable Markdown rules.

## Research loop

```text
PLAN
  ↓
IMPLEMENT
  ├── ENGINE (.md rules for LLM)
  └── EXPERIMENTS (generated artifacts and results)
  ↓
PAPER
  ↓
New Hypothesis
  ↺ PLAN
```

The paper is an output of the evolving production/research system, not the primary objective.
