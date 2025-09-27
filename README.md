# diabetes_prediction
Diabetes Prediction Project
1) Introduction:
This project aims to predict the chance of someone getting diabetes based on different health-related features. We explore the influence of various features on the diabetes target column within the given dataset. The motivation for this project stems from the high prevalence of diabetes and the potential for a data-driven analytical approach to aid in early detection, hypothesis generation regarding the disease, or even contribute to its cure. A significant challenge tackled in this study is the class imbalance, where the number of non-diabetic cases greatly outweighs diabetic cases. This real-world scenario demands careful evaluation metrics and resampling strategies.

2) Dataset Description:
The goal is to explore whether a person is diabetic (diabetes = 1) or not (diabetes = 0) from the dataset. The target column is 'diabetes', making this a classification problem with two classes: 0 (non-diabetic) and 1 (diabetic). The dataset contains the following 9 input features:

gender (categorical)
age (quantitative)
hypertension (binary/categorical)
heart_disease (binary/categorical)
smoking_history (categorical)
bmi (quantitative)
HbA1c_level (quantitative)
blood_glucose_level (quantitative)
diabetes (target variable - binary class)
After initial cleaning (removing the missing target labels), the dataset has around 90,000+ entries, with roughly 80,000 non-diabetic and <10,000 diabetic samples.

This indicates an imbalanced dataset. If models are trained without addressing this imbalance, they might tend to predict the majority class (non-diabetic) frequently, leading to high accuracy but poor performance in detecting actual diabetes cases. Therefore, techniques like SMOTE (Synthetic Minority Over-sampling Technique) and using models with class_weight='balanced' were employed.

3) Methodology:
The project followed these steps:

Data Loading: The diabetes dataset was loaded into a pandas DataFrame.
Exploratory Data Analysis (EDA): Initial exploration included viewing the head of the dataset, checking columns and shape, visualizing the class distribution of the target variable, and examining the correlation between features and the target.
Data Preprocessing:
Rows with missing target values were removed.
Missing values in numerical columns ('age', 'bmi', 'HbA1c_level', 'blood_glucose_level') were imputed using the median.
Missing values in categorical columns ('smoking_history', 'gender', 'hypertension', 'heart_disease') were filled with default values or 0.
Categorical features were encoded: 'gender' was mapped to numerical values, and 'smoking_history' was one-hot encoded.
Features were scaled using StandardScaler.
Handling Class Imbalance: SMOTE was applied to the training data to oversample the minority class (diabetic cases).
Model Training: Several classification models were trained on the processed data:
Logistic Regression (with class_weight='balanced')
K-Nearest Neighbors (KNN)
Decision Tree
Naive Bayes
Neural Network (MLP Classifier)
Model Evaluation: The trained models were evaluated using various metrics suitable for imbalanced datasets, including:
Classification Report (precision, recall, f1-score)
Confusion Matrix
ROC Curve and AUC Score
Accuracy Score
F1 Score
ROC AUC Score
4) Results and Discussion:
The models were evaluated based on their performance on the test set. The classification reports, confusion matrices, and ROC curves provided insights into how well each model performed, particularly in identifying the minority class (diabetic cases).

[Include a summary of the key findings from the model evaluation, e.g., which models performed best on recall or F1-score for the diabetic class, and any observations about the impact of SMOTE.]

The correlation analysis and feature importance from Logistic Regression highlighted the most influential features in predicting diabetes.

[Include a summary of the most important features identified.]

5) Conclusion:
This project demonstrated an approach to predicting diabetes using a dataset with class imbalance. By applying appropriate preprocessing and handling the imbalance, we were able to train and evaluate several classification models. The results provide a basis for understanding the factors influencing diabetes and the potential for using machine learning in its prediction. Further work could involve exploring more advanced modeling techniques, feature engineering, or hyperparameter tuning to improve performance.
