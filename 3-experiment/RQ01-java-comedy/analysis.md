# RQ01 Java Comedy — Analysis

## Research question

Can an integrated prompt containing multiple specialized comedy guidelines improve the quality of LLM-generated comedy compared with a simple prompt?

## Hypothesis

H1: The integrated prompt produces higher comedy quality than the simple-prompt baseline.

H2: Expectation, deviation, interpretability, escalation, reversal, and revision provide measurable contributions to output quality.

## Analysis procedure

1. Compare the integrated-prompt output with the controlled baseline.
2. Compare human laughter rates.
3. Compare optional human ratings.
4. Compare structural scores.
5. Identify disagreement between human and AI evaluation.
6. Identify the weakest beat in the generated story.
7. Record a possible guide revision only when supported by repeated evidence.

## Current analysis

No conclusion is drawn from a single generated story. The current artifact is a PoC specimen and requires controlled repeated samples.

## Expected evidence table

```text
condition | n | laughter_rate | funny_mean | surprise_mean | clarity_mean | punchline_mean
baseline  |   |               |            |               |             |
integrated|   |               |            |               |             |
```

## Failure analysis

Prioritize:

- high AI humor + human no-laugh
- low AI humor + human laugh
- high deviation + low humor
- low deviation + high humor
- high surprise + low humor

## Next step

Run a controlled baseline-vs-integrated experiment with multiple scripts generated from matched seeds.

→ 実施済み: [RQ01b-controlled](../RQ01b-controlled/design.md)。3 シード × 2 条件の 6 本を生成し、構造評価・AI 評価・失敗保全を完了。人間 laughter データは pending。
