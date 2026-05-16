# Bangalore House Price Prediction Model

A Machine Learning project to predict residential property prices in Bangalore
using Multiple Linear Regression, built with Python and Scikit-learn.

---

##  Project Overview

This project builds a price prediction model for Bangalore real estate using
the Bengaluru House Price dataset from Kaggle. The goal is to estimate property
prices based on key features like location, total area, number of bedrooms, and
bathrooms. The project covers the complete data science pipeline, from raw data
cleaning to model evaluation.

---

##  Dataset

- **Source:** [Kaggle - Bengaluru House Price Data](https://www.kaggle.com/amitabhajoy/bengaluru-house-price-data)
- **Size:** ~13,000 property listings
- **Features Used:** Location, Total Sqft, BHK (Bedrooms), Bathrooms, Price

---

##  Tech Stack

| Category        | Tools / Libraries                        |
|----------------|-------------------------------------------|
| Language        | Python                                   |
| ML Library      | Scikit-learn                             |
| Data Handling   | Pandas, NumPy                            |
| Visualization   | Matplotlib                               |
| Environment     | Jupyter Notebook                         |

---

##  Project Workflow

### 1. Data Loading
- Loaded the Bengaluru house prices dataset from Kaggle
- Explored the dataset structure, shape, and column types

### 2. Data Cleaning
- Dropped irrelevant columns (area_type, society, balcony, availability)
- Handled missing/null values by dropping incomplete rows
- Standardized the `size` column (extracted BHK count from strings)
- Cleaned the `total_sqft` column ,converted range values (e.g. 2100–2850)
  to their mean

### 3. Feature Engineering
- Created a new `price_per_sqft` column for outlier analysis
- Reduced dimensionality by grouping rare locations under "other"

### 4. Outlier Removal
- Removed properties where sqft per BHK was below 300
  (e.g. a 2 BHK with only 400 sqft)
- Removed properties with unusual price per sqft using
  mean and standard deviation per location
- Removed cases where a lower BHK flat was priced higher
  than a higher BHK flat in the same location

### 5. Model Building
- Applied One Hot Encoding on the location column
- Split data into training and test sets
- Trained a **Multiple Linear Regression** model using Scikit-learn

### 6. Model Evaluation
- Evaluated using **R² Score** on test data
- Used **GridSearchCV** to fine-tune hyperparameters
- Validated generalizability of predictions on unseen property inputs



##  Results

| Metric        | Value        |
|--------------|--------------|
| Algorithm     | Multiple Linear Regression |
| R² Score      | ~0.84 (update with your actual score) |


