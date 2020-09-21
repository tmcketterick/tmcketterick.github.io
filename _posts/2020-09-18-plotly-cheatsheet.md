

```python
import plotly.graph_objects as go
import plotly.express as px
```


```python
# load an example data frame
df = px.data.iris()
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>sepal_length</th>
      <th>sepal_width</th>
      <th>petal_length</th>
      <th>petal_width</th>
      <th>species</th>
      <th>species_id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5.1</td>
      <td>3.5</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>setosa</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4.9</td>
      <td>3.0</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>setosa</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4.7</td>
      <td>3.2</td>
      <td>1.3</td>
      <td>0.2</td>
      <td>setosa</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.6</td>
      <td>3.1</td>
      <td>1.5</td>
      <td>0.2</td>
      <td>setosa</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5.0</td>
      <td>3.6</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>setosa</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>



# Scatter plot


```python
fig = go.Figure()

# 'setosa'
species = 'setosa'
tmp = df[df['species'] == species]
data1 = go.Scatter(x=tmp['sepal_length'], y=tmp['sepal_width'], mode='markers', name=species,
                  marker=dict(line_width=1, size=8))

# 'versicolor'
species = 'versicolor'
tmp = df[df['species'] == species]
data2 = go.Scatter(x=tmp['sepal_length'], y=tmp['sepal_width'], mode='markers', name=species,
                  marker=dict(line_width=1, size=8))

# 'virginica'
species = 'virginica'
tmp = df[df['species'] == species]
data3 = go.Scatter(x=tmp['sepal_length'], y=tmp['sepal_width'], mode='markers', name=species,
                  marker=dict(line_width=1, size=8))

# layout
layout = go.Layout(title='Iris sepal-length vs sepal-width scatter plot',
                   xaxis_title="Sepal length (cm)",
                   yaxis_title="Sepal width (cm)",
                   legend_title="Species",
                   xaxis=dict(range=[0, 10]),
                   yaxis=dict(range=[0, 5]))

# plot
fig=go.Figure(data=[data1, data2, data3], layout=layout)
fig.show("svg")
```


![svg](/../images/2020-09-18-plotly-cheatsheet/plotly_001.svg)



```python

```
