# Fraud Detection with PCA & t-SNE

![screenshot-localhost_8888-2025 04 06-13_42_17](https://github.com/user-attachments/assets/337c4ae8-2875-4731-9365-1a154b1eedd6)

A project exploring feature engineering for credit card fraud detection using dimensionality reduction techniques.

### Project Overview

This project investigates how PCA (Principal Component Analysis) and t-SNE (t-Distributed Stochastic Neighbor Embedding) impact fraud detection performance in credit card transactions. The goal is to:

- Visualize fraud patterns in 2D space
- Compare PCA vs. t-SNE for feature engineering
- Improve fraud recall using non-linear dimensionality reduction

### Dataset

File: creditcard.csv (Credit Card Fraud Detection dataset)

**Features**:
- Time - Transaction timestamp
- Amount - Transaction value
- V1-V28 - Anonymized PCA-transformed features
- Class - Fraud label (0 = normal, 1 = fraud)

**Class Imbalance**:
- Non-fraud (99.83%) | Fraud (0.17%)

### Code Workflow

1. Preprocessing
- Normalize features (StandardScaler)
- Separate fraud/non-fraud samples

2. Dimensionality Reduction
- PCA: Linear projection (2 components)
- t-SNE: Non-linear clustering (2 components)

3. Visualization
- Scatter plots of fraud vs. normal transactions

4. Classification
Train Random Forest on:
- PCA features
- t-SNE features
- Combined (PCA + t-SNE) features
Evaluate using precision, recall, F1-score

### Results & Interpretation

- Fraud Recall	(PCA) 7% (t-SNE) 76%
- Fraud F1	(PCA) 0.14 (t-SNE) 0.82

### Key Insights
- PCA fails to detect most fraud (low recall) due to linear assumptions.
- t-SNE captures non-linear fraud patterns, drastically improving recall.
- Combining both features may offer balanced performance (needs testing).

### Future Improvements

- Try UMAP (faster alternative to t-SNE)
- Class balancing (SMOTE/ADASYN)
- Hybrid models (e.g., t-SNE + Isolation Forest)
- Real-time deployment testing


### Source

[Synthetic Bank Transfers Dataset from Kaggle](https://www.kaggle.com/datasets/nyingsha/synthetic-bank-transfers)

