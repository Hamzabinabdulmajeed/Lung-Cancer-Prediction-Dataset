# **Lung Cancer Risk Prediction: Clinical & Environmental Analysis**

This project provides an end-to-end machine learning framework for predicting lung cancer risk scores based on a robust dataset of **5,000 individuals** across **30 clinical and lifestyle features**. The analysis encompasses comprehensive data cleaning, statistical association studies, and high-performance predictive modelling using gradient-boosted decision trees.

---

## **1. Project Notebooks**
Access the full code and interactive visualisations via the links below:
*   **EDA & Statistical Analysis:** [Kaggle: EDA - Lung Cancer Prediction Dataset](https://www.kaggle.com/code/hamzabinbutt/eda-lung-cancer-prediction-dataset)
*   **Predictive Modelling & Tuning:** [Kaggle: Lung Cancer Prediction - Modelling](https://www.kaggle.com/code/hamzabinbutt/lung-cancer-prediction-dataset-modelling)

---

## **2. Methodology & Workflow**

### **Data Engineering & Preprocessing**
*   **Variable Mapping:** Categorical indicators were mapped from raw numeric codes into clinically meaningful labels for **gender**, **income levels**, and **dietary quality**.
*   **Dataset Dimensions:** The pipeline processes 29 feature columns, including demographics, clinical markers (e.g., `crp_level`, `fev1_x10`), and environmental factors (`air_pollution_index`, `radon_exposure`).

### **Exploratory Data Analysis (EDA)**
*   **Statistical Distributions:** Distributional analysis was conducted for **12 numerical variables** using box plots and **18 categorical variables** via frequency bar charts.
*   **Categorical Association:** **Cramér’s V** was implemented to quantify the strength of the relationship between categorical features and lung cancer risk. Significant associations were identified for `xray_abnormal` (0.75), `shortness_of_breath` (0.66), and `smoker` status (0.63).

### **Model Development & Benchmarking**
*   **Multi-Model Evaluation:** The training pipeline compared five distinct algorithms: **XGBoost, LightGBM, CatBoost, SVR, and Decision Tree Regressors**.
*   **Algorithm Selection:** **CatBoost** was identified as the champion model, yielding the lowest baseline **RMSE of 0.1439**.
*   **Bayesian Optimisation:** To further minimise error, an **Optuna study** was conducted over 30 trials to find the ideal hyperparameters, including a learning rate of approximately 0.033 and a model depth of 5.

---

## **3. Final Model Performance**
The final, optimised **CatBoost** regressor demonstrated exceptional precision in predicting risk scores, explaining nearly **90% of the variance** in the data.

| Metric | Value |
| :--- | :--- |
| **RMSE** (Root Mean Squared Error) | **0.1404** |
| **MAE** (Mean Absolute Error) | **0.0558** |
| **R² Score** | **0.8946** |

*Note: The RMSE indicates that, on average, the model's risk predictions are accurate within a very narrow margin.*

---

## **4. Clinical Predictors (Feature Importance)**
The model identified the following features as the most significant drivers of lung cancer risk:
1.  **pack_years**: The leading predictor, reflecting cumulative smoking intensity.
2.  **xray_abnormal**: Presence of radiological anomalies.
3.  **age**: Biological risk progression.
4.  **crp_level**: C-reactive protein, a marker of systemic inflammation.
5.  **air_pollution_index**: Environmental exposure impact.
6.  **copd**: History of Chronic Obstructive Pulmonary Disease.

---
