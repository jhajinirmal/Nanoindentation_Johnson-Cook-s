# Nanoindentation_Johnson-Cook's

Goal: The goal of this project was to establish a Relationship among yield stress (A/X), strain hardening constant (B/Y), strain hardening exponent (n) and Mean Loading Error (MLE) for the coating material Ni–P–Cu–W. 

Experimetal data for nanoindentation on Ni–P–Cu–W coated soft steel samples was provided by the client. The data included Load and indentation depth variables.

The same experiment was simulated on ABAQUS by fixing the maximum depth and 27 different combinations of A, B and n (3 factor 3 level design of experiment). The loads correponding to each combination were noted for different depths. The simulated loads were compared to the actual experimental loads and Mean Load Error was calculated for each combination. The data for 6 more sets of A, B and n were obtained for testing.

Different Machine Learning Algorithms were tested using 5-fold cross validation to avoid overfitting. Hyperparameter tuning was done using GridSearchCV and RandomizedSearchCV. The Mean Squared Errors for training and validation are below-

| Algorithm      | Train MSE  | Validation MSE |
| ----------- | ----------- | -------- |
| Linear Regression      | 0.2354       | 0.401 |
| DecisionTreeRegressor   | 0.2354        |  0.3714 |
| RandomForestRegressor      | 0.1075 |   0.362 |
| SVR | 0.3235 | 0.1679 |
| GradientBoostingRegressor      | 0.11       | 0.1897 |
| XGBoostRegressor   | 0.2178        | 0.1697 |


Based on the above results, XGBoost was chosen as the best algorithm.
The test MSE was found to be 0.2463.
