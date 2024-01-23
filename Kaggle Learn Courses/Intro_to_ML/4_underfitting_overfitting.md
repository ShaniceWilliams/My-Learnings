# Underfitting and Overfitting

## Experimenting with Different Models

Now that we have established a way to measure model accuracy, we can try different models to compare performance to see which will give the best predictions.

The decision tree model has lot's of hyperparameters that can be tested to see which set of parameters is optimal for our specific problem.

One of these such parameters is a trees depth, that is how many splits are made before coming to a prediction.

This is an example of a shallow tree:

![Insert image here]()

It is not uncommon for a tree toi have 10 splitsm leading to $2^{10}$ leaves.

When we divide the houses over so many leaves, thje predictions will be closer to the actual price in our training data, however it is morelikely that when the model sees new data, it will not reliably make predictions accuratgely. This is called **overfitting**, where a model fits the training data very well, but there is a high level of variance. 

At the other end of the spectrum, if there are two few splits, the predictions will not be very accurate even in the training set. This is called **underfitting**, and shows high bias.

## Example

```python
from sklearn.metrics import mean_absolute_error
from sklearn.tree import DecisionTreeRegressor

def get_mae(max_leaf_nodes, train_X, test_X, train_y, test_y):
    model = DecisionTreeRegressiopn(max_leaf_nodes=max_leaf_nodes, random_state=42)
    model.fit(train_X, train_y)
    preds = model.predict(test_X)
    mae = mean_absolute_error(test_y, preds)
    return(mae)


for i in [5, 50, 500, 1000, 5000]
    i_mae = get_mae(max_leaf_nodes, train_X, test_X, train_y, test_y)
    print(f"Max leaf nodes: {i} \t\t Mean Absolute Error: {i_mae}")
```