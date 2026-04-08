## Fraud Detection Model Evaluation — Metrics that Matter

### Objective
Rigorously evaluate a logistic regression fraud classifier on a severely imbalanced real-world dataset, demonstrating why accuracy alone is a misleading performance metric and how threshold selection and business constraints should drive model deployment decisions.

### Methodology
- **Data:** Kaggle Credit Card Fraud Detection dataset — 284,807 European credit card transactions with PCA-anonymized features (V1–V28), transaction `Amount`, and a binary fraud label (0.172% positive class)
- **Baseline audit:** Constructed a naive all-negative classifier to expose the accuracy paradox — 99.83% accuracy achieved with zero fraud recall, illustrating the fundamental failure of accuracy as a metric under severe class imbalance
- **Model training:** Fit a logistic regression classifier using `scikit-learn`, evaluated against a held-out test set using confusion matrices and `classification_report`
- **Threshold analysis:** Computed ROC and Precision-Recall curves across the full threshold space; identified the F1-optimal threshold, which diverges meaningfully from the default 0.5 cutoff
- **Business constraint integration:** Applied a capacity constraint of 500 maximum daily fraud investigations to select a financially-motivated operating point on the Precision-Recall curve, balancing investigator workload against fraud capture rate
- **Visualization:** Produced annotated ROC curves, PR curves, and confusion matrix heatmaps using `matplotlib` and `seaborn`

### Key Findings
The accuracy paradox is stark — a model that never predicts fraud achieves 99.83% accuracy while catching zero cases, underscoring that accuracy is not a valid optimization target under extreme class imbalance. Logistic regression achieved a strong ROC-AUC and meaningful PR-AUC on the minority fraud class, confirming the model extracts genuine signal from the PCA features. The F1-optimal decision threshold differs substantially from the conventional 0.5 default, and selecting it materially improves the precision-recall tradeoff. Incorporating an operational constraint (≤500 daily reviews) further illustrates that the right operating point is determined not by statistical optima alone, but by the cost structure and capacity of the downstream business process — a principle central to deploying classifiers in production risk management settings.

### Tech Stack
`Python` · `scikit-learn` · `pandas` · `numpy` · `matplotlib` · `seaborn`
