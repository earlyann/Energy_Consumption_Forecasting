## Energy Consumption XGBoost Model
### Project Overview
This project aims to predict energy consumption using XGBoost, a popular machine learning algorithm for regression and classification problems. The dataset contains historical energy consumption data, which is used to train the model and make predictions. The main focus is on improving the model's performance by incorporating various features and tuning hyperparameters.

### Technologies
- Python
- XGBoost
- Scikit-learn
- Pandas
- NumPy

### Project Description
Performance Metrics - 
The following performance metrics were used to assess the model's performance:

-  Mean Squared Error (MSE): Measures the average squared difference between the actual values and the predicted values from the model. It calculates how close the predictions are to the actual values by taking the difference, squaring it (to eliminate negative values), and then averaging those squared differences. A lower MSE value indicates better model performance.
##### Root Mean Squared Error (RMSE): Measures the average error made by the model in predicting the target variable. It is the square root of the Mean Squared Error and has the same unit as the original values, making it more interpretable than MSE. Like MSE, a lower RMSE value indicates better model performance.
- Mean Absolute Error (MAE): Measures the average absolute difference between the actual values and the predicted values from the model. It calculates how close the predictions are to the actual values by taking the absolute difference (ignoring the sign, positive or negative) and then averaging those differences. MAE is less sensitive to outliers than MSE and RMSE. A lower MAE value indicates better model performance.
Lower values for these metrics indicate better model performance.

### Models and Results
Four different models were built and evaluated, each incorporating different features to examine their impact on the model's performance:

- Model 1: Basic XGBoost model using original features from the dataset. This model serves as a baseline for comparison with subsequent models.
- Model 2: Model 1 + holiday data. Holiday data was added to examine whether energy consumption patterns change during holidays, potentially improving the model's predictive accuracy.
- Model 3: Model 2 + lag features. Lag features were introduced to capture the temporal dependencies in the data. These features represent the energy consumption values at previous time steps, which can help the model identify trends and seasonality in the data.
- RS Hyperparameter Tuned Model 3: Model 3 + hyperparameter tuning using Random Search. This model aims to optimize the performance by searching for the best combination of hyperparameters for the XGBoost algorithm.

### Insights
Model 1 and Model 2 have the same performance metrics on both the training and holdout sets, indicating that holiday data did not improve the model's performance. This suggests that holiday data may not be an important feature for this particular dataset or problem.
Model 3, which included lag features, showed a significant improvement in performance compared to Models 1 and 2. The much lower RMSE, MAE, and MSE values on both the training and holdout sets indicate that the lag features are valuable predictors and help the model make better predictions by capturing temporal dependencies in the data.
RS Hyperparameter Tuned Model 3 further improved the performance over Model 3, albeit with slightly higher RMSE, MAE, and MSE values on the training set. However, the performance on the holdout set is still better than Model 3, suggesting that hyperparameter tuning using random search was effective in improving the model's generalization. This implies that selecting the right hyperparameters plays an important role in optimizing the model's performance.

### Conclusion
Incorporating lag features and hyperparameter tuning with random search proved to be beneficial for the model's performance. The lag features helped capture temporal dependencies in the data, leading to better predictions by identifying trends and seasonality. Hyperparameter tuning using random search allowed the model to find the best combination of hyperparameters, resulting in improved generalization and performance on the holdout set. However, the holiday data did not have a noticeable impact on the model's performance, suggesting that it may not be an important feature for this particular dataset or problem.
