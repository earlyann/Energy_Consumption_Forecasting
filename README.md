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
##### Performance Metrics -
The following performance metrics were used to assess the model's performance:

- R-squared (R²): Measures the proportion of the variance in the dependent variable that can be explained by the independent variables in the model. R-squared ranges from 0 to 1, where a higher value indicates a better fit of the model to the data. A value of 1 means the model explains all the variability in the data.
- Root Mean Squared Error (RMSE): Measures the average error made by the model in predicting the target variable. It is the square root of the Mean Squared Error and has the same unit as the original values, making it more interpretable than MSE. A lower RMSE value indicates better model performance.
- Mean Absolute Error (MAE): Measures the average absolute difference between the actual values and the predicted values from the model. It calculates how close the predictions are to the actual values by taking the absolute difference (ignoring the sign, positive or negative) and then averaging those differences. MAE is less sensitive to outliers than RMSE. A lower MAE value indicates better model performance.

### Models
Four different models were built and evaluated, each incorporating different features to examine their impact on the model's performance:

- Model 1: Basic XGBoost model using original features from the dataset. This model serves as a baseline for comparison with subsequent models.
- Model 2: Model 1 + holiday data. Holiday data was added to examine whether energy consumption patterns change during holidays, potentially improving the model's predictive accuracy.
- Model 3: Model 2 + lag features. Lag features were introduced to capture the temporal dependencies in the data. These features represent the energy consumption values at previous time steps, which can help the model identify trends and seasonality in the data.
- RS Hyperparameter Tuned Model 3: Model 3 + hyperparameter tuning using Random Search. This model aims to optimize the performance by searching for the best combination of hyperparameters for the XGBoost algorithm.

### Results

![Screen Shot 2023-04-24 at 7 03 02 AM](https://user-images.githubusercontent.com/119711479/233990861-b8ef060f-7acf-46ed-9b9c-db91a835f326.png)

### Insights
- Model 1 and Model 2 have the same performance metrics on both the training and holdout sets, indicating that holiday data did not improve the model's performance. Looking at the feature importance for this model, confirms that the holiday information was not helpful.
- Model 3, which included lag features, showed a significant improvement in performance compared to Models 1 and 2. The much higher R-squared and lower RMSE and MAE values on both the training and holdout sets indicate that the lag features are valuable predictors and help the model make better predictions by capturing temporal dependencies in the data; looking at the feature importance of the model confirms the observation.
- RS Hyperparameter Tuned Model 3 demonstrated further improvements in performance compared to Model 3. Although it exhibited slightly higher RMSE and MAE values on the training set, this could indicate a potential reduction in overfitting. The performance on the holdout set remains superior to that of Model 3, which implies that hyperparameter tuning using random search effectively enhanced the model's generalization. While the R-squared value is marginally lower, it remains in close proximity to Model 3's R-squared value. Taking into account the overall improvements in RMSE and MAE on the holdout set, as well as the minor reduction in R-squared, we can conclude that hyperparameter tuning through random search successfully improved the model's generalization capabilities.


### Conclusion
Incorporating lag features and hyperparameter tuning with random search proved to be beneficial for the model's performance. The lag features helped capture temporal dependencies in the data, leading to better predictions by identifying trends and seasonality. Hyperparameter tuning using random search allowed the model to find the best combination of hyperparameters, resulting in improved generalization and performance on the holdout set. However, the holiday data did not have a noticeable impact on the model's performance, suggesting that it may not be an important feature for this particular dataset or problem.

#### Data sourced: https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption

Author: Lacey Morgan
