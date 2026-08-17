# Experiment Design

## Phase 1 — Script-only

顔・声・身振り・観客映像を除外し、言語構造を測定する。

```text
Source → Script → Segmentation → Annotation → Generation → Human Evaluation
```

## Phase 2 — Non-verbal

Phase 1のモデルを基準に、声・間・顔・視線・身体・観客反応を追加する。

## A/B Design

同一題材について原則1変数だけ変更する。

- mild vs strong violation
- literal interpretation vs exaggeration
- stand-up vs manzai
- human vs android persona

## Measures

```text
funny_score
weird_score
understandable_score
offensive_score
originality_score
order_strength
expectation_strength
violation_strength
boundary_distance
semantic_distance
```

## Human Evaluation

人間を最終的な評価データ提供者とする。自由記述 `why_funny / why_not_funny / what_was_wrong` を保存する。

## Negative Results

面白くなかった候補、評価者間の不一致、仮説に反する結果を削除しない。

## Reproducibility

実験ID、台本バージョン、仮説ID、プロンプト、モデル、評価条件、データセット版を記録する。
