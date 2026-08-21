# 型: エスカレーション・ラダー (Escalation Ladder)

## 確度

**B** — 自プロジェクト実験(RQ01b)で最も明確に支持された次元(escalation +3.4)。ただし「上昇」そのものは笑いの必要条件ではない。

## 型の説明

逸脱を段階的に極端化し、それぞれの段階が前の段階に接続されたまま上昇していく構造。

```text
逸脱 v1 → 逸脱 v2(より極端) → 逸脱 v3(さらに極端) → 限界
```

## 典型的な構造

1. 秩序からの最初の逸脱(小さく、理解可能)
2. 逸脱を拡大する(同じ軸でより極端に)
3. さらに拡大する(論理的な帰結へ)
4. 限界点に到達する(そこで反転・パンチライン)

## 実例

- RQ01b integrated-php: フレームワークなし → echo → 3000回echo → 入力を受け付けない → クローラーだけが見る → 「サイトは休止中です」
- RQ01b integrated-js: 1行 → 型なし → 本番に聞く → undefined/NaN → 「回ってるように見えてるだけ」
- RQ01: 3行コード → 設計書30ページ → Java用のJava

## 対応 MicroSkill

- escalation
- rule-of-three(3段階の上昇)
- accelerated-delivery(上昇のテンポ)

## 証拠

- RQ01b: escalation が integrated 5.7 vs baseline 2.3(delta +3.4)— 6 次元中最大の差
- baseline は escalation 2.3 で「flat roast」に終わり、humor も低い(3.3)
- エスカレーションを持つ integrated 台本はすべて punchline ≥ 4

## 反例・限界

- 上昇が速すぎ・大きすぎると over_escalation になり、解釈不能になる(uninterpretable_deviation)
- 上昇が前提(秩序)から切断されると、ただの誇張の羅列になる
- 上昇は「何が・何から・どの方向へ」の軸を保つ必要がある(基本モデルの deviation ベクトル)

## 次に測ること

- 上昇の段数(2段 vs 3段 vs 4段)と humor の関係
- 上昇軸の一貫性(同じ軸か、軸が変わるか)と解釈可能性の関係
