# 🩺 Liver Cirrhosis Stage Prediction

# 📌 Project Overview
This project aims to develop a machine learning model that can accurately predict the histological stage of liver cirrhosis using a dataset of patient clinical information. The goal is to create a reliable classification model that can aid in the early diagnosis and treatment planning for this disease. The notebook details the entire process from data cleaning to model evaluation, focusing on two classification models: **Random Forest** and **XGBoost**.

# 📊 Dataset
The dataset, provided in a TSV file named 1A.tsv, contains clinical data for **418** patients across **18** variables. These variables include patient demographics, drug types, and various medical test results crucial for assessing liver health.

# 🔍 Key Findings
1. The most influential features for predicting cirrhosis stage were **SGOT, Copper, Alkaline Phospatase (U/L), Hepatomegaly, and Bilirubin**, which are all clinically relevant indicators of liver health.
2. The models performed well in predicting later stages of cirrhosis (Stage 4) but struggled with the earlier stages (Stage 1 and 2), highlighting a common challenge with imbalanced medical datasets.
3. Hyperparameter tuning on both models resulted in only minor improvements to overall performance.

# 📈 Steps
1. **Data Cleaning**: Dropped irrelevant columns like ID and Registration Date. Engineered a new feature, **Age**, from the Birth Date column. Handled missing values through a combination of stage-specific imputation for variables with discernible patterns, KNNImputer for others, and row removal for insignificant missing data. Standardized inconsistent categorical data entries. The final dataset size was **399 rows and 15 columns**.
2. **Preprocessing**: The data was split into training and testing sets. Categorical variables were converted into numerical formats using binary encoding, LabelEncoder, and OrdinalEncoder. To address class imbalance in the target variable Stage, **SMOTE (Synthetic Minority Over-sampling Technique)** was applied to the training data.
3. **Modeling and Evaluation**: Two classification models, **Random Forest** and **XGBoost**, were built and evaluated using **precision, recall, and f1-score** to ensure a balanced performance, as both false positives and false negatives carry significant weight in a medical context. **GridSearchCV** was used for hyperparameter tuning to optimize model performance.

# 💡 Conclusion
The **Random Forest Classifier** emerged as the better-performing model with a post-tuning accuracy of **64%**. While it showed strong predictive capabilities for advanced stages of cirrhosis, it had difficulty accurately classifying earlier stages. The feature importance analysis confirmed that the model relies on key clinical indicators for its predictions, demonstrating its potential as a supplementary diagnostic tool.

# 🔮 Possible Future Works
1. **Advanced Sampling Techniques**: Explore other oversampling or undersampling methods to better address the class imbalance for earlier stages of cirrhosis.
2. **Alternative Models**: Experiment with other machine learning models, such as support vector machines or neural networks, to see if they can achieve better performance.
3. **Larger Dataset**: A larger and more balanced dataset would help improve the model's ability to accurately predict all stages of the disease.
4. **Outlier Analysis**: Conduct a deeper analysis of the outliers to determine if they represent unique patient cases that provide valuable information rather than noise.

# 👨‍💻 Author
Liliana Djaja Witama | Undergraduate Data Science Student at BINUS University
