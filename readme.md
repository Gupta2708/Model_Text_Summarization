# Selection of Optimal Pre-trained Model for Text Summarization Using TOPSIS

## Abstract
The rapid development of transformer-based architectures has resulted in a wide range of pre-trained models for text summarization. Selecting an optimal model requires systematic evaluation across multiple performance criteria. This study employs the **Technique for Order Preference by Similarity to Ideal Solution (TOPSIS)**, a multi-criteria decision-making (MCDM) method, to rank and identify the most suitable pre-trained model for text summarization. The analysis is conducted in accordance with the assignment specification for roll numbers ending with **5**, which corresponds to the text summarization task.

---

## 1. Introduction
Text summarization aims to generate concise and coherent summaries while preserving the key information of the original text. Numerous transformer-based pre-trained models have been proposed, each exhibiting varying performance across different evaluation metrics. Traditional single-metric comparisons are insufficient for comprehensive evaluation. Therefore, this work adopts TOPSIS to integrate multiple criteria and objectively rank candidate models.

---

## 2. Models Considered
The following pre-trained models were selected for evaluation due to their widespread use and relevance in abstractive text summarization:

- `facebook/bart-large-cnn`
- `ARTeLab/it5-summarization-fanpage-64`
- `google/pegasus-xsum`
- `pszemraj/led-large-book-summary`

---

## 3. Evaluation Criteria
Model performance was assessed using five criteria, including both beneficial and non-beneficial attributes:

| Criterion | Description | Nature |
|---------|-------------|--------|
| ROUGE-1 | Unigram overlap between generated and reference summaries | Beneficial |
| ROUGE-2 | Bigram overlap | Beneficial |
| ROUGE-L | Longest common subsequence-based score | Beneficial |
| Loss | Model loss value | Non-beneficial |
| Generation Length | Average length of generated summaries | Non-beneficial |

---

## 4. Weight Assignment and Impact Direction
The relative importance of each criterion was defined through a weighted scheme, ensuring balanced consideration of quality and efficiency metrics.

Weights = [0.25, 0.25, 0.20, 0.15, 0.15]
Impacts = [+1, +1, +1, -1, -1]

## 5. Methodology

This study employs the **Technique for Order Preference by Similarity to Ideal Solution (TOPSIS)** to rank pre-trained text summarization models based on multiple evaluation criteria. TOPSIS is a widely used multi-criteria decision-making (MCDM) approach that selects alternatives closest to the ideal solution and farthest from the negative ideal solution.

## 5.1 Decision Matrix Construction
A decision matrix was constructed using quantitative evaluation metrics (ROUGE-1, ROUGE-2, ROUGE-L, Loss, and Generation Length) obtained for each pre-trained model.

### 5.2 Normalization
Since the evaluation metrics have different units and scales, vector normalization was applied to transform the decision matrix into a normalized form, ensuring comparability across criteria.

### 5.3 Weight Assignment
Each criterion was assigned a weight reflecting its relative importance. ROUGE metrics were given higher weights as they directly represent summarization quality, while loss and generation length were assigned comparatively lower weights.

### 5.4 Ideal Best and Ideal Worst Solutions
- **Ideal Best Solution**: Consists of the maximum values for beneficial criteria and minimum values for non-beneficial criteria.
- **Ideal Worst Solution**: Consists of the minimum values for beneficial criteria and maximum values for non-beneficial criteria.

### 5.5 Distance Measures
The Euclidean distance of each model from the ideal best and ideal worst solutions was calculated.

### 5.6 TOPSIS Score and Ranking
The TOPSIS closeness coefficient was computed for each model. Models were ranked in descending order of their TOPSIS scores, with a higher score indicating better overall performance.

---

## 6. Results

The TOPSIS analysis produced the following ranking of pre-trained text summarization models:

| Rank | Model | TOPSIS Score |
|-----:|------|--------------|
| 1 | facebook/bart-large-cnn | **0.7903** |
| 2 | ARTeLab/it5-summarization-fanpage-64 | 0.7038 |
| 3 | google/pegasus-xsum | 0.3880 |
| 4 | pszemraj/led-large-book-summary | 0.1545 |

### 6.1 Interpretation of Results
The model **facebook/bart-large-cnn** achieved the highest TOPSIS score, indicating that it is closest to the ideal solution when considering all evaluation criteria collectively. Although some models perform well on specific metrics, their overall performance is lower when assessed using a multi-criteria framework.

### 6.2 Key Observation
The results highlight the importance of multi-criteria evaluation in model selection, as reliance on a single metric may not accurately reflect overall performance.

---

## 7. Final Outcome
Based on the TOPSIS-based ranking, **facebook/bart-large-cnn** is identified as the most suitable pre-trained model for text summarization under the defined evaluation criteria and weights.
