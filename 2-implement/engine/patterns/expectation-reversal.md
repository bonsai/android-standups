# 型: 期待の反転 (Expectation Reversal)

## 確度

**B** — 自プロジェクト実験(RQ01b)で支持(punchline +2.3)。Comedy Guide v2 の手順 6(reversal)に対応する。

## 型の説明

最後に提示される情報が、それまでの台本全体の意味を変える。

```text
解釈 A(観客が保持) → 新情報 → 解釈 B(全話を回収)
```

## 典型的な構造

1. 観客に解釈 A を確立させる(例: 新人は頑張っている / サイトはちゃんとしている)
2. 逸脱を積み重ねる
3. 最後の一行で解釈 B を提示する(例: 実は全然ちゃんとしていない / 動いていること自体が目的)
4. 観客は解釈 A のまま過去を振り返り直す

## 実例

- RQ01b integrated-php: 「サイトは休止中です」→「あります。動いてますから」(サイトの意味が反転)
- RQ01b integrated-py: 「インデントを直します」→「直った気がします」(直すことの意味が反転)
- RQ01: 「Write Once, Run Anywhereって……」→「コードの話じゃない。会社員の話だ」(文脈全体が反転)

## 対応 MicroSkill

- misdirection(観客を解釈 A に誘導)
- callback(過去の要素を回収)
- punchline

## 証拠

- RQ01b: punchline が integrated 5.3 vs baseline 3.0(delta +2.3)
- 反転を持つ台本(integrated 3 本)はすべて punchline ≥ 4
- RQ01 の最終行「会社員の話だ」は反転の典型例

## 反例・限界

- 反転が唐突すぎると weak_reversal(解釈 B に辿り着けない)
- 反転を説明すると explained_joke になる。反転は示すだけで説明しない
- 反転の前に十分な解釈 A の確立が必要。序盤が弱いと反転の重みが出ない(no_clear_pattern)

## 次に測ること

- 反転の位置(最終行 vs 前から 2 行目)と punchline スコアの関係
- 反転なし(上昇のみで終了)との対照比較
