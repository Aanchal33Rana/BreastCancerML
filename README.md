# Breast Cancer Diagnosis Prediction – EDA + Linear Regression

This project presents a structured and practical analysis of breast cancer data, focusing on **data cleaning**, **exploratory data analysis (EDA)**, and implementing a **Linear Regression** model to numerically predict diagnosis outcomes. The dataset is sourced from **Kaggle**, and the notebook is organized into clear steps following a real-world data science workflow.

---

##  Dataset Source

- **Title**: Breast Cancer Dataset  
- **Source**: https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data
- **Description**:  
  - Contains clinical and radiological data of breast cancer patients.  
  - Includes features like Age, T stage, Grade, Tumor Size, Lymph Node status, and more.  
  - Target/derived variable: **Diagnosis Status** (Benign / Malignant based on T stage)

- **Total Samples**: 116  
- **Columns**:  
  Patient_ID, Age, T stage, Grade, ER status, PR status, HER2 status, Surgery type, etc.

---

##  Sections Overview

###  1. Introduction

This notebook investigates the dataset to uncover insights from tumor characteristics and applies a Linear Regression model to explore if diagnosis status can be predicted numerically.

---

###  2. Data Cleaning & Preprocessing

- **Null Value Handling**: Missing entries in important columns were checked and filled or removed as needed.  
- **Column Name Cleaning**: Columns like `T stage` were renamed and reformatted for clarity and consistency.  
- **Diagnosis Status Engineering**: A new column `status` was derived from the cleaned `T stage` values to reflect whether the tumor is likely benign or malignant.

---

###  3. Exploratory Data Analysis (EDA)

To explore relationships and patterns:

- **Bar Graphs**: Plotted frequency of categorical variables such as `T stage`, `Grade`, and `Surgery type`.  
- **Histograms**: Created for numeric and ordinal features.  
- **Paired Column Comparisons**: Visualized features that are naturally grouped (e.g., hormone receptor statuses) using side-by-side plots.

These visualizations revealed:

- The class distribution of tumor stages  
- Trends across hormone receptor markers  
- Feature-group behaviors that vary across diagnosis status

---

###  4. Linear Regression Model

- **Target Variable**: Derived `status` (Malignant = 1, Benign = 0)  
- **Approach**:  
  - Encoded categorical features  
  - Trained a **Linear Regression** model using all relevant features  
  - Evaluated model using appropriate regression metrics

---

###  5. Evaluation Metrics

The model achieved:

- **R² Score**: `1.0` → The model explains 100% of the target variance  
- **Mean Absolute Error (MAE)**: `1.70e-14` → Effectively zero error

These results indicate strong predictability, potentially due to clean and well-separated features. (However, the model may have been evaluated on training data only — future improvement should include generalization testing.)

---

###  6. Final Remarks

This project showcases the complete data pipeline from preprocessing to modeling. While Linear Regression is not ideal for classification, it reveals meaningful linear patterns in the data and demonstrates how well-structured data contributes to model accuracy.

---

##  How to Run

1. **Clone the Repository**

git clone https://github.com/Aanchal33Rana/BreastCancerML.git
cd BreastCancerML

2. **Install Required Libraries**
   
pip install pandas numpy matplotlib seaborn scikit-learn

3. **Launch the Notebook**
   
jupyter notebook BreastCancerEDA.ipynb

---
## Future Work

- **Use classification models** like Logistic Regression, Support Vector Machines (SVM), or Random Forest to perform true binary classification instead of regression.
- **Apply train/test split** or **cross-validation** to evaluate model performance more realistically and avoid overfitting.
- **Introduce dimensionality reduction** techniques such as **Principal Component Analysis (PCA)** or use feature selection methods to reduce noise and improve model performance.
- **Deploy the model** using a web framework like **Streamlit**, **Flask**, or integrate it into a full-stack web application for real-time prediction.

