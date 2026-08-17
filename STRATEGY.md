# android-standups — Research & Development Strategy

## 1. Starting Point

本プロジェクトは、スタンドアップ・コメディを題材に、

> **「なぜ、この言葉・この瞬間が面白いのか」**

を分析可能な構造へ分解し、その知識をAIエージェントによる台本生成へ戻すことを目的とする。

最終目標は「面白い文章を生成すること」ではなく、**笑いの発生機構を説明・測定・再利用できる言語工学的モデル**を作ること。

## 2. Core Hypothesis

### H-001: 笑いは秩序のボーダーの発見器である

人間は暗黙の秩序・規範・期待を形成している。

```text
秩序
  ↓
期待
  ↓
境界
  ↓
逸脱
  ↓
「おかしい」
  ↓
認識可能な逸脱
  ↓
笑い
```

「おかしい」は単なる無秩序ではなく、**何らかの秩序を前提として初めて成立する**と仮定する。

### H-002: 笑いは境界付近で強くなり得る

```text
正常 ───── 境界 ───── 逸脱 ───── 無秩序
             ↑
          仮説領域
```

ただし、この形を事前に正しいと決めない。実験によって検証する。

### H-003: MicroSkillは秩序と期待を操作する

Setup、Misdirection、Incongruity、Exaggeration、Understatement、Punchlineなどは、独立した「技法名」ではなく、**秩序・期待・逸脱を操作する再利用可能なマイクロスキル**として扱う。

## 3. The Comedy Knife

発話を「面白い」と一括判定しない。

```text
発話
 ↓
意味
 ↓
文脈
 ↓
暗黙の秩序
 ↓
期待
 ↓
逸脱
 ↓
ボーダー距離
 ↓
Mechanism
 ↓
MicroSkill
 ↓
Modality
 ↓
Audience Reaction
```

この分解器を**Comedy Knife（笑いのナイフ）**と呼ぶ。

目的は評価ではなく、原因候補を切り分けること。

## 4. Modality

笑いをジャンルだけで分類しない。

```text
verbal
semantic
social
physical
bodily
innocence
absurd
observational
insult
surprise
character
situational
```

例：

```text
おなら
→ bodily + norm_violation + surprise

転ぶ
→ physical + anticipation + failure

毒舌
→ verbal/social + status_violation + incongruity

赤ちゃんの笑い
→ innocence + unexpected_behavior + recognition
```

ModalityとMicroSkillを分離し、タグ系列として記録する。

## 5. Tag Sequence

単独タグではなく、笑いの生成過程を系列として記録する。

```text
setup
→ expectation
→ misdirection
→ violation
→ punchline
→ reaction
```

別の例：

```text
observation
→ literal_interpretation
→ reframing
→ incongruity
→ recognition
→ laughter
```

## 6. Stand-up

一人の話者が観客の期待を制御するモデル。

```text
Speaker
 ↓
Setup
 ↓
Expectation
 ↓
Misdirection
 ↓
Punchline
 ↓
Audience
```

## 7. Manzai

漫才では相方そのものがComedy Engineの一部になる。

```text
A
 ↓
B's interpretation
 ↓
Correction / Amplification
 ↓
A
 ↓
Audience
```

ボケ・ツッコミを人格ではなく機能として分析する。

```text
Boke
 ├─ expectation_violation
 ├─ misinterpretation
 ├─ exaggeration
 ├─ literal_interpretation
 └─ absurdity

Tsukkomi
 ├─ error_detection
 ├─ reality_check
 ├─ expectation_restoration
 ├─ labeling
 ├─ correction
 └─ amplification
```

仮説：ツッコミは「訂正」だけではなく、観客が逸脱を認識するための**メタ認知的補助装置**として働く場合がある。

## 8. Android × Human

アンドロイドと人間の漫才を研究用の実演形式として利用する。

```text
Human
 ├─ emotion
 ├─ intuition
 ├─ action
 └─ social convention

Android
 ├─ observation
 ├─ logic
 ├─ classification
 ├─ optimization
 └─ literal interpretation
```

非対称性そのものを笑いの素材にする。

### Human → Android

```text
Human behavior
 ↓
Android analysis
 ↓
unexpected logical conclusion
 ↓
Human reaction
 ↓
Audience laughter
```

### Android → Human

```text
Android statement
 ↓
Human interpretation
 ↓
Tsukkomi
 ↓
Audience laughter
```

## 9. Phase Strategy

### Phase 1 — Script

顔・身振り・声などを混ぜない。

```text
Script
 ↓
Ontology
 ↓
MicroSkill
 ↓
Comedy Knife
 ↓
Human Evaluation
```

目的：**言葉だけでどこまで笑いを説明できるか**を測る。

### Phase 2 — Non-Verbal

```text
Script
+
Face
Voice
Timing
Gesture
EyeContact
StageMovement
AudienceReaction
```

ノンバーバルも独立したOntologyとして扱う。

## 10. Agent Strategy

エージェントは分析器であると同時に生成器になる。

```text
Ontology
 ↓
Hypothesis
 ↓
Script Agent
 ↓
Candidate A/B/C
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
```

重要なのは、AIの自己評価だけでループを閉じないこと。

**人間の評価を実験データとしてループに戻す。**

## 11. Quantification

候補ごとに以下を記録する。

```text
order_strength
boundary_distance
expectation_strength
violation_strength
semantic_distance
micro_skill_sequence
funny_score
weird_score
understandable_score
offensive_score
originality_score
```

特に「面白くない」データを捨てない。

失敗は、どの境界モデルが成立しなかったかを示す重要なデータである。

## 12. A/B Testing

同一題材で一つの変数だけを変更する。

```text
A: mild violation
B: strong violation
```

または、

```text
A: exaggeration
B: literal interpretation
C: contrast
```

これによりMicroSkillや境界距離の寄与を比較する。

## 13. Learning

高得点の台本を単純コピーしない。

```text
Result
 ↓
Difference
 ↓
Mechanism
 ↓
MicroSkill performance
 ↓
Hypothesis evidence
 ↓
Agent update
```

成功だけでなく、反例・失敗・評価者間の不一致を保存する。

## 14. Research Dataset

最終的には、以下を実験単位として蓄積する。

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

## 15. Research Question

中心となる問い：

> **人間は、どのような秩序のボーダーの逸脱を「おかしい」と認識し、それをどの条件で「笑い」に変換するのか。**

副問：

1. 境界距離と笑いの強度には関係があるか。
2. MicroSkillの系列は笑いの強度を説明できるか。
3. Modalityによって境界の形は変化するか。
4. スタンドアップと漫才では境界操作がどう違うか。
5. アンドロイドの合理性は、人間の暗黙の秩序を笑いとして可視化できるか。

## 16. Evidence Policy

仮説に合う結果だけを採用しない。

```text
support
counterexample
uncertain
```

を明示する。

観察と解釈も分離する。

```text
Observation:
「パンチライン後に2秒沈黙した」

Interpretation:
「期待を延長した可能性」
```

## 17. Publication Strategy

研究成果は、最終的に以下の構造で論文化する。

```text
Research Question
 ↓
Related Work
 ↓
Hypothesis
 ↓
Ontology
 ↓
Comedy Knife
 ↓
Agent Architecture
 ↓
Experiment
 ↓
Human Evaluation
 ↓
Quantitative Results
 ↓
Counterexamples
 ↓
Discussion
 ↓
Limitations
 ↓
Conclusion
```

大学教員の個人的指導を前提にしない場合でも、研究としては**査読・学位審査・研究倫理・実験設計・先行研究調査**を独立した要件として扱う。

## 18. Long-Term Goal

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
Perform
 ↓
Measure again
```

最終的には、AIが「面白い」と言うのではなく、

> **「この発話では、観客が共有している秩序Aを前提に、MicroSkill Xによって境界Bを越えたため、笑いが発生したと仮説化する」**

ところまで説明できるエージェントを目指す。
