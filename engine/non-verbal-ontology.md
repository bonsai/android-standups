# Non-Verbal Comedy Ontology

## Purpose

スタンドアップ・コメディにおけるノンバーバル要素を、再利用可能な概念・関係・マイクロスキルとして記述するための暫定オントロジー。

Phase 2で使用する。Phase 1のScript Ontologyとは分離し、後から両者の相互作用を接続する。

## Core entities

```text
NonVerbalComedy
 ├─ FacialExpression
 ├─ VoiceProsody
 ├─ Timing
 ├─ Gesture
 ├─ EyeContact
 ├─ StageMovement
 ├─ AudienceReaction
 ├─ PhysicalActOut
 ├─ CharacterSwitch
 └─ Silence
```

## FacialExpression

```text
FacialExpression
 ├─ neutral
 ├─ smile
 ├─ surprise
 ├─ confusion
 ├─ anger
 ├─ fear
 ├─ sadness
 └─ expression_contrast
```

重要な関係：

```text
FacialExpression
  └─ contrasts_with → VerbalMeaning
```

## VoiceProsody

```text
VoiceProsody
 ├─ volume
 ├─ pitch
 ├─ speed
 ├─ emphasis
 ├─ intonation
 ├─ voice_quality
 └─ emotional_delivery
```

## Timing

```text
Timing
 ├─ pause
 ├─ delay
 ├─ acceleration
 ├─ deceleration
 ├─ punchline_timing
 └─ post_punch_silence
```

## Gesture

```text
Gesture
 ├─ hand_movement
 ├─ pointing
 ├─ miming
 ├─ body_pose
 ├─ imitation
 └─ physical_emphasis
```

## EyeContact

```text
EyeContact
 ├─ audience_gaze
 ├─ gaze_away
 ├─ directional_gaze
 └─ gaze_contrast
```

## StageMovement

```text
StageMovement
 ├─ approach
 ├─ retreat
 ├─ lateral_movement
 ├─ position_change
 └─ posture_change
```

## AudienceReaction

```text
AudienceReaction
 ├─ laughter
 ├─ applause
 ├─ silence
 ├─ delayed_laughter
 ├─ overlapping_laughter
 └─ reaction_intensity
```

AudienceReactionは「笑いの原因」と断定せず、観測された反応として記録する。

## Relations

```text
NonVerbalElement
  ├─ occurs_at → Timestamp
  ├─ accompanies → ScriptSegment
  ├─ modifies → Expectation
  ├─ amplifies → Punchline
  ├─ contrasts_with → VerbalMeaning
  ├─ reinforces → Persona
  └─ correlates_with → AudienceReaction
```

相関と因果を区別する。

## Non-Verbal Mechanisms

初期候補：

```text
expression_incongruity
prosodic_incongruity
timing_extension
expectation_delay
physical_exaggeration
character_embodiment
silence_amplification
attention_redirection
verbal_nonverbal_contrast
reaction_alignment
reaction_mismatch
```

## Non-Verbal MicroSkills

```text
deadpan_delivery
facial_contrast
prosodic_emphasis
strategic_pause
post_punch_silence
accelerated_delivery
delayed_delivery
physical_act_out
character_switch
look_to_audience
look_away
body_contrast
movement_punctuation
```

各MicroSkillは以下の属性を持つ。

```text
name
input
operation
expectation_effect
comic_effect
prerequisites
evidence
confidence
```

## Interaction with Script Ontology

ノンバーバルを独立した笑いとしてだけでなく、Script Ontologyとの相互作用として記述する。

```text
Setup
  ↓
Expectation
  ↓
Punchline
  ↓
Non-Verbal Signal
  ↓
Amplification / Modification / Suppression
  ↓
AudienceReaction
```

代表的な関係：

```text
serious_verbal
 + smile
 → expression_incongruity

absurd_verbal
 + deadpan
 → deadpan_amplification

punchline
 + long_pause
 → expectation_extension

verbal_setup
 + physical_act_out
 → embodied_visualization
```

## Contribution model

Phase 2では、次の3要素を区別する。

```text
script_effect
nonverbal_effect
interaction_effect
```

```text
Total observed effect
 ≈
script effect
+ non-verbal effect
+ interaction effect
```

これは仮説モデルであり、固定された因果モデルではない。

## Evidence model

ノンバーバル分析では、動画上の時間位置を一次的な証拠単位とする。

```text
Video
 ↓
Timestamp
 ↓
ScriptSegment
 ↓
ObservedNonVerbalElement
 ↓
Mechanism hypothesis
 ↓
MicroSkill
 ↓
AudienceReaction
```

例：

```text
Observation:
00:03:21.4 - 00:03:23.5
パンチライン後に約2.1秒の沈黙

Interpretation:
期待を延長している可能性

Confidence:
medium
```

## Ontology update rule

このオントロジーは固定しない。

```text
Observation
 ↓
Existing Concept
 ↓
Evidence
 ↓
confirm / modify / split / merge / reject
```

新しい概念は、複数の作品で再現されるか、既存概念では説明困難な反例がある場合に追加候補とする。

## Phase boundary

```text
Phase 1
Script Ontology

Phase 2
Non-Verbal Ontology
        +
Script Ontology
        ↓
Interaction Ontology
```

最終的には、言語・非言語・観客反応を統合した**Comedy Ontology**へ発展させる。
