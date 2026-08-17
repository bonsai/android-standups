# Comedy Agent Workflow

## 目的

既存のスタンドアップ・コメディのスクリプトを収集・分解・評価し、笑いの構造をマイクロスキルとして蓄積するためのエージェント・ワークフロー。

**Phase 1 はテキストのみ。** 顔、表情、声、身振り、視線、舞台動作、観客反応などのノンバーバル要素はPhase 2へ持ち越す。

## 全体フロー

```text
Source Discovery
      ↓
Script Acquisition
      ↓
Normalization
      ↓
Segmentation
      ↓
Comedy Element Extraction
      ↓
Expectation Modeling
      ↓
Mechanism Detection
      ↓
MicroSkill Classification
      ↓
Humor Evaluation
      ↓
Evidence Recording
      ↓
Ontology Update
      ↓
Knowledge Base
      ↓
Agent Improvement
```

## 1. Source Discovery

YouTube等から分析対象となるスタンドアップ・コメディを選定する。

記録する基本情報：

```text
source
performer
work_title
language
publication_date
source_url
transcript_source
```

原則として、まず**スクリプト取得可能性**を優先する。

## 2. Script Acquisition

公開されている字幕・トランスクリプト等からテキストを取得する。

取得した原文は分析用データと分離して保存する。

```text
raw script
    ↓
normalized script
```

## 3. Normalization

分析に不要なノイズを除去する。

例：

- 字幕タイムスタンプ
- 重複字幕
- 話者識別ノイズ
- 明らかな文字起こし誤り

ただし、**間・反復・言い直しなど、笑いに関係する可能性のあるテキスト情報は勝手に削除しない。**

## 4. Segmentation

スクリプトを分析単位に分割する。

```text
Set
 ↓
Bit
 ↓
Setup
 ↓
Line
 ↓
Punchline
 ↓
Tag
```

最初から完全自動分類せず、エージェントが仮説を提示し、人間が修正できる構造にする。

## 5. Comedy Element Extraction

ontology.md に定義された概念を抽出する。

主な対象：

```text
Topic
Persona
Observation
Premise
Setup
Expectation
Misdirection
Punchline
Tag
Callback
Incongruity
Mechanism
```

## 6. Expectation Modeling

各ビットについて、

> setupを読んだ観客が次に何を予測すると考えられるか

を明示する。

```text
Setup
 ↓
Expected interpretation
 ↓
Actual interpretation
 ↓
Delta
```

ここでの `Delta` を、笑いの重要な観測値候補とする。

## 7. Mechanism Detection

笑いを生む構造を分類する。

初期候補：

```text
incongruity
reversal
contrast
exaggeration
understatement
literal_interpretation
analogy
escalation
ambiguity
surprise
recognition
absurdity
```

複数のMechanismを同時に付与可能とする。

## 8. MicroSkill Classification

使用された技法をマイクロスキルとして記録する。

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

重要なのは「技法名を付ける」だけでなく、

```text
input
operation
expectation_effect
punch_effect
prerequisites
evidence
```

を残すこと。

## 9. Humor Evaluation

Phase 1では、スクリプトから説明可能な範囲だけを評価する。

初期評価軸：

```text
setup_strength
expectation_clarity
surprise
incongruity_strength
semantic_distance
punchline_clarity
compression
callback_dependency
script_explainability
```

### 割合推定

「言葉が笑いの何%を占めるか」を先に固定しない。

Phase 1では、

> **この笑いがスクリプトだけでどの程度説明可能か**

を `script_explainability` として推定する。

Phase 2でノンバーバル分析を追加し、差分から追加寄与を推定する。

```text
Phase 1 explanation
        ↓
Phase 2 explanation
        ↓
additional nonverbal contribution
```

## 10. Evidence Recording

すべての分類・評価には、可能な限り元スクリプト上の根拠を紐付ける。

```text
claim
 ↓
evidence span
 ↓
mechanism
 ↓
micro-skill
 ↓
evaluation
```

推測と観測事実を分離する。

## 11. Ontology Update

分析によって既存Ontologyに反例や新概念が発生した場合のみ更新候補とする。

```text
existing concept
      ↓
new evidence
      ↓
confirm / modify / split / merge / reject
```

Ontologyを先に固定して、作品を無理に分類しない。

## 12. Knowledge Base

分析結果を再利用可能な知識として保存する。

```text
sources/
analysis/
skills/
ontology/
```

将来的には検索・類似例取得・生成支援に利用する。

## 13. Agent Loop

最終的なエージェントは以下のループを持つ。

```text
Observe
  ↓
Hypothesize
  ↓
Analyze
  ↓
Construct
  ↓
Evaluate
  ↓
Learn
  ↓
Update
  ↓
Observe again
```

AIは思考・分析・分類・提案を担当する。

人間は、対象選択、判断、修正、行動、評価データの提供を担当する。

## 14. Phase 2

Phase 1が十分に蓄積された後に開始する。

追加対象：

```text
FacialExpression
VoiceProsody
Timing
PauseDuration
Gesture
EyeContact
StageMovement
AudienceReaction
```

Phase 2では、Phase 1との差分からノンバーバル要素の寄与と相互作用を分析する。

## 開発原則

1. 最初はスクリプトだけを見る。
2. 仮説と事実を分離する。
3. 笑いを二値評価しない。
4. マイクロスキルを証拠付きで蓄積する。
5. Ontologyは実データによって変化する。
6. Phase 2を先取りしない。
7. AIの分析結果は人間が検証可能であること。
