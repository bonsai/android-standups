# android-standups — Repository Tree

> 研究プロジェクトの構造そのものを、計画・実装・実験・論文化の流れに合わせて管理する。

```text
android-standups/
├── plan/                         # PLAN：問い・仮説・実験設計
│   ├── hypotheses.md
│   ├── research-questions.md
│   └── experiment-design.md
│
├── engine/                       # IMPLEMENT：分析・生成エンジン
│   ├── agent/
│   │   └── workflow.md           # 仮説→生成→評価→更新
│   ├── analysis/
│   │   └── comedy-knife.md       # 発話を切開する分析器
│   ├── ontology/
│   │   ├── core.md
│   │   ├── humor-modalities.md
│   │   ├── non-verbal-ontology.md
│   │   ├── non-verbal.md
│   │   └── manzai-comparison.md
│   ├── skills/                    # MicroSkill：原則1技能=1MD
│   └── workflow.md                # 既存作品→分析→Ontology更新
│
├── experiments/                  # EXPERIMENT：実験資産
│   └── logs/
│       └── 2026-08-17-human-update.md
│
├── paper/                        # PAPER：論文
│   └── paper-skeleton.md
│
├── STRATEGY.md                   # 全体戦略
├── tree.md                       # 本ファイル：構造の設計図
└── README.md
```

## 4段階

```text
PLAN
  ↓
IMPLEMENT
  ↓
EXPERIMENT
  ↓
PAPER
  ↺ 新しい仮説へ
```

## 再配置方針

- 既存資産は内容を変えず、役割に応じて再配置する。
- 新規ファイルはこの構造に従う。
- 歴史的なファイルを無理にrenameしない。ただし今回の骨格化では明確な重複・役割移動を整理する。
- `plan` は研究判断、`engine` は再利用可能な知識・ロジック、`experiments` は観測データ、`paper` は論文成果とする。
- Phase 1はScript中心。Phase 2でNon-verbalを追加する。

## 研究ループ

```text
仮説
 ↓
Ontology / MicroSkill
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
 ↺
```
