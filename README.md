# Predicting Cognitive Decline in Parkinson's Disease Patients using Machine Learning

[cite_start]This project explores the use of machine learning algorithms to predict cognitive decline in individuals with Parkinson's disease. [cite_start]The core of the study involves analyzing biomarkers to forecast the progression of cognitive impairment.

## Project Overview

[cite_start]The primary goal of this research is to investigate the applicability of machine learning in the medical field, specifically for predicting cognitive decline in Parkinson's patients. [cite_start]The study utilizes a dataset of 197 patients, focusing on biomarkers relevant to this condition.

[cite_start]The model's target variable is Pitch Period Entropy (PPE), which serves as an indicator of a patient's neural state[cite: 8]. [cite_start]As Parkinson's disease advances, speech becomes impaired, leading to an increase in the PPE value. [cite_start]By analyzing the influence of other biomarkers on PPE, the project aims to accurately predict the level of cognitive decline.

Two primary machine learning models were employed and compared:
* [cite_start]**Linear Regression**: Chosen for its ability to model relationships between a target and multiple variables and to interpret the influence of different factors through its coefficients.
* [cite_start]**Random Forest**: Utilized for its high prediction accuracy and its effectiveness in handling complex, non-linear relationships and measuring feature importance.

## Methodology

### Feature Selection
To identify the most influential biomarkers for predicting PPE, a two-step process was used:
1.  [cite_start]**Correlation Matrix**: A correlation matrix was generated to study the relationship between each biomarker and PPE. [cite_start]Variables with absolute correlation values close to 1 were initially considered significant.
2.  [cite_start]**P-value Calculation**: The p-value was calculated for each biomarker to test the null hypothesis (i.e., no relationship with the target variable). [cite_start]A small p-value (≤ 0.05) indicates that the variable has a statistically significant effect on the target.

[cite_start]Based on this analysis, the following biomarkers were selected as the most relevant features for predicting cognitive decline: **MDVP:PPQ, MDVP: Jitter(%), MDVP: Shimmer, RPDE, DFA, spread1, spread2, and D2**.

### Implementation
[cite_start]The project was developed using several Python libraries:
* [cite_start]**Pandas**: For data manipulation and creating DataFrames to compare results.
* [cite_start]**Scikit-learn**: For data splitting, model training (Linear Regression and Random Forest), and calculating performance metrics (MSE and R² score).
* [cite_start]**Seaborn** and **Matplotlib**: For data visualization, including creating scatter plots.

[cite_start]The dataset was preprocessed using `StandardScaler` to normalize the feature data, a common practice for Linear Regression models. [cite_start]The data was then split into three sets: 60% for training (117 cases), 20% for validation (39 cases), and 20% for testing (39 cases).

## Results

[cite_start]The performance of both the Linear Regression and Random Forest models was evaluated using Mean Squared Error (MSE) and the R-squared (R²) score. [cite_start]A lower MSE and a higher R² score indicate better model performance.

### Performance Metrics

| Model | Data Set | Mean Squared Error (MSE) | R² Score |
| :--- | :--- | :--- | :--- |
| **Linear Regression** | Validation | [cite_start]0.00074 | [cite_start]0.89 |
| **Random Forest** | Validation | [cite_start]0.00058 | [cite_start]0.92 |
| **Linear Regression** | Test | [cite_start]0.00051 | [cite_start]0.91 |
| **Random Forest** | Test | [cite_start]0.00037 | [cite_start]0.94 |

[cite_start]The results show that while both models performed well, the **Random Forest algorithm marginally outperformed the Linear Regression model** on both the validation and test sets, making it the more robust choice for this specific problem.

### Visualizations

[cite_start]To visually assess the models' accuracy, scatter plots were generated comparing the actual PPE values against the values predicted by each model on the test set.
