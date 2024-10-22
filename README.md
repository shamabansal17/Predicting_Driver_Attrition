## Project Overview
This project focuses on predicting driver attrition for Ola, a leading ride-hailing service, using monthly driver data from 2019 and 2020. The goal is to determine whether a driver will leave the company based on demographic, tenure, and performance-related attributes. This analysis is crucial for addressing high driver churn, which negatively impacts driver morale and increases operational costs for acquiring new drivers.

## Dataset
The dataset `ola_driver.csv` includes the following key features:

- **MMMM-YY**: Reporting date (monthly)
- **Driver_ID**: Unique identifier for drivers
- **Age**: Driver's age
- **Gender**: Gender (0: Male, 1: Female)
- **City**: City code
- **Education_Level**: Education level (0: 10+, 1: 12+, 2: Graduate)
- **Income**: Monthly average income of the driver
- **Date_Of_Joining**: Joining date of the driver
- **LastWorkingDate**: Last working date (if applicable)
- **Joining Designation**: Designation at the time of joining
- **Grade**: Grade at the time of reporting
- **Total Business Value**: Total business value acquired by the driver in a month
- **Quarterly Rating**: Quarterly rating (1 to 5, higher is better)

## Key Concepts
- **Ensemble Learning**: Bagging and Boosting
- **KNN Imputation for Missing Values**
- **Class Imbalance Treatment**

## Objective
The primary objective is to predict driver attrition (whether a driver will leave the company), and perform the following tasks:
1. **Exploratory Data Analysis (EDA)**: Examine the dataset's structure and characteristics.
2. **Feature Engineering**: Create new features such as income growth and quarterly rating improvement.
3. **Class Imbalance Treatment**: Apply appropriate methods to handle imbalanced classes.
4. **Modeling**: Use ensemble learning methods (Bagging, Boosting) to predict driver attrition.
5. **Evaluation**: Evaluate model performance using classification reports and ROC AUC curves.

## Steps to Run the Project

1. **Data Preprocessing**:
   - Convert date-like features (e.g., `MMMM-YY`, `Date_Of_Joining`, `LastWorkingDate`) to appropriate data types.
   - Handle missing values using **KNN Imputation** for numerical features.
   - Aggregate data at the driver level using `Driver_ID`.
   
2. **Feature Engineering**:
   - Create a target column: `1` for drivers who left the company (i.e., `LastWorkingDate` is present), `0` otherwise.
   - Create new features:
     - `Quarterly_Rating_Improved`: `1` if quarterly rating has improved.
     - `Income_Increased`: `1` if monthly income has increased.

3. **Modeling**:
   - Apply ensemble methods: **Bagging** and **Boosting**.
   - Tune hyperparameters for model optimization.
   - Handle class imbalance using techniques like **SMOTE** or **class weighting**.

4. **Evaluation**:
   - Generate classification reports to evaluate precision, recall, and F1 scores.
   - Plot ROC AUC curves to assess model performance.

## Results & Insights
- Evaluate the classification performance using the confusion matrix, classification reports, and ROC AUC.
- Provide actionable insights on the key drivers of attrition and recommend strategies to retain drivers, including improving their experience based on tenure, income growth, and performance.

## Dependencies
- Python 3.x
- Libraries:
  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `xgboost`
  - `matplotlib`
  - `seaborn`
