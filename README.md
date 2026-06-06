# Chain-of-Thought & Tree-of-Thought Reasoning

## Overview

This project demonstrates two important reasoning techniques used in Generative AI:

1. **Chain-of-Thought (CoT)** for Sentiment Analysis of Customer Reviews.
2. **Tree-of-Thought (ToT)** for Hyperparameter Selection in Machine Learning.

The objective is to showcase how structured reasoning can improve decision-making and explainability in AI systems.

---

# Project Structure

```text
assignment/
│
├── Task1/
│   ├── customer_reviews_dataset.csv
│   ├── sentiment_results.csv
│   └── Sentiment-with-CoT_from_Customer_Reviews.ipynb
│
├── Task2/
│   ├── random_forest_tot_results.csv
│   ├── tree_of_thought_prompt.txt
│   └── Choosing_right_parameters_using_Tree-of-Thought.ipynb
│
└── README.md
```

---

# Task 1: Sentiment Analysis using Chain-of-Thought (CoT)

## Objective

Predict customer review sentiment as:

* Positive
* Neutral
* Negative

while providing transparent reasoning through a Chain-of-Thought style process.

---

## Dataset

A custom dataset containing customer reviews collected from e-commerce products.

### Dataset Columns

| Column           | Description              |
| ---------------- | ------------------------ |
| review_id        | Unique review identifier |
| review           | Customer review text     |
| actual_sentiment | Ground truth sentiment   |

Total Reviews: **8**

---

## Chain-of-Thought Prompt Design

The prompt guides reasoning through multiple steps:

### Reasoning Steps

1. Identify positive sentiment phrases.
2. Identify negative sentiment phrases.
3. Detect mixed or contradictory opinions.
4. Decide the final sentiment.
5. Explain the decision.

### Few-Shot Examples Included

* Positive Review Example
* Neutral Review Example
* Negative Review Example

This enables the model to follow a structured reasoning pattern before making a prediction.

---

## Approach

The notebook:

1. Loads customer reviews.
2. Defines a Chain-of-Thought prompt template.
3. Extracts positive and negative phrases.
4. Detects mixed sentiment.
5. Generates final sentiment predictions.
6. Produces explanations for each prediction.
7. Saves results to CSV.

---

## Output

Generated file:

```text
sentiment_results.csv
```

Contains:

* Review ID
* Actual Sentiment
* Predicted Sentiment
* Positive Phrases
* Negative Phrases
* Mixed Sentiment Indicator
* Explanation
* Prompt Used

---

## Sample Reasoning

Review:

```text
The sound quality is excellent and battery backup is very good.
```

Reasoning:

```text
Positive phrases:
- excellent
- very good

Negative phrases:
- none

Mixed sentiment:
- no

Final Label:
- positive
```

---

# Task 2: Hyperparameter Selection using Tree-of-Thought (ToT)

## Objective

Train a Machine Learning model and use Tree-of-Thought reasoning to analyze hyperparameter configurations and identify the best-performing model.

---

## Dataset

Breast Cancer Wisconsin Dataset

Source:

```python
from sklearn.datasets import load_breast_cancer
```

### Problem Type

Binary Classification

Classes:

* Malignant
* Benign

---

## Machine Learning Model

Random Forest Classifier

```python
RandomForestClassifier()
```

---

## Hyperparameter Search Space

### n_estimators

```python
[50, 100, 200]
```

### max_depth

```python
[3, 5]
```

### min_samples_split

```python
[2, 5]
```

Total Configurations:

```text
12
```

---

## Evaluation Strategy

### Cross Validation

```python
StratifiedKFold(
    n_splits=5,
    shuffle=True,
    random_state=42
)
```

### Metrics Collected

* Mean Training Accuracy
* Mean Cross Validation Accuracy
* Train-Validation Gap
* Training Time

---

## Tree-of-Thought Prompt Design

The prompt instructs the reasoning process to:

### Branch 1: Performance Analysis

* Compare validation accuracies.
* Identify top-performing configurations.

### Branch 2: Overfitting Analysis

* Examine train-validation gap.
* Detect overly complex models.

### Branch 3: Efficiency Analysis

* Compare training times.
* Evaluate computational cost.

### Final Decision

Choose the best configuration balancing:

* Accuracy
* Generalization
* Computational Efficiency

---

## Results

Generated file:

```text
random_forest_tot_results.csv
```

Contains:

* Configuration ID
* n_estimators
* max_depth
* min_samples_split
* Mean Train Accuracy
* Mean CV Accuracy
* Train-Validation Gap
* Training Time

---

## Best Configuration

Example top-performing configuration:

```text
n_estimators = 200
max_depth = 5
min_samples_split = 5
```

Reasons:

* Highest validation accuracy
* Low overfitting
* Good generalization
* Acceptable training time

---

# Technologies Used

* Python
* Pandas
* NumPy
* Scikit-Learn
* Jupyter Notebook

---

# Key Concepts Demonstrated

## Chain-of-Thought (CoT)

A prompting strategy where reasoning steps are explicitly generated before arriving at a final answer.

Benefits:

* Improved transparency
* Better explainability
* Easier debugging of decisions

---

## Tree-of-Thought (ToT)

An advanced reasoning strategy where multiple candidate paths are explored and evaluated before selecting the best solution.

Benefits:

* Better decision quality
* Structured exploration
* Improved optimization reasoning

---

# Learning Outcomes

By completing this project:

* Implemented Chain-of-Thought prompting.
* Performed sentiment analysis with explainable reasoning.
* Conducted hyperparameter tuning using Random Forest.
* Applied Tree-of-Thought reasoning for model selection.
* Compared performance, overfitting, and efficiency trade-offs.

---

# Author

**Mothe Naveen**

B.Tech Student | Python | Machine Learning | Generative AI | Data Science
