# Model Results

Original results from the published analysis. All metrics are reported on the 25% held-out test set (n ≈ 341), drawn from a stratified 10% subsample of the UCI Dry Bean Dataset (n = 1,364 working sample). Hyperparameters were selected by 5-fold cross-validation on the training split.

## Performance Summary

| Method | Tuned Parameters | OOB / Train Error | Test Accuracy | Test ARI |
|---|---|---|---|---|
| Bagging | ntree = 2,100; mtry = 16 (all features) | 8.87% (OOB) | ~91.1% | — |
| Random Forest | ntree = 500; mtry = 6 | 8.77% (OOB) | **91.1%** | **0.785** |
| Boosting (GBM) | n.trees = 200; depth = 3; λ = 0.05; minobs = 20 | 0.2% (train) | 90.5% | — |
| Mixture Discriminant Analysis | BIC-selected Gaussian mixture per class | — | ~91% | — |
| ANN | size = 11; decay = 4; softmax; maxit = 500 | — | **91.1%** | 0.779 |

## Key Findings

- **Performance spread:** all five methods within 1.5% test misclassification (SD ≈ 0.6% across methods).
- **Best overall:** Random Forest and ANN tie at 91.1% test accuracy; Random Forest preferred by ARI (0.785 vs. 0.779).
- **Boosting overfitting:** 0.2% training misclassification vs. 9.5% test misclassification — the largest train–test gap among the five models despite regularisation.
- **Top predictors (RF Mean Decrease Gini):** Perimeter, ShapeFactor1, Compactness, MinorAxisLength, MajorAxisLength.
- `set.seed(42)` used throughout; minor variation across R versions is expected.

## Tuning Details

| Method | Tuning Grid | CV Folds | Selected |
|---|---|---|---|
| Bagging | ntree ∈ {100, 200, …, 2500} | 5 | ntree = 2,100 |
| Random Forest | mtry ∈ {6,…,10} × ntree ∈ {100,…,2500} | 5 | mtry = 6, ntree = 500 |
| Boosting | n.trees ∈ {200,…,2000} × depth ∈ {1,2,3,4} × λ ∈ {0.01, 0.05, 0.1} | 5 | 200, depth 3, λ = 0.05 |
| ANN | size ∈ {1,…,20} × decay ∈ {0,1,2,3,4,5} | 5 | size = 11, decay = 4 |
