# android-standups Repository Tree

> Repository structure is a living research artifact. Reorganize incrementally; do not mass-rename historical files unless necessary.

```text
android-standups/
├── plan/                    # 計画・研究設計
│   ├── hypotheses.md        # 仮説
│   ├── research-questions.md
│   └── experiment-design.md
│
├── engine/                  # 分析・生成エンジン
│   ├── ontology/            # Comedy Ontology
│   ├── skills/              # MicroSkills（原則1技能=1MD）
│   ├── modalities/          # 笑いの発生様式
│   ├── comedy-knife.md      # 発話を切開する分析モデル
│   ├── manzai-comparison.md # 漫才との比較
│   └── agent-workflow.md    # 生成→評価→更新ループ
│
├── experiments/             # 実験データ
│   ├── scripts/             # 実験用台本
│   ├── datasets/            # 評価データ
│   ├── evaluations/         # 人間評価
│   └── results/             # 集計・分析結果
│
├── paper/                   # 論文
│   ├── paper-skeleton.md
│   ├── figures/
│   └── references/
│
├── STRATEGY.md              # 全体戦略
├── tree.md                  # 本ファイル：構造の設計図
└── README.md
```

## 4段階モデル

```text
PLAN
  ↓
IMPLEMENT
  ↓
EXPERIMENT
  ↓
PAPER
  ↺
```

### PLAN

研究質問、仮説、Ontology、実験設計を定義する。

### IMPLEMENT

Comedy Knife、MicroSkill、Modality、Script Agentを実装する。

### EXPERIMENT

台本生成 → 人間評価 → 数値化 → 分析 → 反例を収集する。

### PAPER

実験結果から論文を構成し、結果から新しい仮説を生む。

## 再構成ルール

1. **既存ファイルを一括renameしない。**
2. 新規ファイルから命名規則を適用する。
3. フォルダは役割を少数に保つ。
4. 詳細な属性はファイル名・Front Matter・Ontologyで管理する。
5. 研究データと論文本文を混在させない。
6. 仮説・実験・結果を追跡可能にする。
7. Phase 1はScript中心、Phase 2でNon-Verbalを追加する。
8. 変更するたびにこのtree.mdを更新する。

## 命名方針

新規ファイルは原則として、内容が検索可能な名前にする。

```text
YYYY-MM-DD-type-title.md
```

ただし、Ontologyや固定的な仕様ファイルなど、安定した論理名が重要なものは無理に日付を付けない。

## 研究の流れ

```text
仮説
 ↓
Ontology
 ↓
MicroSkill
 ↓
Comedy Knife
 ↓
Script Agent
 ↓
Candidate A/B/C
 ↓
Human Evaluation
 ↓
Quantification
 ↓
Counterexample
 ↓
Hypothesis Update
 ↓
再生成
```

## 将来の拡張

```text
experiments/
 ├── youtube/               # 既存YouTubeスクリプト
 ├── standup/
 ├── manzai/
 └── android-human/

engine/
 ├── ontology/
 │   ├── verbal/
 │   ├── non-verbal/
 │   └── interaction/
 └── evaluator/

paper/
 ├── data/
 ├── figures/
 └── references/
```

この拡張は必要になった段階で行う。最初から巨大なディレクトリ構造を作らない。
