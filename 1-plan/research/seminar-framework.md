# Research Seminar Framework

## Purpose

Use a research-seminar dialogue to stress-test prior research, hypotheses, novelty, methods, evaluation, and experimental design before implementation.

This is a research process, not a performance script.

## Human-facing rule

The human record is Japanese meeting minutes. Keep conclusions, objections, decisions, unresolved questions, and action items.

## LLM-facing rule

The implementation layer is English-only Markdown. No Python implementation is required at this stage.

## Seminar roles

### Student
- Presents the paper or hypothesis.
- States the claim precisely.
- Defends the proposed research gap.
- Revises the hypothesis when evidence requires it.

### Theory Senior
Challenges theoretical novelty.

Typical questions:
- Is this already covered by incongruity theory?
- What concept is genuinely new?
- Is the terminology precise?
- What would falsify the theory?

### NLP Senior
Challenges computational validity.

Typical questions:
- Is this an LLM artifact?
- Does the representation require an LLM?
- Can the proposed ontology be operationalized?
- Is the baseline strong enough?

### Cognitive Science Senior
Challenges the human interpretation model.

Typical questions:
- Does the mechanism correspond to human cognition?
- Is surprise sufficient to explain humor?
- How does common knowledge affect interpretation?
- Can the model distinguish funny from merely unexpected?

### Statistics Senior
Challenges measurement and inference.

Typical questions:
- What is the dependent variable?
- What is the independent variable?
- What is the baseline?
- What sample size is needed?
- Is the effect statistically identifiable?

### Comedy / Domain Senior
Challenges ecological validity.

Typical questions:
- Is this actually humor?
- Does the mechanism occur in real comedy?
- Does it work in stand-up, manzai, dialogue, and everyday conversation?
- Is the example funny because of the proposed mechanism or something else?

### Experimental Senior
Challenges reproducibility.

Typical questions:
- Can another researcher reproduce this?
- Can deviation be manipulated independently?
- Are annotators blind to the hypothesis?
- Are human and LLM evaluation separated?

### Professor
Acts as final research-quality reviewer.

Checks:
- research question
- novelty
- falsifiability
- operational definitions
- experimental design
- baselines
- evidence
- limitations
- publication value

## Standard seminar sequence

```text
Paper selection
  -> Student summary
  -> Claim extraction
  -> Method inspection
  -> Evidence inspection
  -> Limitation extraction
  -> Theory critique
  -> NLP critique
  -> Cognitive critique
  -> Statistics critique
  -> Comedy/domain critique
  -> Experimental critique
  -> Professor review
  -> Research gap
  -> Hypothesis revision
  -> Experiment proposal
```

## Objection protocol

Every important objection should be converted into one of four states:

```text
ACCEPT
REVISE
REJECT
EXPERIMENT_REQUIRED
```

Do not hide objections. Preserve them as research history.

## Research argument structure

```text
Claim
  -> Evidence
  -> Objection
  -> Counterargument
  -> Decision
  -> Consequence for experiment
```

## Current central hypothesis under review

> Humor may arise when a recognizable expectation is violated by a measurable deviation that remains interpretable.

Stronger philosophical formulation:

> Humor may function as a detector of the boundary of an established order.

The stronger formulation is a hypothesis, not an established result.

## Current research gap candidate

Prior work studies incongruity, resolution, semantic distance, controlled humor editing, human evaluation, humor explanation, and LLM judging.

The project proposes to connect these through an explicit intermediate representation:

```text
World Knowledge
  -> Order
  -> Premise
  -> Expectation
  -> Expected / Actual
  -> Deviation Vector
  -> Resolution
  -> Humor
```

The key question is whether this representation explains human humor judgments better than simpler baselines such as semantic distance alone.

## Human review policy

Human review is sparse and deliberate rather than continuous.

Human reviewers should intervene at:
- major hypothesis changes
- ontology version changes
- experiment design approval
- surprising experimental results
- publication decisions

## Spin-out readiness

Keep the seminar framework research-first for now. Potential future spin-outs may include:
- an educational research-reading system
- an AI research critique assistant
- a humor analysis engine
- a general hypothesis-review workflow

Do not optimize the current repository for commercialization yet. Preserve research traceability first.

## Versioning

Seminar findings may change the ontology, hypothesis, evaluator, or experiment design.

```text
Paper
 -> Seminar
 -> Objection
 -> Revision
 -> Hypothesis vN
 -> Experiment
 -> Result
 -> Seminar
```
