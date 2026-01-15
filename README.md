```markdown
# Lung Cancer Prediction Dataset

This dataset contains clinical, lifestyle, and environmental information for **5,000 individuals**, designed to assist in predicting lung cancer risk using machine learning techniques.

## Dataset Overview
- **Total Entries:** 5,000.
- **Total Features:** 29 clinical and demographic independent variables.
- **Target Variable:** `lung_cancer_risk` (Binary: Yes/No).
- **Data Types:** All columns were initially recorded as integers (`int64`) before preprocessing.

## Data Dictionary
The features are categorised into several key areas affecting lung health:

### 1. Demographic & Socioeconomic
- **age:** Range 18 to 90 years (Mean: 54.57).
- **gender:** Initially encoded (0: Female, 1: Male).
- **income_level:** Ranked from 1 (Very Low) to 5 (Very High).
- **education_years:** Average of 11.5 years of schooling.

### 2. Smoking & Lifestyle Factors
- **smoker:** Current smoking status (Binary).
- **smoking_years:** Total years of active smoking (Max: 52 years).
- **cigarettes_per_day:** Daily consumption.
- **pack_years:** Calculated smoking intensity (Mean: 6.25).
- **exercise_hours_per_week:** Physical activity levels.
- **diet_quality:** Scale of 1 (Poor) to 5 (Excellent).

### 3. Environmental & Clinical Metrics
- **Exposures:** `air_pollution_index`, `occupational_exposure`, `radon_exposure`, and `passive_smoking`.
- **Medical History:** `family_history_cancer`, `copd`, `asthma`, `previous_tb`, and `chronic_cough`.
- **Biometrics:** `bmi`, `oxygen_saturation`, `fev1_x10` (Lung function), and `crp_level` (Inflammatory marker).

## Data Preprocessing
To improve interpretability during analysis, the following mappings were applied to categorical variables:
- **Binary Variables:** 0 mapped to 'No', 1 mapped to 'Yes' (e.g., `smoker`, `fatigue`, `xray_abnormal`).
- **Quality Scales:** 1–5 scale mapped to 'Poor', 'Fair', 'Average', 'Good', and 'Excellent' (e.g., `diet_quality`, `healthcare_access`).
- **Socioeconomic:** 1–5 scale for `income_level` mapped to 'Very Low' through 'Very High'.

## Exploratory Data Analysis (EDA)
- **Target Distribution:** The dataset is imbalanced, with approximately **22.5%** (1,126) of individuals at risk of lung cancer and **77.5%** (3,874) not at risk.
- **Statistical Associations:** Using **Cramér’s V** to measure association strength (where >0.3 is strong), the highest associations with `lung_cancer_risk` were:
    - `xray_abnormal`: 0.75
    - `shortness_of_breath`: 0.66
    - `smoker`: 0.63
    - `chronic_cough`: 0.63
    - `copd`: 0.62

## Machine Learning Modelling
The modelling objective was to predict the risk score using a split of **80% training** (4,000 samples) and **20% testing** (1,000 samples).

### Model Comparison
Five models were evaluated based on Root Mean Squared Error (RMSE):
1. **CatBoost:** RMSE 0.1439 (Winner).
2. **LightGBM:** RMSE 0.1531.
3. **XGBoost:** RMSE 0.1664.
4. **SVR:** RMSE 0.2025.
5. **Decision Tree:** RMSE 0.2408.

### Final Optimized Model
The CatBoost model was fine-tuned using **Optuna** to minimize prediction error. The final model achieved:
- **RMSE:** 0.1404
- **MAE:** 0.0558
- **R² Score:** 0.8946 (Explaining ~90% of the variance in cancer risk)

## Key Predictors
According to the final model's feature importance, the top factors driving lung cancer risk are:
1. **pack_years** (Significantly highest importance)
2. **xray_abnormal**
3. **age**
4. **crp_level**
5. **air_pollution_index**
6. **copd**
```
