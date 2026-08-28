# Water Potability Data

Two Excel datasets are included for reproducibility.

## `water_potability.xlsx`

- 2,011 complete observations
- 9 predictor variables
- binary `Potability` target
- class distribution: 1,200 not potable and 811 potable

## `water_potability_original.xlsx`

- 3,276 observations
- same 9 predictor variables and target
- missing values:
  - `ph`: 491
  - `Sulfate`: 781
  - `Trihalomethanes`: 162

## Variables

| Column | Role |
|---|---|
| `ph` | predictor |
| `Hardness` | predictor |
| `Solids` | predictor |
| `Chloramines` | predictor |
| `Sulfate` | predictor |
| `Conductivity` | predictor |
| `Organic_carbon` | predictor |
| `Trihalomethanes` | predictor |
| `Turbidity` | predictor |
| `Potability` | binary target |
