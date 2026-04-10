# Boston Housing Analysis

### Problem Statement
Predict median house value (in $1000s) for Boston neighborhoods using 12 demographic and geographic features.

### Dataset
- **Source:** ISLP package (Boston dataset)
- **Observations:** 506 neighborhoods
- **Features:** 12 (crime rate, rooms, age, tax rate, pupil-teacher ratio, etc.)
- **Target:** `medv` (median house value)

### Methodology

| Step | Description |
| :--- | :--- |
| 1 | Data inspection (missing values, outliers, distributions) |
| 2 | Train/test split (80/20) |
| 3 | Simple linear regression (rm, lstat individually) |
| 4 | Multiple linear regression (all 12 features) |
| 5 | Feature selection using p-values (removed indus, age) |
| 6 | Collinearity check using VIF |
| 7 | Final model evaluation |

### Key Findings

| Predictor | Effect | Interpretation |
| :--- | :--- | :--- |
| `rm` (rooms) | Positive (+) | Each extra room adds ~$9,250 |
| `lstat` (lower status %) | Negative (-) | 1% increase lowers price by ~$970 |
| `crim` (crime rate) | Negative (-) | Higher crime = lower price |
| `nox` (pollution) | Negative (-) | Higher pollution = lower price |

### Model Performance

| Model | R-squared | RMSE |
| :--- | :--- | :--- |
| Simple (rm only) | 0.371 | $6,793 |
| Simple (lstat only) | 0.543 | $5,478 |
| Full (12 predictors) | 0.689 | $4,773 |
| **Final (10 predictors)** | **0.691** | **$4,762** |

### Key Insight
Removing `indus` and `age` (high p-values) improved model performance. More predictors is not always better.

### Visualizations

| Plot | What it shows |
| :--- | :--- |
| `rm_vs_medv.png` | Positive relationship: more rooms = higher price |
| `lstat_vs_medv.png` | Negative relationship: more poverty = lower price |
| `correlation_heatmap.png` | Collinearity between predictors (e.g., rad and tax) |
