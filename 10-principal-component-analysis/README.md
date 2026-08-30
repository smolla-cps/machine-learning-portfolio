# Principal Component Analysis

This project explores Principal Component Analysis (PCA) as both a dimensionality-reduction technique and a geometric transformation.

The MNIST study examines PCA components, orthogonality, manual transformation, explained variance, image reconstruction, reconstruction error, and downstream classification. A second study uses synthetic two-dimensional datasets to visualize how feature variance and correlation determine the learned principal directions.

## Repository Structure

```text
10-principal-component-analysis/
├── README.md
├── requirements.txt
└── notebooks/
    ├── 01_mnist_pca_dimensionality_reduction_and_classification.ipynb
    └── 02_synthetic_2d_pca_geometry.ipynb
```

## 1. MNIST — PCA Dimensionality Reduction and Classification

### Methods

- flatten and normalize MNIST images
- one-hot encode targets
- fit 30-component and 392-component PCA models
- inspect component dimensions and explained variances
- verify unit-length and orthogonal principal directions
- visualize principal components as 28×28 images
- reproduce the PCA transform manually
- compare manual and scikit-learn transformations
- analyze variance across principal components
- reconstruct images using increasing numbers of components
- measure reconstruction MSE
- evaluate Linear Regression, Logistic Regression, MLP, and Decision Tree classifiers on PCA features

### Selected Saved Results

| Experiment | Result |
|---|---:|
| Manual vs. library PCA transformation MSE | `1.8634e-14` |
| Reconstruction MSE — 5 components | `0.04491` |
| Reconstruction MSE — 390 components | `0.000324` |
| Linear Regression — best saved accuracy | `0.8623` |
| Logistic Regression — best saved accuracy | `0.9263` |
| MLP — best saved accuracy | `0.9793` |
| Randomized Decision Tree — best saved accuracy | `0.8465` |

## 2. Synthetic 2D — PCA Geometry

The geometric study contains five distinct data configurations:

1. isotropic Gaussian data
2. unequal feature scales
3. strong positive correlation
4. moderate positive correlation
5. negative correlation with principal-axis visualization

For each configuration, the experiment displays the original point cloud, transformed PCA coordinates, component matrix, data mean, and explained variance.

## Skills Demonstrated

- Principal Component Analysis
- dimensionality reduction
- orthogonal transformations
- explained variance
- image reconstruction
- reconstruction-error analysis
- feature-space visualization
- linear algebra with NumPy
- classification using reduced features
- scikit-learn PCA
- MNIST preprocessing
- TensorFlow/Keras dataset loading

## Tools

Python, NumPy, Matplotlib, scikit-learn, TensorFlow/Keras, Jupyter Notebook

## Reproducibility

MNIST is loaded directly through TensorFlow/Keras. The synthetic two-dimensional examples generate their data programmatically.
