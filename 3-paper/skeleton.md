# Paper Skeleton

## Title

秩序のボーダーと笑いの発生機構：世界知識・前提・ズレを用いたコメディ分析エージェント

## 1. Research Question

人間は、どのような秩序・前提を構築し、どのようなズレを「おかしい」と認識し、それをどの条件で笑いへ変換するのか。

## 2. Hypotheses

- H-001: 笑いは秩序のボーダーの発見器である。
- H-001r: 境は「やぶれ」(逸脱の出来事)によってのみ発見可能である。やぶれが境界を可視化し、笑いが発見をマークする。
- H-002: ズレの大きさと笑いには単純な比例ではなく、理解可能性を含む最適領域がある。
  - **H-002o (分布の山): 笑いはズレ距離 d の関数として「分布の山」(逆 U 字)を形成する。単一判定ではなく d に対する分布として評価する。** ← 証明すべき中心主張
- H-003: MicroSkillの系列は笑いの発生を説明・再現する手掛かりになる。

### 分布の山(証明計画)

```text
humor(d)  ∿  逆U字
  ▲          ．
  │        ．   ．
  │      ．       ．
  │    ．           ．
  │  ．               ．
  └─・────・────・────→ d (ズレ距離)
    d=1(近接)  山(d=3〜4)   d=6(破綻)
```

- 材料: ダジャレ(二解釈間の意味距離)とギャグ(期待からの逸脱距離)を d=1..6 で等級化
- 予測: 山の左肩 = trivial_deviation(やぶれなし)、右肩 = uninterpretable_deviation(別の秩序に見える)
- 実験: RQ01c-deviation-distribution(暫定データ: ダジャレ山 d=3 / ギャグ山 d=4, n=2/level, AI 評価。人間データ pending)
- 評価の含意: 山の位置=最適やぶれ距離、山の幅=許容範囲、右肩=解釈可能性の限界(H-001r の境界の操作化)

## 3. Model

World Knowledge → Order → Premise → Expectation → Deviation → Humor

## 4. Why-Funny Evaluator

発話・文脈・前提・期待・実際の出力・ズレ・理解可能性・意外性を分解して評価する。

## 5. Agent Architecture

Hypothesis → Planner → Writer → Analyzer → Evaluator → Critic → Engine Evolution

## 6. Experiments

- RQ01(java-comedy): 統合プロンプトの PoC 標本。失敗出力も保全。
- RQ01b(controlled): 3 マッチドシード × baseline/integrated。統合条件が構造 6 次元で優位(escalation +3.4, punchline +2.3)。understandability は baseline が高くトレードオフ兆候。
- RQ01c(deviation-distribution): ダジャレ・ギャグをズレ距離 d=1..6 で等級化し humor 分布を測定。
  - 暫定: ダジャレ山 d=3 / ギャグ山 d=4(逆 U 字)。人間 laughter データ pending。

A/B比較、人間評価、AI評価、反例分析、世代ごとの仮説更新を行う。

## 7. Results

実験データを蓄積して記述する。支持結果だけでなく失敗・反例・評価者間不一致を含める。

## 8. Discussion

世界知識、暗黙の秩序、境界距離、MicroSkill、Human-AI gapの関係を検討する。

- **分布の山としての評価**: 笑いを単一スカラーでなく、ズレ距離 d に対する分布(山)として捉えると、「最適やぶれ距離」(山の位置)・「許容範囲」(山の幅)・「解釈可能性の限界」(右肩)がそれぞれ境界の操作化になる。H-001r の「境」は d 軸上の分布で定義される。

## 9. Limitations

文化差、個人差、文脈依存性、LLM評価の偏り、笑いの測定誤差を扱う。

## 10. Conclusion

面白さを直接生成するのではなく、秩序と前提を構築し、ズレを発見・測定・説明することで、笑いを人間とAIの双方に伝達可能な工学的知識へ変換する。