---
title: "Pandas Cheatsheet"
date: 2020-09-18
tags: [python, pandas, datascience]
excerpt: "Python, Pandas, Datascience"
mathjax: "true"
---

```python
import pandas as pd
```


```python
# create dataframe
df = pd.DataFrame.from_dict([{'column1': 'column1-value1',
                              'column2': 'column2-value1',
                              'column3': 'column3-value1'},
                             {'column1': 'column1-value2',
                              'column2': 'column2-value2',
                              'column3': 'column3-value2'}])
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
df = df.rename(columns={"column1": "new_column1",
                        "column2": "new_column2"})
```


```python
# drop column
df = df.drop(['column3'], axis=1)
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
for index, row in df.iterrows():
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
