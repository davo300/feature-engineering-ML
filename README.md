# Titanic Feature Engineering & Selection

**Course:** COMP 4730 – Machine Learning  
**Institution:** University of Windsor  
**Instructor:** Dr. Sherif Saad  
**Student:** Matt Davies  
**Lab:** Lab 3 – Feature Engineering & Selection  
**Language:** Python  
**Environment:** Google Colab / Jupyter Notebook  

---

## 📌 Project Overview

This project explores **feature engineering, encoding, and feature selection** using the classic **Titanic survival dataset**.  
The goal is to understand how thoughtful preprocessing and engineered features impact model performance and interpretability.

Using logistic regression and multiple feature-selection techniques, the project compares:
- A **baseline model** using raw features
- A **feature-engineered model**
- A **reduced model** using selected features

---

## 🎯 Learning Objectives

- Load and inspect a real-world dataset
- Handle missing data using principled imputation
- Encode categorical variables for ML models
- Engineer new, meaningful features
- Apply feature selection methods (Filter & Wrapper)
- Evaluate and compare model performance

---

## 📊 Dataset

- Source: `seaborn.load_dataset("titanic")`
- Target variable: `survived`
- Initial features:
  - `pclass`, `sex`, `age`, `sibsp`, `parch`, `fare`, `embarked`

---

## 🧹 Data Cleaning & Encoding

### Missing Values
- **Age, Fare:** Imputed using median (robust to outliers)
- **Embarked:** Imputed using mode

### Encoding
- One-hot encoding applied to:
  - `sex`
  - `embarked`
- Used `drop_first=True` to avoid multicollinearity

---

## 🧠 Feature Engineering

New features were created to capture social and economic structure:

- **family_size** = `sibsp + parch + 1`
- **is_alone** = indicator for solo travelers
- **fare_per_person** = `fare / family_size`

These features better represent evacuation behavior and socioeconomic status.

---

## 🤖 Models & Evaluation

### Baseline Model
- Logistic Regression
- Encoded features only
- Accuracy ≈ **80%**

### Feature-Engineered Model
- Logistic Regression
- Includes engineered features
- Similar accuracy, but improved recall for survivors

### Feature Selection
- **Mutual Information (Filter)**
- **Recursive Feature Elimination (Wrapper)**
- Reduced to **top 8 features**
- Maintained performance while improving interpretability

---

## 📈 Key Results

- Feature engineering improved minority-class (survivor) recall
- Feature selection reduced model complexity with no accuracy loss
- Economic and family-based features were among the most informative

---

## 🛠️ Technologies Used

- **Python**
- **Pandas, NumPy**
- **Seaborn, Matplotlib**
- **Scikit-learn**
- **Logistic Regression**
- **RFE, Mutual Information**

---

## 📁 Files

- `COMP4730_Lab3_Titanic_Feature_Engineering_Davies.ipynb` – Main notebook
- PDF export submitted via Brightspace (course requirement)

---

## 🤖 AI Assistance Disclosure

- **Tool:** ChatGPT  
- **Used for:** Clarification on concepts and result interpretation  
- **All code, analysis, and decisions are my own work**

---

## 📌 Notes

This project emphasizes **interpretability and reasoning**, not just raw accuracy, reflecting real-world ML practice where understanding *why* a model works matters as much as performance.

---

