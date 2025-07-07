Of course! Here is a cleaned-up and enhanced version of the README file.

---

# 🧠 Predicting Cognitive Decline in Parkinson's Disease

This project explores the use of machine learning algorithms to predict cognitive decline in individuals with Parkinson's disease. The core of the study involves analyzing key biomarkers to forecast the progression of cognitive impairment.

---

## 🎯 Project Overview

The primary goal of this research is to investigate the applicability of machine learning in the medical field, specifically for predicting cognitive decline in Parkinson's patients. The study utilizes a dataset of **197 patients**, focusing on biomarkers relevant to this condition.

The model's target variable is **Pitch Period Entropy (PPE)**, which serves as an indicator of a patient's neural state. As Parkinson's disease advances, speech becomes impaired, leading to an increase in the PPE value. By analyzing the influence of other biomarkers on PPE, the project aims to accurately predict the level of cognitive decline.

Two primary machine learning models were employed and compared:
* **Linear Regression**: Chosen for its ability to model relationships between a target and multiple variables and to interpret the influence of different factors through its coefficients.
* **Random Forest**: Utilized for its high prediction accuracy and its effectiveness in handling complex, non-linear relationships and measuring feature importance.

---

## ⚙️ Methodology

### Feature Selection
To identify the most influential biomarkers for predicting PPE, a two-step process was used:
1.  **Correlation Matrix**: A correlation matrix was generated to study the relationship between each biomarker and PPE. Variables with absolute correlation values close to 1 were initially considered significant.
2.  **P-value Calculation**: The p-value was calculated for each biomarker to test the null hypothesis (i.e., no relationship with the target variable). A small p-value (≤ 0.05) indicates that the variable has a statistically significant effect on the target.

Based on this analysis, the following biomarkers were selected as the most relevant features: **MDVP:PPQ, MDVP: Jitter(%), MDVP: Shimmer, RPDE, DFA, spread1, spread2, and D2**.

### Implementation
The project was developed using several Python libraries:
* **Pandas**: For data manipulation and creating DataFrames.
* **Scikit-learn**: For data splitting, model training, and calculating performance metrics.
* **Seaborn** & **Matplotlib**: For data visualization and creating plots.

The dataset was preprocessed using `StandardScaler` to normalize the feature data. The data was then split into three sets: **60% for training** (117 cases), **20% for validation** (39 cases), and **20% for testing** (39 cases).

---

## 📊 Results

The performance of both models was evaluated using **Mean Squared Error (MSE)** and the **R-squared (R²)** score. A lower MSE and a higher R² score indicate better model performance.

### Performance Metrics

| Model | Data Set | Mean Squared Error (MSE) | R² Score |
| :--- | :--- | :--- | :--- |
| **Linear Regression** | Validation | 0.00074 | 0.89 |
| **Random Forest** | Validation | 0.00058 | 0.92 |
| **Linear Regression** | Test | 0.00051 | 0.91 |
| **Random Forest** | Test | 0.00037 | 0.94 |

The results show that while both models performed well, the **Random Forest algorithm marginally outperformed the Linear Regression model** on both the validation and test sets, making it the more robust choice for this specific problem.

### Visualizations
To visually assess model accuracy, scatter plots were generated comparing the actual PPE values against the values predicted by each model on the test set.
