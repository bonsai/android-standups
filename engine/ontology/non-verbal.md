# Non-Verbal Comedy Analysis — Phase 2

## Position

本ドキュメントは、スタンドアップ・コメディにおける**ノンバーバル要素**を分析するためのPhase 2仕様・仮説を記録する。

Phase 1ではスクリプトのみを分析し、Phase 2ではその結果に以下の情報を追加する。

```text
Phase 1
Script
 ↓
Comedy Structure
 ↓
MicroSkill
 ↓
Script Explainability

Phase 2
        +
Face / Voice / Timing / Gesture / Audience
        ↓
Non-Verbal Contribution
        ↓
Interaction Analysis
```

## Analysis targets

### FacialExpression

- 表情の変化
- 真顔 / deadpan
- 笑顔
- 驚き
- 困惑
- 怒り
- 表情と発話内容の不一致

### VoiceProsody

- 声量
- 高低
- 速度
- 抑揚
- 強調
- 声質
- 感情表現

### Timing

- pause
- delay
- acceleration
- deceleration
- punchlineまでの時間
- punchline後の間

### Gesture

- 手振り
- 指差し
- 身体の向き
- 身体動作
- mimicry
- act-out

### EyeContact

- 観客を見る
- 特定方向を見る
- 視線を外す
- 視線と発話の不一致

### StageMovement

- 立ち位置
- 移動
- 接近
- 後退
- 姿勢変化

### AudienceReaction

- laughter
- applause
- silence
- delayed laughter
- overlapping laughter
- reaction intensity

## Phase 2 hypothesis

ノンバーバル要素は、スクリプトそのものとは別に笑いを生成するだけでなく、**Phase 1で形成された期待・ズレ・パンチラインを増幅または弱体化する**可能性がある。

```text
Script Meaning
      ↓
Expectation
      ↓
Punchline
      ↓
+ Non-Verbal Signal
      ↓
Amplification / Modification / Suppression
      ↓
Audience Reaction
```

## Contribution model

Phase 1の `script_explainability` を基準とする。

Phase 2では、単純に「言葉○%、表情○%」とは決めない。

代わりに、以下を推定する。

```text
script_only_effect
nonverbal_only_effect
interaction_effect
```

概念的には：

```text
Total Humor Effect
    ≈
Script Effect
+ Non-Verbal Effect
+ Interaction Effect
```

これは**検証前のモデル**であり、実データによって修正する。

## Interaction

特に重要なのは、ノンバーバルを独立変数として扱わず、スクリプトとの組み合わせを観測すること。

例：

```text
serious line
+
smiling face
=
incongruity amplification
```

```text
absurd line
+
deadpan delivery
=
comic amplification
```

```text
punchline
+
long pause
=
expectation extension
```

## MicroSkill candidates

Phase 2では、以下のノンバーバル・マイクロスキルを候補とする。

```text
deadpan_delivery
facial_contrast
prosodic_emphasis
strategic_pause
accelerated_delivery
delayed_reaction
physical_act_out
character_switch
look_to_audience
look_away
body_contrast
movement_punctuation
silence_after_punch
```

## Evidence

各分析結果には、可能な限り動画上の時間位置を付与する。

```text
video
 ↓
timestamp
 ↓
verbal segment
 ↓
non-verbal observation
 ↓
mechanism
 ↓
micro-skill
 ↓
audience reaction
```

ノンバーバル分析では、観察事実と解釈を分離する。

```text
Observation:
「パンチライン直後に2.1秒沈黙した」

Interpretation:
「沈黙が期待を延長した可能性」
```

## Phase 2 workflow

```text
Video
 ↓
Audio / Visual Segmentation
 ↓
Script Alignment
 ↓
Facial Analysis
 ↓
Prosody Analysis
 ↓
Timing Analysis
 ↓
Gesture Analysis
 ↓
Audience Reaction
 ↓
Phase 1 Alignment
 ↓
Interaction Analysis
 ↓
Contribution Estimation
 ↓
MicroSkill Update
```

## Boundary

Phase 2をPhase 1の代替にはしない。

まずテキストだけでどこまで笑いを説明できるかを確立し、その後にノンバーバル情報を追加する。

> **Phase 1 = 言語構造**
>
> **Phase 2 = 非言語構造＋相互作用**

最終的な目的は、ノンバーバルを単なる「演技情報」としてではなく、**コメディを構成する再利用可能なマイクロスキル**として記述することである。
