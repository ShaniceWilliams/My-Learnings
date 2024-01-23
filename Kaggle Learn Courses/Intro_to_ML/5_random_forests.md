# Random Forests

## Introduction

Decision trees leave you with a difficult decision (haha) between overfitting and underfitting your data.

This is where random forests can come into play. The random forest model uses many trees and makes predictions by averaging the predicitions of all of the trees in the forest. This generally will perform better thant one single tree.

## Example

Building a random forest regressor is very similar to builfing a decision tree model as can be seen below:

```python
from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import mean_absolute_error

rf = RandomForestRegressor(random_state=1)
rf.fit(train_X, train_y)
rf_preds = rf.predict(test_X)
print(mean_absolute_error(test_y, rf_preds))

```