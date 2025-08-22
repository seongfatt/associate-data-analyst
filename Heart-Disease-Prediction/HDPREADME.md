# Project Summary: Cardio Data Analysis and Classification

**Project Purpose**
The primary objective of this project was to perform a comprehensive data analysis and build a classification model to predict the presence of heart disease based on various health and lifestyle factors. The project aims to identify key risk factors and evaluate the performance of different machine learning models.

**Methodology & Process**
The project followed a structured machine learning workflow, from raw data to model evaluation.

1.  **Data Cleaning & Preprocessing**
    The initial raw data (`cardio_data.csv`) required significant cleaning to ensure data quality and prepare it for modeling.
    * **Data Loading and Inspection:** The CSV file was loaded into a pandas DataFrame. The `data.info()` and `data.describe()` functions were used to inspect data types, missing values, and statistical summaries.
    * **Data Type Conversion:** The `date` column was converted from an object to a proper datetime format. Categorical columns like `country`, `gender`, and `occupation` were encoded into numerical representations using `LabelEncoder`.
    * **Feature Transformation:** The `age` column, which was in days, was converted to years for better interpretability.
    * **Missing Value Handling:** Missing values, particularly in the `date` column, were addressed using forward fill (`ffill`) imputation.
    * **Outlier Treatment:** Outliers in the `ap_hi` (systolic blood pressure) column were removed using the Interquartile Range (IQR) method to improve model robustness.

2.  **Feature Engineering**
    A new feature, BMI (Body Mass Index), was created to provide a more comprehensive measure of a person's weight relative to their height.
    * **BMI Calculation:** `BMI = weight / (height / 100)^2`

3.  **Exploratory Data Analysis (EDA) & Visualization**
    A series of visualizations were created using `matplotlib` and `seaborn` to gain insights into the data and the relationships between variables.
    * **Bar Chart:** A stacked bar chart was used to visualize the distribution of heart disease across different countries.
    * **Histograms & Distribution Plots:** Histograms and KDE plots were generated to compare the age, cholesterol, and glucose distributions between patients with and without heart disease.
    * **Box Plots:** Box plots were used to visualize the distribution of systolic and diastolic blood pressure (`ap_hi`, `ap_lo`) for different disease statuses, revealing potential differences in these vital signs.
    * **Count Plots:** Count plots were created to compare lifestyle factors such as smoking, alcohol consumption, and physical activity between the two disease groups.
    * **Correlation Heatmap:** A heatmap was generated to visualize the correlation matrix of all numerical features, helping to identify potential multicollinearity.
    * **Pair Plot:** A `pairplot` was used to visualize the pairwise relationships between key numerical variables (`age`, `ap_hi`, `ap_lo`, `cholesterol`, `gluc`) for both disease statuses.

4.  **Model Building & Evaluation**
    The dataset was split into training and testing sets, and features were standardized using `StandardScaler`. Three classification models were trained and evaluated.
    * **Model Selection:** Logistic Regression, Random Forest, and Gradient Boosting were chosen for their effectiveness in classification tasks.
    * **Training & Prediction:** Each model was trained on the standardized training data (`X_train`) and used to make predictions on the test set (`X_test`).
    * **Performance Metrics:** The models were evaluated using several key metrics:
        * **Accuracy Score:** The proportion of correctly classified instances.
        * **Precision, Recall, F1-Score:** Metrics from the `classification_report` to assess the model's performance for each class (diseased vs. non-diseased).
        * **ROC Curve & AUC:** The ROC curve was plotted to visualize the trade-off between the true positive rate and false positive rate, with the Area Under the Curve (AUC) providing a single value to compare model performance.
    * **Model Interpretation:** Feature importance from the Random Forest model was visualized to identify which features were most influential in the prediction of heart disease. A confusion matrix was also generated to provide a detailed breakdown of correct and incorrect predictions.

**Key Technologies Used**
* **Python:** The core language for the entire analysis.
* **Pandas:** For data manipulation and cleaning.
* **NumPy:** For numerical operations.
* **Scikit-learn:** For data splitting, standardization, and machine learning models (Logistic Regression, RandomForestClassifier, GradientBoostingClassifier) and evaluation metrics.
* **Matplotlib & Seaborn:** For creating a wide range of insightful visualizations.

**Conclusion**
The project successfully transformed raw cardio data into a clean, structured dataset suitable for machine learning. The analysis identified key relationships between lifestyle factors, blood pressure, and heart disease. The trained models, particularly Gradient Boosting, showed promising results in predicting heart disease, with a focus on interpretability through feature importance and the confusion matrix. The visualizations provide a clear and intuitive way for stakeholders to understand the underlying risk factors.
