# Predicting-Adolescent-Depression

.

📊 Predicting Adolescent Depression Using Classical ML, TabPFN & Stacked Ensembles

Authors:
Sherwin D’Souza
Monil Patel
Christom Joseph
Department of Mathematics & Statistics
University of Guelph

📌 Project Overview

This research project presents a comprehensive benchmarking study comparing:

Classical Machine Learning Models

Transformer-based Foundation Model (TabPFN)

Stacked Ensemble Architectures

for predicting adolescent depression using behavioral, lifestyle, and psychosocial survey data.

The goal was to evaluate model performance with a primary focus on:

🔴 Maximizing Recall for the Depressed Class
(to minimize false negatives in mental health screening)

🎯 Research Objectives

This study aimed to:

Establish baseline performance across 14 classical ML models

Evaluate TabPFN’s zero-shot tabular learning capabilities

Implement stacked ensemble configurations

Address class imbalance using SMOTE

Compare sensitivity-focused performance metrics

Analyze model failures on minority class prediction

📂 Dataset

3,000 adolescents (ages 13–19)

19 final predictive features after preprocessing

Binary Target:

0 → No/Minimal symptoms (70%)

1 → Mild/Moderate/Severe depression (30%)

Feature Groups:

Demographics

Technology Usage Patterns

Lifestyle Indicators

Psychosocial Factors

Class imbalance handled using SMOTE applied only to training data.

⚙️ Preprocessing Pipeline

Removed identifiers and leakage-prone variables

Outlier clipping (±3σ)

Label encoding for ordinal variables

StandardScaler applied to continuous variables

Stratified 70–30 train-test split

SMOTE balancing (training set only)

Final Training Set:

2,940 samples × 19 features

🤖 Models Evaluated
Classical Models

Logistic Regression (Base & Tuned)

Forward / Backward Stepwise Regression

Decision Trees (Entropy & Gini)

Random Forest

Gradient Boosting

XGBoost

LightGBM

CatBoost

Multi-Layer Perceptron

Foundation Model

TabPFN (Transformer-based, Zero-Shot)

Stacked Ensembles

(LogReg + DT + RF) → Logistic Meta-Learner

(RF + XGBoost) → Logistic Meta-Learner

📊 Evaluation Metrics

Primary Metric:

Recall (Depressed Class)

Secondary Metrics:

F1-Score

Accuracy

Precision

AUC (TabPFN)

🏆 Key Results
Model	Recall	F1	Accuracy
Tuned Logistic Regression	0.49	0.38	0.52
TabPFN	0.46	0.39	0.57
Stacked (RF + XGB) Tuned	0.53	0.39	0.52
🔥 Best Model:

Stacked (Random Forest + XGBoost) with Tuned Meta-Learner

Highest recall (0.53)

Balanced F1 (0.39)

Outperformed individual classical models

🧠 Key Insights
1️⃣ Linear models performed strongly

Well-regularized logistic regression achieved high recall due to explicit class weighting.

2️⃣ Complexity ≠ Performance

Many ensemble boosting models underperformed due to:

Majority class bias

Accuracy-focused tuning

Limited hyperparameter exploration

3️⃣ Neural Network Failure

MLP collapsed to predicting majority class (Recall = 0.01).

4️⃣ TabPFN Competitiveness

Achieved recall 0.46 without dataset-specific tuning.
Demonstrates promise of foundation models in tabular healthcare prediction.

5️⃣ Stacked Ensembles Require Proper Optimization

Untuned stacked models collapsed.
After recall-optimized GridSearch, performance significantly improved.

🔎 Most Predictive Features

Logistic regression analysis identified:

Low Self-Esteem (Strongest predictor)

Poor Family Communication

High Screen Time Before Bed

Daily Phone Usage

These provide actionable insights for prevention strategies.

🏥 Clinical Implications

53% sensitivity can meaningfully improve early screening

Suitable for two-stage mental health screening frameworks

Threshold tuning allows recall-precision tradeoff depending on deployment context

⚠️ This is a screening tool — not a diagnostic system.

🚧 Limitations

Cross-sectional dataset

Self-reported survey bias

No external validation

Limited sample size for deep models

No probability calibration analysis

Future work includes:

Longitudinal modeling

SHAP interpretability

Alternative sampling methods (ADASYN, SMOTEENN)

External dataset validation

Integration with clinicians

🛠 Technologies Used

Python

Scikit-learn

XGBoost

LightGBM

CatBoost

PyTorch

TabPFN

SMOTE (imbalanced-learn)

GridSearchCV

📌 Conclusion

This study demonstrates that:

Properly tuned stacked ensembles can improve minority class sensitivity

Foundation models like TabPFN are viable alternatives in small tabular datasets

Metric selection (recall-focused) significantly impacts model selection

Model tuning strategy matters more than algorithm complexity

The ultimate objective is to support early identification and timely intervention for at-risk adolescents.
