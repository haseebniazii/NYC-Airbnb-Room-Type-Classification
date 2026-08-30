# 🏠 NYC Airbnb Room Type Classification

<p align="center">
  🚀 Machine Learning | 📊 Classification | 🤖 Random Forest | 🗽 NYC Airbnb Data | ⚡ FastAPI
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas">
  <img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?style=for-the-badge&logo=scikit-learn">
  <img src="https://img.shields.io/badge/FastAPI-API-009688?style=for-the-badge&logo=fastapi">
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge">
</p>

---

## 🌐 Live Demo

### 🏠 Live Web Application

👉 **[Open NYC Airbnb Room Type Predictor](https://haseebniazii.github.io/NYC-Airbnb-Room-Type-Classification/)**

Enter Airbnb listing details and get a prediction for:

* 🏠 Entire home/apt
* 🚪 Private room
* 🛏️ Shared room

The frontend is connected to a deployed FastAPI machine-learning API.

---

# 📌 About The Project

**NYC Airbnb Room Type Classification** is an end-to-end Machine Learning classification project that predicts the **room type** of an Airbnb listing in New York City.

The model predicts one of three categories:

* 🏠 **Entire home/apt**
* 🚪 **Private room**
* 🛏️ **Shared room**

The project follows a complete Machine Learning workflow, starting from data exploration and cleaning and continuing through preprocessing, model comparison, cross-validation, hyperparameter tuning, final evaluation, model serialization, API development, deployment, and frontend integration.

---

# 🎯 Project Objective

The main objective of this project is to build a Machine Learning model that can predict the room type of an Airbnb listing using listing information such as:

* Price
* Latitude
* Longitude
* Minimum nights
* Number of reviews
* Reviews per month
* Host listing count
* Availability
* Neighbourhood group
* Neighbourhood

The project also demonstrates how a trained Machine Learning pipeline can be converted into a real-world prediction API and connected to a web interface.

---

# 📊 Dataset

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

The dataset contains both numerical and categorical features, making it suitable for demonstrating real-world Machine Learning preprocessing and classification techniques.

---

# 🔎 Exploratory Data Analysis

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

EDA helped identify patterns in the dataset and prepare the data for Machine Learning.

---

# 🧹 Data Cleaning & Feature Engineering

Before model training, the dataset was prepared through several preprocessing steps.

### Data Preparation Included

* Handling missing values
* Removing unnecessary columns
* Cleaning categorical variables
* Processing numerical variables
* Inspecting skewed features
* Handling outliers where appropriate
* Preparing Machine Learning features
* Separating features and target variable

The goal was to create clean and consistent input data for the classification models.

---

# ⚙️ Machine Learning Pipeline

The project uses **ColumnTransformer** and **Pipeline** from Scikit-Learn to organize preprocessing and model training.

```text
Raw Data
   ↓
Numerical Features
   ↓
Numerical Preprocessing
   ↓
Categorical Features
   ↓
Categorical Encoding
   ↓
ColumnTransformer
   ↓
Machine Learning Model
   ↓
Prediction
```

Using a complete pipeline ensures that the same preprocessing steps are automatically applied during both training and prediction.

It also helps reduce the risk of data leakage and makes the final trained model easier to reuse.

---

# 🤖 Models Compared

Multiple classification algorithms were trained and compared.

## 1. Logistic Regression

Used as a baseline classification model.

It provides a simple and interpretable reference point for evaluating more complex models.

## 2. Decision Tree

A non-linear classification algorithm capable of learning complex decision boundaries from the data.

## 3. Random Forest

An ensemble learning algorithm that combines multiple decision trees.

Random Forest was used because it performs well on many tabular classification problems and can capture non-linear relationships between features.

## 4. Gradient Boosting

A sequential ensemble learning method that builds models iteratively to improve prediction performance.

---

# 🔬 Model Evaluation

The candidate models were evaluated using **3-fold Stratified Cross-Validation** on the training data.

The following classification metrics were considered:

* Accuracy
* Precision
* Recall
* F1-Score

Using the same preprocessing pipeline for each model provides a fair comparison between the algorithms.

---

# 🎯 Hyperparameter Tuning

After comparing the candidate models, the strongest model was selected for further optimization.

Hyperparameter tuning was performed to identify better model parameters and improve generalization performance.

The final tuned model was then evaluated on the **untouched test set**.

This provides a more realistic estimate of how the model performs on unseen data.

---

# 📈 Feature Importance

Feature importance was analyzed to understand which features contributed most to the model's predictions.

This provides additional insight into the factors associated with Airbnb room types and improves the interpretability of the Machine Learning model.

---

# 💾 Model Saving

The final preprocessing and Machine Learning pipeline was saved as a model artifact using Joblib.

```python
import joblib

joblib.dump(final_pipeline, "Model_Pipeline.pkl")
```

The saved pipeline contains the preprocessing steps together with the trained Machine Learning model.

This allows new raw input data to be passed through the same preprocessing process before generating predictions.

---

# ⚡ FastAPI Backend

The trained Machine Learning pipeline was integrated with **FastAPI** to create a prediction API.

The API accepts listing information as JSON and returns:

* Predicted room type
* Prediction probabilities

### API Endpoint

```text
POST /predict
```

### Input Features

```text
latitude
longitude
price
minimum_nights
number_of_reviews
reviews_per_month
calculated_host_listings_count
availability_365
neighbourhood_group
neighbourhood
```

---

# 📥 API Request Example

```json
{
  "latitude": 40.6782,
  "longitude": -73.9442,
  "price": 120,
  "minimum_nights": 2,
  "number_of_reviews": 50,
  "reviews_per_month": 2.5,
  "calculated_host_listings_count": 3,
  "availability_365": 200,
  "neighbourhood_group": "Brooklyn",
  "neighbourhood": "Bedford-Stuyvesant"
}
```

---

# 📤 API Response Example

```json
{
  "Predicted_room_type": "Entire home/apt",
  "Probability": [
    0.8333333333333334,
    0.16666666666666666,
    0
  ]
}
```

The API successfully returns the predicted room type together with the model's probability values.

---

# 🌐 Frontend

A responsive frontend was developed using:

* HTML
* CSS
* JavaScript

The frontend collects listing information from the user and sends it to the FastAPI backend using a `POST` request.

```text
User
 ↓
Web Form
 ↓
JavaScript
 ↓
FastAPI /predict
 ↓
Machine Learning Pipeline
 ↓
Prediction
 ↓
JSON Response
 ↓
Frontend Result
```

The frontend also displays prediction probabilities and visually represents the predicted room type.

---

# 🔗 Frontend ↔ API Integration

The JavaScript frontend communicates with the deployed FastAPI backend.

Example:

```javascript
const API_BASE_URL =
  "https://nyc-airbnb-room-type-predictor.fastapicloud.dev";

const PREDICT_ENDPOINT = `${API_BASE_URL}/predict`;
```

The prediction request is sent using:

```javascript
const res = await fetch(PREDICT_ENDPOINT, {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify(payload)
});
```

This allows the GitHub Pages frontend to communicate with the deployed Machine Learning API.

---

# 🧪 Example Prediction

For example, a listing with:

```text
Latitude: 40.6782
Longitude: -73.9442
Price: $120
Minimum nights: 2
Reviews: 50
Reviews/month: 2.5
Host listings: 3
Availability: 200 days
Borough: Brooklyn
Neighbourhood: Bedford-Stuyvesant
```

produced:

```text
Predicted Room Type:
Entire home/apt
```

with the returned probability distribution:

```text
Entire home/apt → 83.33%
Private room   → 16.67%
Shared room    → 0%
```

---

# 🛠️ Technologies Used

## Machine Learning

* 🐍 Python
* 🐼 Pandas
* 🔢 NumPy
* 🤖 Scikit-Learn
* 💾 Joblib

## Data Visualization

* 📊 Matplotlib
* 📈 Seaborn

## Backend

* ⚡ FastAPI
* 🧩 Pydantic
* 🚀 Uvicorn
* 🌐 CORS

## Frontend

* HTML
* CSS
* JavaScript

## Development & Deployment

* 📓 Jupyter Notebook
* 💻 Google Colab
* 🐙 Git
* 🐙 GitHub
* 🌐 GitHub Pages
* ☁️ FastAPI Cloud

---

# 📂 Project Structure

```text
NYC-Airbnb-Room-Type-Classification/
│
├── NYC_Airbnb_Room_Type_Classification.ipynb
├── AB_NYC_2019.csv
├── Model_Pipeline.pkl
├── README.md
├── LICENSE
│
└── frontend/
    ├── index.html
    ├── style.css
    └── script.js
```

---

# 🔄 Complete Machine Learning Workflow

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
   ↓
FastAPI Backend
   ↓
API Deployment
   ↓
Frontend Integration
   ↓
Live Prediction Web App
```

---

# 🎓 Key Learning Outcomes

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
* FastAPI development
* Pydantic validation
* REST API development
* CORS configuration
* Frontend API integration
* Machine Learning deployment
* Building a live prediction web application

---

# 🚀 How To Use The Live App

### Step 1 — Open the Web App

Open:

```text
https://haseebniazii.github.io/NYC-Airbnb-Room-Type-Classification/
```

### Step 2 — Enter Listing Details

Provide:

```text
Latitude
Longitude
Borough
Neighbourhood
Price
Minimum nights
Days available
Total reviews
Reviews per month
Listings by host
```

### Step 3 — Predict

Click:

```text
Predict room type
```

### Step 4 — View Result

The application displays:

```text
Predicted Room Type
Probability Distribution
Visual Prediction
```

---

# 📚 API Documentation

The deployed API includes interactive Swagger documentation.

👉 **Swagger UI**

```text
https://nyc-airbnb-room-type-predictor.fastapicloud.dev/docs
```

You can use the documentation to test the `/predict` endpoint directly from your browser.

---

# 📌 API Health Check

The root endpoint is:

```text
GET /
```

It confirms that the FastAPI application is running.

Example response:

```text
Hello Guyss
```

---

# 📊 Prediction Classes

The model predicts three room types:

| Room Type          | Description                                       |
| ------------------ | ------------------------------------------------- |
| 🏠 Entire home/apt | The entire property is available to the guest     |
| 🚪 Private room    | Guest has a private room within a shared property |
| 🛏️ Shared room    | Guest shares the room/property space with others  |

---

# 📌 Conclusion

This project demonstrates a complete end-to-end Machine Learning workflow for a real-world **multi-class classification problem** using New York City Airbnb listing data.

The project goes beyond model training by integrating the trained Scikit-Learn pipeline with FastAPI and connecting the API to a live frontend.

The final system allows users to enter Airbnb listing details and receive a real-time room-type prediction through a web application.

```text
Machine Learning
       +
FastAPI
       +
REST API
       +
JavaScript Frontend
       +
Deployment
       =
Live ML Application 🚀
```

---

# 👨‍💻 Author

## Haseeb Khan

**Computer Science Student | Machine Learning & AI Enthusiast**

GitHub: **haseebniazii**

Portfolio:

```text
https://haseebniazii.github.io/
```

---

# ⭐ Support

If you found this project useful, feel free to:

* ⭐ Star the repository
* 🍴 Fork the project
* 📓 Explore the notebook
* 🌐 Try the live application
* 🚀 Experiment with the API

**Thank you for checking out the project! 🚀**
