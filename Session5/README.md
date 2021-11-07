# TSAI Assignment

## SESSION 5 - TorchText & Advanced Concepts

ASSIGNMENT

1. Look at the given code: <https://colab.research.google.com/drive/1z2N6ipI6n6t1ivprJtugDeqKrCM2NPFy?usp=sharing>
2. Pick any 2 datasets (except AG_NEWS) from torchtext.datasets and train your model on them achieving 50% more accuracy than random prediction.
3. Upload to Github with a proper readme file describing your datasets, and showing your logs as well.

---

## SogouNews DATASET

The labels includes:

- 0 : Sports
- 1 : Finance
- 2 : Entertainment
- 3 : Automobile - 4 : Technology

Number of lines per split:

- train: 450000
- test: 60000

Number of classes: 5

**Examples:**

- train_dataset, test_dataset = torchtext.datasets.SogouNews(ngrams=3)

**ACCURACY:** 94.6%

---

## YelpReviewPolarity DATASET

The labels includes:

- 0 : Negative polarity.
- 1 : Positive polarity.

Number of lines per split:

- train: 560000
- test: 38000

Number of classes: 2

**Examples:**

- train_dataset, test_dataset = torchtext.datasets.YelpReviewPolarity(ngrams=3)

**ACCURACY:** 91.0%

---

## LOGS SCREENSHOTS

**SogouNews**
![image](https://user-images.githubusercontent.com/15984084/140643955-e2384885-77a6-47f1-aac6-0a85dc5f7bdb.png)

**YelpReviewPolarity**
![image](https://user-images.githubusercontent.com/15984084/140643940-8bca09ce-175e-490b-ac6e-2d045b604645.png)

---
