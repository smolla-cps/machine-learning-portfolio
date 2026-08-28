# Naive Bayes Classifier

This portfolio section develops Naive Bayes from first principles and then compares multiple scikit-learn implementations on MNIST.

The organization preserves every distinct technical implementation and experiment represented in the supplied source notebooks while removing only true repetition.

## Repository Structure

```text
05-naive-bayes-classifier/
├── README.md
├── requirements.txt
└── notebooks/
    ├── 01_synthetic_mnist_naive_bayes_from_scratch.ipynb
    └── 02_mnist_naive_bayes_sklearn_comparison.ipynb
```

## Notebook 1 — Synthetic + MNIST Naive Bayes from Scratch

**Goal:** Build a binary-feature Naive Bayes classifier directly from class priors and conditional probabilities, then scale the same reasoning to MNIST.

### Technical Progression

1. Define priors and conditional probabilities for a three-class binary-feature problem.
2. Inspect individual conditional probabilities.
3. Compute raw class scores manually.
4. Implement classification with an attribute loop.
5. Implement two distinct vectorized probability-product formulations.
6. Load, normalize, flatten, and binarize MNIST.
7. Estimate class priors with both counting and vectorized calculations.
8. Estimate class-conditional pixel probabilities with both loop-based and vectorized calculations.
9. Visualize the 10 learned class-conditional probability maps.
10. Apply multiple from-scratch classifiers to MNIST.
11. Demonstrate floating-point underflow across 784 probability terms.
12. Apply probability smoothing.
13. Replace products with sums of logarithms for numerical stability.

### Selected Results

| Implementation | Test Accuracy |
|---|---:|
| Instance-level loop classifier | 0.8458 |
| Instance-level vectorized classifier | 0.8458 |
| Batch direct-product classifier | 0.8469 |
| Smoothed log-probability classifier | **0.8469** |

## Notebook 2 — MNIST Naive Bayes Comparison with scikit-learn

**Goal:** Compare multiple Naive Bayes model families and Bernoulli configurations on a common MNIST representation.

### Models and Configurations

- GaussianNB
- MultinomialNB
- ComplementNB
- BernoulliNB
- BernoulliNB with mean-based binarization
- BernoulliNB with 0.5 binarization
- BernoulliNB with mean-based binarization and `alpha=0.05`

### Results

| Model / Configuration | Test Accuracy |
|---|---:|
| GaussianNB | 0.5558 |
| MultinomialNB | 0.8357 |
| ComplementNB | 0.7286 |
| BernoulliNB | 0.8413 |
| BernoulliNB + mean binarization | 0.8462 |
| BernoulliNB + 0.5 binarization | 0.8427 |
| BernoulliNB + mean binarization + alpha=0.05 | **0.8465** |

## Content Coverage

The portfolio version retains all distinct technical content from the supplied sources:

- conditional-independence framing of Naive Bayes
- binary class-prior and feature-probability tables
- direct conditional-probability lookups
- manual class-score products
- loop-based binary-feature classification
- vectorized class-probability product
- `np.multiply.reduce` classification formulation
- MNIST normalization and binary thresholding
- inspection of the threshold and binary-pixel rate
- two class-prior estimation methods and their equality check
- two conditional-probability estimation methods and their equality check
- visualization of learned class-conditional pixel probabilities
- multiple direct-product MNIST prediction implementations
- zero-probability failure mode
- explicit numerical-underflow demonstration
- smoothing
- log-probability prediction
- GaussianNB
- MultinomialNB
- ComplementNB
- BernoulliNB
- mean-based Bernoulli binarization
- 0.5 Bernoulli binarization
- adjusted Bernoulli smoothing
- accuracy and confusion matrices for every supplied scikit-learn model

The repeated scikit-learn notebooks contain the same model code and are consolidated into one portfolio notebook. Blank cells, duplicated executions, source headers, and other nontechnical repetition are not retained.

## Skills Demonstrated

- Naive Bayes classification
- Bernoulli feature modeling
- Prior probability estimation
- Conditional probability estimation
- Conditional independence
- Vectorized probability computation
- Numerical stability
- Smoothing
- Log probabilities
- Confusion-matrix analysis
- MNIST image classification
- NumPy implementation
- scikit-learn Naive Bayes models

## Tools

Python, NumPy, Matplotlib, scikit-learn, TensorFlow/Keras, Jupyter Notebook

## Reproducibility

MNIST is loaded through `tf.keras.datasets.mnist`, so no local dataset files are required. An internet connection may be needed the first time the dataset is downloaded.
