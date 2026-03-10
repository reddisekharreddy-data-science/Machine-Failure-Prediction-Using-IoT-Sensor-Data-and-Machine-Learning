# Machine Failure Prediction Using IoT Sensor Data and Machine Learning

## Project Overview
This project develops a machine learning model to predict machine failures using IoT sensor data. Predictive maintenance helps industries detect potential failures early, reducing downtime, maintenance costs, and operational risks.

The model analyzes multiple machine operating parameters such as temperature, rotational speed, torque, and tool wear to estimate the probability of machine failure.

This project follows the complete **Data Science Life Cycle**, including data collection, preprocessing, outlier handling, feature engineering, model training, evaluation, and deployment preparation.

---

## Business Problem

Industrial machines generate large volumes of sensor data. Unexpected failures can cause:

- Production downtime
- High maintenance costs
- Safety risks
- Reduced operational efficiency

A predictive maintenance system can detect early warning signs of machine breakdown.

Examples:

Example 1  
High **torque and tool wear** may indicate mechanical stress.

Example 2  
High **temperature and rotational speed** may indicate overheating.

The goal is to build a machine learning model that predicts machine failure before it occurs.

---

## Dataset

Dataset used: **AI4I 2020 Predictive Maintenance Dataset**

Key features:

| Feature | Description |
|-------|-------------|
| Air temperature | Ambient machine temperature |
| Process temperature | Temperature during machine operation |
| Rotational speed | Machine rotation speed |
| Torque | Mechanical load on machine |
| Tool wear | Duration of tool usage |
| Machine type | Type of machine (L, M, H) |

Target variable:

Machine failure

---

## Data Science Lifecycle

The project follows a structured machine learning workflow:

1. Business Understanding
2. Data Collection (AWS S3)
3. Data Understanding (EDA)
4. Data Cleaning
5. Outlier Detection
6. Outlier Handling
7. Feature Engineering
8. Data Preparation
9. Handling Imbalanced Data (SMOTE)
10. Model Training
11. Model Evaluation
12. Model Deployment Preparation

---

## Data Preprocessing

The following preprocessing steps were applied:

- Missing value analysis
- Duplicate record check
- Outlier detection using boxplots
- Outlier handling using **IQR capping**
- Removal of identifier columns
- Removal of **data leakage features**
- One-hot encoding of categorical variables
- Feature scaling using **StandardScaler**

---

## Handling Imbalanced Data

The dataset contains approximately **3% failure cases**, which creates class imbalance.

To address this problem:

SMOTE (Synthetic Minority Oversampling Technique)

was applied to balance the training dataset.

---

## Machine Learning Model

Algorithm used:

Random Forest Classifier

Reasons for using Random Forest:

- Handles nonlinear relationships
- Robust to noisy data
- Performs well on tabular datasets
- Reduces overfitting through ensemble learning

Model parameters:

- n_estimators = 400
- max_depth = 12
- class_weight = balanced

---

## Model Evaluation

The model was evaluated using:

- Precision
- Recall
- F1 Score
- Accuracy

Example performance:

| Metric | Value |
|------|------|
Accuracy | ~97.5% |
Failure Precision | ~63% |
Failure Recall | ~69% |
F1 Score | ~66% |

The model successfully detects most machine failures while maintaining high overall accuracy.

---

## Example Prediction

Input sensor data:

Air temperature = 300 K  
Process temperature = 310 K  
Rotational speed = 1500 rpm  
Torque = 55 Nm  
Tool wear = 180 minutes  

Model prediction:

Machine Failure = 1

This indicates a high probability of machine failure.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- AWS S3
- SMOTE
- Random Forest

---

## Project Structure
Machine-Failure-Prediction
│
├── data
│ └── ai4i2020.csv
│
├── notebooks
│ └── IOT.ipynb
│
├── models
│ ├── machine_failure_model.pkl
│ └── scaler.pkl
│
└── README.md

---

## Future Improvements

Possible improvements include:

- Hyperparameter tuning with GridSearchCV
- Feature importance analysis
- ROC and Precision-Recall curves
- Real-time prediction system
- Deployment using AWS SageMaker or Streamlit

---

## Author

Reddisekhar Reddy Yarramaddu  
Data Science and Machine Learning Enthusiast
