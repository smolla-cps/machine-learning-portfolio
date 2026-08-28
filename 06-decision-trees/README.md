# Decision Trees

This portfolio section develops decision trees from their information-theoretic foundations through classification, regression, overfitting analysis, randomized trees, and ensemble comparison.



## Repository Structure

```text
06-decision-trees/
├── README.md
├── requirements.txt
└── notebooks/
    ├── 01_synthetic_binary_decision_tree_id3_foundations.ipynb
    ├── 02_iris_mnist_synthetic_blobs_decision_tree_classification.ipynb
    └── 03_california_housing_decision_tree_regression.ipynb
```

## 1. Synthetic Binary Data — ID3 Foundations

**Goal:** Build the logic of a decision tree from entropy and information gain, then reproduce the complete tree with scikit-learn.

### Technical Progression

- decision-tree structure
- use cases and interpretability
- ID3 workflow and pseudocode
- binary attribute-split analysis
- two entropy implementations
- entropy examples and entropy curve
- information-gain calculations
- recursive splitting and pure-node stopping
- complete tree construction
- numeric encoding of categorical attributes
- scikit-learn tree fitting
- depth 1, 2, 3, and 10 comparisons
- detailed and simplified tree visualizations

## 2. Iris, MNIST, and Synthetic Blobs — Classification

**Goal:** Evaluate decision-tree classification across tabular, synthetic, and high-dimensional image data while studying model complexity.

### Selected Results

| Dataset / Configuration | Test Accuracy |
|---|---:|
| Iris — entropy | **0.9667** |
| Synthetic pass/fail — entropy | 0.8900 |
| MNIST — entropy, best splitter | 0.8870 |
| MNIST — entropy, random splitter | 0.8818 |
| MNIST — Gini | 0.8780 |
| MNIST depth sweep — best saved result | **0.8893** |
| MNIST leaf sweep — best saved result | 0.8889 |

The MNIST depth and leaf sweeps retain both training and test accuracy so the progression from underfitting to overfitting is visible directly.

## 3. California Housing — Regression

**Goal:** Study regression-tree complexity, randomization, prediction averaging, and ensemble behavior.

### Selected Results

| Experiment | Test MSE |
|---|---:|
| Unrestricted regression tree | 0.527064 |
| Depth 3 | 0.6331 |
| Depth 4 | 0.5788 |
| Best depth (`max_depth=9`) | 0.423657 |
| Random splitter — average individual MSE | 0.604320 |
| Averaged predictions from randomized trees | **0.266055** |
| Averaged predictions from depth-30 best-split trees | 0.493030 |
| Random Forest | 0.26668 |

## Content Coverage

The portfolio retains the complete distinct technical progression represented across the supplied notebooks:

- decision-tree definition and interpretability
- conditions where decision trees are useful
- ID3 pseudocode and attribute selection
- complete eight-observation binary tree example
- majority-class split reasoning
- entropy formula and examples
- both source entropy implementations
- entropy-vs-probability visualization
- auxiliary NumPy mean calculation retained from the earlier implementation
- information-gain calculations for all candidate attributes
- recursive tree construction and every embedded tree/table illustration
- categorical-to-numeric encoding
- scikit-learn depth-controlled tree reconstruction
- entropy verification
- Iris classification and both tree visualizations
- synthetic pass/fail classification and visualization
- MNIST entropy/best, entropy/random, and Gini models
- MNIST maximum-depth sweep and accuracy plot
- MNIST maximum-leaf sweep and accuracy plot
- California Housing unrestricted regression tree
- depth-3 and depth-4 regression trees and visualization
- maximum-depth search
- regression train/test MSE curves
- 30-run random-splitter evaluation
- averaging predictions from randomized trees
- averaging repeated depth-30 best-split predictions
- RandomForestRegressor comparison

Only repeated copies of the same implementation, repeated source headers, blank cells, and duplicated setup material are consolidated.

## Skills Demonstrated

- Decision-tree classification
- Decision-tree regression
- ID3
- Entropy
- Information gain
- Gini impurity
- Tree visualization
- Hyperparameter tuning
- Overfitting analysis
- Randomized trees
- Prediction averaging
- Ensemble methods
- Confusion matrices
- Mean squared error
- scikit-learn
- NumPy
- TensorFlow dataset loading

## Tools

Python, NumPy, Matplotlib, scikit-learn, TensorFlow/Keras, Jupyter Notebook

## Reproducibility

Iris and California Housing are loaded through scikit-learn, while MNIST is loaded through TensorFlow/Keras. The synthetic datasets are generated programmatically, so no local dataset files are required.
