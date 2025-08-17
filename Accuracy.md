# E-Commerce Page Value Prediction from User Behavior Data

---

## Model Accuracy Before Feature Engineering
The initial set of models was trained **without advanced feature engineering**.  
Performance (measured in **RMSE**) was consistent but limited in capturing deeper session-level insights.

| Model                                         |    RMSE   |
|-----------------------------------------------|----------:|
| Linear Model                                  | 5.902286  |
| Random Sample Concuses (Linear Model)         | 6.018235  |
| Random Sample Concuses (Lasso Regularization) | 6.199422  |
| Polynomial Regression                         | 5.902286  |
| Random Forest Regression                      | 5.780631  |
| Gradient Boost Regression                     | 5.767567  |
---

## Feature Engineering Introduced
To better capture **user behavior patterns**, the following engineered features were created:

- **Page Ratios**:  
  *`adminPageRatio`*, *`infoPageRatio`* — show distribution of visits across page types  

- **Time Ratios**:  
  *`adminTimeRatio`*, *`infoTimeRatio`* — capture where session time is being spent  

- **Efficiency Metrics**:  
  *`pageValuePerView`*, *`timeToValueRatio`* — measure conversion efficiency of pages and time  

- **Engagement Score**:  
  *`engagementScore`* — a composite metric combining duration, value, and bounce rates  

- **Temporal Features**:  
  *`monthNum`*, *`season`* — to capture seasonality effects  

- **Visitor Segmentation**:  
  *`isHighValueVisitor`* — flagging above-average Page Value sessions  
  *`weekendHighEngagement`* — flagging highly engaged weekend sessions  

---

## Model Accuracy After Feature Engineering
With the engineered features included, the models showed improved generalization, particularly for ensemble methods.

| Model             | Test Score | Train Score |
|-------------------|------------|-------------|
| Linear Model      | 0.922663   | 0.937731    |
| Lasso Regression  | 1.321685   | 1.313111    |
| Polynomial Model  | 0.922663   | 0.937731    |
| Random Forest     | 0.912186   | 1.313111    |
| Gradient Boosting | **0.891760** | **0.885656** |

---

## Conclusion
- After adding **Feature Engineering**, the models became more capable of capturing **session engagement patterns, time allocation, and seasonal effects**.  
- **Gradient Boost Regression** emerged as the **best-performing model**, achieving the lowest RMSE on both training and testing sets while avoiding overfitting.  
- This highlights the importance of creating **domain-relevant features** that reflect actual user behavior rather than relying only on raw counts and durations.

---

## Tech Stack
- **Python**  
- **Pandas, NumPy, Scikit-learn**  
- **Matplotlib, Seaborn**  
- **Jupyter Notebook**

---

*This project demonstrates how careful feature engineering combined with ensemble methods can significantly improve predictive performance in real-world e-commerce analytics.*
