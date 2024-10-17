Diabetes Diagnosis Prediction
Project Overview
This project focuses on building a predictive model for diagnosing diabetes using the Behavioral Risk Factor Surveillance System (BRFSS) dataset. The dataset contains health-related behaviors and chronic conditions collected by the CDC. The objective is to develop machine learning models to accurately predict whether an individual has diabetes (binary classification).

Key Objectives:
Predict whether an individual has diabetes based on survey responses.
Prioritize recall to minimize false negatives (missed diagnoses).
Compare multiple machine learning models and apply techniques like SMOTE and threshold tuning to optimize model performance.
Dataset Information
The dataset contains 253,680 survey responses with 21 feature variables. The target variable is Diabetes_binary, where:

0 represents no diabetes,
1 represents prediabetes or diabetes.
Features:
The key features include:

HighBP: High blood pressure (0 = no, 1 = yes)
HighChol: High cholesterol (0 = no, 1 = yes)
BMI: Body Mass Index
PhysActivity: Physical activity in the past 30 days (0 = no, 1 = yes)
GenHlth: General health rating on a scale from 1 (excellent) to 5 (poor)
MentHlth: Days of poor mental health in the past 30 days
Age: Age group from 1 (18–24) to 13 (80 or older)
Models Used
Three machine learning models were implemented:

Logistic Regression
Random Forest Classifier
K-Nearest Neighbors (KNN)
Preprocessing:
Standardization: Features were standardized to ensure optimal model performance.
Handling Class Imbalance: SMOTE (Synthetic Minority Over-sampling Technique) was used to balance the dataset and improve performance on the minority class (diabetes).
Model Performance
Final Model: Random Forest Classifier
Accuracy: 91.76%
Recall for Class 1 (Diabetes): 95%
Precision for Class 1: 84%
The Random Forest model was chosen as the final model due to its superior performance in minimizing false negatives (high recall) and maintaining a good precision-recall balance. This model was particularly suited to a diabetes diagnosis task, where missing diabetes cases (false negatives) could have serious consequences.

Threshold Tuning:
Threshold tuning was performed to optimize the balance between precision and recall. A threshold of 0.3 was selected to maximize recall for diabetes prediction.

Explored Research Questions
Can survey questions asked from the CDC provide accurate predictions of whether an individual has diabetes?

Yes, the CDC’s BRFSS survey questions provide valuable features for predicting diabetes. However, additional features like medical history (e.g., family history of diabetes) or blood sugar levels could further enhance accuracy.
What risk factors are most predictive of diabetes risk?

The top predictive features identified by the Random Forest model include:
High Blood Pressure (HighBP)
BMI (Body Mass Index)
Age
General Health (GenHlth)
Physical Activity (PhysActivity)
Can a subset of the risk factors be used to predict diabetes?

Yes, using a subset of the most predictive features (such as HighBP, BMI, Age, GenHlth, and PhysActivity) can still provide high accuracy for diabetes prediction.
What machine learning models are best for classifying the disease?

After comparing Logistic Regression, Random Forest, and KNN, the Random Forest Classifier performed the best. It had the highest recall for class 1 (diabetes) and balanced precision well, making it ideal for this medical diagnosis problem.
Correlation Between Mental Health and Diabetes
Although mental health was not identified as a top predictor in the model, research indicates a bidirectional relationship between diabetes and mental health. Individuals diagnosed with diabetes are at a higher risk of developing mental health issues such as depression and anxiety. The survey question asked in the dataset, "For how many days during the past 30 days was your mental health not good?" captures short-term mental health but may not reflect the long-term mental health impacts of diabetes.

According to a study published in the Canadian Journal of Diabetes, diabetes can exacerbate mental health problems due to the stress of managing the disease. While the feature did not show a strong predictive correlation in this dataset, it is likely more relevant as a consequence of diabetes rather than a direct risk factor.

Running the Project
To run the project:

Install dependencies:

bash
pip install -r requirements.txt
Dataset:

The dataset used for this project should be preloaded into the environment. Make sure to have the diabetes_binary_classification_data.csv file in your working directory.
Running the Code:

bash
jupyter notebook diabetes_model.py
Results:

The script will output the evaluation metrics for each machine learning model, including precision, recall, accuracy, and ROC-AUC scores. Additionally, it will plot ROC curves to compare model performance.
Conclusion
The Random Forest Classifier with threshold tuning to 0.3 was selected as the final model for diabetes diagnosis. This model prioritizes recall, ensuring that the majority of diabetes cases are identified, which is critical in medical diagnosis tasks.

Future improvements could include incorporating more clinical features and lifestyle data to further improve model performance and generalizability across different populations.

References
Canadian Journal of Diabetes: Diabetes and Mental Health