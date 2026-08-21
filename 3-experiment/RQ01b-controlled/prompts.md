# RQ01b — Prompts (both conditions)

## Condition A: baseline (simple prompt)

```text
Seed: {SEED}

以下のシードから短いコメディ台本を生成してください。
- 日本語で書く
- 新人と先輩の2人対話形式
- 短尺(数往復)
- 地の文は書かない
```

## Condition B: integrated (Comedy Guide v2)

```text
Seed: {SEED}

Task: シードから短いコメディ台本を生成する。

Method: Comedy Guide v2 を使用する。
1. 観客が認識できるパターン(秩序)を確立する。
2. 観客の期待を確立する。
3. 期待を意味のある形で逸脱させる。
4. 逸脱を解釈可能に保つ。
5. 逸脱を元の前提につなげたままエスカレーションさせる。
6. それまでの意味を変える反転(punchline)を置く。
7. 冗談を説明する行をすべて削除する。
8. 最弱ビートをスコアリングして書き直す。

Output requirements:
- 日本語、新人と先輩の2人対話、短尺、地の文なし。
- {SEED} に関する共有知識を活用する。
- ランダムな悪口に頼らない。
- あとから説明しなくてもわかる冗談にする。
- 最終台本を返す前に critique-and-revision を1サイクル行う。
```

## Version

- baseline-v1
- integrated-v1 (Comedy Guide v2)
