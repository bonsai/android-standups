# Recap of Lab — 研究室雑談による研究検討

## 今日の雑談

研究室の飲み会のような雑談スタイルで、自分の「笑いの工学」研究を先輩・教授に説明し、研究として成立するかを批判的に検討する。

---

### 学生
「笑いって、秩序のボーダーを発見するものなんじゃないかと思ってまして。」

### 先輩
「待って。それ、incongruity theoryじゃない？」

### 学生
「……確かに。ズレそのものは昔から研究されています。」

### 先輩
「じゃあ、何が新しいの？」

### 学生
「ズレを単なるsemantic distanceとして扱うんじゃなくて、世界知識から秩序・前提・期待を作って、そこからDeviation Vectorとして記述します。」

### 教授
「それなら研究になる可能性はある。ただし、Deviation Vectorを作っただけでは弱い。」

### 学生
「どうすれば？」

### 教授
「人間が面白いと判断することを予測できるか。さらに既存のsemantic distanceより説明力があるか比較しなさい。」

### 先輩
「LLM Judgeだけで評価するなよ。」

### 学生
「人間評価をground truthとして残します。」

### 教授
「よし。実験計画を書いてから実装しよう。」

---

## 研究室会話モデル

```text
Research Papers
      ↓
Research Ontology
      ↓
研究室雑談
      ↓
先輩：先行研究チェック
      ↓
教授：妥当性・新規性チェック
      ↓
学生：仮説修正
      ↓
AI：反論・証拠整理
      ↓
Research Gap
      ↓
Hypothesis vN
      ↓
Experiment Plan
```

## 研究上の意味

研究室雑談は、単なる演出ではなく**仮説の内部査読プロセス**として利用する。

先輩役は「それは既知では？」を担当し、教授役は「その仮説は検証可能か」「実験として成立するか」「何が新規性なのか」を担当する。

AIは先行研究の検索・証拠整理・反論生成・論点整理を担当する。

## Human-in-the-loop

人間は常時評価者ではなく、節目で研究判断を行う。

```text
AI research loop
    ↓
仮説生成
    ↓
批判
    ↓
修正
    ↓
実験
    ↓
結果
    ↓
人間レビュー
    ↓
version up
```

## Current Research Gap

既存研究ではincongruity、semantic distance、resolution、人間評価、LLM judgeなどが研究されている。

本研究では、これらを以下の中間表現で接続することを候補とする。

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
Deviation Vector
 ↓
Resolution
 ↓
Humor
```

## Critical questions

- 「笑いは秩序のボーダーの発見器」という仮説は、既存のincongruity theoryと何が違うか？
- Deviation Vectorはsemantic distanceより何を説明できるか？
- 世界知識・前提・期待をどう操作的に定義するか？
- LLM Judgeと人間評価の不一致をどう扱うか？
- どの実験で仮説を反証できるか？
- 面白さと「単なる意外性」をどう区別するか？

## Status

これは研究結果ではなく、先行研究を踏まえた**研究室雑談形式の検討記録（recap）**である。

次回はこの議論からResearch Questions、仮説、実験条件を具体化する。
