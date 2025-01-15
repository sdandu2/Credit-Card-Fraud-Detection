# Credit Card Fraud Detection

This project implements a machine learning system for detecting fraudulent financial transactions in real-time. Traditional rule-based fraud detection often fails to keep up with evolving fraud techniques. Our approach leverages machine learning to identify anomalies and fraudulent patterns with high accuracy and adaptability.

## Table of Contents
- [Introduction](#introduction)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Feature Engineering](#feature-engineering)
- [Modeling and Results](#modeling-and-results)
  - [Logistic Regression](#logistic-regression)
  - [Random Forest](#random-forest)
  - [XGBoost](#xgboost)
  - [SVM](#svm)
- [Conclusion](#conclusion)
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)

---

## Introduction

The goal of this project is to develop a machine learning system to classify financial transactions as legitimate or fraudulent in real time. The objectives include:
- **Accurately classify transactions** as legitimate or fraudulent.
- **Minimize false positives** to reduce disruptions for genuine customers.
- **Adapt dynamically** to new forms of fraud without constant manual intervention.

---

## Exploratory Data Analysis (EDA)

### Key Observations:
- **Correlation Analysis**: Weak correlations observed between most features and the target variable (`Class`). Feature interactions may be more predictive than individual features.
- **Feature Insights**:
  - Strongly correlated features were identified and optimized to avoid redundancy.
  - Weakly correlated features were explored for advanced modeling.

---

## Feature Engineering

### Why Random Forest for Feature Selection?
- Random Forest was used to identify the most important features contributing to fraud detection, based on Gini Impurity or entropy.

### Steps Performed:
1. Trained a Random Forest model.
2. Extracted feature importance scores.
3. Ranked features by importance.
4. Retained features with importance above a threshold (e.g., 0.01).

### Impact:
- Reduced dataset dimensionality while retaining critical information.
- Improved model efficiency and interpretability.

---

## Modeling and Results

### Logistic Regression
- **Strengths**:
  - High recall for fraud cases (86%).
  - Strong AUC-ROC (0.9621).
- **Weaknesses**:
  - Low precision for fraud cases (15%).
  - Low F1-score (26%).

### Random Forest
- **Strengths**:
  - High precision (81%) and recall (85%) for fraud cases.
  - AUC-ROC (0.9635).
- **Weaknesses**:
  - Residual false negatives (15 cases).
  - Complexity due to ensemble nature.

### XGBoost
- **Strengths**:
  - Balanced precision (81%) and recall (80%).
  - Excellent AUC-ROC (0.9548).
- **Weaknesses**:
  - Computational cost.
  - Residual false negatives (19 cases).

### SVM
- **Strengths**:
  - Perfect precision and recall (100%).
  - AUC-ROC (1.000).
- **Weaknesses**:
  - Potential overfitting.
  - Scalability challenges.

---

## Conclusion

- **Best Overall Model**: Random Forest strikes a balance between precision, recall, and efficiency, making it ideal for real-world scenarios.
- **SVM Performance**: Achieved perfect metrics but may overfit or face scalability issues.
- **Future Work**:
  - Fine-tuning hyperparameters for XGBoost and Random Forest.
  - Implementing real-time fraud detection pipelines.

---

## Installation

To set up this project, clone the repository and install the dependencies:

```bash
git clone https://github.com/yourusername/credit-card-fraud-detection.git
cd credit-card-fraud-detection
pip install -r requirements.txt
