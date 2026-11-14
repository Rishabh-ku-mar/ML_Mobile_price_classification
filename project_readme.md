# Mobile Price Classification: End-to-End Machine Learning Pipeline

This repository contains the complete machine learning assignment, exploratory data analysis (EDA), model benchmarking, and final project report for the **Mobile Price Classification** project.

## Project Overview
The objective of this project is to predict the price tier (`price_range` from 0 to 3) of mobile devices based on 20 hardware specifications (such as RAM, battery power, pixel resolution, and internal memory). The pipeline explores 2 simple baseline models and 3 advanced learners, culminating in champion model selection and rigorous evaluation on unlabelled test data.

---

## Repository Structure

- `Mobile_Price_Classification_Flow_Diagram_and_Summary-v2.docx`: Polished assignment report featuring UI/UX flow diagrams, stage-by-stage technical summaries, and model comparison tables.
- `ML_mobile_price_prediction.ipynb`: Kaggle notebook containing data ingestion, EDA visualizations, feature scaling, model training, and evaluation.
- `my_mobile_predictions.csv`: Final test set predictions generated on the unlabelled `test.csv` dataset.
- `LICENSE`: Open-source MIT license governing this repository.

---

## Model Benchmarking Results

All models were evaluated on a stratified 20% validation split (400 devices):

| Rank | Model Name | Category | Scaling Required? | Test Accuracy | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | **Logistic Regression** | **Simple Baseline** | **Yes (`StandardScaler`)** | **96.50%** | **Champion Model** |
| 2 | Gradient Boosting | Advanced Learner | No (Tree-based) | 91.25% | Strong Runner-Up |
| 3 | Support Vector Machine (RBF) | Advanced Learner | Yes (`StandardScaler`) | 89.50% | Solid Kernel Fit |
| 4 | Random Forest (100 Trees) | Advanced Learner | No (Tree-based) | 88.00% | Ensemble Baseline |
| 5 | Decision Tree Classifier | Simple Baseline | No (Tree-based) | 83.00% | Overfit Prone |

---

## Key Findings & Recommendation
- **Champion Model:** **Logistic Regression (96.50% Accuracy)** achieved the highest performance.
- **Why it outperforms:** Exploratory Data Analysis demonstrated that **RAM** has a powerful, nearly linear monotonic relationship with price tiers. Logistic Regression fits smooth linear hyperplanes across standardized features, avoiding the rigid axis-aligned partitioning and overfitting risks associated with decision trees on compact tabular datasets.