# Comedy Script Agent Workflow

## 目的

「笑いは秩序のボーダーの発見器である」という仮説を中心に、

**仮説 → 台本生成 → 人間評価 → 数値化 → 学習 → 再生成**

を反復する実験型コメディ・エージェントを構築する。

このシステムの目的は、単に「面白い台本」を生成することではない。

> **なぜその言葉が面白いのかを説明可能な形で記録し、その説明を次の生成へ反映する。**

## Core Loop

```text
Comedy Ontology
      ↓
Hypothesis
      ↓
Script Agent
      ↓
Candidate Scripts
      ↓
Human Evaluation
      ↓
Quantification
      ↓
Analysis
      ↓
Hypothesis Update
      ↓
Script Agent
      ↑          │
      └──────────┘
```

## 1. Hypothesis Layer

生成前に、使用する笑いの仮説を明示する。

例：

```text
order
expectation
boundary
violation
incongruity
recognition
laughter
```

仮説にはIDを付与する。

```text
H-001: 笑いは秩序の境界付近で発生しやすい
H-002: 期待形成後の軽度な逸脱は笑いを生成しやすい
H-003: 理解不能なほど大きな逸脱は笑いを弱める可能性がある
H-004: ツッコミは逸脱箇所の認識を補助する
H-005: アンドロイドの合理性は人間の暗黙の秩序を可視化できる
```

仮説は「正解」として扱わない。

## 2. Script Generation

AgentはOntologyとMicroSkillを参照して台本を生成する。

```text
Topic
 ↓
Target Order
 ↓
Expected Behavior
 ↓
Boundary
 ↓
Violation
 ↓
Mechanism
 ↓
MicroSkill Sequence
 ↓
Script
```

生成結果には、使用した仮説と技法を付与する。

```text
script_id
hypothesis_ids
modality
micro_skills
expected_order
violation_type
predicted_effect
```

## 3. Candidate Generation

一つの完成稿だけを生成しない。

同じ仮説から複数候補を作る。

```text
Hypothesis H-001
       ↓
 ┌─────┼─────┐
 ↓     ↓     ↓
A     B     C
```

候補間で、逸脱の強度・言葉・構造・MicroSkill sequenceを変える。

## 4. Human Evaluation

AI自身を最終評価者にしない。

人間に候補を提示し、評価を収集する。

### 基本評価

```text
funny_score
weird_score
understandable_score
offensive_score
originality_score
```

### 理解に関する評価

```text
expected_meaning
actual_meaning
noticed_violation
```

### 任意の自由記述

```text
why_funny
why_not_funny
what_was_wrong
```

「面白くない」という結果も重要なデータとして保存する。

## 5. Quantification

各Candidateを数値化する。

```text
script_id
hypothesis_id
order_strength
boundary_distance
expectation_strength
violation_strength
semantic_distance
micro_skill_count
funny_score
understandable_score
originality_score
```

Phase 1ではScript中心。

Phase 2ではNon-Verbal Ontologyを追加する。

## 6. Boundary Analysis

中心仮説を検証する。

```text
Funny Score
     ↑
     │             ●
     │          ●     ●
     │       ●           ●
     │    ●                 ●
     │ ●
     └────────────────────────→
       Order  Boundary  Chaos
```

重要なのは、この曲線を**仮定しない**こと。

データが異なる形を示した場合、仮説を変更する。

## 7. Explanation Layer

Agentは「面白い」と判断するだけでなく、理由を構造化する。

```text
Why?
 ↓
Target Order
 ↓
Expectation
 ↓
Violation
 ↓
Mechanism
 ↓
MicroSkill
 ↓
Modality
 ↓
Predicted Reaction
```

### 例

```text
発話：
「人間は健康診断で異常がないと安心し、
異常があると病院に行く。」

Order:
健康を維持する

Violation:
努力と結果の逆説

Mechanism:
incongruity

Persona:
android observer

MicroSkills:
observation
contrast
literal_interpretation
reframing

Predicted effect:
recognition + surprise
```

## 8. Learning Loop

人間評価を次の生成へ反映する。

```text
Generated Script
      ↓
Human Scores
      ↓
Error / Success Analysis
      ↓
MicroSkill performance
      ↓
Hypothesis evidence
      ↓
Agent policy update
```

重要なのは、単純な「高得点台本をコピーする」学習にしないこと。

**どの構造が、どの条件で評価を変化させたのか**を学習する。

## 9. A/B Experiment

同じ題材について一つの要素だけ変更する。

```text
A:
setup + mild violation

B:
setup + strong violation
```

または、

```text
A: literal interpretation
B: exaggeration
C: contrast
```

として比較する。

これによりMicroSkillの寄与を推定する。

## 10. Human-in-the-loop

人間は「AIの教師」ではなく、実験系の評価者として位置付ける。

```text
AI
 ├─ 仮説生成
 ├─ 台本生成
 ├─ 分解
 ├─ 分析
 └─ 再生成

Human
 ├─ 読む / 観る
 ├─ 評価する
 ├─ 違和感を記録する
 └─ 自由記述する
```

## 11. Result Dataset

将来的には以下のようなデータセットを構築する。

```text
experiment_id
script_id
version
hypothesis_id
topic
modality
micro_skill_sequence
order_model
boundary_distance
expectation_delta
violation_type
funny_score
weird_score
understandable_score
offensive_score
originality_score
human_comment
```

## 12. Phase 2: Non-Verbal Loop

Phase 1のテキスト実験が確立した後、動画を追加する。

```text
Phase 1
Script
 ↓
Human Evaluation
 ↓
Model

Phase 2
Script
 +
Face / Voice / Timing / Gesture / Audience
 ↓
Human Evaluation
 ↓
Interaction Model
```

## 13. Android × Human Manzai

研究用の実演形式として、人間とアンドロイドの漫才を利用できる。

### Human

```text
emotion
intuition
action
social convention
```

### Android

```text
observation
logic
classification
optimization
literal interpretation
```

この非対称性そのものをComedy Mechanismとして利用する。

```text
Human statement
      ↓
Android analysis
      ↓
Unexpected logical conclusion
      ↓
Human reaction
      ↓
Audience laughter
```

逆方向も可能。

```text
Android statement
      ↓
Human interpretation
      ↓
Tsukkomi
      ↓
Audience laughter
```

## 14. Research Loop

最終的な研究プロセス：

```text
Hypothesis
 ↓
Experiment Design
 ↓
Generation
 ↓
Human Evaluation
 ↓
Quantification
 ↓
Statistical Analysis
 ↓
Counterexample
 ↓
Hypothesis Revision
 ↓
New Experiment
```

## 15. Paper Generation

十分な実験結果が蓄積したら、研究成果を論文形式に整理する。

```text
Research Question
 ↓
Related Work
 ↓
Hypothesis
 ↓
Ontology
 ↓
Method
 ↓
Experiment
 ↓
Results
 ↓
Counterexamples
 ↓
Discussion
 ↓
Limitations
 ↓
Conclusion
```

「仮説を証明するためのデータ」だけを集めない。

**仮説に反するデータを同等に重要な結果として記録する。**

## Core Principle

> 面白い台本を作ることが目的ではない。
>
> **「なぜ、この言葉が面白いのか」を切り分け、測定し、再現可能な知識へ変換することが目的である。**

その知識を使って生成し、生成結果を再び実験データとして利用する。

```text
Analyze
  ↓
Explain
  ↓
Generate
  ↓
Measure
  ↓
Learn
  ↓
Generate again
```
