# Prior Research Ontology

## Purpose
先行研究を論文単位ではなく、計算ユーモア研究の概念・方法・評価・データ・未解決領域として整理する。

## Research Ontology

```text
COMPUTATIONAL HUMOR
├── THEORY
│   ├── Incongruity
│   ├── Resolution
│   ├── Script / Domain
│   └── Expectation
├── REPRESENTATION
│   ├── Semantic Domain
│   ├── Script
│   ├── Context
│   ├── Word / Phrase
│   └── Text
├── HUMOR MECHANISM
│   ├── Deviation
│   ├── Incongruity
│   ├── Distance
│   ├── Resolution
│   └── Surprise
├── GENERATION
│   ├── Text Editing
│   ├── Joke Generation
│   ├── LLM Generation
│   └── Creative Generation
├── EXPLANATION
│   ├── Why Funny?
│   ├── Incongruity Explanation
│   └── Resolution Explanation
├── EVALUATION
│   ├── Human Rating
│   ├── Pairwise Preference
│   ├── LLM Judge
│   ├── Humor Score
│   └── Agreement
└── DATASET
    ├── Jokes
    ├── Headlines
    ├── Edited Text
    └── Generated Text
```

## Existing Research vs Project Gap

| Concept | Prior research | Project direction |
|---|---|---|
| Incongruity | established | retain |
| Resolution | established | retain |
| Semantic distance | studied | extend |
| Human evaluation | established | retain as ground truth |
| Controlled deviation | Humicroeditなど | extend to scripts/dialogue |
| LLM generation | current research | engine |
| LLM explanation | current research | structured explanation |
| World knowledge | partial | explicit model |
| Premise | partial | explicit node |
| Expectation | partial | explicit node |
| Deviation vector | gap | core candidate |
| Ontology-based evaluator | gap | core candidate |
| Human/AI interpretation gap | gap | benchmark candidate |

## Proposed Project Ontology

```text
WORLD KNOWLEDGE
      │
      ├── Entity
      ├── Role
      ├── Relation
      ├── Rule
      ├── Norm
      └── Convention
             ↓
           ORDER
             ↓
          PREMISE
             ↓
        EXPECTATION
             ↓
     ┌───────┴───────┐
     ↓               ↓
 EXPECTED          ACTUAL
     │               │
     └───────┬───────┘
             ↓
      DEVIATION DETECTOR
             ↓
      DEVIATION VECTOR
             ↓
          RESOLUTION
             ↓
            HUMOR
```

## Deviation dimensions

```text
semantic
role
social
logical
contextual
emotional
physical
linguistic
cultural_convention
expectation
```

## Research Hypothesis

> Humor may arise when a recognizable expectation is violated by a measurable deviation that remains interpretable.

The stronger philosophical hypothesis is retained separately:

> 「笑いは秩序のボーダーの発見器である」

これは結論ではなく、実験で支持・反証・修正する仮説とする。

## Example: 青りんご

```text
Phrase: 青りんご
Literal interpretation: blue apple
Human conventional knowledge: green apple
Mismatch: literal ↔ conventional
Deviation: semantic + cultural convention
Potential effect: surprise / humorous potential
```

## Evaluator Position

```text
World Model
  ↓
Ontology
  ↓
Order
  ↓
Premise
  ↓
Expectation
  ↓
Expected / Actual
  ↓
Deviation Vector
  ↓
Resolution
  ↓
Why-Funny Evaluator
```

## Versioning

Ontology itself is experimental and must evolve:

```text
Ontology v0.1
 → Experiment
 → Missing concept / counterexample
 → Ontology v0.2
 → Experiment
 → Ontology v0.3
```

Do not silently overwrite theoretical concepts. Preserve version history and evidence.
