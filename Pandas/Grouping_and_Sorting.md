# Grouping and Sorting

## Groupwise analysis

We have used `value_counts()` at various points in previous sections. We can get the same effect with the following:

```Python
reviews.groupby('points').points.count()
```