# Comedy Ontology

## Purpose

スタンドアップ・コメディのスクリプトを分析するための暫定オントロジー。

**Phase 1ではスクリプトだけを対象とする。**
顔・身振り・声・視線・舞台動作などのノンバーバル情報はPhase 2で扱う。

このファイルは確定した理論ではなく、YouTubeスクリプトを評価しながら更新するためのエージェント用知識モデルである。

## Core entities

```text
Comedy
 ├─ Set
 │   ├─ Premise
 │   ├─ Setup
 │   ├─ Misdirection
 │   ├─ Punchline
 │   ├─ Tag
 │   └─ Callback
 │
 ├─ Observation
 ├─ Topic
 ├─ Character / Persona
 ├─ Expectation
 ├─ Incongruity
 ├─ Mechanism
 ├─ MicroSkill
 ├─ LaughterEvent
 └─ Evaluation
```

## Relations

```text
Observation
  └─ about → Topic

Setup
  └─ creates → Expectation

Misdirection
  └─ redirects → Expectation

Punchline
  └─ violates / transforms → Expectation

Incongruity
  └─ connects → conflicting interpretations

MicroSkill
  └─ operates_on → ComedyElement

Tag
  └─ extends → Punchline

Callback
  └─ references → PreviousElement

Evaluation
  └─ evaluates → ComedyElement

LaughterEvent
  └─ associated_with → ComedyElement
```

## Phase 1: Script ontology

### Premise

観客に共有される前提・題材・状況。

### Setup

観客の予測を形成する情報。

### Expectation

setupから観客が自然に予測すると仮定する意味・展開。

### Misdirection

観客の注意や予測を別方向へ誘導する操作。

### Punchline

期待との差を明示または発生させる主要な笑いの単位。

### Tag

Punchlineの直後に追加される短い笑いの単位。

### Callback

以前に提示した情報を再利用する笑いの単位。

### Incongruity

同時には自然に成立しにくい意味・価値観・分類などを接続する関係。

### Persona

話者が採用する立場・視点。

例：

- human
- android
- AI
- expert
- novice
- outsider
- victim
- observer

### Mechanism

笑いを発生させる構造的メカニズム。

初期候補：

- incongruity
- reversal
- contrast
- exaggeration
- understatement
- literal_interpretation
- analogy
- escalation
- ambiguity
- surprise
- recognition
- absurdity

## MicroSkill ontology

```text
MicroSkill
 ├─ input
 ├─ operation
 ├─ expectation_effect
 ├─ punch_effect
 ├─ prerequisites
 ├─ compatible_mechanisms
 └─ evidence
```

初期マイクロスキル：

```text
setup
punchline
misdirection
contrast
incongruity
exaggeration
understatement
deadpan
pause
callback
tag
escalation
rule_of_three
literal_interpretation
```

## Android-specific ontology

アンドロイド・コメディでは、以下を固有概念候補として扱う。

```text
HumanBehavior
      ↓
MachineObservation
      ↓
LiteralInterpretation
      ↓
LogicalAnalysis
      ↓
UnexpectedConclusion
```

候補概念：

- machine_observation
- literal_interpretation
- optimization_vs_humanity
- logic_vs_emotion
- prediction_vs_free_will
- classification_of_humans
- error_detection
- responsibility_shift
- human_irrationality

## Evaluation ontology

Phase 1では、スクリプトから観測可能な要素だけを評価する。

```text
Evaluation
 ├─ setup_strength
 ├─ expectation_clarity
 ├─ surprise
 ├─ incongruity_strength
 ├─ semantic_distance
 ├─ punchline_clarity
 ├─ compression
 ├─ callback_dependency
 └─ script_explainability
```

数値は最初から正解として固定しない。複数の実スクリプトを分析し、評価軸そのものを検証する。

## Phase 2 boundary

Phase 2で追加する候補：

```text
FacialExpression
Gesture
VoiceProsody
Timing
EyeContact
StageMovement
AudienceReaction
```

Phase 2では、Phase 1で説明できなかった笑いに対する**追加寄与**と、言語要素との**相互作用**を分析する。

## Agent use

エージェントはスクリプトを次の順で処理する。

```text
Script
 ↓
Segmentation
 ↓
Entity extraction
 ↓
Relation extraction
 ↓
Expectation model
 ↓
Mechanism classification
 ↓
MicroSkill classification
 ↓
Evaluation
 ↓
Evidence
 ↓
Ontology update
```

## Principle

> オントロジーは最初から完成させない。
>
> **実データ → 分析 → 反例 → 概念追加・削除 → 再分析**
>
> のループで育てる。
