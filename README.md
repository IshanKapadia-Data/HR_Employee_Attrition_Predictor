# 🧠 HR Analytics: Employee Attrition Prediction

Predicting whether an employee is likely to leave the organization using machine learning and HR data.

## 📌 Project Overview

**Objective**: Build an end-to-end machine learning pipeline to predict employee attrition based on historical HR data and employee profiles.

**Business Value**:  
Early detection of high attrition risk helps HR teams take proactive measures to improve employee satisfaction and retention.

## 📊 Dataset Summary

- **Rows**: 1,470 employees  
- **Columns**: 35 original features → 44 engineered features  
- **Target**: `Attrition` (Yes/No)  
- **Features Include**:
  - Demographics: Age, Gender, Marital Status
  - Job Info: Department, Role, DistanceFromHome
  - Compensation: Monthly Income, Stock Option Level
  - Performance: Job Involvement, Years at Company, Training

## 🧪 ML Pipeline

### Step 1: Data Cleaning & Feature Engineering
- Dropped constant columns (`Over18`, `StandardHours`, `EmployeeCount`)
- One-hot encoded categorical features (e.g., `Department`, `JobRole`)
- Label-encoded binary features (`Gender`, `OverTime`)
- Scaled numerical features using `StandardScaler`

### Step 2: Model Comparison
| Model               | ROC-AUC | Comments                         |
|--------------------|---------|----------------------------------|
| Logistic Regression| ~0.83   | Strong baseline                  |
| Random Forest       | ~0.86   | ✅ **Final Selected Model**       |
| XGBoost (Tuned)     | ~0.85   | Improved with hyperparameter tuning|

### Step 3: Final Deployment
- Saved model using `joblib`
- Built a reusable prediction script
- Prediction example returns:

### Attrition Prediction: Yes
### Attrition Probability: 0.61


