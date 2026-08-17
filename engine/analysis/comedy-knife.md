# Comedy Knife

## Purpose

「面白い」という評価を一括判定せず、発話のどこで秩序が提示され、どこで期待が変化し、どこで逸脱が発生したかを切り分ける分析器。

## Analysis Chain

```text
utterance
 ↓
meaning
 ↓
context
 ↓
order
 ↓
expectation
 ↓
violation
 ↓
boundary_distance
 ↓
mechanism
 ↓
micro_skill
 ↓
modality
 ↓
reaction
```

## Observation / Interpretation

必ず分離する。

```text
Observation: 発話後に評価者のfunny_scoreが低下した
Interpretation: 期待された逸脱が認識されなかった可能性
```

## Questions

1. 何と言ったか
2. 直前に何を期待させたか
3. 通常ならどう解釈するか
4. どこで意味がずれたか
5. どの秩序・規範を前提としたか
6. どの境界を越えたか
7. どのMicroSkillが操作したか
8. どのModalityか
9. 代替表現で笑いは変化するか
10. 人間評価は何を示したか

## Principle

> Comedy Knifeは「面白さ」を説明するためのナイフであり、面白い／面白くないを決めるだけの分類器ではない。
