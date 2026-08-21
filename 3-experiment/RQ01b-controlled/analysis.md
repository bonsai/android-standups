# RQ01b — Controlled Baseline vs Integrated — Analysis

## Research question

Can an integrated prompt containing multiple specialized comedy guidelines improve the quality of LLM-generated comedy compared with a simple prompt, across multiple matched seeds?

## Hypotheses

- H1: integrated 条件は baseline 条件より高い構造スコア(deviation / escalation / surprise / punchline)を出す。
- H2: 構造スコアの向上は humor 評価に転移するが、understandability とトレードオフしうる。

## Result summary

| dimension | baseline mean | integrated mean | delta |
|-----------|---------------|-----------------|-------|
| expectation | 3.0 | 5.0 | +2.0 |
| deviation | 3.3 | 5.3 | +2.0 |
| clarity | 4.7 | 5.0 | +0.3 |
| escalation | 2.3 | 5.7 | +3.4 |
| surprise | 3.0 | 5.3 | +2.3 |
| punchline | 3.0 | 5.3 | +2.3 |
| humor (AI) | 3.3 | 5.7 | +2.4 |
| surprise (AI) | 3.0 | 5.3 | +2.3 |
| understandability (AI) | 5.7 | 5.0 | **−0.7** |

## Interpretation

- H1 は暫定的に支持: 構造 6 次元すべてで integrated > baseline。特に escalation と punchline の差が大きい。Guide v2 の手順 5(escalation)と 6(reversal)が効いている。
- H2 は部分的支持: humor への転移は大きい(+2.4)が、understandability は integrated が低い(−0.7)。複雑な構造(escalation の積み上げ・反転)は解釈コストを上げる。これは「解釈可能性と意外性のトレードオフ」を示唆する仮説改訂候補(H-003 分岐)だが、**n=3・AI 自己評価のみでは結論できない**。
- baseline の強みは clarity と understandability: 構造が単純なぶん理解しやすいが、面白さ(笑いの可能性)には寄与していないよう見える。

## Weakest beats (integrated)

- js integrated: 最終行「動かないところが、明日の仕事です」は punchline として弱い(4/7)。reversal の後に追加の説明感がある。
- 全 integrated に共通: 台本冒頭の「1行/3000回/スペース4つ」の具体数値がパターン確立に寄与しているが、数値の選択は文化的依存(エンジニア知識)が強い。

## AI_human_disagreement candidates

- php baseline: 「でも安全です」の開き直りは笑いとしては成立するが、AI humor 評価は低い(3)。人間なら笑う可能性があり、AI 低評価 + 人間笑いの不一致候補。
- py baseline: 最後の「エラーが出てないことになってるので、出てないんです」は小さな反転がある。AI 評価(4)より人間評価が高くなる不一致候補。

## Next step

1. 人間の laughter データ取得(laughed = true | false)で RQ01b を確定させる。
2. サンプル数を各条件 n≥10 に増やし、評価者を分離(生成 LLM と評価 LLM を別にする)。
3. understandability トレードオフが再現するか確認。再現すれば H2 を H-003 として世代管理し、Guide v2 に「解釈コストの調整」手順を追加する改訂候補を記録する。
