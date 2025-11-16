# MSCS 634 Lab 4: Regression and Regularization on the Diabetes Dataset

## Overview

This lab applies several regression techniques to the Diabetes dataset from scikit-learn in order to predict disease progression. The work focuses on understanding how model complexity and regularization affect prediction accuracy and generalization.

The following models were implemented and evaluated:

- Simple Linear Regression (single feature)
- Multiple Linear Regression (all features)
- Polynomial Regression
- Ridge Regression
- Lasso Regression

All models were trained and tested using the same data split, and their performance was compared using standard regression metrics.

## Dataset

The lab uses the Diabetes dataset from `sklearn.datasets`.  
The dataset contains standardized numerical features, including age, sex, body mass index, blood pressure, and several blood serum measurements, with the target representing a quantitative measure of disease progression.

Basic preprocessing steps included:

- Loading the dataset using scikit-learn utilities
- Converting the data to a pandas DataFrame
- Verifying that there were no missing values
- Splitting the data into training and testing sets

## Methods and Models

1. Simple Linear Regression  
   - Used a single feature as the independent variable.  
   - Provided a baseline for model performance.  

2. Multiple Linear Regression  
   - Used all available features as predictors.  
   - Captured the multivariate nature of the problem.  

3. Polynomial Regression  
   - Extended the feature space using polynomial terms.  
   - Allowed the model to fit non-linear relationships.  

4. Ridge Regression  
   - Applied L2 regularization to shrink coefficients.  
   - Aimed to reduce overfitting and handle multicollinearity.  

5. Lasso Regression  
   - Applied L1 regularization, encouraging sparse coefficients.  
   - Performed implicit feature selection by driving some coefficients to zero.  

Each model was evaluated using the following metrics:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R squared (R²)

Visualizations included:

- Scatter plots of actual versus predicted values
- Line or point plots comparing actual and predicted targets across the test set

## Results and Insights

The main numerical results for the models were:

- Simple Linear Regression: Highest error values and lowest R². It explained only a small portion of the variance in the target and served mainly as a weak baseline.
- Multiple Regression: Noticeable improvement in MAE, RMSE, and R² compared to the simple model. This confirmed that disease progression depends on multiple interacting features rather than a single variable.
- Polynomial Regression: Slightly worse or comparable performance to multiple regression. The additional flexibility did not translate into better test performance and showed signs of mild overfitting.
- Ridge Regression: Similar performance to polynomial regression. Regularization stabilized the coefficients but did not provide a large gain over multiple regression for this dataset.
- Lasso Regression: Best overall performance. It achieved the lowest RMSE and the highest R² among all models, indicating the best balance between accuracy and generalization. Lasso likely improved performance by reducing the influence of weak or noisy features through coefficient shrinkage and feature selection.

Overall, the results show that:

- Using multiple features is essential for modeling diabetes progression.
- Increasing model complexity through polynomial terms does not automatically improve generalization.
- Regularization, particularly L1 regularization in lasso, can improve performance by controlling overfitting and focusing the model on the most informative predictors.

## Challenges and Decisions

Several design decisions and challenges were encountered during the lab:

- Choosing the feature for simple linear regression required selecting a meaningful single predictor, such as body mass index, while understanding that this would be an intentionally limited model.
- Selecting the polynomial degree involved balancing model flexibility and overfitting risk. A moderate degree was chosen to avoid extreme overfitting while still capturing possible non-linear patterns.
- Setting the regularization strength (alpha) for ridge and lasso required experimentation. Too small an alpha behaves like standard linear regression, while too large an alpha can oversimplify the model and degrade performance.
- Comparing models fairly required using the same train–test split and the same evaluation metrics across all configurations.



