# 笑いの型コレクション (Patterns of Laughter)

## 目的

笑いを生む「型」(繰り返し現れる構造)を、**確度付き**で md にコレクションする。実験のたびに追加・更新していく生きた知識ベース。

型と MicroSkill は別レイヤー。

```text
型 (patterns/)    = 笑いの構造(理論)  …「何がズレたか」
MicroSkill (skills/) = 操作(実装)      …「どう操作したか」
```

## 確度レジェンド

| 確度 | 意味 | 例 |
|------|------|-----|
| **A** | 確立 — 文献で確立され、自プロジェクト実験でも支持・整合する | 不一致-解決 |
| **B** | 実験支持 — 自プロジェクトの実験(RQ01 / RQ01b)のデータで支持される | 開き直り |
| **C** | 単一観測 — 生成物 1 本・評価 1 回での観察のみ | 無知の問い返し |
| **D** | 仮説 — 未検証。類推・予測のみ | (Phase 2 の身体型など) |

## 収集ルール

1. 型は観察(生成物・評価・文献)から抽出し、**必ず証拠を添える**。
2. 確度は証拠の蓄積で更新する。**1 回の観測で上げない**(プロジェクト原理: 1 結果で改訂しない)。
3. 反例が出たら確度を下げ、`反例・限界` セクションに記録する。
4. 失敗分析(failure taxonomy)と対応付ける — 型の単独使用がなぜ弱いのかも記録する。
5. 対応 MicroSkill と相互リンクする。
6. 人間の laughter データが取れるまでは、AI スコアを根拠にした確度は暫定とする。

## 目次

| 型 | 確度 | 対応 MicroSkill | 主な証拠 |
|----|------|------------------|----------|
| **[やぶれ(マスター型)](order-breach.md)** | B | (全型の枠組み) | H-001 + RQ01b deviation/surprise |
| [不一致-解決](incongruity-resolution.md) | A | misdirection, incongruity | 文献確立 + RQ01b deviation/surprise |
| [優越](superiority.md) | A | exaggeration, deadpan | 文献確立 + RQ01 全般 |
| [解放](relief.md) | A | pause, post-punch-silence | 文献確立(身体側は Phase 2) |
| [開き直り](shameless-reversal.md) | B | deadpan, literal-interpretation | RQ01, RQ01b php |
| [欠陥の目的化](defect-as-purpose.md) | B | callback, escalation | RQ01b js/py integrated |
| [エスカレーション・ラダー](escalation-ladder.md) | B | escalation, rule-of-three | RQ01b (escalation +3.4) |
| [期待の反転](expectation-reversal.md) | B | misdirection, callback | RQ01b (punchline +2.3) |
| [具体数字の誇張](numeric-escalation.md) | B | exaggeration | RQ01「30ページ」, RQ01b「3000回」 |
| [無知の問い返し](innocence-loop.md) | C | innocence, literal-interpretation | RQ01「何で作るんですか?」 |
| [タテマエとホンネの交換](surface-vs-real.md) | C | deadpan, understatement | RQ01「会社員の話だ」 |
| [ボケとツッコミ](straight-man-funny-man.md) | C | setup, tag | RQ01/RQ01b の話者構成 |

## 進め方

```text
実験(RQ01c 以降)
  ↓
評価
  ↓
型の抽出(新規) or 既存型の確度更新(証拠追加)
  ↓
failure taxonomy との対応
  ↓
コミット
```

実験のたびにこのループを回し、型コレクションを育てる。
