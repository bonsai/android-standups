# Humor Modalities — 総合分析への拡張

## 目的

現在のMicroSkill中心の分析を、より広い**笑いのモダリティ（発生様式）**へ拡張する。

個々の技法をタグとして付与するだけでなく、タグの系列・組み合わせ・発生順を記録し、最終的に「何が、どの経路で笑いを生んだか」を総合分析する。

## 基本モデル

```text
Stimulus
  ↓
Modality
  ↓
MicroSkill sequence
  ↓
Expectation / Emotion / Reaction
  ↓
Laughter
```

## ModalityとMicroSkillを分離する

**Modality** = 笑いの発生様式・入力タイプ

**MicroSkill** = その素材を笑いへ変換する操作

例えば：

```text
転ぶ
  = physical_comedy modality

転倒を予想させる
  = setup

実際に転ぶ
  = punch / physical_release

さらに大げさに転ぶ
  = exaggeration
```

つまり「転ぶ」は技法名ではなく、分析対象となる**笑いの素材・発生様式**として扱える。

## 初期Modality taxonomy

### 1. Innocent / Baby Comedy

```text
baby_laughter
baby_behavior
innocent_reaction
naive_observation
```

特徴仮説：

- 無意識性
- 素朴さ
- 予測不能性
- 観察者との認識差

### 2. Bodily Comedy

```text
fart
burp
fall
slapstick
awkward_movement
physical_failure
```

特徴仮説：

- 身体性
- 即時性
- 社会規範からの逸脱
- 因果関係の分かりやすさ

### 3. Verbal Comedy

```text
wordplay
pun
misunderstanding
literal_interpretation
insult
sarcasm
absurd_statement
```

### 4. Social Comedy

```text
social_awkwardness
status_violation
embarrassment
hypocrisy
norm_violation
relationship_conflict
```

### 5. Character / Persona Comedy

```text
character_contrast
persona_failure
expert_failure
naive_person
outsider
android_vs_human
```

### 6. Cognitive Comedy

```text
incongruity
surprise
reversal
misdirection
false_assumption
category_error
literal_logic
```

### 7. Observational Comedy

```text
daily_life
recognition
common_experience
behavior_observation
social_pattern
```

### 8. Absurd / Surreal Comedy

```text
absurdity
impossible_situation
non_sequitur
scale_distortion
reality_break
```

## 「毒を吐く」の扱い

毒舌・侮辱的発言は、単一の笑い技法ではなく、複数のModalityを持ち得る。

```text
insult
 + status_violation
 + surprise
 + target_selection
 + exaggeration
```

重要なのは、**対象・文脈・関係性・強度を別々に記録すること**。

```text
target
relationship
intensity
intent
context
mechanism
```

「毒舌だから面白い」と単純化しない。

## Tag Sequence

笑いを単一タグではなく**タグの系列**として保存する。

例：

```text
setup
→ expectation
→ misdirection
→ literal_interpretation
→ punchline
→ tag
```

身体ギャグ：

```text
anticipation
→ physical_action
→ failure
→ surprise
→ audience_reaction
```

毒舌：

```text
observation
→ target_identification
→ expectation
→ status_violation
→ insult
→ reaction
```

アンドロイド漫才：

```text
human_statement
→ android_analysis
→ literal_interpretation
→ logical_conclusion
→ human_reaction
→ escalation
```

## Sequence analysis

将来的にはタグ系列そのものを分析対象とする。

```text
Tag A
  ↓
Tag B
  ↓
Tag C
  ↓
Laughter
```

これにより、単一技法の頻度ではなく、

- どの技法が前に来るか
- どの組み合わせが多いか
- どの順序でPunchlineに到達するか
- どの系列が強い反応と相関するか

を調べる。

## 総合分析モデル

```text
                ┌─ verbal
                ├─ physical
Stimulus ───────┼─ social
                ├─ cognitive
                ├─ character
                └─ observational
                         ↓
                    Modality
                         ↓
                  MicroSkill Chain
                         ↓
              Expectation / Incongruity
                         ↓
                    Reaction
                         ↓
                     Laughter
```

## 赤ちゃん・おなら・転ぶ・毒舌の共通分析

一見まったく違う素材でも、同じ抽象構造に写像できる可能性がある。

```text
素材
 ↓
期待
 ↓
逸脱
 ↓
認識
 ↓
反応
```

例：

```text
赤ちゃん
期待：無邪気な反応
逸脱：予想外の行動

おなら
期待：社会的に抑制される身体現象
逸脱：発生 / 公開

転ぶ
期待：正常な身体運動
逸脱：失敗・予測外の動作

毒舌
期待：社会的に許容される会話
逸脱：直接的な評価・攻撃
```

ただし、これは**共通構造の仮説**であり、実データによって検証する。

## 将来の統合Ontology

```text
Comedy Ontology
│
├─ Stimulus
│   ├─ verbal
│   ├─ physical
│   ├─ social
│   ├─ cognitive
│   └─ character
│
├─ Modality
│
├─ Expectation
│
├─ Mechanism
│
├─ MicroSkill
│
├─ TagSequence
│
├─ Delivery
│
├─ AudienceReaction
│
└─ LaughterEvent
```

## 最終目標

最終的には、スタンドアップ、漫才、アンドロイド×人間の漫才、身体ギャグ、観察系、毒舌などを同じ分析基盤で比較できるようにする。

```text
作品
 ↓
Segment
 ↓
Modality
 ↓
Tag Sequence
 ↓
Mechanism
 ↓
MicroSkill
 ↓
Delivery
 ↓
Audience Reaction
 ↓
Laughter Model
```

> **笑いを「ジャンル」で分類するのではなく、笑いが発生する構造の系列として分析する。**
