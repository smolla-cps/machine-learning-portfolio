# Ensemble Methods

This portfolio project explores tree-based ensemble learning for both classification and regression.

The experiments build ensemble behavior directly from randomized decision trees and then compare established implementations including Random Forests, Extra Trees, gradient boosting, histogram-based gradient boosting, and XGBoost.

## Repository Structure

```text
08-ensemble-methods/
├── README.md
├── requirements.txt
├── data/
│   └── README.md
└── notebooks/
    ├── 01_mnist_tree_ensemble_methods.ipynb
    ├── 02_fashion_mnist_random_forest_tuning.ipynb
    └── 03_gpu_runtime_regression_ensembles.ipynb
```

## 1. MNIST — Tree Ensemble Methods

This notebook demonstrates how randomized decision trees become stronger when their predictions are aggregated.

### Methods

- entropy and Gini decision trees
- random splitters
- hard voting
- 50% and 75% random feature subsets
- bootstrap sampling
- probability averaging
- Random Forest
- Extra Trees
- gradient boosting
- histogram gradient boosting
- XGBoost

### Selected Results

| Method | Saved Accuracy |
|---|---:|
| Single entropy tree | 0.8868 |
| Randomized entropy tree | 0.8780 |
| 30-tree manual entropy ensemble | **0.9701** |
| 30-tree manual Gini ensemble | 0.9676 |
| Random Forest — 30 trees | 0.9634 |
| Random Forest — 100 trees | 0.9693 |
| Extra Trees — 30 trees | 0.9665 |
| Gradient Boosting — 30 stages | 0.9057 |
| Histogram Gradient Boosting — 30 iterations | 0.9618 |
| XGBoost — 30 estimators | 0.9670 |

## 2. Fashion-MNIST — Random Forest Tuning

This notebook keeps the ensemble size fixed at 30 trees while studying split criterion, maximum depth, and per-tree training-sample size.

### Selected Results

| Configuration | Saved Accuracy |
|---|---:|
| Default Random Forest | 0.8729 |
| Entropy Random Forest | **0.8738** |
| Adaptive depth search — depth 20 | 0.8731 |
| Depth 60 + log_loss | 0.8733 |

## 3. GPU Runtime — Regression Ensembles

This notebook extends the ensemble concepts to regression.

### Methods

- mean-prediction baseline
- single regression tree
- 100 randomized regression trees
- cumulative prediction averaging
- Random Forest Regressor
- Extra Trees Regressor
- Gradient Boosting Regressor
- Histogram Gradient Boosting Regressor

The regression notebook expects `gpu_running_time.csv` in the `data/` directory.

## Skills Demonstrated

- ensemble learning
- hard voting
- probability averaging
- bootstrap sampling
- random feature selection
- Random Forests
- Extra Trees
- gradient boosting
- histogram gradient boosting
- XGBoost
- classification and regression
- feature importance
- hyperparameter analysis
- ensemble-size analysis
- bias/variance behavior
- accuracy, MSE, and MAE evaluation

## Tools

Python, NumPy, Pandas, Matplotlib, scikit-learn, TensorFlow/Keras, XGBoost, Jupyter Notebook

## Reproducibility

MNIST and Fashion-MNIST are loaded through TensorFlow/Keras. The GPU runtime notebook uses a repository-relative path for `data/gpu_running_time.csv`.
