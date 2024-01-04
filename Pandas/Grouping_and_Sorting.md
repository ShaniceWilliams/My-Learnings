# Grouping and Sorting

## Groupwise analysis

We have used `value_counts()` at various points in previous sections. We can get the same effect with the following:

```Python
reviews.groupby('points').points.count()
```

`groupby()` created a group of reviews which allotted the same point values to the given wines. Then, for each of these groups, we grabbed the `.points` column and counted how many times it appeared. `value_counts()` is just a shortcut to this `groupby()` operation.

We can use the summary functions from the last topic, in conjunction with the groupby method to get more from the data:

```Python
reviews.groupby('points').price.min()
```

The above example will show the cheapest wine in each point value category.

When the groupby method is used, we generate a dataframe containing a slice of of our data. We can then use the apply method to manipulate that slice of data. The next example shows a way that we can find the first wine reviewed from each winery:

```Python
reviews.groupby('winery').apply(lambda df: df.title.iloc[0])
```

We can also group by more than one column, like in the next example we can look for the best wine grouped by country and province:

```Python
reviews.groupby(['country', 'province']).apply(lambda df: df.loc[df.points.idxmax()])
```

Another method we can use along side groupby is agg(), which allows you to run multiple methods on your slice to allow you to summarise the data. The folowing statement will give you a summary of the number of wine reviews, the minimum price and maximum price by country.

```Python
reviews.groupby(['country']).price.agg([len, min, max])
```
---
## Multi-indexes




## Sorting