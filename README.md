# android-standups

アンドロイドによるブラック・スタンドアップコメディを題材に、**笑いを分析・説明・生成・測定するエージェント**を研究する。

> **AIが思考して、人間が行動する。**

## 全体の地図

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

### PLAN — 何を考えるか

問い、仮説、Comedy Ontology、MicroSkill、Comedy Knife、実験設計を定義する。

### IMPLEMENT — どう分析・生成するか

分析・生成エージェントを構築する。

### EXPERIMENT — 実際に何が起きたか

生成した台本、既存作品の分析、人間評価、データ、結果、反例を保存する。

### PAPER — 何が分かったか

実験結果から論文を構成し、結果を次の仮説へ戻す。

## 中心仮説

> **笑いは秩序のボーダーの発見器である。**

人間は暗黙の秩序・規範・期待を形成する。その境界からの認識可能な逸脱が「おかしい」として認識され、条件によって笑いへ変換されるのではないか、という仮説を検証する。

仮説を正しいものとして扱わない。支持・反証・不確実を同じ実験データとして残す。

## Comedy Knife

「面白い／面白くない」で終わらせず、言葉を切り分ける。

```text
発話
 ↓
意味
 ↓
文脈
 ↓
秩序
 ↓
期待
 ↓
逸脱
 ↓
境界距離
 ↓
Mechanism
 ↓
MicroSkill
 ↓
Modality
 ↓
Audience Reaction
```

## Comedy Ontology

笑いを、ジャンルではなく構造として記述する。

```text
Order
Expectation
Boundary
Violation
Mechanism
MicroSkill
Modality
Reaction
```

対象には、スタンドアップ、漫才、身体的な笑い、赤ちゃんの予想外の行動、おなら、転倒、毒舌、アンドロイド×人間などを含める。ただし、対象ごとの差異を実験で検証する。

## MicroSkill

コメディ技法を再利用可能な小さな技能へ分解する。

```text
setup
expectation
misdirection
contrast
incongruity
exaggeration
understatement
literal_interpretation
punchline
callback
escalation
```

Phase 1ではScript中心。Phase 2で顔、声、間、視線、ジェスチャー、身体動作などのNon-Verbal Ontologyを追加する。

## Stand-up / Manzai

スタンドアップでは一人の話者が観客の期待を制御する。

漫才では、ボケとツッコミを人格ではなく機能として分析する。

```text
Boke
 ↓
Expectation Violation
 ↓
Tsukkomi
 ↓
Recognition / Restoration
 ↓
Audience
```

さらに、**Android × Human**を研究用の実演形式として扱う。

```text
Human: emotion / intuition / social convention
Android: logic / classification / literal interpretation
```

この非対称性が、人間社会の暗黙の秩序を可視化できるかを検証する。

## エージェントの研究ループ

```text
Hypothesis
 ↓
Ontology / MicroSkill
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

AI自身の評価だけで閉じず、人間の評価を実験データとしてループへ戻す。

## 研究データ

候補ごとに、例えば以下を記録する。

```text
experiment_id
script_id
hypothesis_id
modality
micro_skill_sequence
order_strength
boundary_distance
expectation_strength
violation_strength
funny_score
understandable_score
originality_score
human_comment
```

**面白くなかった結果も重要なデータである。**

## リポジトリ構造

README以外の研究ドキュメントは原則 `plan/` に置き、生成物・実験結果は `experiments/` に押し込む。構造は小さく保ち、必要になった時点で内部を再構成する。

```text
android-standups/
├── README.md
├── plan/                 # 仮説・設計・Ontology・MicroSkill・論文計画
└── experiments/          # 台本・分析・評価・データ・結果
```

## 開発原則

1. **計画と生成物を分離する。**
2. **既存作品は実験資産として扱う。**
3. **Phase 1はScript、Phase 2はNon-Verbal。**
4. **A/B実験で変数をできるだけ制御する。**
5. **失敗・反例を捨てない。**
6. **観察と解釈を分離する。**
7. **AIの自己評価を最終結果としない。**
8. **実験結果から仮説を更新する。**
9. **論文は結果から書く。**

## 長期目標

```text
Analyze
 ↓
Explain
 ↓
Generate
 ↓
Measure
 ↓
Learn
 ↓
Perform
 ↓
Measure again
```

最終的には、AIが「面白い」と言うだけでなく、**どの秩序を前提に、どの境界を、どのMicroSkillで越えたため笑いが発生したと考えるのか**を説明できるComedy Agentを目指す。

## 地図

- `plan/` — 研究を考える場所
- `experiments/` — 実際に生成・観測・評価する場所
- `README.md` — このプロジェクト全体の地図
