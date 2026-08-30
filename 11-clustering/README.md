# Clustering

This project explores three major clustering approaches across tabular, synthetic, and image data:

- hierarchical clustering
- density-based clustering with DBSCAN
- centroid-based clustering with k-means

The notebooks move from explicit distance calculations and dendrograms to density-based outlier identification and high-dimensional image clustering.

## Repository Structure

```text
11-clustering/
├── README.md
├── requirements.txt
├── data/
│   └── README.md
└── notebooks/
    ├── 01_mtcars_hierarchical_clustering.ipynb
    ├── 02_iris_dbscan_outlier_detection.ipynb
    └── 03_mnist_kmeans_cluster_centers.ipynb
```

## 1. mtcars — Hierarchical Clustering

This notebook combines real-data agglomerative clustering with two synthetic single-linkage examples.

### Methods

- complete-linkage dendrogram
- truncated dendrogram
- Ward + Euclidean agglomerative clustering
- average + Euclidean agglomerative clustering
- average + Manhattan agglomerative clustering
- manual pairwise Euclidean distance matrices
- single-linkage dendrograms

### Saved Direct Label-Agreement Results

| Configuration | Agreement |
|---|---:|
| Ward + Euclidean | 0.78125 |
| Average + Euclidean | 0.78125 |
| Average + Manhattan | 0.71875 |

Cluster identifiers are arbitrary, so these values are presented as the direct numerical agreement calculated by the implementation rather than as a permutation-invariant clustering score.

## 2. Iris — DBSCAN Clustering and Outlier Detection

The model uses:

```text
eps = 0.8
min_samples = 19
```

The saved run identifies six observations as noise:

```text
98, 105, 117, 118, 122, 131
```

The notebook retains the complete label vector, extracted noise observations, and two-dimensional visualization.

## 3. MNIST — k-Means Cluster Centers

MNIST images are normalized, flattened to 784 features, and clustered using:

```python
KMeans(n_clusters=30, random_state=0, n_init="auto")
```

The 30 learned centroids are reshaped to 28×28 images and displayed as visual cluster prototypes.

## Skills Demonstrated

- unsupervised learning
- hierarchical clustering
- agglomerative clustering
- dendrogram analysis
- single, complete, average, and Ward linkage
- Euclidean and Manhattan distance
- pairwise distance matrices
- DBSCAN
- density-based clustering
- outlier/noise detection
- k-means clustering
- centroid visualization
- image clustering
- NumPy
- Pandas
- Matplotlib
- SciPy
- scikit-learn
- TensorFlow/Keras

## Reproducibility

The hierarchical-clustering notebook expects `data/mtcars.csv`, and the DBSCAN notebook expects `data/iris.data.csv`. The MNIST notebook downloads the dataset through TensorFlow/Keras.
