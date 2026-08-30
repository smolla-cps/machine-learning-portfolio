# Support Vector Machines

This portfolio project explores Support Vector Machines through geometric visualization and a real-data classification application.

The first notebook focuses on the mechanics of a linear SVM in two dimensions, including support vectors, regularization, the separating hyperplane, dual coefficients, and manual reconstruction of the model's predictions. The second notebook applies an SVM classifier to water-potability data and evaluates its behavior through accuracy and the confusion matrix.

## Repository Structure

```text
09-support-vector-machines/
├── README.md
├── requirements.txt
├── data/
│   ├── README.md
│   └── water_potability.xlsx
└── notebooks/
    ├── 01_synthetic_2d_linear_svm_geometry.ipynb
    └── 02_water_potability_svm_classification.ipynb
```

## 1. Synthetic 2D — Linear SVM Geometry

### Technical Progression

- generate a reproducible linearly separable 2D dataset
- visualize positive and negative classes
- fit a linear SVM
- identify and visualize support vectors
- compare `C = 0.1, 1, 10, 100`
- sweep `C = 0.01, 0.1, 1, 10, 100` on a second separable sample
- repeat the sweep with overlapping classes
- inspect signed dual coefficients
- reconstruct the decision scores manually
- reproduce predictions by thresholding at zero
- recover the primal weight vector from the support vectors

### Separable-Data Sweep

| C | Accuracy | Support Vectors |
|---:|---:|---:|
| 0.01 | 1.0000 | 90 |
| 0.10 | 1.0000 | 24 |
| 1.00 | 1.0000 | 6 |
| 10.00 | 1.0000 | 3 |
| 100.00 | 1.0000 | 3 |

### Overlapping-Data Sweep

| C | Accuracy | Support Vectors |
|---:|---:|---:|
| 0.01 | 0.9600 | 132 |
| 0.10 | 0.9667 | 58 |
| 1.00 | **0.9733** | 30 |
| 10.00 | **0.9733** | 18 |
| 100.00 | 0.9667 | 15 |

## 2. Water Potability — SVM Classification

The water-potability notebook uses nine measured attributes and a binary target.

### Saved Baseline Result

| Model | Test Accuracy |
|---|---:|
| Default `SVC()` | 0.6010 |

Confusion matrix:

```text
[[363   0]
 [241   0]]
```

The baseline predicts every test observation as non-potable, showing why confusion-matrix analysis is essential when evaluating an imbalanced binary classification result.

## Skills Demonstrated

- Support Vector Machines
- linear SVM geometry
- support vectors
- regularization parameter `C`
- separating hyperplanes
- dual coefficients
- manual decision-function reconstruction
- weight-vector recovery
- binary classification
- confusion matrices
- NumPy matrix operations
- scikit-learn SVC
- data loading with Pandas

## Tools

Python, NumPy, Pandas, Matplotlib, scikit-learn, Jupyter Notebook

## Reproducibility

The synthetic dataset is generated programmatically with a fixed NumPy seed. The water-potability dataset is included in the `data/` directory and loaded through a repository-relative path.
