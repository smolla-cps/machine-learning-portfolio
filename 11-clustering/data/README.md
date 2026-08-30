# Data

Two notebooks use local tabular datasets.

## `mtcars.csv`

Used by:

```text
notebooks/01_mtcars_hierarchical_clustering.ipynb
```

The notebook expects the standard `mtcars` columns used in the source implementation, including:

```text
mpg, disp, hp, wt, am
```

## `iris.data.csv`

Used by:

```text
notebooks/02_iris_dbscan_outlier_detection.ipynb
```

The file is read without a header and is expected to contain five columns in this order:

```text
Sepal Length, Sepal Width, Petal Length, Petal Width, Species
```

## MNIST

The k-means notebook loads MNIST directly through TensorFlow/Keras, so no local MNIST file is required.
