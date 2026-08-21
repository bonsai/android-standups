# RQ01 Java Comedy — Evaluation

## Evaluation target

The generated Java comedy story.

## Human evaluation

Primary signal:

```text
laughed = true | false
```

Optional ratings:

```text
funny: 1..7
surprise: 1..7
understandable: 1..7
originality: 1..7
```

## Structural evaluation

```text
expectation_strength: 1..7
deviation_strength: 1..7
clarity: 1..7
escalation: 1..7
surprise: 1..7
punchline_strength: 1..7
```

## AI evaluation

The AI evaluator may score the same dimensions, but AI scores are evaluator outputs and are not ground truth.

## Primary comparison for RQ01

Compare this integrated-prompt condition against a simple-prompt baseline using the same model, seed, output constraints, and sample size.

## Current observation status

Human reaction data: pending.

AI evaluation data: pending.

MediaPipe physical observation: not used in Phase 1.

→ RQ01b-controlled で baseline vs integrated の対照実験を開始(6 本生成・AI 評価済み)。本 RQ01 生成物は integrated 条件の PoC 標本として位置づけを維持。
