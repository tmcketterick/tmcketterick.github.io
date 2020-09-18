---
title: "Pandas Cheat Sheet"
date: 2020-09-18
tags: [pandas, python, cheat sheet]
header:
  image: "/images/2020-09-18-pandas-cheat-sheet/pandas.png"
excerpt: "Python, Pandas, Cheat sheet"
mathjax: "true"
---

```python
import pandas as pd
```


```python
# read file
df = pd.read_csv('filename.csv')
```


```python
# write file
df.to_csv('filename.csv', index=False)
```


```python
# rename column
df = df.rename(columns={"old_column_1": "new_column_1",
                        "old_column_2": "new_column_2"})
```


```python
# drop column
df = df.drop(['column_1', 'column_2'], axis=1)
```


```python
# flag duplicate rows
df['duplicates'] = df.duplicated(subset=['column1', 'column2'], keep=False)
```


```python
# groupby
df = df.groupby(['column_1', 'column_2'], as_index=False)['column_3'].count()
```


```python
# apply function to row
df['new_column'] = df.apply(lambda row: function(row['column_1'], row['column_2']), axis=1)
```


```python
# loop through rows
for index, row in df.iterrows:
    # read value
    val = row['column_name']
    # write value if condition met
    if <condition>:
        df.set_value(index,'column_name', new_val)
```


```python
# search a column list for contains
mask = df.['column_name'].apply(lambda x: any(item for item in column if item in x))
df1 = df[mask]
```
