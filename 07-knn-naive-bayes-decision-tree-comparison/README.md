# Water Potability Classification: Classical Model Comparison

This project evaluates classical machine-learning approaches for predicting water potability from nine measured water-quality attributes. The analysis combines library-based benchmarking, cross-validation, hyperparameter search, ensemble voting, from-scratch algorithm implementations, and missing-data strategies.

## Repository Structure

```text
07-water-potability-classical-model-comparison/
├── README.md
├── requirements.txt
├── data/
│   ├── README.md
│   ├── water_potability.xlsx
│   └── water_potability_original.xlsx
└── notebooks/
    ├── 01_water_potability_sklearn_model_comparison.ipynb
    ├── 02_water_potability_from_scratch_missing_data.ipynb
    └── 03_california_housing_mnist_adaptive_knn_decision_tree_wrappers.ipynb
```

## Project Scope

The water-potability analysis compares:

- k-nearest neighbors
- Multinomial Naive Bayes
- Bernoulli Naive Bayes
- decision trees
- majority-vote ensembles
- custom implementations of k-NN, Naive Bayes, and decision trees
- mean, median, and regression-based missing-value estimation

The project also includes a reusable k-NN and decision-tree wrapper design evaluated on California Housing and structured for MNIST classification.

## Dataset

The complete water dataset contains 2,011 observations with nine predictors and a binary potability target. The larger dataset contains 3,276 observations and introduces missing values in `ph`, `Sulfate`, and `Trihalomethanes`.

## Notebook 1 — Water Potability with scikit-learn

This notebook evaluates holdout splits, normalization, 10-fold cross-validation, leave-one-out cross-validation, hyperparameter search, and majority-vote ensembles.

### Baseline Accuracy

| Model | 20% Test | 25% Test | 30% Test |
|---|---:|---:|---:|
| KNeighborsClassifier | 0.5881 | 0.5865 | 0.5960 |
| MultinomialNB | 0.5434 | 0.5408 | 0.5613 |
| BernoulliNB | **0.6700** | **0.6322** | **0.6391** |
| DecisionTreeClassifier | 0.6129 | **0.6322** | 0.6109 |

### Cross-Validation

| Model | 10-Fold | Leave-One-Out |
|---|---:|---:|
| KNeighborsClassifier | 0.5520 | 0.5485 |
| MultinomialNB | 0.5216 | 0.5236 |
| BernoulliNB | 0.5967 | 0.5967 |
| DecisionTreeClassifier | **0.6047** | **0.6012** |

### Ensemble Accuracy

| Ensemble | 20% Test | 25% Test | 30% Test |
|---|---:|---:|---:|
| Baseline models | **0.6873** | **0.6600** | **0.6623** |
| Tuned models | 0.6799 | 0.6421 | 0.6424 |

The strongest saved tuned individual result is a decision tree with **0.7097** accuracy.

## Notebook 2 — From-Scratch Models and Missing Data

Three classifiers are implemented directly with NumPy/SciPy logic:

- vectorized Euclidean-distance k-NN
- Naive Bayes from class priors and conditional probabilities
- recursive binary decision trees with accuracy- and entropy-based split selection

### From-Scratch Accuracy

| Model | 20% Test | 25% Test | 30% Test |
|---|---:|---:|---:|
| k-NN | 0.6551 | 0.5984 | 0.6424 |
| Naive Bayes | 0.6675 | 0.6302 | 0.6407 |
| Decision tree — accuracy | **0.6774** | 0.6123 | 0.6308 |
| Decision tree — entropy | 0.6675 | **0.6302** | **0.6407** |

The larger dataset is then evaluated using mean, median, and regression-based missing-value estimation. The strongest saved tuned result after imputation is **0.6265** for the decision tree with regression-based estimates.

## Notebook 3 — Adaptive Model Wrapper Design

The final notebook presents common k-NN and decision-tree interfaces designed for both regression and classification. The default implementations are evaluated on California Housing, while the optimization interface defines task detection, validation splitting, preprocessing selection, hyperparameter search, and final retraining.

### Saved California Housing Results

| Model | MAE | MSE |
|---|---:|---:|
| k-NN | 0.8152 | 1.1420 |
| Decision tree | **0.4571** | **0.5235** |

## Skills Demonstrated

- supervised classification
- k-nearest neighbors
- Naive Bayes
- decision trees
- ensemble voting
- cross-validation
- hyperparameter tuning
- model comparison
- feature normalization
- missing-data handling
- regression-based imputation
- from-scratch machine-learning implementation
- recursive tree construction
- vectorized distance computation
- reusable model-interface design

## Tools

Python, NumPy, Pandas, SciPy, scikit-learn, TensorFlow/Keras, Matplotlib, Jupyter Notebook

## Reproducibility

The two Excel datasets are included in the `data/` directory. Notebook paths are repository-relative, so the project can be run locally, in VS Code/Jupyter, or after cloning the repository into Google Colab.
