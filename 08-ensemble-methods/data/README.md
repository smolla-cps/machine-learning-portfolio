# Data

## GPU Runtime Regression

`03_gpu_runtime_regression_ensembles.ipynb` expects:

```text
gpu_running_time.csv
```

The notebook interprets:

- all columns except the final four as predictor variables
- the final four columns as repeated runtime measurements
- the mean of the final four measurements as the regression target
