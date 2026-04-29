# Selection of Optimal Pre-trained Model for Text Summarization Using TOPSIS

## Abstract

The rapid development of transformer-based architectures has resulted in a wide range of pre-trained models for text summarization. Selecting an optimal model requires systematic evaluation across multiple performance criteria.

This study employs the **Technique for Order Preference by Similarity to Ideal Solution (TOPSIS)**, a multi-criteria decision-making method, to rank and identify the most suitable pre-trained model for text summarization.

The objective of this project is to compare different pre-trained text summarization models using multiple evaluation metrics and determine the best-performing model through TOPSIS-based ranking.

---

## 1. Introduction

Text summarization aims to generate concise and coherent summaries while preserving the key information of the original text.

Many transformer-based pre-trained models are available for summarization tasks. However, these models perform differently across different evaluation metrics such as ROUGE scores, loss, and generation length.

A single metric is not enough to select the best model. Therefore, this project uses TOPSIS to combine multiple criteria and rank the models objectively.

---

## 2. Models Considered

The following pre-trained models were selected for evaluation:

- `facebook/bart-large-cnn`
- `ARTeLab/it5-summarization-fanpage-64`
- `google/pegasus-xsum`
- `pszemraj/led-large-book-summary`

These models were selected because they are relevant to abstractive text summarization and are commonly used for summarization tasks.

---

## 3. Evaluation Criteria

The models were evaluated using five criteria.

| Criterion | Description | Nature |
|----------|-------------|--------|
| ROUGE-1 | Unigram overlap between generated and reference summaries | Beneficial |
| ROUGE-2 | Bigram overlap between generated and reference summaries | Beneficial |
| ROUGE-L | Longest common subsequence-based score | Beneficial |
| Loss | Model loss value | Non-beneficial |
| Generation Length | Average length of generated summaries | Non-beneficial |

Beneficial criteria are those where higher values are better.

Non-beneficial criteria are those where lower values are better.

---

## 4. Weight Assignment and Impact Direction

The following weights were assigned to the evaluation criteria:

```text
Weights = [0.25, 0.25, 0.20, 0.15, 0.15]
```

The corresponding impact directions were:

```text
Impacts = [+1, +1, +1, -1, -1]
```

Explanation:

- ROUGE-1, ROUGE-2, and ROUGE-L are beneficial because higher scores indicate better summarization quality.
- Loss is non-beneficial because lower loss indicates better model performance.
- Generation Length is considered non-beneficial because shorter and more concise summaries are preferred.

---

## 5. Methodology

This project uses **TOPSIS**, which stands for **Technique for Order Preference by Similarity to Ideal Solution**.

TOPSIS ranks alternatives based on their distance from:

- the ideal best solution
- the ideal worst solution

The best alternative is the one closest to the ideal best solution and farthest from the ideal worst solution.

---

### 5.1 Decision Matrix Construction

A decision matrix was created using the evaluation values of each model across the selected criteria:

- ROUGE-1
- ROUGE-2
- ROUGE-L
- Loss
- Generation Length

Each row represents a model, and each column represents an evaluation criterion.

---

### 5.2 Normalization

Since all criteria have different scales, vector normalization was applied to convert the decision matrix into a normalized matrix.

This ensures that all criteria can be compared fairly.

---

### 5.3 Weighted Normalized Matrix

After normalization, each criterion was multiplied by its assigned weight.

This gives more importance to criteria that are more relevant to summarization quality.

---

### 5.4 Ideal Best and Ideal Worst Solutions

For each criterion:

- For beneficial criteria, the maximum value is selected as the ideal best.
- For non-beneficial criteria, the minimum value is selected as the ideal best.

Similarly:

- For beneficial criteria, the minimum value is selected as the ideal worst.
- For non-beneficial criteria, the maximum value is selected as the ideal worst.

---

### 5.5 Distance Calculation

The Euclidean distance of each model from the ideal best and ideal worst solutions was calculated.

---

### 5.6 TOPSIS Score and Ranking

The TOPSIS score was calculated using the closeness coefficient.

Models were ranked in descending order of their TOPSIS scores.

The model with the highest TOPSIS score was ranked first.

---

## 6. Results

The TOPSIS analysis produced the following ranking of pre-trained text summarization models:

| Rank | Model | TOPSIS Score |
|-----:|-------|--------------|
| 1 | `facebook/bart-large-cnn` | **0.7903** |
| 2 | `ARTeLab/it5-summarization-fanpage-64` | 0.7038 |
| 3 | `google/pegasus-xsum` | 0.3880 |
| 4 | `pszemraj/led-large-book-summary` | 0.1545 |

---

## 7. Interpretation of Results

The model `facebook/bart-large-cnn` achieved the highest TOPSIS score of **0.7903**.

This means it is closest to the ideal solution when all evaluation criteria are considered together.

Although other models may perform well on some individual metrics, their overall performance is lower when evaluated using the multi-criteria TOPSIS method.

---

## 8. Key Observation

The results show that multi-criteria evaluation is more reliable than using only one metric.

A model may perform well on ROUGE scores but may have higher loss or longer generation length. TOPSIS helps balance all these factors and provides a more complete ranking.

---

## 9. Final Outcome

Based on the TOPSIS-based ranking, the best pre-trained model for text summarization is:

```text
facebook/bart-large-cnn
```

It achieved the highest TOPSIS score and Rank 1 among the selected models.

---

## 10. TOPSIS Package Used

The TOPSIS calculations can be performed using the Python package developed for this assignment:

**Package Name:** `Topsis-Vaibhav-102316130`

**PyPI Link:**  
[https://pypi.org/project/Topsis-Vaibhav-102316130/](https://pypi.org/project/Topsis-Vaibhav-102316130/)

Install using:

```bash
pip install Topsis-Vaibhav-102316130
```

Run using:

```bash
python -m topsis_vaibhav_102316130.topsis data.csv "0.25,0.25,0.20,0.15,0.15" "+,+,+,-,-" output-result.csv
```

---

## 11. Conclusion

This project successfully applies the TOPSIS method to select the most suitable pre-trained model for text summarization.

Using multiple evaluation criteria, the analysis identifies `facebook/bart-large-cnn` as the best-performing model.

The project demonstrates how TOPSIS can be used as an effective decision-making technique for machine learning model selection.

---

## Author

**Vaibhav Gupta**  
**Roll Number:** 102316130  
