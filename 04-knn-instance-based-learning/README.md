# k-Nearest Neighbors and Instance-Based Learning

This portfolio section explores instance-based learning through classification and regression. The notebooks progress from interpretable synthetic decision boundaries to high-dimensional image classification and real-data regression.

## Repository Structure

```text
04-knn-instance-based-learning/
├── README.md
├── requirements.txt
└── notebooks/
    ├── 01_synthetic_blobs_knn_classification.ipynb
    ├── 02_mnist_fashion_mnist_knn_classification.ipynb
    └── 03_california_housing_knn_regression.ipynb
```

## 1. Synthetic Blobs — k-NN Classification

**Goal:** Visualize how neighborhood size and distance weighting affect local decision boundaries.

### Methods
- 1-NN and 3-NN
- Distance-weighted k-NN
- Decision-boundary visualization
- Accuracy and confusion matrices

### Selected Results

| Configuration | Test Accuracy |
|---|---:|
| 1-NN | 0.84 |
| 3-NN | 0.86 |
| Weighted 5-NN | 0.90 |
| Weighted 8-NN | **0.91** |

## 2. MNIST and Fashion-MNIST — k-NN Classification

**Goal:** Study instance-based classification in high-dimensional image spaces using both from-scratch and scikit-learn implementations.

### Methods
- Raw image and pixel inspection
- Simple baseline classifiers
- One-nearest-neighbor from scratch
- Vectorized Euclidean distance
- Custom confusion matrix
- Full k-NN implementation from scratch
- Class-mean prototype compression
- Neighbor-vote confidence
- Uniform and distance weighting
- Manhattan and Euclidean distances
- Constant-pixel feature removal
- Brute-force, KD-tree, and Ball-tree search

### Selected Results

| Experiment | Accuracy |
|---|---:|
| Vectorized 3-NN — MNIST | 0.9705 |
| Vectorized 3-NN — Fashion-MNIST | 0.8541 |
| Mean prototypes — MNIST | 0.8203 |
| Mean prototypes — Fashion-MNIST | 0.6768 |
| Best saved distance-weighted MNIST sweep | **0.9717** |
| Manhattan distance comparison | 0.9618 |
| Euclidean distance comparison | 0.9688 |

The vote-agreement analysis also shows that MNIST predictions supported by all five neighbors reach 0.9935 saved accuracy.

## 3. California Housing — k-NN Regression

**Goal:** Evaluate the influence of feature scaling, neighborhood size, weighting, and distance-computation strategy on instance-based regression.

### Methods
- Weighted and unweighted k-NN regression
- k-value sweeps
- Manual standardization
- MinMaxScaler and StandardScaler
- Custom k-NN regressor
- Four distance-computation strategies
- Brute-force hyperparameter search
- Efficient cumulative-neighbor evaluation

### Selected Results

| Representation | Best k | Test MSE |
|---|---:|---:|
| Raw features, weighted | 10 | 1.082650 |
| Standardized, weighted | 12 | 0.414660 |
| Min-Max scaled, weighted | **12** | **0.380764** |
| Min-Max scaled, uniform | 10 | 0.390547 |

## Skills Demonstrated

- Instance-based learning
- k-nearest-neighbor classification
- k-nearest-neighbor regression
- Distance metrics
- Uniform and weighted neighborhoods
- Hyperparameter selection
- Feature scaling
- Prototype-based compression
- Confidence analysis
- Confusion matrices
- Vectorized distance computation
- Runtime and memory analysis
- scikit-learn neighbor-search backends
- NumPy implementation of k-NN

## Tools

Python, NumPy, SciPy, Matplotlib, scikit-learn, TensorFlow/Keras, Jupyter Notebook

## Reproducibility

MNIST and Fashion-MNIST are loaded through TensorFlow/Keras. California Housing is loaded through scikit-learn. No local dataset files are required.

Some from-scratch k-NN cells intentionally construct large pairwise-distance arrays to demonstrate the algorithm directly. These cells can be computationally demanding on the complete image datasets; the scikit-learn implementations provide the practical optimized alternative.
