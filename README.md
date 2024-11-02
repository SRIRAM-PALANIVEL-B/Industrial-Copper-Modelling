# Industrial Copper Modeling

- **Table of Contents**
- **Problem Statement**
- **Approach**
- **Solution Overview**
- **Technologies Used**
- **How to Run the Project**
- **Contributing**

# Problem Statement

The copper industry deals with relatively straightforward data concerning sales and pricing. However, this data can be plagued by issues such as skewness and noise, which may impact the accuracy of manual predictions. Addressing these challenges manually is often time-consuming and can lead to suboptimal pricing decisions.

This project utilizes machine learning regression models to tackle these issues through advanced techniques including:

- **Data normalization**
- **Feature scaling**
- **Outlier detection**
  
Additionally, the copper industry faces challenges in lead capture. A lead classification model evaluates and classifies leads based on their likelihood to convert into customers. The STATUS variable is leveraged, where 'WON' signifies success and 'LOST' signifies failure.

# Approach

1. **Data Understanding:** Identify variable types (continuous, categorical) and their distributions. Convert irrelevant values in Material_Reference (e.g., starting with '00000') to null and treat reference columns as categorical variables.

2. **Data Preprocessing:**
    - Handle missing values with mean/median/mode.
    - Treat outliers using IQR or Isolation Forest from the sklearn library.
    - Address skewness in the dataset with transformations (e.g., log transformation, Box-Cox transformation).
    - Encode categorical variables using one-hot, label, or ordinal encoding as appropriate.


3. **Exploratory Data Analysis (EDA):** Visualize outliers and skewness before and after treatment using Seaborn’s boxplot, distplot, and violinplot.

4. **Feature Engineering:** Create new features if applicable, aggregate or transform existing features, and eliminate highly correlated columns using SNS HEATMAP.

5. **Model Building and Evaluation:**
    - Split the dataset into training and testing/validation sets.
    - Train and evaluate classification models (e.g., ExtraTreesClassifier, XGBClassifier, Logistic Regression) using metrics such as accuracy, precision, recall, F1 score, and AUC curve.
    - Optimize model hyperparameters through cross-validation and grid search.
    - Conduct similar steps for regression modeling, noting that tree-based models handle noise and linearity better.
      
6. **Model GUI:** Create an interactive Streamlit application with:
                      - Task input (Regression or Classification)
                      - Input fields for entering column values (excluding Selling_Price for regression and Status for classification)
                      - Prediction results displayed based on the processed input data.
   
7. **Model Management:** Use the pickle module to save and load models (e.g., encoders, scaling models, ML models). Ensure to fit and transform in separate lines, using transform only for unseen data.

# Solution Overview

The solution encompasses:

  - Exploration of skewness and outliers in the dataset.
  - Data transformation and necessary cleaning/preprocessing.
  - A machine learning regression model to predict the continuous variable Selling_Price.
  - A machine learning classification model to predict the Status (WON or LOST).
  - A Streamlit interface for user input and prediction outputs.


# Technologies Used

    Python
    Pandas
    Scikit-learn
    Seaborn
    Matplotlib
    Streamlit
    Pickle

# How to Run the Project

1. Clone the repository:
   
       git clone <repository-url>
       cd Industrial-Copper-Modelling

2. Install the required packages:

        pip install -r requirements.txt

3. Run the Streamlit application:

       streamlit run app.py


# Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue for suggestions or improvements.

   
