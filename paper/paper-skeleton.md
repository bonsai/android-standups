# 笑いは秩序のボーダーの発見器である

## ― 言語マイクロスキルと人間評価によるコメディ生成・分析エージェントの試論 ―

> **Paper Skeleton / Working Draft**
>
> 本稿は現時点では研究計画・仮説段階であり、実験結果は未確定である。

---

## Abstract

### 背景

人間は「普通」「自然」「適切」といった暗黙の秩序を共有し、その秩序からの逸脱を「おかしい」と認識する。しかし、どのような逸脱が笑いへ変換されるのかを、生成可能な単位まで分解することは容易ではない。

### 目的

本研究では、笑いを**秩序とその境界の関係を検出する現象**として捉え、コメディの発話をModality、MicroSkill、Tag Sequence等に分解する分析モデルを提案する。

### 仮説

> **笑いは秩序のボーダーの発見器である。**

すなわち、笑いは単なる無秩序への反応ではなく、観客が共有する秩序・期待を前提として、その境界付近に生じる認識可能な逸脱と関係すると仮定する。

### 方法

スタンドアップ・コメディ、漫才、さらにアンドロイドと人間の対話を対象として、発話をMicroSkillとModalityの系列として記述し、AIエージェントにより台本を生成する。生成物を人間に提示して評価し、数値化した結果を次の生成・仮説更新へ戻すHuman-in-the-loop型実験系を構築する。

### 期待される成果

「面白い／面白くない」の分類にとどまらず、**なぜ特定の言葉が面白いと認識されるのかを説明する言語工学的モデル**を構築する。

---

# 1. Introduction

## 1.1 問題設定

- 「面白い」という評価だけでは生成機構を説明できない
- 同じ言葉でも文脈によって笑いが変化する
- 面白くない例も、秩序と境界を推定するための重要なデータである
- コメディ生成AIには、生成だけでなく分析・評価・説明のループが必要である

## 1.2 研究目的

本研究の目的は、コメディの発話を「笑いのナイフ」によって切り分け、

```text
秩序
→ 期待
→ 境界
→ 逸脱
→ 認識
→ MicroSkill
→ Modality
→ 笑い
```

という構造を実証的に検討することである。

## 1.3 Research Questions

**RQ1:** 人間が共有する秩序と笑いの発生にはどのような関係があるか。

**RQ2:** 秩序からの逸脱の強度と笑いの強度にはどのような関係があるか。

**RQ3:** MicroSkillの系列によって笑いの発生機構を説明できるか。

**RQ4:** Modalityによって「笑いのボーダー」は変化するか。

**RQ5:** スタンドアップと漫才では、期待と逸脱の操作方法はどのように異なるか。

**RQ6:** アンドロイドの論理的・文字通りの解釈は、人間社会の暗黙の秩序を笑いとして可視化できるか。

---

# 2. Related Work

## 2.1 Humor Research

- incongruity
- superiority
- relief
- benign violation
- expectation / surprise
- script-based approaches

## 2.2 Computational Humor

- humor classification
- joke generation
- computational creativity
- LLM-based generation

## 2.3 Dialogue and Performance

- stand-up comedy
- manzai
- boke / tsukkomi
- conversational repair
- audience interaction

## 2.4 LLM Agents

- agentic generation
- evaluation loops
- Human-in-the-loop
- iterative refinement

> ここは実際の先行研究を調査してから記述する。現段階では引用を捏造しない。

---

# 3. Theoretical Framework

## 3.1 Order

人間が暗黙的・明示的に共有する規範、期待、因果、分類、社会的ルール。

## 3.2 Boundary

「正常」と「逸脱」の区別が成立する境界。

## 3.3 Violation

予測・規範・意味・身体・社会的地位等の秩序からの逸脱。

## 3.4 Humor Boundary Hypothesis

```text
Normal
   │
   │
   ├──── Boundary ────┤
   │                   │
   │   recognizable    │
   │     violation     │
   │                   │
   └──────────────→
          Chaos
```

この形状自体は仮説であり、実験によって反証可能とする。

## 3.5 Comedy Knife

発話を以下の層へ分解する。

```text
surface utterance
↓
semantic interpretation
↓
context
↓
order
↓
expectation
↓
violation
↓
boundary distance
↓
mechanism
↓
micro-skill
↓
modality
↓
reaction
```

---

# 4. Comedy Ontology

## 4.1 Modality

候補：

- verbal
- semantic
- observational
- social
- physical
- bodily
- innocence
- absurd
- situational
- character
- insult
- surprise

例：

```text
おなら
→ bodily + norm_violation

転倒
→ physical + failure + surprise

毒舌
→ verbal/social + status_violation

赤ちゃんの予想外の反応
→ innocence + unexpected_behavior
```

## 4.2 MicroSkills

### Phase 1: Script

- setup
- punchline
- misdirection
- contrast
- incongruity
- exaggeration
- understatement
- deadpan
- callback
- tag
- escalation
- rule-of-three
- literal-interpretation

### Phase 2: Non-Verbal

- deadpan-delivery
- facial-contrast
- prosodic-emphasis
- strategic-pause
- post-punch-silence
- accelerated-delivery
- physical-act-out
- character-switch
- look-to-audience
- look-away
- body-contrast
- movement-punctuation

## 4.3 Tag Sequence

単独の技法ではなく、笑いの生成過程を系列として記録する。

```text
setup
→ expectation
→ misdirection
→ violation
→ punchline
→ reaction
```

---

# 5. Stand-up and Manzai

## 5.1 Stand-up

```text
Speaker
→ Audience expectation
→ Misdirection
→ Punchline
→ Audience reaction
```

## 5.2 Manzai

```text
A
→ B interpretation
→ correction/amplification
→ A
→ audience
```

## 5.3 Functional Boke / Tsukkomi

人格ではなく機能としてモデル化する。

### Boke

- expectation violation
- misinterpretation
- exaggeration
- literal interpretation
- absurdity

### Tsukkomi

- error detection
- reality check
- expectation restoration
- labeling
- correction
- amplification

## 5.4 Android × Human Manzai

Androidの合理性・分類・文字通りの解釈と、人間の感情・直感・社会規範の差を笑いの構造として利用する。

---

# 6. Agent Architecture

```text
Ontology
 ↓
Hypothesis
 ↓
Script Agent
 ↓
Candidate A / B / C
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

## 6.1 Hypothesis Layer

仮説IDを付与する。

```text
H-001: 笑いは秩序の境界付近で発生しやすい
H-002: 軽度の認識可能な逸脱は笑いを生成しやすい
H-003: 過大な逸脱は理解不能により笑いを弱める可能性がある
H-004: ツッコミは逸脱の認識を補助する
H-005: Androidの合理性は暗黙の人間秩序を可視化する
```

## 6.2 Generation

同一仮説から複数候補を生成し、変数を制御する。

## 6.3 Explanation

Agentは「面白い」だけではなく、以下を説明する。

```text
Order
→ Expectation
→ Violation
→ Mechanism
→ MicroSkill
→ Modality
→ Predicted Reaction
```

---

# 7. Experimental Design

## 7.1 Phase 1 — Script-only

顔・声・身振りを除外し、言語構造を測定する。

## 7.2 Phase 2 — Non-verbal

顔、声、間、視線、姿勢、ジェスチャー等を追加する。

## 7.3 Human Evaluation

候補を人間に提示する。

### 評価項目

```text
funny_score
weird_score
understandable_score
offensive_score
originality_score
```

自由記述：

```text
why_funny
why_not_funny
what_was_wrong
```

## 7.4 A/B Testing

一つの要因だけ変更する。

```text
A: mild violation
B: strong violation
```

またはMicroSkillを変更する。

## 7.5 Participants

- 人数：未定
- 年齢：記録
- 言語：記録
- コメディ経験：記録
- 評価順序：ランダム化を検討

## 7.6 Ethics

- 人間評価者への説明
- 同意
- 個人情報の最小化
- 攻撃的・差別的素材への配慮
- 評価データの匿名化

---

# 8. Quantitative Analysis

## 8.1 Variables

```text
order_strength
boundary_distance
expectation_strength
violation_strength
semantic_distance
micro_skill_sequence
funny_score
understandable_score
```

## 8.2 Primary Analysis

まず、境界距離と笑い評価の関係を検証する。

## 8.3 Secondary Analysis

- Modality別比較
- MicroSkill別比較
- Stand-up / Manzai比較
- Human / Android比較
- 評価者間差

## 8.4 Negative Results

面白くなかった例を除外しない。

反例を仮説修正に利用する。

---

# 9. Results

> 実験実施後に記述する。

## 9.1 Dataset

## 9.2 Descriptive Statistics

## 9.3 Boundary Distance × Humor

## 9.4 MicroSkill Contribution

## 9.5 Modality Comparison

## 9.6 Stand-up vs Manzai

## 9.7 Android × Human

## 9.8 Counterexamples

---

# 10. Discussion

## 10.1 仮説は支持されたか

## 10.2 笑いのボーダーは単一か

## 10.3 Modalityによる違い

## 10.4 言語と非言語の役割

## 10.5 AIによる笑いの説明可能性

## 10.6 AIによる笑いの生成可能性

## 10.7 人間とAIの役割分担

---

# 11. Limitations

- 「笑い」の主観性
- サンプルサイズ
- 文化差
- 言語差
- 評価者バイアス
- LLMの自己評価バイアス
- Script-only Phaseと実演との差
- 「秩序」の推定誤差

---

# 12. Future Work

- YouTube等の既存スクリプト分析
- 動画によるNon-Verbal分析
- Audience Reactionの自動計測
- Android × Human漫才
- 多言語比較
- 文化圏比較
- リアルタイム台本生成
- Comedy Agentの実演

---

# 13. Conclusion

本研究では、笑いを単なる感情評価ではなく、**共有された秩序とその境界の認識に関係する現象**として捉える。

さらに、Comedy Ontology、MicroSkill、Modality、Comedy Knife、Human-in-the-loop Agentを組み合わせ、

```text
Analyze
→ Explain
→ Generate
→ Measure
→ Learn
→ Generate again
```

という循環型モデルを提案する。

最終的な問いは、

> **人間はどこまでを「普通」とし、その境界を越えた何を「おかしい」と認識し、なぜそれを笑うのか。**

である。

---

# Appendix A. MicroSkill Ontology

`engine/skills/` を参照。

# Appendix B. Experimental Dataset Schema

今後作成。

# Appendix C. Annotation Manual

今後作成。

# Appendix D. Scripts

実験台本をバージョン管理する。

# Appendix E. Reproducibility

実験条件、プロンプト、モデル、温度、評価方法、データセットのバージョンを保存する。
