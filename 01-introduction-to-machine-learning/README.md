# Introduction to Machine Learning

This repository presents numerical foundations for machine learning and an end-to-end classification project with model comparison and performance evaluation.

## Repository Structure

```text
01-introduction-to-machine-learning/
├── README.md
├── requirements.txt
├── .gitignore
└── notebooks/
    ├── 01_numpy_for_machine_learning.ipynb
    └── 02_student_performance_classification.ipynb
```

## Notebooks

### 1. NumPy and Linear Algebra Foundations for Machine Learning

A focused numerical foundation for later machine-learning projects:

- Array creation, shape, data types, reshaping, indexing, and slicing
- References, views, and copying behavior
- Vectorized arithmetic and reductions
- Broadcasting and broadcasting compatibility
- Boolean indexing and data filtering
- Variance-based feature selection
- Dot product, Euclidean distance, and Manhattan distance
- Accuracy and mean-squared error
- Nearest-neighbor search with NumPy
- Matrix multiplication, identity, transpose, inverse, and pseudoinverse
- The common machine-learning transformation `X @ W + b`

### 2. Student Performance Classification and Model Evaluation

A two-feature classification problem demonstrates a complete supervised-learning and model-evaluation workflow:

- Generate and visualize a binary classification dataset
- Train Logistic Regression, 1-Nearest Neighbor, and Decision Tree classifiers
- Compare training and test accuracy
- Visualize model decision boundaries
- Implement a custom Nearest-Mean classifier
- Interpret true positives, true negatives, false positives, and false negatives
- Evaluate models with confusion matrices, precision, recall, and F1 score
- Extend evaluation to a four-class classification problem
- Implement accuracy, precision, recall, F1, and confusion-matrix calculations directly with NumPy

## Technical Highlights

- Numerical computing with NumPy
- Vectorized operations and linear algebra
- Supervised classification
- Decision-boundary analysis
- Train/test evaluation
- Binary and multiclass confusion matrices
- Precision, recall, and F1 score
- Custom classifier implementation
- Evaluation metrics implemented from scratch

## Tools

- Python
- NumPy
- Matplotlib
- scikit-learn
- Jupyter Notebook
