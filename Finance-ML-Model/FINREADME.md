# Finance Machine Learning Model

### Project Summary

This project outlines a data science workflow for predicting loan default status. The primary purpose is to prepare a loan dataset for machine learning model training. The process is divided into two key stages: Data Cleaning and Data Preprocessing.

#### **Process**

The project followed a structured approach to ensure data quality and readiness for modeling:

**1. Data Cleaning**
* **Data Loading:** The process began by loading the `loan.csv` dataset into a pandas DataFrame.
* **Handling Missing Values:** Rows with missing values in critical columns (`loan_amount`, `interest_rate`, `loan_term`, `credit_score`, and `default_status`) were removed.
* **Date Conversion:** Date columns (`application_date`, `approval_date`, `disbursement_date`, and `due_date`) were converted to a datetime format. Rows with invalid dates, which resulted in `NaT` (Not a Time) after conversion, were dropped to ensure data integrity.
* **Duplicate Removal:** A check for duplicate rows was performed, and duplicates were removed to prevent data redundancy and potential biases in the analysis.

**2. Data Preprocessing**
* **Column Separation:** The cleaned dataset was prepared for a machine learning model by identifying and separating numerical and categorical features. The numerical columns were `loan_amount`, `interest_rate`, `loan_term`, and `credit_score`, while the categorical columns included `loan_type`, `employment_type`, `income_level`, `gender`, `marital_status`, and `education_level`.
* **Future Steps:** The project is set up to continue with further preprocessing steps, such as scaling numerical features and applying one-hot encoding to categorical features, which is typically done using scikit-learn pipelines.
