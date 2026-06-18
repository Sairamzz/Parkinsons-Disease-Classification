# Parkinson's Disease Classification using Machine Learning

This repository contains an academic machine learning project focused on classifying Parkinson's Disease from speech-based biomedical features. The project compares multiple supervised learning models and studies the effect of feature selection on classification performance.

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

The dataset contains speech-related features extracted from voice recordings.

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

In the notebook run, the final comparison table reports the following performance:

| Model | Train Accuracy | Test Accuracy | F1-Score | Recall | AUC |
|---|---:|---:|---:|---:|---:|
| KNN | 83.85 | 81.25 | 82.35 | 80.77 | 81.29 |
| SVC | 85.42 | 79.17 | 80.77 | 80.77 | 79.02 |
| Naive Bayes | 83.33 | 75.00 | 76.92 | 76.92 | 74.83 |
| Logistic Regression | 84.90 | 81.25 | 81.63 | 76.92 | 81.64 |
| Meta Classifier | 84.38 | 77.08 | 78.43 | 76.92 | 77.10 |
| Decision Tree | 85.42 | 68.75 | 66.67 | 57.69 | 69.76 |
| Bagging | 85.42 | 75.00 | 76.00 | 73.08 | 75.17 |
| AdaBoost | 87.50 | 72.92 | 74.51 | 73.08 | 72.90 |
| Gradient Boosting | 92.71 | 72.92 | 73.47 | 69.23 | 73.25 |
| Random Forest | 98.96 | 72.92 | 76.36 | 80.77 | 72.20 |

## Disclaimer

This project is for educational purposes only. The models and results presented here are not intended be used for clinical diagnosis, medical advice, or healthcare decision-making.

## Contributors:

Sairam Sridharan
Mruthunjay Mani
