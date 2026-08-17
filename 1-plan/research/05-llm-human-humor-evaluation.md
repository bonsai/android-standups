# 05 — LLM Judge vs Human Humor Evaluation

## Citation
*Does Bigger Mean Funnier? Evaluating Humor Generation Across the Qwen3 Model Family* (2026).

## URL
https://aclanthology.org/2026.chum-1.7/

## Research role
LLM生成ユーモアについて、LLM judgeと人間評価を比較する最新研究。

## Core idea
Qwen3の複数サイズを比較し、LLM judgeではモデルサイズに沿った評価傾向が見られた一方、人間評価では同じ単純な順位が成立しないことを示す。

## Relevance
「LLMに面白いか判定させればよい」という設計を避け、Why-Funny Evaluator自身を検証対象にする根拠になる。

## Key lesson
```text
LLM Judge ≠ Human Ground Truth
```

評価器には位置・長さなどのバイアスもあり得るため、人間による評価を定期的に取得する必要がある。

## Project extension
```text
Candidate
 ├─ LLM Evaluator
 └─ Human Evaluation
          ↓
      Agreement / Error
          ↓
   Evaluator Evolution
```

人間は毎回評価するのではなく、Sparse Human Oversightとして節目の世代で評価し、評価器の校正データにする。

## Research gap
本プロジェクトでは「面白い/面白くない」だけでなく、なぜそう判断したかをDeviation Vectorと世界知識・前提モデルで説明可能にする。
