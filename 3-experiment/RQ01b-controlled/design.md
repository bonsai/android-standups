# RQ01b — Controlled Baseline vs Integrated — Design

## Research question

RQ01 (java-comedy) は単一生成物の PoC だった。RQ01b では、統合プロンプト(Comedy Guide v2)と単純プロンプト(ベースライン)を、**マッチドシードで複数サンプル生成**して比較する。

## Research question

Can an integrated prompt containing multiple specialized comedy guidelines improve the quality of LLM-generated comedy compared with a simple prompt, **across multiple matched seeds**?

## Hypothesis

- H1: integrated 条件は baseline 条件より高い構造スコア(deviation / escalation / surprise / punchline)を出す。
- H2: 構造スコアの向上は humor 評価にも転移するが、understandability との間にトレードオフが観察される可能性がある(解釈可能性は構造の複雑さと競合しうる)。

## Seeds (matched)

RQ01 の `JAVAをこき下ろす` と同型の「こき下ろし」系シード。トピック・長さ・話者構成を揃える。

| id | seed |
|----|------|
| js | JavaScriptをこき下ろす |
| php | PHPをこき下ろす |
| py | Pythonをこき下ろす |

## Conditions

| condition | prompt | guide |
|-----------|--------|-------|
| baseline | 単純プロンプト(シード + 形式指示のみ) | なし |
| integrated | RQ01 prompt と同型(Comedy Guide v2 統合) | v2 |

## Controlled variables

- モデル: 同一 LLM(生成・評価とも)
- 話者構成: 新人/先輩の2人対話
- 出力長: RQ01 生成物と同等(短尺・数往復)
- 形式: 日本語、セリフの連続、地の文なし
- シード形式: `{言語}をこき下ろす`

## Procedure

1. 各シード × 各条件で 1 本ずつ台本を生成する(n = 3 × 2 = 6)。
2. 各出力に構造評価(6 次元, 1..7)と AI 評価(humor / surprise / understandability, 1..7)を付与する。
3. 条件ごとに平均し、期待エビデンステーブルに集約する。
4. 失敗出力は捨てず failure-analysis に保全し、taxonomy で分類する。
5. 人間の laughter データは Phase 1 の最小インターフェースとして将来取得。今回は pending のまま残す。

## Reproducibility record

```text
experiment_id: RQ01b-controlled
hypothesis_version: H1 / H2 (unchanged from RQ01)
generator_version: LLM (same model as RQ01)
evaluator_version: LLM-as-evaluator (same model)
dataset_version: seeds-v1 (js / php / py)
prompt_version: baseline-v1 / integrated-v1 (Comedy Guide v2)
sample_size: 3 seeds × 2 conditions = 6 scripts
conditions: baseline, integrated
human_labels: pending
AI_outputs: recorded in evaluation.md
analysis_version: v1
```

## Limitation

本ランの生成と AI 評価は同一 LLM による自己評価パスである。AI スコアは ground truth ではなく、人間の laughter データが取得されるまでの暫定指標。真の対照実験は、同一モデルに二つのプロンプトテンプレートを渡し、評価者を分離して実施する。
