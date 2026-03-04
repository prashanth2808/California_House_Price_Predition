# California House Price Prediction 🏠📊

## Project Overview

This project focuses on predicting house prices using Machine Learning techniques. The **California Housing dataset** is used to train regression models that estimate house prices based on various features such as income, house age, number of rooms, population, and geographical location.

The main objective of this project is to understand the **complete machine learning workflow**, including data preprocessing, feature analysis, model training, and model evaluation.

---

## Dataset

The dataset contains housing information collected from different districts in California.

Some important features include:

* **MedInc** – Median income in the area
* **HouseAge** – Average age of houses
* **AveRooms** – Average number of rooms
* **AveBedrms** – Average number of bedrooms
* **Population** – Total population in the area
* **AveOccup** – Average house occupancy
* **Latitude** – Latitude location of the house
* **Longitude** – Longitude location of the house

The target variable is:

**MedHouseVal – Median House Value**

---

## Machine Learning Workflow ⚙️

The following steps were performed in this project:

1. Importing required libraries (Pandas, NumPy, Matplotlib, Scikit-learn)
2. Loading and exploring the dataset
3. Understanding the dataset structure using `info()` and `head()`
4. Handling missing values
5. Data visualization using histograms
6. Converting categorical variables into numerical format
7. Checking correlation between features
8. Separating features (X) and target variable (y)
9. Splitting the dataset into training and testing sets
10. Training machine learning models
11. Making predictions on test data
12. Evaluating model performance

---

## Models Used 🤖

### Linear Regression

A basic regression algorithm that models the relationship between independent variables and the target variable using a linear equation.

### Random Forest Regressor

Random Forest is an ensemble learning algorithm that combines multiple decision trees to improve prediction accuracy and reduce overfitting.

---

## Model Evaluation 📈

The models were evaluated using the following metrics:

* **Mean Absolute Error (MAE)**
* **Mean Squared Error (MSE)**
* **R² Score**

These metrics help measure how accurately the model predicts house prices.

---

## Results

After training and evaluation, the **Random Forest model performed better than Linear Regression**, since it can capture more complex patterns in the data.

---

## Technologies Used 💻

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Jupyter Notebook

---

## Project Structure

California-House-Price-Prediction
│
├── California_houseprice.ipynb
└── README.md

---

## Conclusion

This project demonstrates how machine learning can be applied to predict housing prices using real-world data. By training and comparing different models, we can identify which algorithm provides better prediction accuracy for the dataset.
