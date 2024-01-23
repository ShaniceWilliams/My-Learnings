# Model Validation

## What is Model Validation?

To get evaluate every model we make, we measure the model's quality using predictive accuracy. How close are the predictions that can made by are model to what will actually happen?
There are lots of ways to measure predictive accuracy based on the types of model you are using. For this example let's consider Mean Absolute Error (MAE).

This metric is calculated as the following:
$$
\sum_{i=1}^{D}|x_i-y_i|
$$

We can calculate this in python using the following:

```python
from sklearn.metrics import mean_absolute_error

predicted_home_prices = melbourne_model.predict(X)
mean_absolute_error(y, predicted_home_prices)
```

## The problem with "In-Sample" Scores

In the previous example we looked at measureing the model performance against the training data only, but this is not the way to run experiements.



## Coding It

We should create a train test split using the  following code:

```python
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_absolute_error

train_X, test_X, train_y, test_y = train_test_split(X, y, random_state=42)

model = DecisionTreeRegressor()

model.fit(train_X, train_y)

test_pred = model.predict(test_X)
print(mean_absolute_error(test_y, test_pred))
```