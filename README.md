# E-Commerce Page Value Prediction from User Behavior Data

This project analyzes customer sentiment and predicts page value based on user behavior data from an e-commerce website. The goal is to understand the key drivers of revenue and build a machine learning model to predict which sessions are most likely to result in a purchase.

## Data Analysis and Visualizations

To understand user behavior and its impact on revenue, several analyses were performed:

### Key Visualizations and Findings

- **Product Page Visits Per Month**: Visits vary by month, indicating seasonal trends or marketing campaign impacts.
- **Revenue Generated Counts Per Month**: Reveals which months are most profitable, correlating with high product page visits.
- **Bounce Rate vs. Informational Page Visits**: Revenue-generating visitors tend to have lower bounce rates.
- **Visitor Type and Revenue**: A significant portion of both new and existing visitors do not make a purchase, highlighting an area for improvement in customer conversion.
- **Behavior of Buyers vs. Non-Buyers**: Buyers spend more time on product-related pages, indicating that engagement is a strong predictor of purchasing intent.

## Feature Engineering

To improve model performance, several features were engineered to capture user behavior more effectively:

- **`totalPagesViewed`**: Total pages viewed in a session.
- **`totalDuration`**: Total time spent on the website.
- **`avgTimePerPage`**: Average time spent per page.
- **`hasLongSession`**: Flag for sessions with a duration longer than the average.
- **`productFocus`**: Ratio of product-related pages to total pages viewed.
- **`productTimeRatio`**: Proportion of session time spent on product pages.
- **`pageValuePerView`**: Page value normalized by the number of pages viewed.
- **`engagementScore`**: A composite score combining duration, page value, and bounce rates.
- **`isHighValueVisitor`**: Flag for users with above-average page values.
- **`timeToValueRatio`**: Ratio of total duration to page value.
- **`season`**: Categorization of sessions into seasons.
- **`weekendHighEngagement`**: Flag for highly engaged weekend sessions.

## Machine Learning Models

Several regression models were trained to predict `PageValues`.

- **Data Preprocessing**:
    - **Label Encoding**: Converted categorical features to a numerical format.
    - **Standard Scaling**: Scaled encoded features.
    - **Power Transformation**: Applied to numerical features to stabilize variance.

- **Models Implemented**:
    - Linear Regression
    - Polynomial Regression
    - Lasso Regularization (L1)
    - Random Forest Regressor
    - Gradient Boosting Regressor
    - RANSAC Regressor

![Model Performance Scatter Plots](./ref_image/output.png)

## Model Performance and Accuracy

### Before Feature Engineering

| Model                                         |    RMSE   |
|-----------------------------------------------|----------:|
| Linear Model                                  | 5.902286  |
| Random Sample Concuses (Linear Model)         | 6.018235  |
| Random Sample Concuses (Lasso Regularization) | 6.199422  |
| Polynomial Regression                         | 5.902286  |
| Random Forest Regression                      | 5.780631  |
| Gradient Boost Regression                     | 5.767567  |

### After Feature Engineering

| Model             | Test Score | Train Score |
|-------------------|------------|-------------|
| Linear Model      | 0.922663   | 0.937731    |
| Lasso Regression  | 1.321685   | 1.313111    |
| Polynomial Model  | 0.922663   | 0.937731    |
| Random Forest     | 0.912186   | 1.313111    |
| Gradient Boosting | **0.891760** | **0.885656** |

**Conclusion**: Feature engineering significantly improved model performance, with Gradient Boost Regression emerging as the best-performing model.

## Tech Stack

- **Python**
- **Pandas, NumPy, Scikit-learn**
- **Matplotlib, Seaborn**
- **Jupyter Notebook**
