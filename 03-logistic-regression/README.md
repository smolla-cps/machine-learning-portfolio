# Logistic Regression

This portfolio section explores multiclass logistic regression through both **scikit-learn** and **TensorFlow/Keras** using the MNIST handwritten-digit dataset.

The material is organized into two complementary notebooks. Repeated implementations are consolidated, while every distinct technical experiment is retained.

## Repository Structure

```text
03-logistic-regression/
├── README.md
├── requirements.txt
└── notebooks/
    ├── 01_logistic_regression_with_sklearn_mnist.ipynb
    └── 02_logistic_regression_with_tensorflow_mnist.ipynb
```

## Notebook 1 — MNIST Logistic Regression with scikit-learn

**Goal:** Build, interpret, and manually reconstruct a multiclass logistic-regression model.

### Technical Progression

1. Normalize and reshape MNIST images.
2. Train a baseline multiclass logistic-regression model.
3. Compare training and test accuracy.
4. Inspect the confusion matrix.
5. Visualize class-specific learned coefficient vectors.
6. Examine `predict_proba()` class probabilities.
7. Add squared pixel features.
8. Visualize linear and quadratic coefficient blocks.
9. Reconstruct class scores from \(XW^T+b\).
10. Implement softmax and manually reproduce the class predictions.
11. Connect the multiclass softmax formulation to the binary sigmoid function.

### Results

| Model | Test Accuracy |
|---|---:|
| Original pixel features | 0.9256 |
| Original + squared pixel features | 0.9319 |
| Manual softmax reconstruction of baseline model | 0.9256 |

## Notebook 2 — MNIST Logistic Regression with TensorFlow

**Goal:** Compare linear and softmax output models while varying the loss function, feature representation, and linear-layer structure.

### Technical Progression

1. Build a single Dense linear reference model.
2. Add Softmax for multiclass probability output.
3. Compare MSE and categorical cross-entropy objectives.
4. Add quadratic pixel features.
5. Reevaluate linear and softmax models.
6. Add another linear Dense layer.
7. Compare learning curves and test metrics across configurations.

### Results

| TensorFlow Configuration | Test Accuracy |
|---|---:|
| Single Dense linear output, MSE | 0.8590 |
| Single Dense + Softmax, MSE | 0.9305 |
| Single Dense + Softmax, categorical cross-entropy | 0.9263 |
| Linear output + quadratic features | 0.8619 |
| Softmax + quadratic features | 0.9287 |
| Two stacked linear Dense layers | 0.8637 |
| Two stacked linear Dense layers + Softmax | 0.9305 |

## Content Coverage

The portfolio version retains every distinct logistic-regression experiment represented in the source material:

- scikit-learn multiclass logistic regression
- learned coefficient and intercept inspection
- coefficient-image visualization
- class-probability prediction
- quadratic pixel features
- direct score exponentiation and probability normalization
- reusable batch softmax
- one-dimensional sigmoid and softmax demonstrations
- manual prediction reconstruction from learned parameters
- TensorFlow linear reference models
- TensorFlow softmax models
- MSE and categorical-cross-entropy comparisons
- quadratic feature experiments
- stacked linear-layer experiments
- training and validation curves
- expanded feature-shape inspection

Repeated model definitions, incomplete duplicates, and foundational linear-algebra material already represented elsewhere in the portfolio are not duplicated here.

## Skills Demonstrated

- Multiclass logistic regression
- Softmax probabilities
- Sigmoid probability mapping
- Model coefficient interpretation
- Confusion-matrix analysis
- Manual prediction from learned parameters
- Quadratic feature engineering
- MNIST image classification
- TensorFlow/Keras model construction
- Loss-function comparison
- Training/validation curve analysis
- NumPy matrix operations
- scikit-learn workflows

## Tools

Python, NumPy, Matplotlib, scikit-learn, TensorFlow/Keras, Jupyter Notebook

## Notebook Naming Convention

Notebook filenames end with the dataset name so the modeling method and data source are immediately visible when browsing the repository.

Examples:

```text
01_logistic_regression_with_sklearn_mnist.ipynb
02_logistic_regression_with_tensorflow_mnist.ipynb
```

The same convention is used throughout the portfolio where a standard named dataset is available, such as `mnist`, `cifar10`, or `california_housing`.

## Reproducibility

MNIST is loaded through `tf.keras.datasets.mnist`, so no local data files are required. The notebooks can be opened in Jupyter, VS Code, or Google Colab. An internet connection may be required the first time MNIST is downloaded.

## Portfolio Organization Note

The general linear-algebra material used by these models is maintained in the introductory machine-learning section of the portfolio and is not duplicated here. This section focuses on the logistic-regression implementations and the distinct probability, feature-engineering, and TensorFlow experiments.
