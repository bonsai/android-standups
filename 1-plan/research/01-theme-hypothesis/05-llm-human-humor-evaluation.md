# 05 — LLM Judge vs Human Humor Evaluation

## Citation
*Does Bigger Mean Funnier? Evaluating Humor Generation Across the Qwen3 Model Family* (2026).

## URL
https://aclanthology.org/2026.chum-1.7/

## Research role
Recent comparison of LLM-judge and human evaluation for generated humor.

## Core lesson
LLM judge rankings do not necessarily reproduce human rankings.

```text
LLM Judge ≠ Human Ground Truth
```

## Relevance
The project's evaluator must itself be evaluated. Human evaluation remains an important calibration signal.

## Project extension
```text
Candidate
 ├─ LLM Evaluator
 └─ Human Evaluation
          ↓
      Agreement / Error
          ↓
   Evaluator Evolution
```

Use sparse human oversight at major generations rather than assuming continuous human labeling.

## Research gap
Evaluate not only funny/not-funny judgments but also whether the evaluator can explain its decision using world knowledge, premises, expectations, and deviation vectors.
