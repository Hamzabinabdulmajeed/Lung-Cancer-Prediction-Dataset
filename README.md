# **Lung Cancer Risk Prediction: Machine Learning Project**

This project provides a comprehensive machine learning pipeline for predicting lung cancer risk scores based on a dataset of **5,000 individuals**. It follows a structured workflow from **Exploratory Data Analysis (EDA)** and clinical association studies to advanced **hyperparameter optimisation** using Optuna.

---

## **1. Project Notebooks**
*   **EDA Notebook:** [eda-lung-cancer-prediction-dataset.ipynb](https://colab.research.google.com/drive/example_eda_link) 
*   **Modelling Notebook:** [lung-cancer-prediction-dataset-modelling.ipynb](https://colab.research.google.com/drive/example_modelling_link)

---

## **2. Project Schedule (4-Week Breakdown)**

### **Week 1: Foundation & Planning (11 Total Hours)**
**Focus:** Data cleaning and identifying clinical associations.
*   **Day 1-2:** Environment setup and **data mapping** for 18 categorical variables (e.g., mapping `gender` and `income_level`).
*   **Day 3-4:** Generating **box plots** for 12 numerical variables and **bar charts** for categorical frequencies.
*   **Day 5:** Calculating **Cramér’s V** to determine the strength of relationships between features like `smoker` and `lung_cancer_risk`.

### **Week 2: Model Development (14 Total Hours)**
**Focus:** Building the supervised learning pipeline and algorithm benchmarking.
*   **Day 1:** Implementing an **80/20 stratified split** to ensure balanced risk distribution.
*   **Day 2-3:** Running baseline experiments with **XGBoost, LightGBM, CatBoost, SVR, and Decision Tree**.
*   **Day 4-5:** Evaluating results to identify **CatBoost** as the initial "Winner" with an RMSE of 0.1439.

### **Week 3: Refinement & Experimentation (17 Total Hours)**
**Focus:** Bayesian optimization to minimize prediction errors.
*   **Day 1-2:** Running **Randomised Search** and defining the objective function for the **Optuna study**.
*   **Day 3-4:** Executing **30 Optuna trials** to tune hyperparameters like `learning_rate` and `l2_leaf_reg`.
*   **Day 5:** Re-training the model with optimised parameters (e.g., iterations=625, depth=5).

### **Week 4: Polish & Presentation (9 Total Hours)**
**Focus:** Final validation and data-driven storytelling.
*   **Day 1-2:** Validating final metrics and creating the **Top 10 Clinical Predictors** chart.
*   **Day 3-5:** Generating **Actual vs. Predicted** scatterplots and completing final project documentation.

---

## **3. Final Model Performance**
The final **CatBoostRegressor**, optimized via Optuna, provides highly accurate risk predictions.

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **RMSE** | **0.1404** | Predictions are accurate within a very narrow margin. |
| **MAE** | **0.0558** | Low average magnitude of error. |
| **R² Score** | **0.8946** | Explains **~90% of the variance** in lung cancer risk. |

---

## **4. Top 10 Clinical Predictors**
The following features were identified as the most significant drivers of lung cancer risk in the model:
1.  **pack_years** (Highest Importance)
2.  **xray_abnormal**
3.  **age**
4.  **crp_level** (Inflammation marker)
5.  **air_pollution_index**
6.  **copd**
7.  **fev1_x10**
8.  **chronic_cough**
9.  **oxygen_saturation**
10. **family_history_cancer**

---

## **5. References**
*Note: These references provide external clinical and technical context and are not part of the primary sources.*

1.  **"Machine Learning for Lung Cancer Diagnosis: A Review"** - [Free Download](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10375005/)
2.  **"CatBoost: unbiased boosting with categorical features"** - [Free Download](https://arxiv.org/abs/1706.09516)
3.  **"C-reactive protein and lung cancer risk: a systematic review"** - [Free Download](https://academic.oup.com/jnci/article/101/8/570/913506)
4.  **"Air pollution and lung cancer: current evidence"** - [Free Download](https://link.springer.com/article/10.1007/s11869-021-01041-3)
5.  **"Algorithms for Hyperparameter Optimization" (Optuna Logic)** - [Free Download](https://proceedings.neurips.cc/paper/2011/file/86e8f7ab32cfd12577bc2619bc635690-Paper.pdf)
6.  **"Smoking intensity (pack-years) and lung cancer risk"** - [Free Download](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2856238/)
7.  **"Machine Learning in Healthcare Review"** - [Free Download](https://www.researchgate.net/publication/327042595_Machine_Learning_in_Healthcare_Review_and_Opportunities)
8.  **"COPD and Lung Cancer Pathways"** - [Free Download](https://err.ersjournals.com/content/29/157/200021)
9.  **"LightGBM: A Highly Efficient GBDT"** - [Free Download](https://proceedings.neurips.cc/paper/2017/file/6449f44a102fde848669bdd9d9bb628c-Paper.pdf)
10. **"XGBoost: A Scalable Tree Boosting System"** - [Free Download](https://arxiv.org/abs/1603.02754)
