

#  Employee Retention Prediction

##  Project Overview

Employee retention is a critical concern for organizations, as high attrition leads to increased hiring costs and loss of experienced talent.
This project focuses on **predicting employee retention (stay vs leave)** using demographic, educational, and professional attributes of employees.

The task is formulated as a **binary classification problem**, where:

* `0` → Employee retained
* `1` → Employee left

A complete **machine learning pipeline** was built, including data preprocessing, exploratory data analysis, feature engineering, class imbalance handling, model training, and performance evaluation.

---

##  Objective

* Predict whether an employee is likely to leave the organization
* Handle real-world challenges like **missing values and class imbalance**
* Compare multiple machine learning models
* Identify **important features influencing attrition**

---

##  Dataset Description

The dataset contains employee-level information related to location, education, experience, and training.

### Key Features

* **enrollee_id** – Unique employee identifier
* **city** – City code
* **city_development_index** – Development index of the city
* **gender** – Gender of the employee
* **relevent_experience** – Whether the employee has relevant experience
* **enrolled_university** – University enrollment status
* **education_level** – Highest education qualification
* **major_discipline** – Field of study
* **experience** – Total professional experience (years)
* **company_size** – Size of the previous company
* **company_type** – Type of organization
* **last_new_job** – Time since last job change
* **training_hours** – Number of training hours completed
* **target** – Attrition label (0 = Retained, 1 = Left)

---

##  Tech Stack & Libraries

* **Language**: Python
* **Data Analysis**: Pandas, NumPy
* **Visualization**: Matplotlib, Seaborn
* **Machine Learning**: Scikit-learn, XGBoost
* **Imbalance Handling**: SMOTE (imblearn)

---

##  Data Preprocessing

Key preprocessing steps included:

* Handling missing values using **median and “Unknown” categories**
* Cleaning inconsistent numeric features:

  * `experience` (`<1`, `>20`, `10+`)
  * `last_new_job` (`never`, `>4`)
* Dropping non-informative columns:

  * `enrollee_id`, `city`, `company_type`, `company_size`, `gender`
* Encoding categorical variables using **One-Hot Encoding**
* Combining train & test datasets temporarily to ensure **consistent encoding**

---

##  Exploratory Data Analysis (EDA)

EDA was performed to understand data distribution and relationships.

### Key Observations:

* The dataset shows **class imbalance** (~75% retained, ~25% attrition)
* Training hours show **weak correlation** with attrition
* Numerical features exhibit limited linear correlation with the target
* Correlation heatmap confirms no strong multicollinearity issues

Visual analysis included:

* Target distribution plots
* Histograms for numerical features
* Boxplots for feature vs target comparison
* Correlation heatmap

---

##  Feature Engineering

* Converted categorical features using **one-hot encoding**
* Encoded `relevent_experience` into binary format
* Removed helper column after encoding (`__is_train`)
* Final dataset prepared for modeling with clean numerical inputs

---

##  Handling Class Imbalance

The dataset was imbalanced, which can bias predictions.

To address this:

* **SMOTE (Synthetic Minority Over-sampling Technique)** was applied
* Balanced the training data before model training
* Improved the model’s ability to detect employee attrition

---

##  Model Training

The following models were trained and compared:

* Logistic Regression
* Support Vector Machine (RBF Kernel)
* Random Forest Classifier
* XGBoost Classifier

### Scaling:

* Applied **StandardScaler** for Logistic Regression and SVM
* Tree-based models trained on unscaled data

---

##  Model Evaluation

Models were evaluated using:

* Accuracy
* Precision, Recall, F1-Score
* Confusion Matrix
* ROC-AUC Curve

### Key Results:

* Tree-based models performed better on imbalanced data
* **XGBoost achieved the best overall performance**
* ROC curves were plotted to visually compare classifiers

---

##  Feature Importance (XGBoost)

XGBoost feature importance was used to interpret model decisions.

Top contributing features included:

* City development index
* Relevant experience
* Education level
* Experience
* Last new job

This provides **actionable insights** into factors influencing employee retention.

---

##  Business Impact

This solution can help organizations:

* Identify employees at high risk of leaving
* Improve workforce planning
* Design better retention strategies
* Make data-driven HR decisions

---

##  Future Improvements

* Hyperparameter tuning with GridSearch / Bayesian Optimization
* SHAP or LIME for better explainability
* Model deployment using Streamlit or Flask
* Integration with HR dashboards (Power BI / Tableau)

---

##  Project Structure

```
Employee-Retention-Prediction/
│
├── data/
│   ├── aug_train.csv
│   └── aug_test.csv
│
├── notebook/
│   └── employee_retention_prediction.ipynb
│
│
├── README.md
└── requirements.txt

##  Author

**Apoorva V Dodwad**
 Aspiring Data Analyst | Data Scientist
 GitHub: [https://github.com/apoorva-2004](https://github.com/apoorva-2004)
 LinkedIn: linkedin.com/in/apoorva-dodwad-321ba6298


Just tell me 👍
