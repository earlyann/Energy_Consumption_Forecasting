# energy_consumption_xgb_model



Mean Squared Error (MSE):
MSE measures the average squared difference between the actual values (true values) and the predicted values from the model. In other words, it calculates how close the predictions are to the actual values by taking the difference, squaring it (to eliminate negative values), and then averaging those squared differences. A lower MSE indicates better model performance.

Root Mean Squared Error (RMSE):
RMSE is the square root of the Mean Squared Error. It has the same unit as the original values, making it more interpretable than MSE. RMSE measures the average error made by the model in predicting the target variable. Like MSE, a lower RMSE value indicates better model performance.

Mean Absolute Error (MAE):
MAE measures the average absolute difference between the actual values and the predicted values from the model. It calculates how close the predictions are to the actual values by taking the absolute difference (ignoring the sign, positive or negative) and then averaging those differences. MAE is less sensitive to outliers than MSE and RMSE. A lower MAE value indicates better model performance.


MSE, RMSE, and MAE are all error metrics that help to assess the performance of a model.
They measure the difference between actual values and predicted values.
Lower values for these metrics indicate better model performance.
RMSE and MAE are more interpretable than MSE since they have the same unit as the original values.
MAE is less sensitive to outliers compared to MSE and RMSE.


Random Search:
Random Search is an  approach for hyperparameter tuning that is more efficient than Grid Search. Instead of trying all possible combinations of hyperparameter values, Random Search randomly samples a predefined number of combinations and evaluates the model performance for each sampled combination using cross-validation. It continues this process for a set number of iterations, and then selects the combination of hyperparameters that gives the best performance based on a chosen evaluation metric. Random Search can be more efficient than Grid Search, particularly when dealing with a large number of hyperparameters, as it does not need to try each combination.

Insights based on the results:

Model 1 and Model 2 have the same performance metrics on both the training and holdout sets, which suggests that adding holiday data (Model 2) did not improve the model's performance. This indicates that holiday data may not be an important feature for this particular dataset or problem.

Model 3, which included lag features, showed a significant improvement in performance compared to Models 1 and 2. The much lower RMSE, MAE, and MSE on both the training and holdout sets indicate that the lag features are valuable predictors and help the model make better predictions.

RS Hyperparameter Tuned Model 3 further improved the performance over Model 3, albeit with slightly higher RMSE, MAE, and MSE on the training set. However, the performance on the holdout set is still better than Model 3, suggesting that hyperparameter tuning using random search was effective in improving the model's generalization. This implies that selecting the right hyperparameters plays an important role in optimizing the model's performance.

In conclusion, incorporating lag features and hyperparameter tuning with random search have proven to be beneficial for the model's performance. The holiday data, however, did not have a noticeable impact on the model's performance.
