---
tags: COMP47750 - Machine Learning with Python
---

# Naive Bayes Classifier

## Overview
- Probabilty-based learning
- Bayes Theorem
- Naive Bays Classifier
- Examples and Exercises
- Handling Numerica Features

## Thomas Bayes Theory
```
P(A|B) = P(B|A)P(A)/P(B)
```

> Bayesian Probability is the name given to sevral related interpretations of probability as an amount of epistemic confidence - the strength of beliefs, hypothoses etc. - rather than a frequency

## Antibody Test Example
- P(I) ~ 500/10,000 = 0.05 (5% infection rate)
- P(Pos(I)) ~ 490/500 = 0.98
- What is P(I|Pos)? - probability someone with a positive test is infected



|  | Infected | Not Infected | Total    |
| -------- | -------- | -------- | --- |
| **Positive**         |      490    |   190       |   680  |
| **Negative**         |    10      |     9310     | 9,320    |
| **Total**     | 500     | 9,500     |   10,000  |

- P(I|POS) = 0.98 * 0.05 / 0.068 = 0.72 (28% False Positive Rate)

## Probability-based learning
- **Key Idea**: Use estimates of likelhoods to determine the most likely prediction whihc should be made for classification. e.g. "email X is more likely spam than not spam"
- Revising estimations on data we collect
- The most common probabilistic approach for classification is the Naive Bays classifier
- Often measures the hypothosis against the data, P(h|D)

## Bayes Classification
- We usually want to find the most likely hypothosis for our data
- Formally, we are lookign for the maxiumum Aposteriori Hypothosis (MAP)
```
hMAP = arg max P(h|D)
```
- **Key Idea:** Apply Bayes Theorum wit the "naive" assumption that all features in the data are conditionally independent!
    - (The value of a particular feature is unrelated to the presense of absense f any other feature, given the class label Vj)



## Classifier Inputs

- Classifier Inputs:
    - A set of labels V = {v1, v2, ...}
    - A set of examples X = {x1, x2,...}, each represented by features {f1, f2, ...., fn}


## Complete formula

```
vNB = arg max vJ (= P(vJ) ∏ P(fi|vJ)
```
∏ = a product over a set of terms