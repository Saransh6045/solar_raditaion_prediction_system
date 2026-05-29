
# Solar Radiation Prediction using Machine Learning

## Project Overview

This project focuses on predicting solar radiation values using multivariate time-series weather data. The goal is to build a regression model capable of learning temporal weather patterns and generating accurate radiation predictions.

The project was developed as part of a Kaggle machine learning workflow and includes preprocessing, feature engineering, model comparison, validation, and submission generation.

---

## Problem Statement

Solar radiation prediction plays an important role in:

* Solar energy forecasting
* Weather analysis
* Renewable energy optimization
* Climate-related studies

The task is formulated as a:

**Multivariate Time-Series Regression Problem**

where the model predicts radiation values from multiple weather and temporal features.

---

## Dataset

Dataset files used:

```text
train.csv
- Features + target column (Radiation)

test.csv
- Features only
```

Target variable:

```text
Radiation
```

---

## Workflow

### 1. Data Preprocessing

Performed:

* Dataset inspection
* Duplicate checking
* Missing value handling using train medians
* Datetime conversion
* Redundant column removal

---

### 2. Feature Engineering

Created temporal features from datetime:

* hour
* day
* month
* weekday
* sunrise_hour
* sunset_hour

Applied cyclic encoding on hourly data:

```python
hour_sin = sin(2π × hour / 24)
hour_cos = cos(2π × hour / 24)
```

This helps the model understand the cyclical nature of time.

---

### 3. Train-Validation Strategy

Used:

```text
Chronological Train-Validation Split
```

instead of random splitting to avoid time-series data leakage.

Split:

```text
80% → Training
20% → Validation
```

---

## Models Used

### Random Forest Regressor

Best performing model in the project.

---

## Evaluation Metric

Used:

```text
RMSE (Root Mean Squared Error)
```

Lower RMSE indicates better prediction performance.

---

## Results

| Model                           | RMSE  |
| ------------------------------- | ----- |
| Random Forest + Cyclic Encoding | 89.31 |

---

## Kaggle Submission

Generated predictions on test data and created:

```text
submission.csv
```

using the best-performing model.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Kaggle

---

## Future Improvements

Potential improvements:

* Hyperparameter tuning
* Advanced time-series validation
* Additional feature engineering
* Model ensembling
* LightGBM implementation

---

## Key Learnings

Through this project, I learned:

* Time-series regression workflows
* Preventing data leakage
* Feature engineering techniques
* Cyclic encoding for temporal data
* Model comparison and evaluation
* Kaggle submission pipeline

---
