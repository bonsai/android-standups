# Generation Output Evaluation Protocol

## Purpose

Evaluate generated comedy outputs and feed failures back into the research engine.

## Experiment principle

The experiment phase evaluates generated artifacts. It does not silently redefine the theory. Theory changes are recorded as hypothesis or theory revisions.

## Core loop

```text
GENERATOR
  ↓
SCRIPT / OUTPUT
  ↓
HUMAN RESPONSE
  ↓
AI EVALUATION
  ↓
PHYSICAL OBSERVATION
  ↓
ANALYSIS
  ↓
FAILURE CASE
  ↓
HYPOTHESIS REVISION
  ↓
GENERATOR VERSION
```

## Human minimum interface

The primary human signal is intentionally minimal:

```text
laughed = true | false
```

Optional:

```text
intensity = 1..5
```

Humans should not be required to explain every reaction. Explanations are collected selectively when they are useful for error analysis.

## Human labels

Keep these concepts separate:

```text
humorousness
amusement
laughter
smile
comprehension
social_laughter
```

A person can find something funny without laughing, or laugh without finding it humorous.

## AI evaluation dimensions

```text
humor
surprise
weirdness
understandability
deviation
interpretability
resolution
timing
originality
```

AI scores are evaluator outputs, not ground truth.

## Physical observation

Physical signals may be collected in Phase 2 using MediaPipe or other observation tools.

```text
facial landmarks
mouth motion
eye motion
posture
movement
temporal response
```

Physical observation must not be treated as proof of humor.

## Controlled evaluation

Whenever possible, generate controlled variants:

```text
baseline
slightly_deviant
deviant
strongly_deviant
uninterpretable
```

Keep topic, length, speaker, and other relevant factors controlled where possible.

## Response dimensions

Record separately:

```text
surprise: 1..7
funny: 1..7
weird: 1..7
understandable: 1..7
```

The minimal experiment may use only the binary human laughter signal. Richer dimensions are added when required by the research question.

## Event alignment

For multimodal experiments, align:

```text
script_segment
trigger
punchline
expected_response_window
human_laughter_event
AI_evaluation
physical_observation
```

## Failure analysis

Prioritize disagreement cases:

```text
AI_funny + human_no_laugh
AI_not_funny + human_laugh
high_deviation + low_humor
low_deviation + high_humor
high_surprise + low_humor
high_humor + low_surprise
```

These cases are more valuable than simply maximizing average score.

## Feedback loop

For each significant failure:

```text
Observed Result
→ Error Classification
→ Possible Cause
→ Existing Hypothesis Check
→ New Evidence
→ Hypothesis Revision Candidate
```

Do not modify the hypothesis merely to fit one result.

## Baselines

Compare the proposed evaluator against simpler alternatives where applicable:

```text
random baseline
human majority baseline
semantic distance
LLM direct humor score
existing humor benchmark
```

## Reproducibility

Every experiment should record:

```text
experiment_id
hypothesis_version
generator_version
evaluator_version
dataset_version
prompt_version
sample_size
conditions
human_labels
AI_outputs
analysis_version
```

## Human oversight

Human review is required for:

- experiment design changes
- interpretation of unexpected results
- major hypothesis revisions
- final claims

Routine generation, scoring, aggregation, and preliminary error analysis may be automated.

## Success criterion

The goal is not merely to maximize a humor score.

The experiment should determine whether the proposed model explains human reactions and whether its failures reveal a better theory of humor.

## Phase progression

### Phase 1 — Script only

Human laughter and textual evaluation.

### Phase 2 — Non-verbal

Add MediaPipe and physical response observation.

### Phase 3 — Multimodal

Combine script, context, language, physical response, timing, and audience reaction.

### Phase 4 — Autonomous evolution

Use validated evaluation signals to iteratively improve the generation engine.
