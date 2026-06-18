# Parkinson's Disease Classification using Machine Learning

This repository contains an academic machine learning project focused on classifying Parkinson's Disease from speech-based biomedical features. The project compares multiple supervised learning models and studies the effect of feature selection on classification performance.

---

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Machine Learning Pipeline](#machine-learning-pipeline)
- [Feature Groups](#feature-groups)
- [Feature Selection](#feature-selection)
- [Train-Test Split](#train-test-split)
- [Models Trained](#models-trained)
- [Results](#results)
- [Disclaimer](#disclaimer)
- [Contributors](#contributors)

---

## Project Overview

Parkinson's Disease can affect speech and vocal patterns. In this project, speech-derived features such as jitter, shimmer, harmonic-to-noise ratios, MFCCs, recurrence measures, and entropy-based features are used to classify whether a sample belongs to a healthy subject or a Parkinson's Disease patient.

The workflow includes:

1. Loading and inspecting the dataset
2. Checking for missing/null values
3. Removing non-predictive identifier columns
4. Studying feature distributions
5. Performing correlation-based feature selection
6. Scaling the dataset
7. Training multiple machine learning classifiers
8. Evaluating models using accuracy, F1-score, recall, and AUC
9. Comparing model performance

---

## Dataset

The dataset consists of biomedical voice measurements collected from healthy individuals and Parkinson's Disease patients. Each sample contains multiple acoustic and signal-processing features designed to capture subtle changes in speech production associated with Parkinson's Disease.

---

## Machine Learning Pipeline

```text
Dataset
   ↓
Data Cleaning
   ↓
Feature Analysis
   ↓
Correlation-Based Feature Selection
   ↓
Train-Test Split (80:20)
   ↓
Feature Scaling
   ↓
Model Training
   ↓
Performance Evaluation
   ↓
Model Comparison
```

---

## Feature Groups

The dataset includes several groups of speech and signal-processing features:

| Feature Group | Examples | Description |
|---|---|---|
| Jitter Features | `Jitter_rel`, `Jitter_abs`, `Jitter_RAP`, `Jitter_PPQ` | Pitch perturbation measures |
| Shimmer Features | `Shim_dB`, `Shim_APQ3`, `Shim_APQ5`, `Shi_APQ11` | Amplitude perturbation measures |
| Harmonic-to-Noise Ratio | `HNR05`, `HNR15`, `HNR25`, `HNR35`, `HNR38` | Harmonic-to-noise ratio across frequency bands |
| Nonlinear Voice Features | `RPDE`, `DFA`, `PPE`, `GNE` | Speech complexity and entropy-related measures |
| MFCC Features | `MFCC0` to `MFCC12` | Mel-frequency cepstral coefficients |
| Delta Features | `Delta0` to `Delta12` | Derivative features associated with MFCC-style representations |

---

## Feature Selection

Many speech features are strongly correlated with each other. Highly correlated features may add redundancy and can reduce model efficiency.

A Pearson correlation-based feature selection method is used.

---

## Train-Test Split

The dataset is split into training and testing sets using an 80:20 split.

After splitting, the correlated features are removed from both training and testing sets.

---

## Models Trained

The project trains and compares the following models:

| Model | Description |
|---|---|
| K-Nearest Neighbors | Distance-based classification |
| Support Vector Classifier | Margin-based classifier using SVM |
| Gaussian Naive Bayes | Probabilistic classifier based on Bayes theorem |
| Logistic Regression | Linear classification model |
| Stacking Classifier | Meta-classifier combining multiple base models |
| Decision Tree | Tree-based classifier |
| Bagging Classifier | Ensemble method using bootstrapped trees |
| AdaBoost | Boosting-based ensemble model |
| Gradient Boosting | Sequential boosting ensemble |
| Random Forest | Ensemble of decision trees |

---

## Results

The following table summarizes the performance of the evaluated machine learning models on the Parkinson's Disease classification task.

| Model | Train Accuracy | Test Accuracy | F1-Score | Recall | AUC |
|--------|--------:|--------:|--------:|--------:|--------:|
| KNN | 81.77 | 81.25 | 83.02 | 91.67 | 81.25 |
| SVC | 82.81 | 79.17 | 81.48 | 91.67 | 79.17 |
| Naive Bayes | 80.73 | 70.83 | 75.86 | 91.67 | 70.83 |
| Logistic Regression | 83.85 | 83.33 | 84.00 | 87.50 | 83.33 |
| Meta Classifier | 82.81 | 75.00 | 77.78 | 87.50 | 75.00 |
| Decision Tree | 81.25 | 75.00 | 77.78 | 87.50 | 75.00 |
| Bagging | 82.81 | 77.08 | 79.25 | 87.50 | 77.08 |
| AdaBoost | 88.02 | 75.00 | 77.78 | 87.50 | 75.00 |
| Gradient Boost | 90.10 | 70.83 | 75.00 | 87.50 | 70.83 |
| Random Forest | 99.48 | 77.08 | 79.25 | 87.50 | 77.08 |

### Observations

- Logistic Regression achieved the highest test accuracy (**83.33%**) and F1-score (**84.00%**).
- KNN and SVC also demonstrated strong performance, achieving test accuracies above **79%**.
- Ensemble methods such as Random Forest and Gradient Boosting showed signs of overfitting, with significantly higher training accuracy than testing accuracy.
- Overall, Logistic Regression provided the best balance between training performance and generalization on the test dataset.

---

## Disclaimer

This project is for educational purposes only. The models and results presented here are not intended be used for clinical diagnosis, medical advice, or healthcare decision-making.

## Contributors:

- [Sairam Sridharan](https://github.com/Sairamzz)
- Mruthunjay Mani
