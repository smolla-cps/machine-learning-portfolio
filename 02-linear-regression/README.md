# Linear Regression

This section of the machine-learning portfolio explores linear regression across regression, feature-engineering, and multiclass prediction tasks.

The material is organized into two coherent notebooks. All distinct technical implementations are retained, while repeated versions and incomplete duplicate templates are removed.

## Repository Structure

```text
02-linear-regression/
├── README.md
├── requirements.txt
├── data/
│   ├── particles_X.npy
│   └── particles_y.npy
└── notebooks/
    ├── 01_linear_regression_and_feature_engineering.ipynb
    └── 02_mnist_classification_with_linear_regression.ipynb
```

## Notebook 1 — Linear Regression and Feature Engineering

**Goal:** Develop an interpretable regression workflow and examine how feature representation affects model performance across synthetic, housing, and large numerical datasets.

### Technical Progression

1. Recover a known linear relationship from noisy synthetic data.
2. Interpret the learned coefficient and intercept.
3. Establish a baseline on a nonlinear quadratic relationship.
4. Add a quadratic feature to represent nonlinear structure.
5. Apply linear regression to the California Housing dataset.
6. Evaluate prediction clipping and squared-feature expansion.
7. Apply the same modeling framework to a large particle dataset.
8. Compare baseline, scaling, squared features, and pairwise interactions.

### Selected Results

| Experiment | Test Metric |
|---|---:|
| Quadratic baseline MSE | 0.12208 |
| Quadratic + \(X^2\) MSE | 0.04786 |
| California Housing baseline MSE | 0.54565 |
| California Housing + squared features MSE | 0.50562 |
| Particle baseline test MSE | 0.04337 |
| Particle + squared features test MSE | 0.03958 |
| Particle + pairwise interactions test MSE | 0.03913 |

**Key point:** Linear regression becomes more expressive when nonlinear structure is introduced through the feature representation.

## Notebook 2 — MNIST Classification with Linear Regression

**Goal:** Examine how target encoding and nonlinear pixel features affect the behavior of a regression estimator on a multiclass image-classification task.

### Technical Progression

1. Normalize and reshape MNIST images.
2. Use continuous digit labels as the first regression target.
3. Round and clip predictions to obtain class labels.
4. Implement one-hot encoding using multiple NumPy approaches.
5. Train linear regression using one-hot targets.
6. Interpret regression outputs as class scores.
7. Add squared pixel-intensity features.
8. Compare accuracy, MSE, MAE, and confusion matrices.

### Results

| Representation | Accuracy |
|---|---:|
| Continuous label + rounding | 0.2300 |
| One-hot targets | 0.8601 |
| One-hot targets + squared pixel features | 0.8900 |

**Key point:** The representation of the prediction target has a major effect on model behavior in multiclass problems.

## Skills Demonstrated

- Linear regression
- Train/test evaluation
- MSE and MAE
- Coefficient interpretation
- Feature engineering
- Polynomial features
- Pairwise interaction features
- Feature scaling
- Large numerical datasets
- California Housing
- MNIST image data
- One-hot encoding
- Confusion matrices
- NumPy vectorization
- scikit-learn workflows

## Tools

Python, NumPy, pandas, Matplotlib, scikit-learn, TensorFlow/Keras, Jupyter Notebook

## Running the Project

The particle data are stored under `data/`.

When running locally, execute the notebooks from the `notebooks/` directory. The particle-data code uses:

```python
PX = np.load('../data/particles_X.npy')
Py = np.load('../data/particles_y.npy')
```

The first notebook also includes an optional Google Colab repository-setup cell. When the notebook is opened directly from GitHub in Colab, that setup clones the complete repository so the `data/` folder is available.
