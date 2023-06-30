# Age-Prediction-Model
Diversiboard TopCrowd- Data Science Intermediate I Challenge

## Introduction
The Age Prediction project aimed to solve problems by applying machine learning techniques. This report summarizes the findings and key insights from the project.

## Problem Statement
The objective of this project is to develop a machine learning model that can accurately predict the age of an entity based on various physical measurements.

The project will involve data preprocessing, feature engineering, model selection, and evaluation to develop a robust machine learning model. The model's performance will be assessed using appropriate evaluation metrics such as Mean Squared Error, Root Mean Squared Error, Mean Absolute Error, and R-squared to ensure accurate age predictions.

 ## Data Characteristics
 
* Sex - M, F, and I (infant).
* Length.
* Diameter.
* Height. 
* Whole Weight.
* Shucked Weight.
* Viscera Weight. 
* Shell Weight.
* Age. 

## Project Workflow
1) **Data Exploration:** In this step, I explored the dataset to gain a better understanding of its structure, variables, and overall quality.
2) **Exploratory Data Analysis**: EDA involved performing statistical analysis, visualizations, and summarization techniques to uncover patterns, relationships, and insights in the dataset. I analyzed the available features, their data types, distributions, and relationships with the target variable. Data exploration helped to identify outliers and anomalies that needed to be addressed during the preprocessing stage.  It helped to identify important variables, correlations, and potential predictive patterns that could guide feature selection and model development. EDA involved various techniques such as data visualization, correlation analysis.
3) **Feature Engineering:** Feature engineering involved transforming existing features and removing outliers using Interquartile range (IQR) to enhance the predictive power of the dataset.
4) **Data Preprocessing:** Data preprocessing is the step where I transformed and prepared the data for model training. This involved scaling numerical variables, and splitting the data into training and testing sets and applying Principal Component Analysis (PCA) to address Multicolinearity in the dataset. Data preprocessing ensured that the data is in a suitable format and quality for model training.
5)** Model Selection and Training:** In this step, I selected appropriate machine learning models that are suitable for the given problem and dataset. I considerED different algorithms such as linear regression, polynomial regression, decision tree regression, random forest regression, gradient boosting regression, support vector regression, etc. I trained these models on the preprocessed training data and evaluated their performance using appropriate evaluation metrics.
6) **Model Stacking and Saving:** Model stacking involved combining multiple trained models to create an ensemble model that leverages the strengths of each individual model. This was achieved by using stacking technique. The stacked model yielded a better prediction compared to using individual models alone. Once the stacked model was created, it was saved or using joblib for future use.
7) **Prediction:** After training the models, I used it to make predictions on new data. I inputed the relevant features of the new data into the trained model, and it outputs the predicted age. Prediction allowed the estimatation of the age.

## Results and Findings

### Model Performance:

| Algorithms                |   Mean Squared Error |   Root Mean Squared Error |   Mean Absolute Error |   R2 Score |
|:--------------------------|---------------------:|--------------------------:|----------------------:|-----------:|
| Linear Regression         |              2.37168 |                   1.54002 |               1.16586 |   0.534542 |
| Polynomial Regression     |              2.14027 |                   1.46297 |               1.10436 |   0.579957 |
| Decision Tree Regression  |              4.48317 |                   2.11735 |               1.55121 |   0.120147 |
| Random Forest Regression  |              2.29884 |                   1.51619 |               1.15048 |   0.548837 |
| Gradient Boost Regression |              2.20508 |                   1.48495 |               1.12408 |   0.567238 |
| SVR                       |              2.18867 |                   1.47941 |               1.08368 |   0.57046  |
| KNeighbors Regressor      |              2.5725  |                   1.6039  |               1.20735 |   0.495129 |
| Lasso                     |              3.02042 |                   1.73794 |               1.33818 |   0.407222 |
| Ridge                     |              2.37168 |                   1.54003 |               1.16585 |   0.534542 |
| Ada Boost                 |              2.75531 |                   1.65991 |               1.3618  |   0.459251 |

### Insights and Patterns:

💡 We can observe that there are 20,192 Data Samples in the training dataset with 9 columns describing each data sample, while there are only 10,000 Data Samples in the testing dataset.<br>

💡There are no missing values in both datasets.<br>

💡 The distribution of Age varies across different Sex categories, with Females generally having a higher age than males and infants.<br>

💡 We can observe that there are more of Male gender contained in the dataset followed by Infants and then Female gender.<br>

💡Heights feature contain a lot of outliers.<br>

💡Length and Diameter have negative skewness.<br>

💡 The Weight is strongly correlated with the Length, Diameter and Height which suggests that Weight can also be used as a predictor.<br>

💡The correlation matrix heatmap shows that there are strong positive correlations between the physical measurements (length, diameter, height, and weight), but only weak correlations between these measurements and the Age. This suggests that predicting the age from the physical measurements may require additional information.<br>

💡Variables with VIF scores close to 1 (e.g., Sex) indicate low multicollinearity, suggesting that these variables are not highly correlated with other predictors in the dataset.<br>

💡Variables with high VIF scores (e.g., Length, Diameter, Weight, Shucked Weight, Viscera Weight, Shell Weight) indicate a strong correlation with other predictor variables. These variables may exhibit multicollinearity, which can impact the stability and interpretability of regression models.<br>

💡Since 99.7% of the total variance is captured by the 1st 6 PCA itself, we take only 6 components of PCA and computing a correlation heatmap to overserve the multicollinearity.<br>

💡Hence by reducing the dimensionality of the data using PCA, the variance is preserved by 99.7% and multicollinearity of the data is removed.

### Challenges Encountered
Hypertunning the SVR Model and Gradient Boost Model took a lot more that 2 Hours which rendered the process obsolete which prompted me to find a new way to optimize my model by using a Stacking Regressor.

### Conclusion
It is important to note that predicting the age from the physical measurements may require additional information in order to achieve the highest possible accuracy. Therefore, future research should continue to explore and refine the predictive models for estimating the age using both physical measurements and any other relevant variables.

## Libraries Used

* Pandas
* Numpy
* Seaborn
* Matplotlib
* Sklearn

## Algorithms Used

*  Linear Regression
*  Polynomial Regression
*  Decision Tree Regressor
*  Random Forest Regressor
*  Gradient Boost Regressor
*  Support Vector Regressor
*  KNeighbors Regressor
*  Lasso Regression
*  Ridge Regression
*  Ada Boost Regressor
*  Stacking Regressor

 ## Selected Algorithm
The following models were best performing and were used as Base Models for the STACKING REGRESSOR.
 1) SVR MODEL
 2) POLYNOMIAL REGRESSION MODEL
 3) GRADIENT BOOST REGRESSION MODEL
