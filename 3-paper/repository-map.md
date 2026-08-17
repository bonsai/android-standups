# Repository Map

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

## 原則

- `1-plan` = 仮説・原理・設計
- `2-implement/engine` = LLMが使う実装知識。原則Markdown
- `2-implement/experiments` = 生成物・評価ケース・実験結果
- `3-paper` = 実験から論文化する成果
- ルートは `README.md` を全体地図として維持する

## 進化ループ

```text
PLAN → IMPLEMENT → EXPERIMENT → PAPER
  ↑                         ↓
  └────── hypothesis update ┘
```
