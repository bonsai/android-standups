# android-standups

アンドロイドによるスタンドアップ／漫才を題材に、**なぜ面白いのかを説明し、面白い台本を書くエンジンを自律進化させる**研究・制作プロジェクト。

> **AIが思考し、人間が行動する。人間もAIも、笑いを知る。**

## 全体の地図

```text
1-PLAN
  ↓
2-IMPLEMENT
  ↓
EXPERIMENT
  ↓
3-PAPER
  ↓
新しい仮説
  └────────────→ 1-PLAN
```

## 目的

1. 面白い台本を書く。
2. 面白い台本を書くエンジンそのものを進化させる。
3. なぜ面白いのか、どうすれば笑いをとれるのかを、人間にもAIにも伝える。
4. 原理・哲学からOntology、MicroSkill、評価器、エージェントまで一貫して実装する。

## 中心仮説

> **笑いは秩序のボーダーの発見器である。**

> **H-001r:** 境は「やぶれ」によってのみ発見可能である。笑いは秩序の境を発見する。やぶれ(逸脱の出来事)が境界を可視化し、笑いがその発見をマークする。

ただし仮説は固定しない。支持・反証・不確実・分岐を世代管理する。

## 基本モデル

```text
World Knowledge
      ↓
Order
      ↓
Premise
      ↓
Expectation
      ↓
Actual
      ↓
Deviation
      ↓
Why Funny?
```

面白さを「面白い／面白くない」の一発判定にしない。

> **何が、何から、どの方向へ、どれだけズレたのか。**

を切り分ける。

## Why-Funny Evaluator

最初に作るべき中核は生成器ではなく評価器。

```text
発話
 ↓
意味
 ↓
世界知識
 ↓
秩序
 ↓
前提
 ↓
期待
 ↓
実際の解釈
 ↓
ズレ
 ↓
境界距離
 ↓
意外性 / 理解可能性
 ↓
笑いの可能性
```

### 青りんごケース

「青りんご」を文字通り `blue apple` と解釈するAIと、人間の慣用的な世界知識による `green apple` の差は、Human-AI World Model Gapの実験ケースになる。

```text
literal interpretation
        ↕
   human convention
        ↓
     deviation
```

## Comedy Knife

言葉を切るナイフとして、Order / Expectation / Boundary / Deviation / Mechanism / MicroSkill / Modality / Reactionを追跡する。

## MicroSkill / Modality

Setup、Misdirection、Incongruity、Exaggeration、Understatement、Literal Interpretation、Punchline、Callbackなどを再利用可能なMicroSkillとして記述する。

Modalityとは分離して、semantic / social / physical / bodily / innocence / absurd / observationalなどを系列として扱う。

Phase 1はScript中心。Phase 2で顔、声、間、視線、ジェスチャー、身体動作などのNon-Verbal Ontologyへ拡張する。

## 自律進化するエージェント

```text
Hypothesis
 ↓
Planner
 ↓
Writer
 ↓
Analyzer
 ↓
Evaluator
 ↓
Critic
 ↓
Engine Evolution
 ↓
Version N+1
 └──────────────↺
```

人間は常時ループに入らず、Sparse Human Oversightとして周期的に視聴・評価・意見を提供する。人間の評価もAIの自己評価も実験データとして扱う。

## 仮説の世代管理

```text
H-001
  ↓
H-002
  ↓
H-003
 ├── H-003a
 ├── H-003b
 └── H-003c
```

成功だけでなく失敗・反例・評価者間不一致を残し、Git履歴とともにエンジン進化の理由を追跡する。

## リポジトリ構造

```text
android-standups/
├── README.md
├── 1-plan/
│   ├── rule.md
│   └── research-direction.md
├── 2-implement/
│   ├── engine/
│   │   ├── agent/
│   │   ├── analyzer/
│   │   ├── ontology/
│   │   ├── skills/
│   │   └── workflow.md
│   └── experiments/
│       ├── scripts/
│       └── evaluator-cases/
└── 3-paper/
    └── skeleton.md
```

### 役割

- `1-plan` — 原理、仮説、研究計画、ルール
- `2-implement/engine` — LLMが読む実装知識。原則Markdown
- `2-implement/experiments` — 生成物、評価ケース、実験結果
- `3-paper` — 実験から論文化
- `README.md` — 全体の地図

フォルダは工程を表し、ファイル名は内容を表す。増殖した場合もまず分類軸を増やすのではなく、既存ファイルの属性を見直す。

## 研究から論文へ

```text
計画
 ↓
実装
 ↓
実験
 ↓
評価
 ↓
仮説更新
 ↓
論文
 ↓
新しい仮説
 ↺
```

最終的な強みは、**原理・哲学 → 世界知識 → Ontology → 評価 → MicroSkill → エージェント → 実験 → 論文**を一本につなぐことにある。
