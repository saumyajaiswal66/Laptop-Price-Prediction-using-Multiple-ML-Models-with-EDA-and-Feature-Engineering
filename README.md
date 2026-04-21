# Laptop-Price-Prediction-using-Multiple-ML-Models-with-EDA-and-Feature-Engineering
Built a laptop price prediction system using multiple machine learning models with extensive data preprocessing, feature engineering, and EDA to improve prediction accuracy.

# 💻 Laptop Price Prediction using Machine Learning

## 📌 Project Overview

This project aims to predict the price of laptops based on various features such as brand, specifications, and hardware configurations. The goal is to understand the key factors influencing laptop prices and build machine learning models to make accurate predictions.

---

## 🎯 Objectives

* Perform **data cleaning and preprocessing**
* Conduct **Exploratory Data Analysis (EDA)** to extract insights
* Apply **feature engineering techniques**
* Build and compare multiple **machine learning models**
* Evaluate model performance and select the best one

---

## 📂 Dataset

* The dataset contains information about laptops including:

  * Brand
  * RAM
  * Processor
  * Storage
  * GPU
  * Operating System
  * Weight
  * Price

---

## 🔧 Project Workflow

### 1. Data Preprocessing

* Handled missing values
* Cleaned inconsistent data formats
* Converted categorical features into usable format

### 2. Text Processing

* Extracted useful information from text columns (e.g., CPU, GPU, OS,ScreenResolution,RAM,Memory)
* Standardized feature values

### 3. Exploratory Data Analysis (EDA)

* Analyzed distribution of price
* Identified relationships between features and price
* Used visualizations to uncover patterns and trends

### 4. Feature Engineering

* Created new meaningful features
* Reduced irrelevant or redundant data

### 5. Model Building

Implemented and compared multiple models:

* Linear Regression
* Ridge Regression
* Lasso Regression
* Decision Tree Regressor
* Random Forest Regressor

---

## 📊 Model Performance

| Model             | Performance (R² Score) |
| ----------------- | ---------------------- |
| Linear Regression | 0.8073277448418653     |
| Ridge Regression  | 0.812733103131181      |
| Lasso Regression  | 0.8071857196899418     |
| Decision Tree     | 0.8446033998579088     |
| Random Forest     | 0.8851499847098487     |

> 🔎 *Random Forest performed the best among all models.*

---

## 📈 Key Insights

* RAM and Processor significantly impact laptop price
* High-end GPUs lead to higher price ranges
* Brand value also plays an important role
* Price distribution is right-skewed

---

## ⚠️ Limitations

* Hyperparameter tuning was not performed
* No deployment or frontend application included
* Model performance can be further improved

---

## 🚀 Future Improvements

* Apply **Hyperparameter Tuning (GridSearchCV / RandomSearchCV)**
* Build a simple **Streamlit web application**
* Deploy the model for real-time predictions
* Use more advanced models for better accuracy

---

## 🛠️ Tech Stack

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn

---

## 🙋‍♂️ About Me

I am a data science enthusiast passionate about solving real-world problems using data. This project reflects my understanding of data preprocessing, visualization, and machine learning fundamentals.

---

## ⭐ If you found this project useful, consider giving it a star!

