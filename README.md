# 문서추출 요약 경진대회 
## 1. BERT 
- 원문에서 요약할 문장을 추출하여 요약하는 방법 
- 데이터 형태 : 추출될 토큰과 추출되지 않을 토큰에 대해 1과 0으로 라벨링하여 학습 
```python
{
  "input_ids": [2, 1618, 7344, 6705, 2132, 5476, 5468, 6116, 1652, 4930, 5030, 6493,...],
  "token_type_ids": [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, ...],
  "attention_mask": [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 0],
  "labels": [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, ...]
}
```
- 모델학습 방법 : NER에서 토큰별 라벨을 분류하는 방법과 같이 추출될 문장 1, 추출되지 않을 문장 0으로 나누어 학습시킴 
- 디렉토리 구성 :
  - checkpoint
    - kobert-extractive.pth
  - data
    - eval_test.jsonl
    - extractive_summary_kobert.csv
    - train_test.jsonl

### 2. TextRank, WordRank
