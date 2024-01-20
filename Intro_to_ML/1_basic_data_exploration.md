# Basic Data Exploration

## Using Pandas to get familiar with your data

Pandas is the library that most data scientists will use to explore and manipulate data. It is usually imported in the following way:

```python
import pandas as pd
```

We can read files in using the `read_csv` method. Then we can use the `describe` method to see as summary of descriptive statistics for all numerical columns within the dataset.

```python
df = pd.read_csv("file/path")
df.describe()
```

## Interpreting Data Description

The results of the `describe method contains the following:
- Count: shows how many rows have non-missing values.
- Mean: the average
- Std: the standard deviation, which measures how numerically spread out the values are.
- Min: the minimum value of that column
- 25%: 25th percentile value
- 50%: the median/ middle value of the column
- 75%: 75th percentile value
- Max: The maximum value for that column
