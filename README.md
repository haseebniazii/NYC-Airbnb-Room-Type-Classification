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

## 📌 About The Project

**NYC Airbnb Room Type Classification** is a Machine Learning classification project that predicts the **room type** of an Airbnb listing in New York City.

The model predicts one of three categories:

* 🏠 **Entire home/apt**
* 🚪 **Private room**
* 🛏️ **Shared room**

The project follows a complete Machine Learning workflow, from data exploration and cleaning to preprocessing, model comparison, cross-validation, hyperparameter tuning, final evaluation, and saving the trained Machine Learning pipeline.

---

## 🎯 Project Objective

The main objective of this project is to build a reliable classification model that can predict the `room_type` of an Airbnb listing using information such as:

* Price
* Location
* Minimum nights
* Number of reviews
* Reviews per month
* Availability
* Host listing information
* Latitude and longitude

The project also focuses on building a reproducible preprocessing and modeling pipeline using Scikit-Learn.

---

## 📊 Dataset

The project uses the **New York City Airbnb Open Data** dataset.

The dataset contains approximately **48,895 Airbnb listings** and **16 columns**.

### Target Variable

```text
room_type
```

### Target Classes

```text
Entire home/apt
Private room
Shared room
```

The dataset contains both numerical and categorical features, making it suitable for demonstrating real-world Machine Learning preprocessing techniques.

---

## 🔎 Exploratory Data Analysis

Exploratory Data Analysis was performed to understand the structure, distributions, relationships, and quality of the dataset.

### EDA Performed

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

EDA helped identify important patterns and prepare the dataset for Machine Learning.

---

## 🧹 Data Cleaning & Feature Engineering

Before model training, the dataset was prepared through several preprocessing steps.

### Data Preparation Included

* Handling missing values
* Removing unnecessary columns
* Cleaning categorical variables
* Processing numerical variables
* Inspecting skewed features
* Handling outliers where appropriate
* Preparing features for Machine Learning
* Separating features and target variable

The goal was to create clean and consistent input data for the classification models.

---

## ⚙️ Machine Learning Pipeline

The project uses **ColumnTransformer** and **Pipeline** from Scikit-Learn to keep preprocessing and model training organized.

```text
Raw Data
   ↓
Numerical Features ──→ Numerical Preprocessing
   ↓
Categorical Features ──→ Categorical Encoding
   ↓
ColumnTransformer
   ↓
Machine Learning Model
   ↓
Prediction
```

Using a complete pipeline ensures that the same preprocessing steps are automatically applied during both training and prediction.

It also helps reduce the risk of **data leakage** and makes the final model easier to reuse.

---

## 🤖 Models Compared

Multiple classification algorithms were trained and compared.

### 1. Logistic Regression

Used as a baseline classification model.

It provides a simple and interpretable reference point for evaluating more complex algorithms.

### 2. Decision Tree

A non-linear classification algorithm capable of learning complex decision boundaries from the data.

### 3. Random Forest

An ensemble learning algorithm that combines multiple decision trees.

Random Forest was used because it performs well on many tabular classification problems and can capture non-linear relationships between features.

### 4. Gradient Boosting

A sequential ensemble learning method that builds models iteratively to improve prediction performance.

---

## 🔬 Model Evaluation

The candidate models were evaluated using **3-fold Stratified Cross-Validation** on the training data.

The following classification metrics were considered:

* Accuracy
* Precision
* Recall
* F1-Score

Using the same preprocessing pipeline for each model provides a fair comparison between the algorithms.

---

## 🎯 Hyperparameter Tuning

After comparing the candidate models, the strongest model was selected for further optimization.

Hyperparameter tuning was performed to identify better model parameters and improve generalization performance.

The final tuned model was then evaluated on the **untouched test set**.

This helps provide a more realistic estimate of how the final model performs on unseen data.

---

## 📈 Feature Importance

Feature importance was analyzed to understand which features contributed most to the model's predictions.

This provides additional insight into the factors associated with Airbnb room types and improves the interpretability of the Machine Learning model.

---

## 💾 Model Saving

The final preprocessing and Machine Learning pipeline was saved as a model artifact.

```python
import joblib

joblib.dump(final_pipeline, "airbnb_room_type_model.pkl")
```

The saved pipeline contains the preprocessing steps together with the trained Machine Learning model.

This allows new raw input data to be passed through the same preprocessing process before generating predictions.

---

## 🛠️ Technologies Used

### Machine Learning

* 🐍 Python
* 🐼 Pandas
* 🔢 NumPy
* 🤖 Scikit-Learn
* 💾 Joblib

### Data Visualization

* 📊 Matplotlib
* 📈 Seaborn

### Development

* 📓 Jupyter Notebook
* 💻 Google Colab
* 🐙 Git
* 🐙 GitHub

---

## 📂 Project Structure

```text
NYC-Airbnb-Room-Type-Classification/
│
├── NYC_Airbnb_Room_Type_Classification.ipynb
├── AB_NYC_2019.csv
├── airbnb_room_type_model.pkl
├── README.md
└── LICENSE
```

---

## 🔄 Machine Learning Workflow

```text
Dataset
   ↓
Data Understanding
   ↓
Exploratory Data Analysis
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
Multiple Classification Models
   ↓
Cross-Validation
   ↓
Model Comparison
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

## 🎓 Key Learning Outcomes

Through this project, I practiced:

* End-to-end Machine Learning workflow
* Exploratory Data Analysis
* Data cleaning
* Feature engineering
* Numerical preprocessing
* Categorical encoding
* `ColumnTransformer`
* `Pipeline`
* Classification algorithms
* Stratified Cross-Validation
* Hyperparameter tuning
* Model evaluation
* Feature importance
* Model serialization with Joblib
* Building reproducible Machine Learning pipelines

---

## 📌 Conclusion

This project demonstrates a complete Machine Learning workflow for a real-world **multi-class classification problem** using New York City Airbnb listing data.

By comparing multiple classification algorithms, applying cross-validation, tuning the selected model, and saving the final preprocessing + model pipeline, the project focuses on building a reliable and reproducible Machine Learning solution.

---

## 👨‍💻 Author

### Haseeb Khan

**Computer Science Student | Machine Learning & AI Enthusiast**

GitHub: **haseebniazii**

---

## ⭐ Support

If you found this project useful, feel free to explore the notebook and give the repository a ⭐ star.

**Thank you for checking out the project!**
