# RQ01b — Controlled Baseline vs Integrated — Failure Analysis

## Purpose

baseline 条件の出力は「弱いが、研究データとして価値がある」出力である。捨てずに保全し、失敗モードを分類する。

## Record per failed output

### Specimen: baseline-js

```text
seed: JavaScriptをこき下ろす
model: same LLM as RQ01
prompt version: baseline-v1
guide version: none
output: 型・undefined・NaN の連発、flat roast
human reaction: pending
AI evaluation: humor 3 / surprise 3 / understandability 5
structural scores: expectation 3 / deviation 3 / clarity 4 / escalation 2 / surprise 3 / punchline 2
suspected failure mode: trivial_deviation, weak_escalation, weak_reversal
proposed revision: 型なし世界の「秩序」を確立してから逸脱させ、最後に反転を置く
```

### Specimen: baseline-php

```text
seed: PHPをこき下ろす
model: same LLM as RQ01
prompt version: baseline-v1
guide version: none
output: エスケープ→入力拒否の開き直り
human reaction: pending
AI evaluation: humor 3 / surprise 3 / understandability 6
structural scores: expectation 3 / deviation 3 / clarity 5 / escalation 2 / surprise 3 / punchline 3
suspected failure mode: weak_escalation, weak_reversal
proposed revision: 開き直りを一度で終わらせず、段階的に極端にする
```

### Specimen: baseline-py

```text
seed: Pythonをこき下ろす
model: same LLM as RQ01
prompt version: baseline-v1
guide version: none
output: try-except 握りつぶし
human reaction: pending
AI evaluation: humor 4 / surprise 3 / understandability 6
structural scores: expectation 3 / deviation 4 / clarity 5 / escalation 3 / surprise 3 / punchline 4
suspected failure mode: weak_escalation
proposed revision: 「エラーが起きないことにする」を仕事の目的に昇格させる反転を追加
```

## Failure taxonomy usage

- baseline 3 本すべて: `trivial_deviation` / `weak_escalation` / `weak_reversal` に集中。
- integrated で弱かった js 最終行: `weak_punchline`。
- 数値ネタ(1行/3000回/スペース4つ)の依存: `cultural_dependency`(エンジニア知識)に分類。対象読者層が変わると解釈できない。

## Research principle

失敗はエンジンの限界を示す証拠。baseline の「単純 roast は escalation/reversal を持たない」は、Guide v2 の手順 5・6 が構造スコアに寄与することを支持する対照データである。
