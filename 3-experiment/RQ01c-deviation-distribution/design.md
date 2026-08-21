# RQ01c — 分布の山としての笑い評価 (Deviation-Distance Distribution)

## Claim (証明すべき)

> **笑いはズレ距離 d の関数として「分布の山」(逆 U 字)を形成する。**
> 単一の funny/not-funny 判定やスカラー値ではなく、d に対する笑い応答の分布として評価する。

これは H-002「ズレの大きさと笑いには単純な比例ではなく、理解可能性を含む最適領域がある」の操作的表現であり、H-001r「境はやぶれによってのみ発見可能」の「やぶれ距離」軸を直接測定する。

## なぜダジャレ・ギャグか

ダジャレは**二解釈間の意味距離**が、ギャグは**期待と実際の逸脱距離**が、構造として明示的で制御しやすい。

```text
ダジャレ: 文脈が作る解釈A ⇄ パンチの解釈B … d = semantic(A, B)
ギャグ: 期待E → 実際X … d = deviation(X | E)
```

「青りんご」(literal vs conventional)と同じ構造を、連続軸で並べられる。

## 軸の定義: ズレ距離 d

| level | d | ダジャレ(解釈間距離) | ギャグ(期待からの逸脱) |
|-------|-----|----------------------|------------------------|
| 1 | 近接 | 意味が近く、ほぼ普通の文 | 言い換え程度(trivial) |
| 2 | やや遠い | 同音異義だが弱い | 常識の微妙なズレ(mild) |
| 3 | 中距離 | 典型的ダジャレ | 明確な期待の裏切り(moderate) |
| 4 | 遠い | 意味が遠いが繋がる | 強い逸脱、解釈可能(strong) |
| 5 | 極遠 | 無理やり・強引 | 不条理(absurd) |
| 6 | 破綻 | 解釈不能(nonsense) | 解釈不能(uninterpretable) |

## 予測

```text
humor(d): d=1 低(やぶれなし) → 中間で山 → d=5-6 低(別の秩序に見える)
interpretability(d): d とともに単調減少
```

- ダジャレは d=3 付近、ギャグは d=3-4 付近に山(ピーク位置は材料で異なる)
- 分布の**山の位置・幅**が材料ごとの境界(やぶれの最適領域)を特徴づける

## Protocol

1. 各 level につきダジャレ 2 本・ギャグ 2 本(n=2/level/材料)を用意する
2. humor 1..7 と interpretability 1..7 を記録する(AI 自己評価)
3. level 平均を出し、d に対する分布を確認する
4. 山の位置・幅・対称性を記録する
5. 人間の laughter データは pending(Phase 1 最小インターフェース)

## Reproducibility record

```text
experiment_id: RQ01c-deviation-distribution
hypothesis_version: H-002 operationalized / H-001r
generator_version: LLM (same model as RQ01/RQ01b)
evaluator_version: LLM-as-evaluator (same model)
dataset_version: materials-v1 (ダジャレ 12, ギャグ 12)
prompt_version: n/a (materials hand-constructed on deviation axis)
sample_size: 6 levels × 2 items × 2 materials = 24 items
conditions: d = 1..6
human_labels: pending
AI_outputs: recorded in evaluation.md
analysis_version: v1
```

## Limitation

n=2/level は極小。AI 自己評価は ground truth ではない。真の検証は人間の laughter データとサンプル増で実施する。ダジャレの意味距離は主観ラベルであり、埋め込み距離による客観化が今後の課題。
