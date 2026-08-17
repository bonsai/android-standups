# 03 — Humicroedit

## Citation
Hossain, Krumm & Gamon (2019), *President Vows to Cut <Taxes> Hair: Dataset and Analysis of Creative Text Editing for Humorous Headlines*.

## URL
https://aclanthology.org/N19-1012/

## PDF
https://aclanthology.org/N19-1012.pdf

## Dataset
https://www.cs.rochester.edu/u/nhossain/humicroedit.html

## Research role
人間評価付きのユーモアデータセットと、controlled text editingの実験型。

## Core idea
通常のニュース見出しの一部を編集して、ユーモアを生む。15,095例を作成し、各例を複数の人間が評価した。

## Relevance
本プロジェクトの「ズレを少しずつ変えて、人間評価との関係を測る」実験設計に非常に近い。

## Project extension
```text
Original
 → Deviation 0.1
 → Deviation 0.2
 → Deviation 0.3
 → Human preference / funny score
```

## Key lesson
生成結果だけを評価するのではなく、変更量を制御した候補を比較すると、ズレと面白さの関係を実験できる。

## Limitation / gap for this project
単語編集中心のデータを超えて、台本・会話・状況・社会規範など複数の世界知識レイヤーを扱う必要がある。
