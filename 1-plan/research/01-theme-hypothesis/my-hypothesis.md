# My Hypothesis

## Status
Working hypotheses. Not established results.

## Core hypothesis

> Humor may arise when a recognizable expectation is violated by a measurable deviation that remains interpretable.

## Strong form

> Humor may function as a detector of the boundary of an established order.

The strong form is a philosophical research hypothesis and must remain falsifiable through operational definitions and experiments.

## Starting model

```text
World Knowledge
    ↓
Order
    ↓
Premise
    ↓
Expectation
    ↓
Expected / Actual
    ↓
Deviation
    ↓
Interpretation / Resolution
    ↓
Humor Response
```

## Main engineering hypothesis

If a system can explicitly represent the expected state and actual state, it may be possible to represent humor-relevant deviation as a structured vector rather than only as a scalar humor score.

## Deviation hypothesis

A useful deviation representation should answer:

- What was expected?
- Why was it expected?
- What actually occurred?
- What changed?
- In which dimension did it change?
- How large is the deviation?
- Can the deviation still be interpreted?
- How is the deviation resolved or reframed?

## Candidate deviation dimensions

```text
semantic
linguistic
logical
contextual
social
role
cultural_convention
emotional
physical
expectation
```

## Important distinction

```text
Unexpected
    ≠
Funny
```

Candidate condition:

```text
Unexpected
+ Recognizable expectation
+ Interpretable deviation
+ Suitable resolution / reframing
→ Humor potential
```

This is a hypothesis, not a universal law.

## Research questions

### RQ1
Can human-perceived humor-relevant deviations be represented explicitly?

### RQ2
Does a structured deviation representation explain human humor judgments better than simple semantic distance?

### RQ3
Can an LLM identify and explain the relevant expectation and deviation reliably?

### RQ4
Can evaluator feedback improve subsequent humor generation?

## Falsification conditions

The hypothesis should be weakened or rejected if:

- deviation cannot be reliably identified by independent annotators;
- structured deviation does not outperform simpler baselines;
- human humor judgments do not correlate with the proposed representation;
- the representation explains only selected comedy forms and fails broadly;
- apparent effects disappear when wording, length, or topic are controlled.

## Example: green apple

```text
Expression: 青りんご
Literal lexical interpretation: blue apple
Japanese conventional interpretation: green apple

Potential deviation:
literal lexical mapping vs world-knowledge convention

Candidate dimensions:
semantic + cultural_convention
```

This is an example of an interpretation mismatch. It is not automatically a joke. Humor must be experimentally established rather than assumed.

## Relation to prior research

Prior work already establishes important parts of the landscape:

- incongruity and resolution;
- semantic/domain distance;
- controlled humorous text editing;
- human humor annotation;
- computational humor generation and explanation;
- LLM judge evaluation.

The proposed contribution is therefore not "incongruity exists". The candidate contribution is an explicit world-knowledge-to-expectation-to-deviation representation and its empirical comparison against existing baselines.

## Research process

```text
Prior Research
    ↓
Seminar Critique
    ↓
Hypothesis
    ↓
Operational Definition
    ↓
Controlled Experiment
    ↓
Human Evaluation
    ↓
LLM Evaluation
    ↓
Error Analysis
    ↓
Hypothesis Revision
    ↓
Versioned Hypothesis
```

## Version policy

This file records the current working hypothesis. Major revisions should be preserved as separate versioned records rather than silently rewriting history.

## Principle

Do not optimize for proving the hypothesis. Optimize for finding where it fails and improving the explanatory model.
