

```python
import pandas as pd 
```


```python
df1 = pd.read_csv('JC-201801-citibike-tripdata.csv')
df1.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>932</td>
      <td>2018-01-01 02:06:17.5410</td>
      <td>2018-01-01 02:21:50.0270</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>31929</td>
      <td>Subscriber</td>
      <td>1992</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>550</td>
      <td>2018-01-01 12:06:18.0390</td>
      <td>2018-01-01 12:15:28.4430</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>31845</td>
      <td>Subscriber</td>
      <td>1969</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>510</td>
      <td>2018-01-01 12:06:56.9780</td>
      <td>2018-01-01 12:15:27.8100</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>31708</td>
      <td>Subscriber</td>
      <td>1946</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>354</td>
      <td>2018-01-01 14:53:10.1860</td>
      <td>2018-01-01 14:59:05.0960</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>31697</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>250</td>
      <td>2018-01-01 17:34:30.1920</td>
      <td>2018-01-01 17:38:40.9840</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>40.719252</td>
      <td>-74.034234</td>
      <td>31861</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df1.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>932</td>
      <td>2018-01-01 02:06:17.5410</td>
      <td>2018-01-01 02:21:50.0270</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>31929</td>
      <td>Subscriber</td>
      <td>1992</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>550</td>
      <td>2018-01-01 12:06:18.0390</td>
      <td>2018-01-01 12:15:28.4430</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>31845</td>
      <td>Subscriber</td>
      <td>1969</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>510</td>
      <td>2018-01-01 12:06:56.9780</td>
      <td>2018-01-01 12:15:27.8100</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>31708</td>
      <td>Subscriber</td>
      <td>1946</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>354</td>
      <td>2018-01-01 14:53:10.1860</td>
      <td>2018-01-01 14:59:05.0960</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>31697</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>250</td>
      <td>2018-01-01 17:34:30.1920</td>
      <td>2018-01-01 17:38:40.9840</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>40.719252</td>
      <td>-74.034234</td>
      <td>31861</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2 = pd.read_csv('JC-201802-citibike-tripdata.csv')
df2.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>134</td>
      <td>2018-02-01 07:38:15.8650</td>
      <td>2018-02-01 07:40:30.5820</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29615</td>
      <td>Subscriber</td>
      <td>1966</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>413</td>
      <td>2018-02-01 08:19:35.8160</td>
      <td>2018-02-01 08:26:29.6490</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29641</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>77</td>
      <td>2018-02-01 08:31:03.0860</td>
      <td>2018-02-01 08:32:20.3510</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29621</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>404</td>
      <td>2018-02-01 15:23:15.0850</td>
      <td>2018-02-01 15:29:59.9300</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>31934</td>
      <td>Subscriber</td>
      <td>1980</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>230</td>
      <td>2018-02-01 15:26:01.8240</td>
      <td>2018-02-01 15:29:52.5440</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>29642</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df2.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>134</td>
      <td>2018-02-01 07:38:15.8650</td>
      <td>2018-02-01 07:40:30.5820</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29615</td>
      <td>Subscriber</td>
      <td>1966</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>413</td>
      <td>2018-02-01 08:19:35.8160</td>
      <td>2018-02-01 08:26:29.6490</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29641</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>77</td>
      <td>2018-02-01 08:31:03.0860</td>
      <td>2018-02-01 08:32:20.3510</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29621</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>404</td>
      <td>2018-02-01 15:23:15.0850</td>
      <td>2018-02-01 15:29:59.9300</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>31934</td>
      <td>Subscriber</td>
      <td>1980</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>230</td>
      <td>2018-02-01 15:26:01.8240</td>
      <td>2018-02-01 15:29:52.5440</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>29642</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3 = pd.read_csv('JC-201803-citibike-tripdata.csv')
df3.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>329</td>
      <td>2018-03-01 06:37:37.0380</td>
      <td>2018-03-01 06:43:06.5520</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>29284</td>
      <td>Subscriber</td>
      <td>1981</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>118</td>
      <td>2018-03-01 07:37:30.1210</td>
      <td>2018-03-01 07:39:28.3910</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29465</td>
      <td>Subscriber</td>
      <td>1966</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>76</td>
      <td>2018-03-01 08:26:17.9390</td>
      <td>2018-03-01 08:27:34.6770</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29681</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>578</td>
      <td>2018-03-01 12:10:36.2160</td>
      <td>2018-03-01 12:20:14.8690</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>31695</td>
      <td>Subscriber</td>
      <td>1970</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>485</td>
      <td>2018-03-01 12:21:47.8800</td>
      <td>2018-03-01 12:29:53.2990</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>31802</td>
      <td>Subscriber</td>
      <td>1979</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df3.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>329</td>
      <td>2018-03-01 06:37:37.0380</td>
      <td>2018-03-01 06:43:06.5520</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>29284</td>
      <td>Subscriber</td>
      <td>1981</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>118</td>
      <td>2018-03-01 07:37:30.1210</td>
      <td>2018-03-01 07:39:28.3910</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29465</td>
      <td>Subscriber</td>
      <td>1966</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>76</td>
      <td>2018-03-01 08:26:17.9390</td>
      <td>2018-03-01 08:27:34.6770</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29681</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>578</td>
      <td>2018-03-01 12:10:36.2160</td>
      <td>2018-03-01 12:20:14.8690</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>31695</td>
      <td>Subscriber</td>
      <td>1970</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>485</td>
      <td>2018-03-01 12:21:47.8800</td>
      <td>2018-03-01 12:29:53.2990</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>31802</td>
      <td>Subscriber</td>
      <td>1979</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df4 = pd.read_csv('JC-201804-citibike-tripdata.csv')
df4.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1814</td>
      <td>2018-04-01 09:43:51.1590</td>
      <td>2018-04-01 10:14:06.1300</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3638</td>
      <td>Washington St</td>
      <td>40.724294</td>
      <td>-74.035483</td>
      <td>26175</td>
      <td>Subscriber</td>
      <td>1978</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>298</td>
      <td>2018-04-01 11:42:53.7090</td>
      <td>2018-04-01 11:47:51.8770</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>31847</td>
      <td>Subscriber</td>
      <td>1979</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1060</td>
      <td>2018-04-01 12:43:11.9640</td>
      <td>2018-04-01 13:00:52.8700</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>33463</td>
      <td>Subscriber</td>
      <td>1972</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1035</td>
      <td>2018-04-01 12:43:40.5890</td>
      <td>2018-04-01 13:00:55.6620</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>31738</td>
      <td>Subscriber</td>
      <td>1983</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>559</td>
      <td>2018-04-01 12:56:47.4600</td>
      <td>2018-04-01 13:06:06.7710</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>31925</td>
      <td>Subscriber</td>
      <td>1989</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df4.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df4.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1814</td>
      <td>2018-04-01 09:43:51.1590</td>
      <td>2018-04-01 10:14:06.1300</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3638</td>
      <td>Washington St</td>
      <td>40.724294</td>
      <td>-74.035483</td>
      <td>26175</td>
      <td>Subscriber</td>
      <td>1978</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>298</td>
      <td>2018-04-01 11:42:53.7090</td>
      <td>2018-04-01 11:47:51.8770</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>31847</td>
      <td>Subscriber</td>
      <td>1979</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1060</td>
      <td>2018-04-01 12:43:11.9640</td>
      <td>2018-04-01 13:00:52.8700</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>33463</td>
      <td>Subscriber</td>
      <td>1972</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1035</td>
      <td>2018-04-01 12:43:40.5890</td>
      <td>2018-04-01 13:00:55.6620</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>31738</td>
      <td>Subscriber</td>
      <td>1983</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>559</td>
      <td>2018-04-01 12:56:47.4600</td>
      <td>2018-04-01 13:06:06.7710</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>31925</td>
      <td>Subscriber</td>
      <td>1989</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df5 = pd.read_csv('JC-201805-citibike-tripdata.csv')
df5.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>131</td>
      <td>2018-05-01 07:29:57.5490</td>
      <td>2018-05-01 07:32:08.6160</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29617</td>
      <td>Subscriber</td>
      <td>1966</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>73</td>
      <td>2018-05-01 08:13:58.2560</td>
      <td>2018-05-01 08:15:11.9230</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29288</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4929</td>
      <td>2018-05-01 08:17:21.3110</td>
      <td>2018-05-01 09:39:31.0770</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>29520</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>432</td>
      <td>2018-05-01 08:25:58.7150</td>
      <td>2018-05-01 08:33:10.8960</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>29595</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>432</td>
      <td>2018-05-01 08:28:09.9160</td>
      <td>2018-05-01 08:35:22.1440</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3638</td>
      <td>Washington St</td>
      <td>40.724294</td>
      <td>-74.035483</td>
      <td>33623</td>
      <td>Subscriber</td>
      <td>1959</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df5.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df5.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>131</td>
      <td>2018-05-01 07:29:57.5490</td>
      <td>2018-05-01 07:32:08.6160</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29617</td>
      <td>Subscriber</td>
      <td>1966</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>73</td>
      <td>2018-05-01 08:13:58.2560</td>
      <td>2018-05-01 08:15:11.9230</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29288</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4929</td>
      <td>2018-05-01 08:17:21.3110</td>
      <td>2018-05-01 09:39:31.0770</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>29520</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>432</td>
      <td>2018-05-01 08:25:58.7150</td>
      <td>2018-05-01 08:33:10.8960</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>29595</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>432</td>
      <td>2018-05-01 08:28:09.9160</td>
      <td>2018-05-01 08:35:22.1440</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3638</td>
      <td>Washington St</td>
      <td>40.724294</td>
      <td>-74.035483</td>
      <td>33623</td>
      <td>Subscriber</td>
      <td>1959</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df6 = pd.read_csv('JC-201806-citibike-tripdata.csv')
df6.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>329</td>
      <td>2018-06-01 07:07:00.2990</td>
      <td>2018-06-01 07:12:30.2220</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>29513</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>259</td>
      <td>2018-06-01 08:24:43.8490</td>
      <td>2018-06-01 08:29:03.8450</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>26221</td>
      <td>Subscriber</td>
      <td>1989</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>686</td>
      <td>2018-06-01 09:17:49.5730</td>
      <td>2018-06-01 09:29:16.1770</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>29266</td>
      <td>Subscriber</td>
      <td>1990</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>164</td>
      <td>2018-06-01 09:44:00.4020</td>
      <td>2018-06-01 09:46:44.6830</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29472</td>
      <td>Subscriber</td>
      <td>1993</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>769</td>
      <td>2018-06-01 09:59:28.7800</td>
      <td>2018-06-01 10:12:18.6660</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>33679</td>
      <td>Subscriber</td>
      <td>1977</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df6.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df6.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>329</td>
      <td>2018-06-01 07:07:00.2990</td>
      <td>2018-06-01 07:12:30.2220</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>29513</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>259</td>
      <td>2018-06-01 08:24:43.8490</td>
      <td>2018-06-01 08:29:03.8450</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>26221</td>
      <td>Subscriber</td>
      <td>1989</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>686</td>
      <td>2018-06-01 09:17:49.5730</td>
      <td>2018-06-01 09:29:16.1770</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>29266</td>
      <td>Subscriber</td>
      <td>1990</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>164</td>
      <td>2018-06-01 09:44:00.4020</td>
      <td>2018-06-01 09:46:44.6830</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29472</td>
      <td>Subscriber</td>
      <td>1993</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>769</td>
      <td>2018-06-01 09:59:28.7800</td>
      <td>2018-06-01 10:12:18.6660</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>33679</td>
      <td>Subscriber</td>
      <td>1977</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df7 = pd.read_csv('JC-201807-citibike-tripdata.csv')
df7.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1234</td>
      <td>2018-07-01 02:08:39.8920</td>
      <td>2018-07-01 02:29:14.4890</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26306</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1041</td>
      <td>2018-07-01 02:09:07.5180</td>
      <td>2018-07-01 02:26:28.8720</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>29204</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2308</td>
      <td>2018-07-01 02:14:45.7400</td>
      <td>2018-07-01 02:53:14.5970</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26234</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>767</td>
      <td>2018-07-01 02:25:12.4020</td>
      <td>2018-07-01 02:38:00.0510</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26238</td>
      <td>Subscriber</td>
      <td>1992</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>151</td>
      <td>2018-07-01 04:07:44.0520</td>
      <td>2018-07-01 04:10:15.8010</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>29204</td>
      <td>Subscriber</td>
      <td>1972</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df7.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df7.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1234</td>
      <td>2018-07-01 02:08:39.8920</td>
      <td>2018-07-01 02:29:14.4890</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26306</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1041</td>
      <td>2018-07-01 02:09:07.5180</td>
      <td>2018-07-01 02:26:28.8720</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>29204</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2308</td>
      <td>2018-07-01 02:14:45.7400</td>
      <td>2018-07-01 02:53:14.5970</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26234</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>767</td>
      <td>2018-07-01 02:25:12.4020</td>
      <td>2018-07-01 02:38:00.0510</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26238</td>
      <td>Subscriber</td>
      <td>1992</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>151</td>
      <td>2018-07-01 04:07:44.0520</td>
      <td>2018-07-01 04:10:15.8010</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>29204</td>
      <td>Subscriber</td>
      <td>1972</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df8 = pd.read_csv('JC-201808-citibike-tripdata.csv')
df8.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>903</td>
      <td>2018-08-01 06:40:33.3610</td>
      <td>2018-08-01 06:55:37.1060</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>29612</td>
      <td>Subscriber</td>
      <td>1977</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>78</td>
      <td>2018-08-01 08:21:00.1450</td>
      <td>2018-08-01 08:22:18.6310</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29791</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>405</td>
      <td>2018-08-01 08:43:52.5150</td>
      <td>2018-08-01 08:50:37.6140</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>29571</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>155</td>
      <td>2018-08-01 09:48:24.9450</td>
      <td>2018-08-01 09:51:00.9360</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>29504</td>
      <td>Subscriber</td>
      <td>1971</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>453</td>
      <td>2018-08-01 12:15:35.1230</td>
      <td>2018-08-01 12:23:08.8880</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3273</td>
      <td>Manila &amp; 1st</td>
      <td>40.721651</td>
      <td>-74.042884</td>
      <td>33669</td>
      <td>Subscriber</td>
      <td>1993</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df8.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df8.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>903</td>
      <td>2018-08-01 06:40:33.3610</td>
      <td>2018-08-01 06:55:37.1060</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>29612</td>
      <td>Subscriber</td>
      <td>1977</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>78</td>
      <td>2018-08-01 08:21:00.1450</td>
      <td>2018-08-01 08:22:18.6310</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29791</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>405</td>
      <td>2018-08-01 08:43:52.5150</td>
      <td>2018-08-01 08:50:37.6140</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>29571</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>155</td>
      <td>2018-08-01 09:48:24.9450</td>
      <td>2018-08-01 09:51:00.9360</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>29504</td>
      <td>Subscriber</td>
      <td>1971</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>453</td>
      <td>2018-08-01 12:15:35.1230</td>
      <td>2018-08-01 12:23:08.8880</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3273</td>
      <td>Manila &amp; 1st</td>
      <td>40.721651</td>
      <td>-74.042884</td>
      <td>33669</td>
      <td>Subscriber</td>
      <td>1993</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df9 = pd.read_csv('JC-201809-citibike-tripdata.csv')
df9.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>284</td>
      <td>2018-09-01 01:48:22.0320</td>
      <td>2018-09-01 01:53:06.9130</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>26303</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>370</td>
      <td>2018-09-01 01:48:22.5010</td>
      <td>2018-09-01 01:54:32.9270</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>29667</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1181</td>
      <td>2018-09-01 09:37:04.3070</td>
      <td>2018-09-01 09:56:45.3280</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>26307</td>
      <td>Customer</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>383</td>
      <td>2018-09-01 09:44:46.0030</td>
      <td>2018-09-01 09:51:09.9230</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>29261</td>
      <td>Subscriber</td>
      <td>1987</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>377</td>
      <td>2018-09-01 09:44:46.1850</td>
      <td>2018-09-01 09:51:03.6330</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>33665</td>
      <td>Subscriber</td>
      <td>1985</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df9.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df9.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>284</td>
      <td>2018-09-01 01:48:22.0320</td>
      <td>2018-09-01 01:53:06.9130</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>26303</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>370</td>
      <td>2018-09-01 01:48:22.5010</td>
      <td>2018-09-01 01:54:32.9270</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>29667</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1181</td>
      <td>2018-09-01 09:37:04.3070</td>
      <td>2018-09-01 09:56:45.3280</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>26307</td>
      <td>Customer</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>383</td>
      <td>2018-09-01 09:44:46.0030</td>
      <td>2018-09-01 09:51:09.9230</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>29261</td>
      <td>Subscriber</td>
      <td>1987</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>377</td>
      <td>2018-09-01 09:44:46.1850</td>
      <td>2018-09-01 09:51:03.6330</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>33665</td>
      <td>Subscriber</td>
      <td>1985</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df10 = pd.read_csv('JC-201810-citibike-tripdata.csv')
df10.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>152</td>
      <td>2018-10-01 07:44:41.4170</td>
      <td>2018-10-01 07:47:14.2960</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>40.719252</td>
      <td>-74.034234</td>
      <td>15302</td>
      <td>Subscriber</td>
      <td>1971</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>122</td>
      <td>2018-10-01 08:50:05.4340</td>
      <td>2018-10-01 08:52:08.2250</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>29654</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>211</td>
      <td>2018-10-01 09:03:17.0640</td>
      <td>2018-10-01 09:06:48.0940</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>33621</td>
      <td>Subscriber</td>
      <td>1958</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>342</td>
      <td>2018-10-01 10:13:07.0090</td>
      <td>2018-10-01 10:18:49.8960</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>26266</td>
      <td>Subscriber</td>
      <td>1982</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2976</td>
      <td>2018-10-01 10:45:14.2800</td>
      <td>2018-10-01 11:34:51.2610</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>27083</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df10.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df10.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>152</td>
      <td>2018-10-01 07:44:41.4170</td>
      <td>2018-10-01 07:47:14.2960</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>40.719252</td>
      <td>-74.034234</td>
      <td>15302</td>
      <td>Subscriber</td>
      <td>1971</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>122</td>
      <td>2018-10-01 08:50:05.4340</td>
      <td>2018-10-01 08:52:08.2250</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>29654</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>211</td>
      <td>2018-10-01 09:03:17.0640</td>
      <td>2018-10-01 09:06:48.0940</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>33621</td>
      <td>Subscriber</td>
      <td>1958</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>342</td>
      <td>2018-10-01 10:13:07.0090</td>
      <td>2018-10-01 10:18:49.8960</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>26266</td>
      <td>Subscriber</td>
      <td>1982</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2976</td>
      <td>2018-10-01 10:45:14.2800</td>
      <td>2018-10-01 11:34:51.2610</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>27083</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df11 = pd.read_csv('JC-201811-citibike-tripdata.csv')
df11.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1188</td>
      <td>2018-11-01 06:32:27.5190</td>
      <td>2018-11-01 06:52:15.9140</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>33662</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>278</td>
      <td>2018-11-01 07:14:31.8680</td>
      <td>2018-11-01 07:19:10.2610</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>29254</td>
      <td>Subscriber</td>
      <td>1963</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>115</td>
      <td>2018-11-01 07:33:17.1920</td>
      <td>2018-11-01 07:35:12.2830</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>33607</td>
      <td>Subscriber</td>
      <td>1966</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>155</td>
      <td>2018-11-01 08:20:10.9320</td>
      <td>2018-11-01 08:22:46.7050</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3681</td>
      <td>Grand St</td>
      <td>40.715178</td>
      <td>-74.037683</td>
      <td>29222</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>82</td>
      <td>2018-11-01 08:35:02.7850</td>
      <td>2018-11-01 08:36:25.1840</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29678</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df11.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df11.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1188</td>
      <td>2018-11-01 06:32:27.5190</td>
      <td>2018-11-01 06:52:15.9140</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>33662</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>278</td>
      <td>2018-11-01 07:14:31.8680</td>
      <td>2018-11-01 07:19:10.2610</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>29254</td>
      <td>Subscriber</td>
      <td>1963</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>115</td>
      <td>2018-11-01 07:33:17.1920</td>
      <td>2018-11-01 07:35:12.2830</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>33607</td>
      <td>Subscriber</td>
      <td>1966</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>155</td>
      <td>2018-11-01 08:20:10.9320</td>
      <td>2018-11-01 08:22:46.7050</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3681</td>
      <td>Grand St</td>
      <td>40.715178</td>
      <td>-74.037683</td>
      <td>29222</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>82</td>
      <td>2018-11-01 08:35:02.7850</td>
      <td>2018-11-01 08:36:25.1840</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>29678</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df12 = pd.read_csv('JC-201812-citibike-tripdata.csv')
df12.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>170</td>
      <td>2018-12-01 00:03:53.3860</td>
      <td>2018-12-01 00:06:43.7160</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>26261</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>172</td>
      <td>2018-12-01 00:47:13.7340</td>
      <td>2018-12-01 00:50:05.8160</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3481</td>
      <td>York St</td>
      <td>40.716490</td>
      <td>-74.041050</td>
      <td>26175</td>
      <td>Subscriber</td>
      <td>1988</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>247</td>
      <td>2018-12-01 00:48:57.6960</td>
      <td>2018-12-01 00:53:05.6780</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29255</td>
      <td>Subscriber</td>
      <td>1990</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>406</td>
      <td>2018-12-01 01:33:53.6630</td>
      <td>2018-12-01 01:40:39.7480</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3638</td>
      <td>Washington St</td>
      <td>40.724294</td>
      <td>-74.035483</td>
      <td>29275</td>
      <td>Subscriber</td>
      <td>1995</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>354</td>
      <td>2018-12-01 06:26:52.5120</td>
      <td>2018-12-01 06:32:46.5170</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>29658</td>
      <td>Subscriber</td>
      <td>1976</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df12.rename(columns = {'Trip Duration': 'tripduration', 'Start Time': 'starttime', 
                      'Stop Time': 'stoptime', 'Gender':'gender', "User Type": "usertype",
                      'Bike ID': 'bikeid', 'Birth Year': 'birth year', 'Start Station ID': 'start station id',
                      'Start Station Name': 'start station name', 'Start Station Latitude': 'start station latitude',
                      'Start Station Longitude': 'start station longitude', 'End Station ID': 'end station id', 
                      'End Station Name': 'end station name', 'End Station Latitude': 'end station latitude',
                      'End Station Longitude': 'end station longitude'}, inplace = True)
df12.head()
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>170</td>
      <td>2018-12-01 00:03:53.3860</td>
      <td>2018-12-01 00:06:43.7160</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>26261</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>172</td>
      <td>2018-12-01 00:47:13.7340</td>
      <td>2018-12-01 00:50:05.8160</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3481</td>
      <td>York St</td>
      <td>40.716490</td>
      <td>-74.041050</td>
      <td>26175</td>
      <td>Subscriber</td>
      <td>1988</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>247</td>
      <td>2018-12-01 00:48:57.6960</td>
      <td>2018-12-01 00:53:05.6780</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29255</td>
      <td>Subscriber</td>
      <td>1990</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>406</td>
      <td>2018-12-01 01:33:53.6630</td>
      <td>2018-12-01 01:40:39.7480</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3638</td>
      <td>Washington St</td>
      <td>40.724294</td>
      <td>-74.035483</td>
      <td>29275</td>
      <td>Subscriber</td>
      <td>1995</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>354</td>
      <td>2018-12-01 06:26:52.5120</td>
      <td>2018-12-01 06:32:46.5170</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>29658</td>
      <td>Subscriber</td>
      <td>1976</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
jc_citibike_2018 = pd.concat([df1, df2, df3, df4, df5, df6, df7, df8, df9, df10, df11, df12])
jc_citibike_2018
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
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>start station latitude</th>
      <th>start station longitude</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>end station latitude</th>
      <th>end station longitude</th>
      <th>bikeid</th>
      <th>usertype</th>
      <th>birth year</th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>932</td>
      <td>2018-01-01 02:06:17.5410</td>
      <td>2018-01-01 02:21:50.0270</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>31929</td>
      <td>Subscriber</td>
      <td>1992</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>550</td>
      <td>2018-01-01 12:06:18.0390</td>
      <td>2018-01-01 12:15:28.4430</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>31845</td>
      <td>Subscriber</td>
      <td>1969</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>510</td>
      <td>2018-01-01 12:06:56.9780</td>
      <td>2018-01-01 12:15:27.8100</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>31708</td>
      <td>Subscriber</td>
      <td>1946</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>354</td>
      <td>2018-01-01 14:53:10.1860</td>
      <td>2018-01-01 14:59:05.0960</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>31697</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>250</td>
      <td>2018-01-01 17:34:30.1920</td>
      <td>2018-01-01 17:38:40.9840</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>40.719252</td>
      <td>-74.034234</td>
      <td>31861</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>1</td>
    </tr>
    <tr>
      <th>5</th>
      <td>613</td>
      <td>2018-01-01 22:05:05.8740</td>
      <td>2018-01-01 22:15:19.4190</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>31859</td>
      <td>Subscriber</td>
      <td>1982</td>
      <td>1</td>
    </tr>
    <tr>
      <th>6</th>
      <td>290</td>
      <td>2018-01-02 12:13:51.7940</td>
      <td>2018-01-02 12:18:42.1070</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>31694</td>
      <td>Subscriber</td>
      <td>1958</td>
      <td>1</td>
    </tr>
    <tr>
      <th>7</th>
      <td>381</td>
      <td>2018-01-02 12:50:03.3430</td>
      <td>2018-01-02 12:56:24.6440</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3205</td>
      <td>JC Medical Center</td>
      <td>40.716540</td>
      <td>-74.049638</td>
      <td>31754</td>
      <td>Subscriber</td>
      <td>1989</td>
      <td>2</td>
    </tr>
    <tr>
      <th>8</th>
      <td>318</td>
      <td>2018-01-02 13:55:58.2430</td>
      <td>2018-01-02 14:01:16.8810</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>31816</td>
      <td>Subscriber</td>
      <td>1960</td>
      <td>1</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1852</td>
      <td>2018-01-02 16:55:29.6390</td>
      <td>2018-01-02 17:26:22.3050</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3281</td>
      <td>Leonard Gordon Park</td>
      <td>40.745910</td>
      <td>-74.057271</td>
      <td>31754</td>
      <td>Subscriber</td>
      <td>1976</td>
      <td>1</td>
    </tr>
    <tr>
      <th>10</th>
      <td>460</td>
      <td>2018-01-02 17:01:50.5860</td>
      <td>2018-01-02 17:09:31.4340</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>33463</td>
      <td>Subscriber</td>
      <td>1989</td>
      <td>2</td>
    </tr>
    <tr>
      <th>11</th>
      <td>403</td>
      <td>2018-01-02 17:05:12.2360</td>
      <td>2018-01-02 17:11:55.2630</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3205</td>
      <td>JC Medical Center</td>
      <td>40.716540</td>
      <td>-74.049638</td>
      <td>26256</td>
      <td>Subscriber</td>
      <td>1985</td>
      <td>1</td>
    </tr>
    <tr>
      <th>12</th>
      <td>264</td>
      <td>2018-01-02 17:05:12.6730</td>
      <td>2018-01-02 17:09:37.4020</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29616</td>
      <td>Subscriber</td>
      <td>1974</td>
      <td>1</td>
    </tr>
    <tr>
      <th>13</th>
      <td>282</td>
      <td>2018-01-02 17:19:56.6090</td>
      <td>2018-01-02 17:24:39.5340</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29681</td>
      <td>Subscriber</td>
      <td>1976</td>
      <td>1</td>
    </tr>
    <tr>
      <th>14</th>
      <td>308</td>
      <td>2018-01-02 17:31:45.9880</td>
      <td>2018-01-02 17:36:54.3590</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>31949</td>
      <td>Subscriber</td>
      <td>1968</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15</th>
      <td>561</td>
      <td>2018-01-02 17:32:54.8400</td>
      <td>2018-01-02 17:42:16.3140</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3269</td>
      <td>Brunswick &amp; 6th</td>
      <td>40.726012</td>
      <td>-74.050389</td>
      <td>29591</td>
      <td>Subscriber</td>
      <td>1976</td>
      <td>1</td>
    </tr>
    <tr>
      <th>16</th>
      <td>114</td>
      <td>2018-01-02 17:37:44.3450</td>
      <td>2018-01-02 17:39:38.8760</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>40.719252</td>
      <td>-74.034234</td>
      <td>31925</td>
      <td>Subscriber</td>
      <td>1988</td>
      <td>1</td>
    </tr>
    <tr>
      <th>17</th>
      <td>302</td>
      <td>2018-01-02 17:54:04.8770</td>
      <td>2018-01-02 17:59:06.9730</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>31777</td>
      <td>Subscriber</td>
      <td>1990</td>
      <td>1</td>
    </tr>
    <tr>
      <th>18</th>
      <td>230</td>
      <td>2018-01-02 17:58:24.6360</td>
      <td>2018-01-02 18:02:15.6320</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>31763</td>
      <td>Subscriber</td>
      <td>1992</td>
      <td>1</td>
    </tr>
    <tr>
      <th>19</th>
      <td>596</td>
      <td>2018-01-02 18:05:59.6240</td>
      <td>2018-01-02 18:15:55.8590</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29662</td>
      <td>Subscriber</td>
      <td>1992</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20</th>
      <td>826</td>
      <td>2018-01-02 18:10:58.8600</td>
      <td>2018-01-02 18:24:45.1600</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>31765</td>
      <td>Subscriber</td>
      <td>1989</td>
      <td>1</td>
    </tr>
    <tr>
      <th>21</th>
      <td>368</td>
      <td>2018-01-02 18:13:41.8510</td>
      <td>2018-01-02 18:19:49.9780</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>31695</td>
      <td>Subscriber</td>
      <td>1985</td>
      <td>1</td>
    </tr>
    <tr>
      <th>22</th>
      <td>291</td>
      <td>2018-01-02 18:18:41.6860</td>
      <td>2018-01-02 18:23:33.0620</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>31934</td>
      <td>Subscriber</td>
      <td>1980</td>
      <td>1</td>
    </tr>
    <tr>
      <th>23</th>
      <td>250</td>
      <td>2018-01-02 18:20:06.1050</td>
      <td>2018-01-02 18:24:16.1640</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>31880</td>
      <td>Subscriber</td>
      <td>1995</td>
      <td>1</td>
    </tr>
    <tr>
      <th>24</th>
      <td>199</td>
      <td>2018-01-02 18:31:11.9870</td>
      <td>2018-01-02 18:34:31.1880</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29623</td>
      <td>Subscriber</td>
      <td>1980</td>
      <td>1</td>
    </tr>
    <tr>
      <th>25</th>
      <td>225</td>
      <td>2018-01-02 18:38:50.5100</td>
      <td>2018-01-02 18:42:36.2120</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>31691</td>
      <td>Subscriber</td>
      <td>1992</td>
      <td>1</td>
    </tr>
    <tr>
      <th>26</th>
      <td>242</td>
      <td>2018-01-02 18:41:29.5240</td>
      <td>2018-01-02 18:45:32.3240</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>26314</td>
      <td>Subscriber</td>
      <td>1981</td>
      <td>0</td>
    </tr>
    <tr>
      <th>27</th>
      <td>214</td>
      <td>2018-01-02 18:42:30.3030</td>
      <td>2018-01-02 18:46:04.4630</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29581</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>1</td>
    </tr>
    <tr>
      <th>28</th>
      <td>218</td>
      <td>2018-01-02 19:29:20.7870</td>
      <td>2018-01-02 19:32:59.1490</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>31954</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>1</td>
    </tr>
    <tr>
      <th>29</th>
      <td>318</td>
      <td>2018-01-02 19:30:19.4880</td>
      <td>2018-01-02 19:35:37.5450</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29615</td>
      <td>Subscriber</td>
      <td>1978</td>
      <td>1</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>20175</th>
      <td>747</td>
      <td>2018-12-10 20:33:10.0440</td>
      <td>2018-12-10 20:45:37.2790</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>29519</td>
      <td>Subscriber</td>
      <td>1958</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20176</th>
      <td>1124</td>
      <td>2018-12-11 06:19:14.0610</td>
      <td>2018-12-11 06:37:58.7960</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>29657</td>
      <td>Subscriber</td>
      <td>1977</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20177</th>
      <td>648</td>
      <td>2018-12-11 12:01:04.1040</td>
      <td>2018-12-11 12:11:52.9080</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>26287</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20178</th>
      <td>575</td>
      <td>2018-12-11 17:46:56.6360</td>
      <td>2018-12-11 17:56:31.6520</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3191</td>
      <td>Union St</td>
      <td>40.718211</td>
      <td>-74.083639</td>
      <td>29239</td>
      <td>Subscriber</td>
      <td>1958</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20179</th>
      <td>961</td>
      <td>2018-12-12 06:19:04.3900</td>
      <td>2018-12-12 06:35:05.8390</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26247</td>
      <td>Subscriber</td>
      <td>1977</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20180</th>
      <td>2058</td>
      <td>2018-12-12 09:09:44.0380</td>
      <td>2018-12-12 09:44:02.7900</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>29641</td>
      <td>Subscriber</td>
      <td>1957</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20181</th>
      <td>640</td>
      <td>2018-12-12 11:54:45.5290</td>
      <td>2018-12-12 12:05:25.7630</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>29641</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20182</th>
      <td>934</td>
      <td>2018-12-13 06:16:06.7510</td>
      <td>2018-12-13 06:31:41.2170</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>29681</td>
      <td>Subscriber</td>
      <td>1977</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20183</th>
      <td>703</td>
      <td>2018-12-13 12:17:13.6280</td>
      <td>2018-12-13 12:28:57.2350</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>26190</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20184</th>
      <td>936</td>
      <td>2018-12-14 06:10:18.5060</td>
      <td>2018-12-14 06:25:54.6120</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26155</td>
      <td>Subscriber</td>
      <td>1977</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20185</th>
      <td>668</td>
      <td>2018-12-14 12:34:01.0310</td>
      <td>2018-12-14 12:45:09.6550</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>26312</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20186</th>
      <td>645</td>
      <td>2018-12-15 13:31:59.3590</td>
      <td>2018-12-15 13:42:45.2030</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>29224</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20187</th>
      <td>1396</td>
      <td>2018-12-15 16:28:38.1250</td>
      <td>2018-12-15 16:51:54.9460</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3279</td>
      <td>Dixon Mills</td>
      <td>40.721630</td>
      <td>-74.049968</td>
      <td>29126</td>
      <td>Subscriber</td>
      <td>1988</td>
      <td>2</td>
    </tr>
    <tr>
      <th>20188</th>
      <td>649</td>
      <td>2018-12-16 11:55:07.8820</td>
      <td>2018-12-16 12:05:57.4260</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>29658</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20189</th>
      <td>984</td>
      <td>2018-12-17 06:26:18.2690</td>
      <td>2018-12-17 06:42:42.9330</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26251</td>
      <td>Subscriber</td>
      <td>1977</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20190</th>
      <td>687</td>
      <td>2018-12-17 12:18:47.1320</td>
      <td>2018-12-17 12:30:14.5090</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>29535</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20191</th>
      <td>726</td>
      <td>2018-12-17 17:38:45.4430</td>
      <td>2018-12-17 17:50:52.4320</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>29276</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>2</td>
    </tr>
    <tr>
      <th>20192</th>
      <td>1041</td>
      <td>2018-12-18 06:21:57.7450</td>
      <td>2018-12-18 06:39:19.7440</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>29221</td>
      <td>Subscriber</td>
      <td>1977</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20193</th>
      <td>654</td>
      <td>2018-12-18 12:12:40.2980</td>
      <td>2018-12-18 12:23:34.4020</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>29300</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20194</th>
      <td>1015</td>
      <td>2018-12-19 06:15:11.2330</td>
      <td>2018-12-19 06:32:06.2450</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26220</td>
      <td>Subscriber</td>
      <td>1977</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20195</th>
      <td>667</td>
      <td>2018-12-19 11:39:50.4270</td>
      <td>2018-12-19 11:50:58.2750</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>29299</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20196</th>
      <td>687</td>
      <td>2018-12-20 13:28:39.0590</td>
      <td>2018-12-20 13:40:06.6410</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>29258</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20197</th>
      <td>625</td>
      <td>2018-12-21 12:05:04.3890</td>
      <td>2018-12-21 12:15:29.5930</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>29664</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20198</th>
      <td>826</td>
      <td>2018-12-21 16:34:37.2330</td>
      <td>2018-12-21 16:48:24.0150</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>26306</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20199</th>
      <td>640</td>
      <td>2018-12-22 10:27:40.6590</td>
      <td>2018-12-22 10:38:21.4170</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>26298</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20200</th>
      <td>1081</td>
      <td>2018-12-22 11:51:46.0600</td>
      <td>2018-12-22 12:09:47.4730</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3269</td>
      <td>Brunswick &amp; 6th</td>
      <td>40.726012</td>
      <td>-74.050389</td>
      <td>29586</td>
      <td>Subscriber</td>
      <td>1993</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20201</th>
      <td>344</td>
      <td>2018-12-25 21:40:09.8660</td>
      <td>2018-12-25 21:45:54.2670</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3280</td>
      <td>Astor Place</td>
      <td>40.719282</td>
      <td>-74.071262</td>
      <td>26241</td>
      <td>Subscriber</td>
      <td>1983</td>
      <td>2</td>
    </tr>
    <tr>
      <th>20202</th>
      <td>1233</td>
      <td>2018-12-29 12:55:45.9690</td>
      <td>2018-12-29 13:16:19.5960</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>29294</td>
      <td>Subscriber</td>
      <td>1988</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20203</th>
      <td>1057</td>
      <td>2018-12-30 15:32:09.3320</td>
      <td>2018-12-30 15:49:46.3510</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>29475</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>2</td>
    </tr>
    <tr>
      <th>20204</th>
      <td>301</td>
      <td>2018-12-31 16:34:11.9340</td>
      <td>2018-12-31 16:39:13.8340</td>
      <td>3694</td>
      <td>Jackson Square</td>
      <td>40.711130</td>
      <td>-74.078900</td>
      <td>3277</td>
      <td>Communipaw &amp; Berry Lane</td>
      <td>40.714358</td>
      <td>-74.066611</td>
      <td>26270</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>353892 rows × 15 columns</p>
</div>




```python
jc_citibike_2018.to_csv('jc_citibike_2018.csv', sep = ',') 
```


```python

```
