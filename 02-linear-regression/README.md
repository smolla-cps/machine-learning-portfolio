# Linear Regression

This portfolio section explores linear regression from interpretable synthetic examples to real-data regression, nonlinear feature engineering, a large particle dataset, and an unconventional multiclass classification application.

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

## 1. Linear Regression and Feature Engineering

The first notebook develops the regression workflow across several datasets:

- Recover a known linear relationship from noisy synthetic data.
- Examine the limitation of a linear model on quadratic data.
- Add nonlinear features to improve the model representation.
- Apply linear regression to the California Housing dataset.
- Compare baseline and transformed representations on a large particle dataset.
- Evaluate scaling, squared features, and pairwise feature interactions.

### Selected Regression Results

| Experiment | MSE | MAE |
|---|---:|---:|
| Synthetic linear relationship | 0.048 | 0.172 |
| Quadratic baseline | 0.12208 | 0.26652 |
| Quadratic with squared feature | 0.04786 | 0.17521 |
| California Housing baseline | 0.54565 | 0.54147 |
| California Housing with clipped predictions | 0.52512 | 0.52926 |
| California Housing with squared features | 0.50562 | 0.52336 |

### Particle Dataset Results

The supplied particle dataset contains 1,774,943 observations and five numerical input features.

| Representation | Test MSE | Test MAE |
|---|---:|---:|
| Baseline linear features | 0.04438 | 0.16935 |
| Min-Max scaled features | 0.04421 | 0.16915 |
| Original + squared features | 0.05370 | 0.17975 |
| Original + pairwise interaction features | 0.04758 | 0.17363 |

The evaluated nonlinear expansions do not improve the particle-data baseline, demonstrating that increasing feature complexity should be justified by held-out performance.

## 2. MNIST Classification with Linear Regression

The second notebook examines how the same estimator behaves when adapted to a 10-class image-classification problem.

| Representation | Test Accuracy |
|---|---:|
| Continuous digit label + rounding | 0.2300 |
| One-hot target | 0.8601 |
| One-hot target + squared pixel features | 0.8900 |

This comparison highlights the effect of target encoding and feature representation on model performance.

## Technical Highlights

- Linear regression
- Train/test evaluation
- Mean squared error and mean absolute error
- Coefficient and intercept interpretation
- Feature scaling
- Polynomial feature expansion
- Pairwise interaction features
- California Housing dataset
- Large numerical dataset modeling
- One-hot encoding
- MNIST image classification
- Confusion matrices
- Feature representation analysis

## Tools

- Python
- NumPy
- Matplotlib
- scikit-learn
- TensorFlow / Keras
- Jupyter Notebook

## Running in Google Colab

The particle dataset is stored in `data/`. Opening a notebook directly from GitHub in Colab loads the notebook itself, but not the complete repository.

The first regression notebook therefore includes an optional Colab setup cell. When the particle data are not already available, the cell asks for the GitHub repository URL, clones the repository into Colab, and changes the working directory to:

```text
02-linear-regression/notebooks/
```

After that, the original relative data paths work normally:

```python
PX = np.load('../data/particles_X.npy')
Py = np.load('../data/particles_y.npy')
```

When the repository is cloned and run locally from the `notebooks/` folder, no Colab setup is required.

## Reproducibility Notes

The particle data files required by the first notebook are included under `data/`. The California Housing and MNIST datasets are loaded through their standard library interfaces; an internet connection may be required the first time those datasets are downloaded.
