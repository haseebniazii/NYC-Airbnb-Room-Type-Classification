# 🏠 NYC Airbnb Room Type Classification

<p align="center">
  🚀 Machine Learning | 📊 Classification | 🤖 Random Forest | 🗽 NYC Airbnb Data
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas">
  <img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?style=for-the-badge&logo=scikit-learn">
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge">
</p>

---

## 📌 About the Project

**NYC Airbnb Room Type Classification** is a Machine Learning classification project that predicts the **room type** of an Airbnb listing in New York City.

The model predicts one of three categories:

* 🏠 **Entire home/apt**
* 🚪 **Private room**
* 🛏️ **Shared room**

The project follows a complete Machine Learning workflow, starting from data exploration and cleaning to model comparison, hyperparameter tuning, final evaluation, and saving the trained model pipeline.

---

## 🎯 Project Objective

The main objective is to build a classification model that can predict the `room_type` of an Airbnb listing using features such as:

* Price
* Location
* Minimum nights
* Number of reviews
* Reviews per month
* Availability
* Host listing information
* Latitude and longitude

---

## 📊 Dataset

The project uses the **New York City Airbnb Open Data** dataset from Kaggle.

**Dataset:** New York City Airbnb Open Data

Dataset contains approximately **48,895 Airbnb listings** and **16 columns**.

Target variable:

```text
room_type
```

Target classes:

```text
Entire home/apt
Private room
Shared room
```

---

## 🔎 Exploratory Data Analysis

The project includes detailed EDA to understand the dataset before modeling.

### EDA performed:

* Dataset shape and structure
* Data types
* Missing-value analysis
* Summary statistics
* Target distribution
* Univariate analysis
* Bivariate analysis
* Feature relationships
* Correlation analysis
* Skewness analysis
* Outlier inspection
* Distribution visualization

---

## 🧹 Data Cleaning & Feature Engineering

The dataset was prepared for Machine Learning by:

* Handling missing values
* Removing unnecessary columns
* Cleaning categorical features
* Processing numerical features
* Inspecting skewed variables
* Handling outliers where appropriate
* Preparing features for model training

---

## ⚙️ Machine Learning Pipeline

To keep preprocessing consistent and avoid data leakage, the project uses:

```python
ColumnTransformer
Pipeline
```

The preprocessing pipeline handles numerical and categorical features separately before passing the transformed data to the Machine Learning model.

This ensures that the same preprocessing steps are automatically applied during both training and prediction.

---

## 🤖 Models Compared

Multiple classification algorithms were trained and compared using cross-validation:

### 1. Logistic Regression

Used as a simple and interpretable baseline model.

### 2. Decision Tree

A non-linear model capable of learning complex decision boundaries.

### 3. Random Forest

An ensemble learning algorithm that combines multiple decision trees and is generally strong for tabular classification problems.

### 4. Gradient Boosting

A sequential ensemble method that builds models to improve upon previous predictions.

---

## 🔬 Model Evaluation

The candidate models were evaluated using **3-fold Stratified Cross-Validation** on the training data.

Evaluation included metrics such as:

* Accuracy
* Precision
* Recall
* F1-Score

The models were compared using the same preprocessing pipeline to ensure a fair comparison.

---

## 🎯 Hyperparameter Tuning

After comparing the candidate models, the best-performing model was selected for further optimization.

Hyperparameter tuning was performed to find better model parameters and improve generalization performance.

The final model was then evaluated on the **untouched test set**.

---

## 📈 Feature Importance

Feature importance was analyzed to understand which features contributed most to the model's predictions.

This helps provide better interpretability and insight into the factors associated with Airbnb room types.

---

## 💾 Model Saving

The final preprocessing + Machine Learning pipeline was saved as a model artifact.

Using a complete pipeline means the saved model can receive raw input and automatically perform the required preprocessing before making a prediction.

Example:

```python
import joblib

joblib.dump(final_pipeline, "airbnb_room_type_model.pkl")
```

---

## 🛠️ Technologies Used

* 🐍 Python
* 🐼 Pandas
* 🔢 NumPy
* 📊 Matplotlib
* 📈 Seaborn
* 🤖 Scikit-Learn
* 💾 Joblib
* 📓 Jupyter Notebook / Google Colab

---

## 📂 Project Structure

```text
NYC-Airbnb-Room-Type-Classification/
│
├── NYC_Airbnb_Room_Type_Classification.ipynb
├── AB_NYC_2019.csv
├── airbnb_room_type_model.pkl
└── README.md
```

---

## 🔄 Machine Learning Workflow

```text
Dataset
   ↓
Data Understanding
   ↓
EDA
   ↓
Data Cleaning
   ↓
Feature Engineering
   ↓
Train/Test Split
   ↓
ColumnTransformer
   ↓
Pipeline
   ↓
Multiple Models
   ↓
Cross-Validation
   ↓
Hyperparameter Tuning
   ↓
Final Evaluation
   ↓
Feature Importance
   ↓
Save Model
```

---

## 🚀 Key Learning Outcomes

Through this project, I practiced:

* End-to-end Machine Learning workflow
* Exploratory Data Analysis
* Data cleaning
* Feature engineering
* Handling numerical and categorical data
* `ColumnTransformer`
* `Pipeline`
* Classification algorithms
* Cross-validation
* Hyperparameter tuning
* Model evaluation
* Feature importance
* Saving Machine Learning pipelines with Joblib

---

## 📌 Conclusion

This project demonstrates a complete Machine Learning workflow for a real-world classification problem using Airbnb listing data from New York City.

By comparing multiple algorithms and tuning the strongest model, the project focuses not only on building a model but also on creating a reliable and reproducible Machine Learning pipeline.

---

## 👨‍💻 Author

**Haseeb Khan**

Computer Science Student | Machine Learning & AI Enthusiast

GitHub: **haseebniazii**

---

⭐ If you find this project useful, feel free to explore the notebook and give the repository a star.
