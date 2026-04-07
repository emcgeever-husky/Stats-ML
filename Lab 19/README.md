# Tree-Based Models — Random Forests

**Course:** ECON 3916: Data Science for Economists
**Dataset:** California Housing (sklearn) — 20,640 observations, 8 features

---

## Objective

Evaluate the predictive performance of ensemble tree-based methods against linear and single-tree baselines on a canonical housing dataset, with emphasis on hyperparameter sensitivity and feature attribution.

---

## Methodology

- Benchmarked three model classes — Decision Tree, Ridge Regression, and Random Forest — on the California Housing dataset using RMSE and R² across train/test splits
- Tuned Random Forest hyperparameters (`n_estimators`, `max_depth`, `max_features`) via 5-fold GridSearchCV, evaluating parameter combinations scored on negative MSE
- Extracted and compared two feature importance methods: MDI (mean decrease in impurity, training-based) and permutation importance (test-based), analyzing where and why they diverge
- Framed a binary classification task — predicting above-median home prices — and benchmarked a Random Forest classifier against Logistic Regression using ROC-AUC
- Built an interactive three-panel Plotly dashboard with ipywidgets sliders for `n_estimators` and `max_features`, visualizing model comparison, MDI importance, and train/test learning curves in real time

---

## Key Findings

- Random Forest (Test R² = **0.8090**) substantially outperformed Ridge Regression (Test R² = **0.6050**), indicating meaningful non-linearity in the feature-price relationship that a linear model cannot capture
- `MedInc` ranked as the dominant predictor under both importance methods; geographic coordinates (`Latitude`, `Longitude`) were inflated by MDI relative to permutation importance, consistent with high-cardinality bias in impurity-based metrics
- The RF classifier (AUC = **0.9609**) achieved materially higher classification accuracy than Logistic Regression (AUC = **0.9060**), reinforcing that the expensive/cheap decision boundary is non-linear in feature space
- Hyperparameter tuning via GridSearchCV produced modest gains over default settings (R² 0.8050 → 0.8090), with optimal parameters of `max_depth=None`, `max_features=0.5`, `n_estimators=100`

---

## Tools & Libraries

`scikit-learn` · `plotly` · `ipywidgets` · `numpy` · `pandas`
