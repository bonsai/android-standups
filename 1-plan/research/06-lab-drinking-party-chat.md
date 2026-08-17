# 06 — 研究室の飲み会の雑談：研究仮説の観察メモ

## Status
雑談から得た仮説。論文の結果・先行研究の事実とは分離して扱う。

## Scene
研究室の飲み会。研究者同士が酒を飲みながら、研究・AI・人間・失敗・日常について雑談している。

## Observation
雑談では、発言そのものよりも「共有されている前提」と「その場で予想される次の発言」から少し外れた発言が笑いを生むことがある。

例：

```text
A「AIに論文を書かせた」
B「じゃあ次は査読もAIにやらせよう」
C「その査読をAIに査読させればいい」
```

最初の発言は通常の報告だが、会話が進むにつれて「AIに仕事を任せる」という秩序が自己増殖し、最後にその構造自体が笑いの対象になる。

## Working hypothesis
笑いは単独の発言に内在するとは限らず、**会話参加者が共有した前提・期待・直前までの文脈に対する局所的なズレ**として発生する。

## Candidate ontology

```text
Conversation
├── Participant
├── Shared Knowledge
├── Local Context
├── Norm
├── Expectation
├── Utterance
├── Deviation
│   ├── semantic
│   ├── contextual
│   ├── role
│   ├── social
│   └── escalation
├── Recognition
└── Humor Response
```

## Important distinction

```text
unexpected ≠ funny

unexpected + interpretable
        ↓
possible humor
```

さらに、会話では「ズレ」だけでなく、ズレを受け取った参加者が意味を理解できること、直前の発言との関係が追えること、過度に説明しなくても共有知識に接続できることが重要だと仮定する。

## Experiment idea
同じ会話の流れに対して、次の発言のDeviationを段階的に操作する。

```text
A: baseline
B: small deviation
C: medium deviation
D: large deviation
E: incoherent
```

人間評価を取得し、Deviationとfunny scoreの関係を見る。

## Relation to project
研究室の飲み会は、自然な会話ユーモアを観察するための仮想的な実験場として使える。

stand-up comedyの一人語りだけでなく、漫才・雑談・人間×アンドロイド会話へ研究対象を拡張する際の仮説候補とする。

## Next step
このメモは実験結果ではない。実際の会話データを収集する場合は、参加者の同意・匿名化・個人情報保護を前提とする。
