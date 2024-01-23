# Your First Machine Learning Model

## Selecting Data for Modeling

For the first example we will select the features based on intuition, but there are statistical methods to help to seelct which will feature later down the line.

We can use the `column` method to view all of the columns present in the dataset:

```python
data.columns
```
This will result in a list of all of the columns names.

We can also drop rows of data where there is missing data using the dropna method:
```python
data.dropna(axis=0)
```

There are two main waysd that we would subset the data to reach our final set of features for modelling:
- Using dot notation to select the target column
- using a list of column names to select the feature columns

### Selecting the Prediction Target

We can save the prediction variable to a y variable using dot notation like below.

```python
y = data.Price
```

## Choosing "Features"
The columns that we are going to use in our model are the features. We can select multiple columns from our dataset for this purpose by entering them into a list.

```python
features = ['Rooms', 'Bathroom', 'Landsize', 'Lattitude', 'Longtitude']
```

Once we have this list we can create an X variable using bracket notation which selects a subset of the data frame.

```python
X = data[features]
```

---
## Building Your Model

For this example we willl use the scikit-learn library to create the model (referred to in code as sklearn). 

Steps to build the model are as follows:
- Define: What type of model will it be?
- Fit: Capture patterns from provided data
- Predict: Make predictions
- Evaluate: How accurate are your predictions?

Here is an example for defining and fitting a decision tree model:

```python
from sklearn.tree import DecisionTreeRegressor
# Define
model = DecisionTreeRegressor(random_state=42)
# Fit
model.fit(X, y)
```

We specify a random state ensures that you get the same results eacch time you run.

Now that we have a fitted model to make predictions.

```python
print("Making predictions for the following 5 houses:")
print(X.head())
print("The predictions are")
print(model.predict(X.head()))
```

