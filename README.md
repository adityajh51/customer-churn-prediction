# Customer Churn Prediction

## Project Overview

This project analyzes customer churn using exploratory data analysis, data cleaning, categorical encoding, multicollinearity analysis, and machine learning classification models.

The objective is to identify patterns associated with customer churn and evaluate classification models for predicting whether a customer is likely to churn.

## Dataset

The dataset contains **7,043 customer records and 21 variables** before data cleaning.

The target variable is:

- `Churn` — Indicates whether a customer churned

The dataset includes customer demographics, account information, subscribed services, contract details, payment methods, tenure, and billing information.

## Objectives

- Understand the structure and quality of the customer dataset
- Explore customer churn patterns
- Clean and prepare the data for machine learning
- Encode categorical variables
- Investigate multicollinearity using Variance Inflation Factor (VIF)
- Build Logistic Regression and Random Forest classification models
- Evaluate model performance using classification metrics

## Analysis & Methodology

### 1. Data Understanding

- Inspected dataset dimensions and data types
- Examined descriptive statistics
- Investigated categorical and numerical variables
- Identified missing/blank values

### 2. Data Cleaning

The `TotalCharges` variable contained blank values.

These blanks were converted to missing values and the affected records were removed.

After cleaning, the dataset contained **7,032 customer records**.

### 3. Exploratory Data Analysis

Explored churn patterns across:

- Customer tenure
- Contract type
- Payment method
- Internet service
- Demographic characteristics
- Subscribed services
- Monthly and total charges

### 4. Feature Preparation

Categorical variables were encoded into numerical representations to prepare the dataset for machine learning.

The data was then separated into features and target variables and divided into training and testing sets.

### 5. Logistic Regression

A Logistic Regression model was trained as a baseline classification model.

The initial model achieved approximately:

**79.7% test accuracy**

ROC-AUC was evaluated using predicted probabilities.

### 6. Random Forest

A Random Forest classifier was trained as a second classification approach.

The model achieved approximately:

**78.3% test accuracy**

The classification report was also examined to evaluate performance across churn and non-churn classes.

### 7. Multicollinearity Analysis

Variance Inflation Factor (VIF) was used to identify features with relatively high multicollinearity.

Several high-VIF variables were removed iteratively and the Logistic Regression model was retrained.

After feature reduction, Logistic Regression achieved approximately:

**78.2% test accuracy**

In this experiment, removing the selected high-VIF variables did not improve predictive accuracy.

## Model Comparison

| Model | Test Accuracy |
|---|---:|
| Logistic Regression | ~79.7% |
| Random Forest | ~78.3% |
| Logistic Regression after VIF reduction | ~78.2% |

Accuracy is reported on the test set used in the notebook.

## Key Findings

- The dataset contained 7,043 customer records before cleaning.
- 11 records contained blank `TotalCharges` values and were removed during preprocessing.
- Customer churn was explored across demographic, service, contract, payment, and tenure-related variables.
- Logistic Regression produced the highest test accuracy among the evaluated models at approximately 79.7%.
- Random Forest achieved approximately 78.3% test accuracy.
- VIF analysis identified variables with relatively high multicollinearity.
- Removing selected high-VIF variables did not improve Logistic Regression accuracy in this experiment.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Statsmodels
- Jupyter Notebook

## Project Structure

```text
customer-churn-prediction/
│
├── README.md
└── customer_churn_prediction.ipynb
```

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/adityajh51/customer-churn-prediction.git
```

### 2. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels jupyter
```

### 3. Add the dataset

The raw dataset is not included in this repository.

Obtain the dataset from its original source and place it in the project directory using the filename expected by the notebook.

### 4. Open the notebook

Launch Jupyter Notebook or JupyterLab and open:

```text
customer_churn_prediction.ipynb
```

Run the cells sequentially to reproduce the analysis and model evaluation.

## Conclusion

This project demonstrates an end-to-end customer churn analysis workflow covering data cleaning, exploratory analysis, categorical encoding, multicollinearity analysis, classification modeling, and model evaluation.

The results also demonstrate the importance of evaluating feature-selection decisions empirically rather than assuming that reducing multicollinearity will automatically improve predictive performance.
