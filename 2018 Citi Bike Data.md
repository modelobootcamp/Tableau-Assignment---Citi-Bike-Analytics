

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
df2 = pd.read_csv('201802-citibike-tripdata.csv')
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
      <td>771</td>
      <td>2018-02-01 00:14:16.4120</td>
      <td>2018-02-01 00:27:08.2290</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>379</td>
      <td>W 31 St &amp; 7 Ave</td>
      <td>40.749156</td>
      <td>-73.991600</td>
      <td>14536</td>
      <td>Subscriber</td>
      <td>1952</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>264</td>
      <td>2018-02-01 05:14:45.1790</td>
      <td>2018-02-01 05:19:09.6860</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>478</td>
      <td>11 Ave &amp; W 41 St</td>
      <td>40.760301</td>
      <td>-73.998842</td>
      <td>32820</td>
      <td>Subscriber</td>
      <td>1965</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>819</td>
      <td>2018-02-01 06:48:55.2290</td>
      <td>2018-02-01 07:02:35.0290</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>405</td>
      <td>Washington St &amp; Gansevoort St</td>
      <td>40.739323</td>
      <td>-74.008119</td>
      <td>16131</td>
      <td>Subscriber</td>
      <td>1968</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>646</td>
      <td>2018-02-01 07:12:50.1740</td>
      <td>2018-02-01 07:23:36.5280</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>20831</td>
      <td>Subscriber</td>
      <td>1990</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1312</td>
      <td>2018-02-01 07:46:48.8750</td>
      <td>2018-02-01 08:08:41.5430</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>435</td>
      <td>W 21 St &amp; 6 Ave</td>
      <td>40.741740</td>
      <td>-73.994156</td>
      <td>15899</td>
      <td>Subscriber</td>
      <td>1957</td>
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
      <td>771</td>
      <td>2018-02-01 00:14:16.4120</td>
      <td>2018-02-01 00:27:08.2290</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>379</td>
      <td>W 31 St &amp; 7 Ave</td>
      <td>40.749156</td>
      <td>-73.991600</td>
      <td>14536</td>
      <td>Subscriber</td>
      <td>1952</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>264</td>
      <td>2018-02-01 05:14:45.1790</td>
      <td>2018-02-01 05:19:09.6860</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>478</td>
      <td>11 Ave &amp; W 41 St</td>
      <td>40.760301</td>
      <td>-73.998842</td>
      <td>32820</td>
      <td>Subscriber</td>
      <td>1965</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>819</td>
      <td>2018-02-01 06:48:55.2290</td>
      <td>2018-02-01 07:02:35.0290</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>405</td>
      <td>Washington St &amp; Gansevoort St</td>
      <td>40.739323</td>
      <td>-74.008119</td>
      <td>16131</td>
      <td>Subscriber</td>
      <td>1968</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>646</td>
      <td>2018-02-01 07:12:50.1740</td>
      <td>2018-02-01 07:23:36.5280</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>20831</td>
      <td>Subscriber</td>
      <td>1990</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1312</td>
      <td>2018-02-01 07:46:48.8750</td>
      <td>2018-02-01 08:08:41.5430</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>435</td>
      <td>W 21 St &amp; 6 Ave</td>
      <td>40.741740</td>
      <td>-73.994156</td>
      <td>15899</td>
      <td>Subscriber</td>
      <td>1957</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3 = pd.read_csv('201803-citibike-tripdata.csv')
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
      <td>816</td>
      <td>2018-03-01 02:29:13.7270</td>
      <td>2018-03-01 02:42:50.1460</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>379</td>
      <td>W 31 St &amp; 7 Ave</td>
      <td>40.749156</td>
      <td>-73.991600</td>
      <td>31413</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>235</td>
      <td>2018-03-01 05:12:37.0320</td>
      <td>2018-03-01 05:16:32.1010</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>478</td>
      <td>11 Ave &amp; W 41 St</td>
      <td>40.760301</td>
      <td>-73.998842</td>
      <td>33202</td>
      <td>Subscriber</td>
      <td>1965</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1250</td>
      <td>2018-03-01 05:45:49.9000</td>
      <td>2018-03-01 06:06:39.9080</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>3664</td>
      <td>North Moore St &amp; Greenwich St</td>
      <td>40.720195</td>
      <td>-74.010301</td>
      <td>26675</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>741</td>
      <td>2018-03-01 06:54:19.6150</td>
      <td>2018-03-01 07:06:40.9790</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>459</td>
      <td>W 20 St &amp; 11 Ave</td>
      <td>40.746745</td>
      <td>-74.007756</td>
      <td>31011</td>
      <td>Subscriber</td>
      <td>1981</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>727</td>
      <td>2018-03-01 07:08:38.8610</td>
      <td>2018-03-01 07:20:46.8500</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>30616</td>
      <td>Subscriber</td>
      <td>1990</td>
      <td>2</td>
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
      <td>816</td>
      <td>2018-03-01 02:29:13.7270</td>
      <td>2018-03-01 02:42:50.1460</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>379</td>
      <td>W 31 St &amp; 7 Ave</td>
      <td>40.749156</td>
      <td>-73.991600</td>
      <td>31413</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>235</td>
      <td>2018-03-01 05:12:37.0320</td>
      <td>2018-03-01 05:16:32.1010</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>478</td>
      <td>11 Ave &amp; W 41 St</td>
      <td>40.760301</td>
      <td>-73.998842</td>
      <td>33202</td>
      <td>Subscriber</td>
      <td>1965</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1250</td>
      <td>2018-03-01 05:45:49.9000</td>
      <td>2018-03-01 06:06:39.9080</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>3664</td>
      <td>North Moore St &amp; Greenwich St</td>
      <td>40.720195</td>
      <td>-74.010301</td>
      <td>26675</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>741</td>
      <td>2018-03-01 06:54:19.6150</td>
      <td>2018-03-01 07:06:40.9790</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>459</td>
      <td>W 20 St &amp; 11 Ave</td>
      <td>40.746745</td>
      <td>-74.007756</td>
      <td>31011</td>
      <td>Subscriber</td>
      <td>1981</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>727</td>
      <td>2018-03-01 07:08:38.8610</td>
      <td>2018-03-01 07:20:46.8500</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>30616</td>
      <td>Subscriber</td>
      <td>1990</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
df4 = pd.read_csv('201804-citibike-tripdata.csv')
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
      <td>840</td>
      <td>2018-04-01 03:07:39.0700</td>
      <td>2018-04-01 03:21:39.1280</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>379</td>
      <td>W 31 St &amp; 7 Ave</td>
      <td>40.749156</td>
      <td>-73.991600</td>
      <td>31977</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1438</td>
      <td>2018-04-01 07:20:02.2150</td>
      <td>2018-04-01 07:44:00.5690</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>426</td>
      <td>West St &amp; Chambers St</td>
      <td>40.717548</td>
      <td>-74.013221</td>
      <td>21403</td>
      <td>Subscriber</td>
      <td>1956</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>219</td>
      <td>2018-04-01 08:11:14.4060</td>
      <td>2018-04-01 08:14:53.7880</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>447</td>
      <td>8 Ave &amp; W 52 St</td>
      <td>40.763707</td>
      <td>-73.985162</td>
      <td>29081</td>
      <td>Subscriber</td>
      <td>1974</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>410</td>
      <td>2018-04-01 08:52:32.3730</td>
      <td>2018-04-01 08:59:23.2190</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>173</td>
      <td>Broadway &amp; W 49 St</td>
      <td>40.760683</td>
      <td>-73.984527</td>
      <td>32130</td>
      <td>Subscriber</td>
      <td>1983</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>485</td>
      <td>2018-04-01 09:37:34.3270</td>
      <td>2018-04-01 09:45:39.9980</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>3159</td>
      <td>W 67 St &amp; Broadway</td>
      <td>40.774925</td>
      <td>-73.982666</td>
      <td>30055</td>
      <td>Subscriber</td>
      <td>1978</td>
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
      <td>840</td>
      <td>2018-04-01 03:07:39.0700</td>
      <td>2018-04-01 03:21:39.1280</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>379</td>
      <td>W 31 St &amp; 7 Ave</td>
      <td>40.749156</td>
      <td>-73.991600</td>
      <td>31977</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1438</td>
      <td>2018-04-01 07:20:02.2150</td>
      <td>2018-04-01 07:44:00.5690</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>426</td>
      <td>West St &amp; Chambers St</td>
      <td>40.717548</td>
      <td>-74.013221</td>
      <td>21403</td>
      <td>Subscriber</td>
      <td>1956</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>219</td>
      <td>2018-04-01 08:11:14.4060</td>
      <td>2018-04-01 08:14:53.7880</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>447</td>
      <td>8 Ave &amp; W 52 St</td>
      <td>40.763707</td>
      <td>-73.985162</td>
      <td>29081</td>
      <td>Subscriber</td>
      <td>1974</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>410</td>
      <td>2018-04-01 08:52:32.3730</td>
      <td>2018-04-01 08:59:23.2190</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>173</td>
      <td>Broadway &amp; W 49 St</td>
      <td>40.760683</td>
      <td>-73.984527</td>
      <td>32130</td>
      <td>Subscriber</td>
      <td>1983</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>485</td>
      <td>2018-04-01 09:37:34.3270</td>
      <td>2018-04-01 09:45:39.9980</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>3159</td>
      <td>W 67 St &amp; Broadway</td>
      <td>40.774925</td>
      <td>-73.982666</td>
      <td>30055</td>
      <td>Subscriber</td>
      <td>1978</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df5 = pd.read_csv('201805-citibike-tripdata.csv')
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
      <td>367</td>
      <td>2018-05-01 05:06:16.5840</td>
      <td>2018-05-01 05:12:23.9650</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>514</td>
      <td>12 Ave &amp; W 40 St</td>
      <td>40.760875</td>
      <td>-74.002777</td>
      <td>30567</td>
      <td>Subscriber</td>
      <td>1965</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1313</td>
      <td>2018-05-01 06:25:49.4250</td>
      <td>2018-05-01 06:47:42.7120</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>426</td>
      <td>West St &amp; Chambers St</td>
      <td>40.717548</td>
      <td>-74.013221</td>
      <td>18965</td>
      <td>Subscriber</td>
      <td>1956</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1798</td>
      <td>2018-05-01 06:40:26.4450</td>
      <td>2018-05-01 07:10:25.1790</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>3435</td>
      <td>Grand St &amp; Elizabeth St</td>
      <td>40.718822</td>
      <td>-73.995960</td>
      <td>30241</td>
      <td>Subscriber</td>
      <td>1959</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>518</td>
      <td>2018-05-01 07:06:02.9730</td>
      <td>2018-05-01 07:14:41.0040</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>477</td>
      <td>W 41 St &amp; 8 Ave</td>
      <td>40.756405</td>
      <td>-73.990026</td>
      <td>28985</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>109</td>
      <td>2018-05-01 07:26:32.3450</td>
      <td>2018-05-01 07:28:21.5420</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>530</td>
      <td>11 Ave &amp; W 59 St</td>
      <td>40.771522</td>
      <td>-73.990541</td>
      <td>14556</td>
      <td>Subscriber</td>
      <td>1991</td>
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
      <td>367</td>
      <td>2018-05-01 05:06:16.5840</td>
      <td>2018-05-01 05:12:23.9650</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>514</td>
      <td>12 Ave &amp; W 40 St</td>
      <td>40.760875</td>
      <td>-74.002777</td>
      <td>30567</td>
      <td>Subscriber</td>
      <td>1965</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1313</td>
      <td>2018-05-01 06:25:49.4250</td>
      <td>2018-05-01 06:47:42.7120</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>426</td>
      <td>West St &amp; Chambers St</td>
      <td>40.717548</td>
      <td>-74.013221</td>
      <td>18965</td>
      <td>Subscriber</td>
      <td>1956</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1798</td>
      <td>2018-05-01 06:40:26.4450</td>
      <td>2018-05-01 07:10:25.1790</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>3435</td>
      <td>Grand St &amp; Elizabeth St</td>
      <td>40.718822</td>
      <td>-73.995960</td>
      <td>30241</td>
      <td>Subscriber</td>
      <td>1959</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>518</td>
      <td>2018-05-01 07:06:02.9730</td>
      <td>2018-05-01 07:14:41.0040</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>477</td>
      <td>W 41 St &amp; 8 Ave</td>
      <td>40.756405</td>
      <td>-73.990026</td>
      <td>28985</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>109</td>
      <td>2018-05-01 07:26:32.3450</td>
      <td>2018-05-01 07:28:21.5420</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>530</td>
      <td>11 Ave &amp; W 59 St</td>
      <td>40.771522</td>
      <td>-73.990541</td>
      <td>14556</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df6 = pd.read_csv('201806-citibike-tripdata.csv')
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
      <td>569</td>
      <td>2018-06-01 01:57:20.5140</td>
      <td>2018-06-01 02:06:50.0880</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>173</td>
      <td>Broadway &amp; W 49 St</td>
      <td>40.760683</td>
      <td>-73.984527</td>
      <td>21481</td>
      <td>Subscriber</td>
      <td>1999</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>480</td>
      <td>2018-06-01 02:02:42.3980</td>
      <td>2018-06-01 02:10:43.3540</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>477</td>
      <td>W 41 St &amp; 8 Ave</td>
      <td>40.756405</td>
      <td>-73.990026</td>
      <td>19123</td>
      <td>Subscriber</td>
      <td>1988</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>692</td>
      <td>2018-06-01 02:04:23.6240</td>
      <td>2018-06-01 02:15:55.7470</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>457</td>
      <td>Broadway &amp; W 58 St</td>
      <td>40.766953</td>
      <td>-73.981693</td>
      <td>26983</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>664</td>
      <td>2018-06-01 03:00:55.4610</td>
      <td>2018-06-01 03:11:59.9060</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>379</td>
      <td>W 31 St &amp; 7 Ave</td>
      <td>40.749156</td>
      <td>-73.991600</td>
      <td>26742</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>818</td>
      <td>2018-06-01 06:04:54.4270</td>
      <td>2018-06-01 06:18:32.6170</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>459</td>
      <td>W 20 St &amp; 11 Ave</td>
      <td>40.746745</td>
      <td>-74.007756</td>
      <td>26386</td>
      <td>Subscriber</td>
      <td>1984</td>
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
      <td>569</td>
      <td>2018-06-01 01:57:20.5140</td>
      <td>2018-06-01 02:06:50.0880</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>173</td>
      <td>Broadway &amp; W 49 St</td>
      <td>40.760683</td>
      <td>-73.984527</td>
      <td>21481</td>
      <td>Subscriber</td>
      <td>1999</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>480</td>
      <td>2018-06-01 02:02:42.3980</td>
      <td>2018-06-01 02:10:43.3540</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>477</td>
      <td>W 41 St &amp; 8 Ave</td>
      <td>40.756405</td>
      <td>-73.990026</td>
      <td>19123</td>
      <td>Subscriber</td>
      <td>1988</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>692</td>
      <td>2018-06-01 02:04:23.6240</td>
      <td>2018-06-01 02:15:55.7470</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>457</td>
      <td>Broadway &amp; W 58 St</td>
      <td>40.766953</td>
      <td>-73.981693</td>
      <td>26983</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>664</td>
      <td>2018-06-01 03:00:55.4610</td>
      <td>2018-06-01 03:11:59.9060</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>379</td>
      <td>W 31 St &amp; 7 Ave</td>
      <td>40.749156</td>
      <td>-73.991600</td>
      <td>26742</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>818</td>
      <td>2018-06-01 06:04:54.4270</td>
      <td>2018-06-01 06:18:32.6170</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>459</td>
      <td>W 20 St &amp; 11 Ave</td>
      <td>40.746745</td>
      <td>-74.007756</td>
      <td>26386</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df7 = pd.read_csv('201807-citibike-tripdata.csv')
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
      <td>500</td>
      <td>2018-07-01 00:33:51.2640</td>
      <td>2018-07-01 00:42:12.0280</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>3236</td>
      <td>W 42 St &amp; Dyer Ave</td>
      <td>40.758985</td>
      <td>-73.993800</td>
      <td>16583</td>
      <td>Subscriber</td>
      <td>1981</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>455</td>
      <td>2018-07-01 02:06:54.0270</td>
      <td>2018-07-01 02:14:29.0900</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>529</td>
      <td>W 42 St &amp; 8 Ave</td>
      <td>40.757570</td>
      <td>-73.990985</td>
      <td>31481</td>
      <td>Subscriber</td>
      <td>1988</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1080</td>
      <td>2018-07-01 02:09:16.4640</td>
      <td>2018-07-01 02:27:17.0290</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>453</td>
      <td>W 22 St &amp; 8 Ave</td>
      <td>40.744751</td>
      <td>-73.999154</td>
      <td>25004</td>
      <td>Subscriber</td>
      <td>1982</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>632</td>
      <td>2018-07-01 02:55:04.5870</td>
      <td>2018-07-01 03:05:36.7910</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>465</td>
      <td>Broadway &amp; W 41 St</td>
      <td>40.755136</td>
      <td>-73.986580</td>
      <td>25867</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1676</td>
      <td>2018-07-01 03:24:27.4350</td>
      <td>2018-07-01 03:52:23.7760</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>3425</td>
      <td>2 Ave &amp; E 104 St</td>
      <td>40.789210</td>
      <td>-73.943708</td>
      <td>31351</td>
      <td>Subscriber</td>
      <td>1992</td>
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
      <td>500</td>
      <td>2018-07-01 00:33:51.2640</td>
      <td>2018-07-01 00:42:12.0280</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>3236</td>
      <td>W 42 St &amp; Dyer Ave</td>
      <td>40.758985</td>
      <td>-73.993800</td>
      <td>16583</td>
      <td>Subscriber</td>
      <td>1981</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>455</td>
      <td>2018-07-01 02:06:54.0270</td>
      <td>2018-07-01 02:14:29.0900</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>529</td>
      <td>W 42 St &amp; 8 Ave</td>
      <td>40.757570</td>
      <td>-73.990985</td>
      <td>31481</td>
      <td>Subscriber</td>
      <td>1988</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1080</td>
      <td>2018-07-01 02:09:16.4640</td>
      <td>2018-07-01 02:27:17.0290</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>453</td>
      <td>W 22 St &amp; 8 Ave</td>
      <td>40.744751</td>
      <td>-73.999154</td>
      <td>25004</td>
      <td>Subscriber</td>
      <td>1982</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>632</td>
      <td>2018-07-01 02:55:04.5870</td>
      <td>2018-07-01 03:05:36.7910</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>465</td>
      <td>Broadway &amp; W 41 St</td>
      <td>40.755136</td>
      <td>-73.986580</td>
      <td>25867</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1676</td>
      <td>2018-07-01 03:24:27.4350</td>
      <td>2018-07-01 03:52:23.7760</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>3425</td>
      <td>2 Ave &amp; E 104 St</td>
      <td>40.789210</td>
      <td>-73.943708</td>
      <td>31351</td>
      <td>Subscriber</td>
      <td>1992</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df8 = pd.read_csv('201808-citibike-tripdata.csv')
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
      <td>681</td>
      <td>2018-08-01 00:00:07.3210</td>
      <td>2018-08-01 00:11:28.9920</td>
      <td>3162.0</td>
      <td>W 78 St &amp; Broadway</td>
      <td>40.783400</td>
      <td>-73.980931</td>
      <td>3383.0</td>
      <td>Cathedral Pkwy &amp; Broadway</td>
      <td>40.804213</td>
      <td>-73.966991</td>
      <td>27770</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>625</td>
      <td>2018-08-01 00:00:19.7480</td>
      <td>2018-08-01 00:10:45.0290</td>
      <td>3260.0</td>
      <td>Mercer St &amp; Bleecker St</td>
      <td>40.727064</td>
      <td>-73.996621</td>
      <td>2012.0</td>
      <td>E 27 St &amp; 1 Ave</td>
      <td>40.739445</td>
      <td>-73.976806</td>
      <td>25938</td>
      <td>Subscriber</td>
      <td>1969</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1319</td>
      <td>2018-08-01 00:00:21.1750</td>
      <td>2018-08-01 00:22:20.6370</td>
      <td>403.0</td>
      <td>E 2 St &amp; 2 Ave</td>
      <td>40.725029</td>
      <td>-73.990697</td>
      <td>285.0</td>
      <td>Broadway &amp; E 14 St</td>
      <td>40.734546</td>
      <td>-73.990741</td>
      <td>28679</td>
      <td>Subscriber</td>
      <td>1970</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>220</td>
      <td>2018-08-01 00:00:26.4700</td>
      <td>2018-08-01 00:04:06.8190</td>
      <td>3637.0</td>
      <td>Fulton St &amp; Waverly Ave</td>
      <td>40.683239</td>
      <td>-73.965996</td>
      <td>399.0</td>
      <td>Lafayette Ave &amp; St James Pl</td>
      <td>40.688515</td>
      <td>-73.964763</td>
      <td>28075</td>
      <td>Subscriber</td>
      <td>1982</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>398</td>
      <td>2018-08-01 00:00:30.2910</td>
      <td>2018-08-01 00:07:09.2810</td>
      <td>3662.0</td>
      <td>31 Ave &amp; Steinway St</td>
      <td>40.761294</td>
      <td>-73.916917</td>
      <td>3517.0</td>
      <td>31 St &amp; Hoyt Ave N</td>
      <td>40.771153</td>
      <td>-73.917007</td>
      <td>25002</td>
      <td>Subscriber</td>
      <td>1987</td>
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
      <td>681</td>
      <td>2018-08-01 00:00:07.3210</td>
      <td>2018-08-01 00:11:28.9920</td>
      <td>3162.0</td>
      <td>W 78 St &amp; Broadway</td>
      <td>40.783400</td>
      <td>-73.980931</td>
      <td>3383.0</td>
      <td>Cathedral Pkwy &amp; Broadway</td>
      <td>40.804213</td>
      <td>-73.966991</td>
      <td>27770</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>625</td>
      <td>2018-08-01 00:00:19.7480</td>
      <td>2018-08-01 00:10:45.0290</td>
      <td>3260.0</td>
      <td>Mercer St &amp; Bleecker St</td>
      <td>40.727064</td>
      <td>-73.996621</td>
      <td>2012.0</td>
      <td>E 27 St &amp; 1 Ave</td>
      <td>40.739445</td>
      <td>-73.976806</td>
      <td>25938</td>
      <td>Subscriber</td>
      <td>1969</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1319</td>
      <td>2018-08-01 00:00:21.1750</td>
      <td>2018-08-01 00:22:20.6370</td>
      <td>403.0</td>
      <td>E 2 St &amp; 2 Ave</td>
      <td>40.725029</td>
      <td>-73.990697</td>
      <td>285.0</td>
      <td>Broadway &amp; E 14 St</td>
      <td>40.734546</td>
      <td>-73.990741</td>
      <td>28679</td>
      <td>Subscriber</td>
      <td>1970</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>220</td>
      <td>2018-08-01 00:00:26.4700</td>
      <td>2018-08-01 00:04:06.8190</td>
      <td>3637.0</td>
      <td>Fulton St &amp; Waverly Ave</td>
      <td>40.683239</td>
      <td>-73.965996</td>
      <td>399.0</td>
      <td>Lafayette Ave &amp; St James Pl</td>
      <td>40.688515</td>
      <td>-73.964763</td>
      <td>28075</td>
      <td>Subscriber</td>
      <td>1982</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>398</td>
      <td>2018-08-01 00:00:30.2910</td>
      <td>2018-08-01 00:07:09.2810</td>
      <td>3662.0</td>
      <td>31 Ave &amp; Steinway St</td>
      <td>40.761294</td>
      <td>-73.916917</td>
      <td>3517.0</td>
      <td>31 St &amp; Hoyt Ave N</td>
      <td>40.771153</td>
      <td>-73.917007</td>
      <td>25002</td>
      <td>Subscriber</td>
      <td>1987</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df9 = pd.read_csv('201809-citibike-tripdata.csv')
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
      <td>1635</td>
      <td>2018-09-01 00:00:05.2690</td>
      <td>2018-09-01 00:27:20.6340</td>
      <td>252.0</td>
      <td>MacDougal St &amp; Washington Sq</td>
      <td>40.732264</td>
      <td>-73.998522</td>
      <td>366.0</td>
      <td>Clinton Ave &amp; Myrtle Ave</td>
      <td>40.693261</td>
      <td>-73.968896</td>
      <td>25577</td>
      <td>Subscriber</td>
      <td>1980</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>132</td>
      <td>2018-09-01 00:00:11.2810</td>
      <td>2018-09-01 00:02:23.4810</td>
      <td>314.0</td>
      <td>Cadman Plaza West &amp; Montague St</td>
      <td>40.693830</td>
      <td>-73.990539</td>
      <td>3242.0</td>
      <td>Schermerhorn St &amp; Court St</td>
      <td>40.691029</td>
      <td>-73.991834</td>
      <td>34377</td>
      <td>Subscriber</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3337</td>
      <td>2018-09-01 00:00:20.6490</td>
      <td>2018-09-01 00:55:58.5470</td>
      <td>3142.0</td>
      <td>1 Ave &amp; E 62 St</td>
      <td>40.761227</td>
      <td>-73.960940</td>
      <td>3384.0</td>
      <td>Smith St &amp; 3 St</td>
      <td>40.678724</td>
      <td>-73.995991</td>
      <td>30496</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>436</td>
      <td>2018-09-01 00:00:21.7460</td>
      <td>2018-09-01 00:07:38.5830</td>
      <td>308.0</td>
      <td>St James Pl &amp; Oliver St</td>
      <td>40.713079</td>
      <td>-73.998512</td>
      <td>3690.0</td>
      <td>Park Pl &amp; Church St</td>
      <td>40.713342</td>
      <td>-74.009355</td>
      <td>28866</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8457</td>
      <td>2018-09-01 00:00:27.3150</td>
      <td>2018-09-01 02:21:25.3080</td>
      <td>345.0</td>
      <td>W 13 St &amp; 6 Ave</td>
      <td>40.736494</td>
      <td>-73.997044</td>
      <td>380.0</td>
      <td>W 4 St &amp; 7 Ave S</td>
      <td>40.734011</td>
      <td>-74.002939</td>
      <td>20943</td>
      <td>Customer</td>
      <td>1994</td>
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
      <td>1635</td>
      <td>2018-09-01 00:00:05.2690</td>
      <td>2018-09-01 00:27:20.6340</td>
      <td>252.0</td>
      <td>MacDougal St &amp; Washington Sq</td>
      <td>40.732264</td>
      <td>-73.998522</td>
      <td>366.0</td>
      <td>Clinton Ave &amp; Myrtle Ave</td>
      <td>40.693261</td>
      <td>-73.968896</td>
      <td>25577</td>
      <td>Subscriber</td>
      <td>1980</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>132</td>
      <td>2018-09-01 00:00:11.2810</td>
      <td>2018-09-01 00:02:23.4810</td>
      <td>314.0</td>
      <td>Cadman Plaza West &amp; Montague St</td>
      <td>40.693830</td>
      <td>-73.990539</td>
      <td>3242.0</td>
      <td>Schermerhorn St &amp; Court St</td>
      <td>40.691029</td>
      <td>-73.991834</td>
      <td>34377</td>
      <td>Subscriber</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3337</td>
      <td>2018-09-01 00:00:20.6490</td>
      <td>2018-09-01 00:55:58.5470</td>
      <td>3142.0</td>
      <td>1 Ave &amp; E 62 St</td>
      <td>40.761227</td>
      <td>-73.960940</td>
      <td>3384.0</td>
      <td>Smith St &amp; 3 St</td>
      <td>40.678724</td>
      <td>-73.995991</td>
      <td>30496</td>
      <td>Subscriber</td>
      <td>1975</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>436</td>
      <td>2018-09-01 00:00:21.7460</td>
      <td>2018-09-01 00:07:38.5830</td>
      <td>308.0</td>
      <td>St James Pl &amp; Oliver St</td>
      <td>40.713079</td>
      <td>-73.998512</td>
      <td>3690.0</td>
      <td>Park Pl &amp; Church St</td>
      <td>40.713342</td>
      <td>-74.009355</td>
      <td>28866</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8457</td>
      <td>2018-09-01 00:00:27.3150</td>
      <td>2018-09-01 02:21:25.3080</td>
      <td>345.0</td>
      <td>W 13 St &amp; 6 Ave</td>
      <td>40.736494</td>
      <td>-73.997044</td>
      <td>380.0</td>
      <td>W 4 St &amp; 7 Ave S</td>
      <td>40.734011</td>
      <td>-74.002939</td>
      <td>20943</td>
      <td>Customer</td>
      <td>1994</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df10 = pd.read_csv('201810-citibike-tripdata.csv')
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
      <td>330</td>
      <td>2018-10-01 00:00:00.7010</td>
      <td>2018-10-01 00:05:30.8490</td>
      <td>293.0</td>
      <td>Lafayette St &amp; E 8 St</td>
      <td>40.730207</td>
      <td>-73.991026</td>
      <td>504.0</td>
      <td>1 Ave &amp; E 16 St</td>
      <td>40.732219</td>
      <td>-73.981656</td>
      <td>30493</td>
      <td>Subscriber</td>
      <td>1995</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>309</td>
      <td>2018-10-01 00:00:13.5780</td>
      <td>2018-10-01 00:05:23.2310</td>
      <td>433.0</td>
      <td>old - E 13 St &amp; Avenue A</td>
      <td>40.729554</td>
      <td>-73.980572</td>
      <td>394.0</td>
      <td>E 9 St &amp; Avenue C</td>
      <td>40.725213</td>
      <td>-73.977688</td>
      <td>33054</td>
      <td>Subscriber</td>
      <td>1967</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>734</td>
      <td>2018-10-01 00:00:16.6040</td>
      <td>2018-10-01 00:12:31.5050</td>
      <td>3472.0</td>
      <td>W 15 St &amp; 10 Ave</td>
      <td>40.742754</td>
      <td>-74.007474</td>
      <td>285.0</td>
      <td>Broadway &amp; E 14 St</td>
      <td>40.734546</td>
      <td>-73.990741</td>
      <td>33400</td>
      <td>Subscriber</td>
      <td>1983</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>788</td>
      <td>2018-10-01 00:00:35.0670</td>
      <td>2018-10-01 00:13:43.5780</td>
      <td>417.0</td>
      <td>Barclay St &amp; Church St</td>
      <td>40.712912</td>
      <td>-74.010202</td>
      <td>3472.0</td>
      <td>W 15 St &amp; 10 Ave</td>
      <td>40.742754</td>
      <td>-74.007474</td>
      <td>31140</td>
      <td>Customer</td>
      <td>1988</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1136</td>
      <td>2018-10-01 00:00:38.1410</td>
      <td>2018-10-01 00:19:34.6490</td>
      <td>3699.0</td>
      <td>W 50 St &amp; 9 Ave</td>
      <td>40.763605</td>
      <td>-73.989180</td>
      <td>495.0</td>
      <td>W 47 St &amp; 10 Ave</td>
      <td>40.762699</td>
      <td>-73.993012</td>
      <td>20294</td>
      <td>Subscriber</td>
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
      <td>330</td>
      <td>2018-10-01 00:00:00.7010</td>
      <td>2018-10-01 00:05:30.8490</td>
      <td>293.0</td>
      <td>Lafayette St &amp; E 8 St</td>
      <td>40.730207</td>
      <td>-73.991026</td>
      <td>504.0</td>
      <td>1 Ave &amp; E 16 St</td>
      <td>40.732219</td>
      <td>-73.981656</td>
      <td>30493</td>
      <td>Subscriber</td>
      <td>1995</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>309</td>
      <td>2018-10-01 00:00:13.5780</td>
      <td>2018-10-01 00:05:23.2310</td>
      <td>433.0</td>
      <td>old - E 13 St &amp; Avenue A</td>
      <td>40.729554</td>
      <td>-73.980572</td>
      <td>394.0</td>
      <td>E 9 St &amp; Avenue C</td>
      <td>40.725213</td>
      <td>-73.977688</td>
      <td>33054</td>
      <td>Subscriber</td>
      <td>1967</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>734</td>
      <td>2018-10-01 00:00:16.6040</td>
      <td>2018-10-01 00:12:31.5050</td>
      <td>3472.0</td>
      <td>W 15 St &amp; 10 Ave</td>
      <td>40.742754</td>
      <td>-74.007474</td>
      <td>285.0</td>
      <td>Broadway &amp; E 14 St</td>
      <td>40.734546</td>
      <td>-73.990741</td>
      <td>33400</td>
      <td>Subscriber</td>
      <td>1983</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>788</td>
      <td>2018-10-01 00:00:35.0670</td>
      <td>2018-10-01 00:13:43.5780</td>
      <td>417.0</td>
      <td>Barclay St &amp; Church St</td>
      <td>40.712912</td>
      <td>-74.010202</td>
      <td>3472.0</td>
      <td>W 15 St &amp; 10 Ave</td>
      <td>40.742754</td>
      <td>-74.007474</td>
      <td>31140</td>
      <td>Customer</td>
      <td>1988</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1136</td>
      <td>2018-10-01 00:00:38.1410</td>
      <td>2018-10-01 00:19:34.6490</td>
      <td>3699.0</td>
      <td>W 50 St &amp; 9 Ave</td>
      <td>40.763605</td>
      <td>-73.989180</td>
      <td>495.0</td>
      <td>W 47 St &amp; 10 Ave</td>
      <td>40.762699</td>
      <td>-73.993012</td>
      <td>20294</td>
      <td>Subscriber</td>
      <td>1969</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df11 = pd.read_csv('201811-citibike-tripdata.csv')
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
      <td>254</td>
      <td>2018-11-01 00:00:12.9100</td>
      <td>2018-11-01 00:04:27.3870</td>
      <td>3522.0</td>
      <td>37 St &amp; 24 Ave</td>
      <td>40.770148</td>
      <td>-73.912094</td>
      <td>3513.0</td>
      <td>21 St &amp; Hoyt Ave S</td>
      <td>40.774645</td>
      <td>-73.923706</td>
      <td>34117</td>
      <td>Subscriber</td>
      <td>1992</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>833</td>
      <td>2018-11-01 00:00:16.3440</td>
      <td>2018-11-01 00:14:09.4320</td>
      <td>252.0</td>
      <td>MacDougal St &amp; Washington Sq</td>
      <td>40.732264</td>
      <td>-73.998522</td>
      <td>251.0</td>
      <td>Mott St &amp; Prince St</td>
      <td>40.723180</td>
      <td>-73.994800</td>
      <td>32569</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>683</td>
      <td>2018-11-01 00:00:17.6630</td>
      <td>2018-11-01 00:11:40.9170</td>
      <td>3405.0</td>
      <td>5 St &amp; 6 Ave</td>
      <td>40.670484</td>
      <td>-73.982090</td>
      <td>3584.0</td>
      <td>Eastern Pkwy &amp; Franklin Ave</td>
      <td>40.670777</td>
      <td>-73.957680</td>
      <td>15795</td>
      <td>Subscriber</td>
      <td>1985</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1840</td>
      <td>2018-11-01 00:00:18.7970</td>
      <td>2018-11-01 00:30:59.3050</td>
      <td>3150.0</td>
      <td>E 85 St &amp; York Ave</td>
      <td>40.775369</td>
      <td>-73.948034</td>
      <td>297.0</td>
      <td>E 15 St &amp; 3 Ave</td>
      <td>40.734232</td>
      <td>-73.986923</td>
      <td>33290</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1212</td>
      <td>2018-11-01 00:00:47.3230</td>
      <td>2018-11-01 00:20:59.8840</td>
      <td>325.0</td>
      <td>E 19 St &amp; 3 Ave</td>
      <td>40.736245</td>
      <td>-73.984738</td>
      <td>212.0</td>
      <td>W 16 St &amp; The High Line</td>
      <td>40.743349</td>
      <td>-74.006818</td>
      <td>17411</td>
      <td>Subscriber</td>
      <td>1989</td>
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
      <td>254</td>
      <td>2018-11-01 00:00:12.9100</td>
      <td>2018-11-01 00:04:27.3870</td>
      <td>3522.0</td>
      <td>37 St &amp; 24 Ave</td>
      <td>40.770148</td>
      <td>-73.912094</td>
      <td>3513.0</td>
      <td>21 St &amp; Hoyt Ave S</td>
      <td>40.774645</td>
      <td>-73.923706</td>
      <td>34117</td>
      <td>Subscriber</td>
      <td>1992</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>833</td>
      <td>2018-11-01 00:00:16.3440</td>
      <td>2018-11-01 00:14:09.4320</td>
      <td>252.0</td>
      <td>MacDougal St &amp; Washington Sq</td>
      <td>40.732264</td>
      <td>-73.998522</td>
      <td>251.0</td>
      <td>Mott St &amp; Prince St</td>
      <td>40.723180</td>
      <td>-73.994800</td>
      <td>32569</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>683</td>
      <td>2018-11-01 00:00:17.6630</td>
      <td>2018-11-01 00:11:40.9170</td>
      <td>3405.0</td>
      <td>5 St &amp; 6 Ave</td>
      <td>40.670484</td>
      <td>-73.982090</td>
      <td>3584.0</td>
      <td>Eastern Pkwy &amp; Franklin Ave</td>
      <td>40.670777</td>
      <td>-73.957680</td>
      <td>15795</td>
      <td>Subscriber</td>
      <td>1985</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1840</td>
      <td>2018-11-01 00:00:18.7970</td>
      <td>2018-11-01 00:30:59.3050</td>
      <td>3150.0</td>
      <td>E 85 St &amp; York Ave</td>
      <td>40.775369</td>
      <td>-73.948034</td>
      <td>297.0</td>
      <td>E 15 St &amp; 3 Ave</td>
      <td>40.734232</td>
      <td>-73.986923</td>
      <td>33290</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1212</td>
      <td>2018-11-01 00:00:47.3230</td>
      <td>2018-11-01 00:20:59.8840</td>
      <td>325.0</td>
      <td>E 19 St &amp; 3 Ave</td>
      <td>40.736245</td>
      <td>-73.984738</td>
      <td>212.0</td>
      <td>W 16 St &amp; The High Line</td>
      <td>40.743349</td>
      <td>-74.006818</td>
      <td>17411</td>
      <td>Subscriber</td>
      <td>1989</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df12 = pd.read_csv('201812-citibike-tripdata.csv')
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
      <td>689</td>
      <td>2018-12-01 00:00:04.3020</td>
      <td>2018-12-01 00:11:33.8460</td>
      <td>3359.0</td>
      <td>E 68 St &amp; Madison Ave</td>
      <td>40.769157</td>
      <td>-73.967035</td>
      <td>164.0</td>
      <td>E 47 St &amp; 2 Ave</td>
      <td>40.753231</td>
      <td>-73.970325</td>
      <td>35033</td>
      <td>Subscriber</td>
      <td>1989</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>204</td>
      <td>2018-12-01 00:00:05.5330</td>
      <td>2018-12-01 00:03:30.5230</td>
      <td>3504.0</td>
      <td>E 123 St &amp; Lexington Ave</td>
      <td>40.802926</td>
      <td>-73.937900</td>
      <td>3490.0</td>
      <td>E 116 St &amp; 2 Ave</td>
      <td>40.796879</td>
      <td>-73.937261</td>
      <td>20501</td>
      <td>Subscriber</td>
      <td>1966</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>316</td>
      <td>2018-12-01 00:00:10.2330</td>
      <td>2018-12-01 00:05:27.2030</td>
      <td>270.0</td>
      <td>Adelphi St &amp; Myrtle Ave</td>
      <td>40.693083</td>
      <td>-73.971789</td>
      <td>243.0</td>
      <td>Fulton St &amp; Rockwell Pl</td>
      <td>40.688226</td>
      <td>-73.979382</td>
      <td>18386</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>726</td>
      <td>2018-12-01 00:00:21.9570</td>
      <td>2018-12-01 00:12:28.1830</td>
      <td>495.0</td>
      <td>W 47 St &amp; 10 Ave</td>
      <td>40.762699</td>
      <td>-73.993012</td>
      <td>3660.0</td>
      <td>W 16 St &amp; 8 Ave</td>
      <td>40.741022</td>
      <td>-74.001385</td>
      <td>27616</td>
      <td>Subscriber</td>
      <td>1983</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>397</td>
      <td>2018-12-01 00:00:29.6320</td>
      <td>2018-12-01 00:07:07.4460</td>
      <td>473.0</td>
      <td>Rivington St &amp; Chrystie St</td>
      <td>40.721101</td>
      <td>-73.991925</td>
      <td>3467.0</td>
      <td>W Broadway &amp; Spring Street</td>
      <td>40.724947</td>
      <td>-74.001659</td>
      <td>35096</td>
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
      <td>689</td>
      <td>2018-12-01 00:00:04.3020</td>
      <td>2018-12-01 00:11:33.8460</td>
      <td>3359.0</td>
      <td>E 68 St &amp; Madison Ave</td>
      <td>40.769157</td>
      <td>-73.967035</td>
      <td>164.0</td>
      <td>E 47 St &amp; 2 Ave</td>
      <td>40.753231</td>
      <td>-73.970325</td>
      <td>35033</td>
      <td>Subscriber</td>
      <td>1989</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>204</td>
      <td>2018-12-01 00:00:05.5330</td>
      <td>2018-12-01 00:03:30.5230</td>
      <td>3504.0</td>
      <td>E 123 St &amp; Lexington Ave</td>
      <td>40.802926</td>
      <td>-73.937900</td>
      <td>3490.0</td>
      <td>E 116 St &amp; 2 Ave</td>
      <td>40.796879</td>
      <td>-73.937261</td>
      <td>20501</td>
      <td>Subscriber</td>
      <td>1966</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>316</td>
      <td>2018-12-01 00:00:10.2330</td>
      <td>2018-12-01 00:05:27.2030</td>
      <td>270.0</td>
      <td>Adelphi St &amp; Myrtle Ave</td>
      <td>40.693083</td>
      <td>-73.971789</td>
      <td>243.0</td>
      <td>Fulton St &amp; Rockwell Pl</td>
      <td>40.688226</td>
      <td>-73.979382</td>
      <td>18386</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>726</td>
      <td>2018-12-01 00:00:21.9570</td>
      <td>2018-12-01 00:12:28.1830</td>
      <td>495.0</td>
      <td>W 47 St &amp; 10 Ave</td>
      <td>40.762699</td>
      <td>-73.993012</td>
      <td>3660.0</td>
      <td>W 16 St &amp; 8 Ave</td>
      <td>40.741022</td>
      <td>-74.001385</td>
      <td>27616</td>
      <td>Subscriber</td>
      <td>1983</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>397</td>
      <td>2018-12-01 00:00:29.6320</td>
      <td>2018-12-01 00:07:07.4460</td>
      <td>473.0</td>
      <td>Rivington St &amp; Chrystie St</td>
      <td>40.721101</td>
      <td>-73.991925</td>
      <td>3467.0</td>
      <td>W Broadway &amp; Spring Street</td>
      <td>40.724947</td>
      <td>-74.001659</td>
      <td>35096</td>
      <td>Subscriber</td>
      <td>1976</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
citibike_2018 = pd.concat([df1, df2, df3, df4, df5, df6, df7, df8, df9, df10, df11, df12])
citibike_2018
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3639.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3203.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3205.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3275.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3281.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3205.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3269.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3639.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3187.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3194.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3187.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3185.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <td>3183.0</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3267.0</td>
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
      <th>1016475</th>
      <td>206</td>
      <td>2018-12-31 23:30:09.5760</td>
      <td>2018-12-31 23:33:36.5100</td>
      <td>390.0</td>
      <td>Duffield St &amp; Willoughby St</td>
      <td>40.692216</td>
      <td>-73.984284</td>
      <td>243.0</td>
      <td>Fulton St &amp; Rockwell Pl</td>
      <td>40.688226</td>
      <td>-73.979382</td>
      <td>27440</td>
      <td>Subscriber</td>
      <td>1985</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1016476</th>
      <td>924</td>
      <td>2018-12-31 23:30:41.7490</td>
      <td>2018-12-31 23:46:06.7030</td>
      <td>446.0</td>
      <td>W 24 St &amp; 7 Ave</td>
      <td>40.744876</td>
      <td>-73.995299</td>
      <td>516.0</td>
      <td>E 47 St &amp; 1 Ave</td>
      <td>40.752069</td>
      <td>-73.967844</td>
      <td>34663</td>
      <td>Subscriber</td>
      <td>1980</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016477</th>
      <td>426</td>
      <td>2018-12-31 23:32:07.9720</td>
      <td>2018-12-31 23:39:14.3750</td>
      <td>368.0</td>
      <td>Carmine St &amp; 6 Ave</td>
      <td>40.730386</td>
      <td>-74.002150</td>
      <td>146.0</td>
      <td>Hudson St &amp; Reade St</td>
      <td>40.716250</td>
      <td>-74.009106</td>
      <td>34329</td>
      <td>Subscriber</td>
      <td>1999</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016478</th>
      <td>247</td>
      <td>2018-12-31 23:32:26.2510</td>
      <td>2018-12-31 23:36:34.0940</td>
      <td>383.0</td>
      <td>Greenwich Ave &amp; Charles St</td>
      <td>40.735238</td>
      <td>-74.000271</td>
      <td>3709.0</td>
      <td>W 15 St &amp; 6 Ave</td>
      <td>40.738046</td>
      <td>-73.996430</td>
      <td>32671</td>
      <td>Subscriber</td>
      <td>1989</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016479</th>
      <td>282</td>
      <td>2018-12-31 23:32:30.8410</td>
      <td>2018-12-31 23:37:13.3520</td>
      <td>383.0</td>
      <td>Greenwich Ave &amp; Charles St</td>
      <td>40.735238</td>
      <td>-74.000271</td>
      <td>3709.0</td>
      <td>W 15 St &amp; 6 Ave</td>
      <td>40.738046</td>
      <td>-73.996430</td>
      <td>15624</td>
      <td>Subscriber</td>
      <td>1988</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016480</th>
      <td>245</td>
      <td>2018-12-31 23:35:10.8400</td>
      <td>2018-12-31 23:39:16.6350</td>
      <td>3136.0</td>
      <td>5 Ave &amp; E 63 St</td>
      <td>40.766368</td>
      <td>-73.971518</td>
      <td>3137.0</td>
      <td>5 Ave &amp; E 73 St</td>
      <td>40.772828</td>
      <td>-73.966853</td>
      <td>26633</td>
      <td>Subscriber</td>
      <td>1961</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016481</th>
      <td>516</td>
      <td>2018-12-31 23:35:37.7230</td>
      <td>2018-12-31 23:44:14.4130</td>
      <td>128.0</td>
      <td>MacDougal St &amp; Prince St</td>
      <td>40.727103</td>
      <td>-74.002971</td>
      <td>308.0</td>
      <td>St James Pl &amp; Oliver St</td>
      <td>40.713079</td>
      <td>-73.998512</td>
      <td>19088</td>
      <td>Subscriber</td>
      <td>1984</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016482</th>
      <td>588</td>
      <td>2018-12-31 23:36:25.3260</td>
      <td>2018-12-31 23:46:13.6530</td>
      <td>3397.0</td>
      <td>Court St &amp; Nelson St</td>
      <td>40.676395</td>
      <td>-73.998699</td>
      <td>143.0</td>
      <td>Clinton St &amp; Joralemon St</td>
      <td>40.692395</td>
      <td>-73.993379</td>
      <td>15107</td>
      <td>Subscriber</td>
      <td>1964</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016483</th>
      <td>306</td>
      <td>2018-12-31 23:36:51.0920</td>
      <td>2018-12-31 23:41:57.3660</td>
      <td>82.0</td>
      <td>St James Pl &amp; Pearl St</td>
      <td>40.711174</td>
      <td>-74.000165</td>
      <td>340.0</td>
      <td>Madison St &amp; Clinton St</td>
      <td>40.712690</td>
      <td>-73.987763</td>
      <td>15864</td>
      <td>Subscriber</td>
      <td>1995</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016484</th>
      <td>927</td>
      <td>2018-12-31 23:37:03.8570</td>
      <td>2018-12-31 23:52:31.7830</td>
      <td>3151.0</td>
      <td>E 81 St &amp; York Ave</td>
      <td>40.772838</td>
      <td>-73.949892</td>
      <td>3137.0</td>
      <td>5 Ave &amp; E 73 St</td>
      <td>40.772828</td>
      <td>-73.966853</td>
      <td>35203</td>
      <td>Customer</td>
      <td>1998</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016485</th>
      <td>94</td>
      <td>2018-12-31 23:37:27.7690</td>
      <td>2018-12-31 23:39:02.0710</td>
      <td>360.0</td>
      <td>William St &amp; Pine St</td>
      <td>40.707179</td>
      <td>-74.008873</td>
      <td>376.0</td>
      <td>John St &amp; William St</td>
      <td>40.708621</td>
      <td>-74.007222</td>
      <td>31001</td>
      <td>Subscriber</td>
      <td>1991</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016486</th>
      <td>1161</td>
      <td>2018-12-31 23:38:29.4360</td>
      <td>2018-12-31 23:57:51.3750</td>
      <td>495.0</td>
      <td>W 47 St &amp; 10 Ave</td>
      <td>40.762699</td>
      <td>-73.993012</td>
      <td>281.0</td>
      <td>Grand Army Plaza &amp; Central Park S</td>
      <td>40.764397</td>
      <td>-73.973715</td>
      <td>16078</td>
      <td>Subscriber</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1016487</th>
      <td>1015</td>
      <td>2018-12-31 23:39:10.7270</td>
      <td>2018-12-31 23:56:06.6920</td>
      <td>379.0</td>
      <td>W 31 St &amp; 7 Ave</td>
      <td>40.749156</td>
      <td>-73.991600</td>
      <td>301.0</td>
      <td>E 2 St &amp; Avenue B</td>
      <td>40.722174</td>
      <td>-73.983688</td>
      <td>34170</td>
      <td>Subscriber</td>
      <td>1985</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016488</th>
      <td>776</td>
      <td>2018-12-31 23:41:17.7150</td>
      <td>2018-12-31 23:54:13.9450</td>
      <td>532.0</td>
      <td>S 5 Pl &amp; S 5 St</td>
      <td>40.710451</td>
      <td>-73.960876</td>
      <td>307.0</td>
      <td>Canal St &amp; Rutgers St</td>
      <td>40.714275</td>
      <td>-73.989900</td>
      <td>34093</td>
      <td>Subscriber</td>
      <td>1988</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1016489</th>
      <td>588</td>
      <td>2018-12-31 23:41:14.4590</td>
      <td>2018-12-31 23:51:02.5500</td>
      <td>195.0</td>
      <td>Liberty St &amp; Broadway</td>
      <td>40.709056</td>
      <td>-74.010434</td>
      <td>534.0</td>
      <td>Water - Whitehall Plaza</td>
      <td>40.702551</td>
      <td>-74.012723</td>
      <td>35081</td>
      <td>Subscriber</td>
      <td>1980</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016490</th>
      <td>71</td>
      <td>2018-12-31 23:42:57.9190</td>
      <td>2018-12-31 23:44:09.2080</td>
      <td>3367.0</td>
      <td>5 Ave &amp; E 103 St</td>
      <td>40.792255</td>
      <td>-73.952499</td>
      <td>3367.0</td>
      <td>5 Ave &amp; E 103 St</td>
      <td>40.792255</td>
      <td>-73.952499</td>
      <td>27026</td>
      <td>Subscriber</td>
      <td>1955</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016491</th>
      <td>217</td>
      <td>2018-12-31 23:43:10.0890</td>
      <td>2018-12-31 23:46:47.4740</td>
      <td>314.0</td>
      <td>Cadman Plaza West &amp; Montague St</td>
      <td>40.693830</td>
      <td>-73.990539</td>
      <td>391.0</td>
      <td>Clark St &amp; Henry St</td>
      <td>40.697601</td>
      <td>-73.993446</td>
      <td>27452</td>
      <td>Subscriber</td>
      <td>1965</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016492</th>
      <td>385</td>
      <td>2018-12-31 23:45:45.7440</td>
      <td>2018-12-31 23:52:10.9330</td>
      <td>3429.0</td>
      <td>Hanson Pl &amp; Ashland Pl</td>
      <td>40.685068</td>
      <td>-73.977908</td>
      <td>3637.0</td>
      <td>Fulton St &amp; Waverly Ave</td>
      <td>40.683239</td>
      <td>-73.965996</td>
      <td>33086</td>
      <td>Subscriber</td>
      <td>1973</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016493</th>
      <td>651</td>
      <td>2018-12-31 23:46:44.4210</td>
      <td>2018-12-31 23:57:35.9100</td>
      <td>3295.0</td>
      <td>Central Park W &amp; W 96 St</td>
      <td>40.791270</td>
      <td>-73.964839</td>
      <td>3165.0</td>
      <td>Central Park West &amp; W 72 St</td>
      <td>40.775794</td>
      <td>-73.976206</td>
      <td>32449</td>
      <td>Subscriber</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1016494</th>
      <td>620</td>
      <td>2018-12-31 23:47:10.2080</td>
      <td>2018-12-31 23:57:30.6020</td>
      <td>3295.0</td>
      <td>Central Park W &amp; W 96 St</td>
      <td>40.791270</td>
      <td>-73.964839</td>
      <td>3165.0</td>
      <td>Central Park West &amp; W 72 St</td>
      <td>40.775794</td>
      <td>-73.976206</td>
      <td>15699</td>
      <td>Customer</td>
      <td>1989</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1016495</th>
      <td>798</td>
      <td>2018-12-31 23:49:37.0590</td>
      <td>2019-01-01 00:02:55.1640</td>
      <td>518.0</td>
      <td>E 39 St &amp; 2 Ave</td>
      <td>40.747804</td>
      <td>-73.973442</td>
      <td>3709.0</td>
      <td>W 15 St &amp; 6 Ave</td>
      <td>40.738046</td>
      <td>-73.996430</td>
      <td>35603</td>
      <td>Subscriber</td>
      <td>1982</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016496</th>
      <td>312</td>
      <td>2018-12-31 23:49:43.9520</td>
      <td>2018-12-31 23:54:56.2510</td>
      <td>3166.0</td>
      <td>Riverside Dr &amp; W 72 St</td>
      <td>40.780578</td>
      <td>-73.985624</td>
      <td>3164.0</td>
      <td>Columbus Ave &amp; W 72 St</td>
      <td>40.777057</td>
      <td>-73.978985</td>
      <td>27419</td>
      <td>Subscriber</td>
      <td>1960</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016497</th>
      <td>165</td>
      <td>2018-12-31 23:50:34.6070</td>
      <td>2018-12-31 23:53:20.5830</td>
      <td>498.0</td>
      <td>Broadway &amp; W 32 St</td>
      <td>40.748549</td>
      <td>-73.988084</td>
      <td>472.0</td>
      <td>E 32 St &amp; Park Ave</td>
      <td>40.745712</td>
      <td>-73.981948</td>
      <td>20190</td>
      <td>Subscriber</td>
      <td>1994</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1016498</th>
      <td>1027</td>
      <td>2018-12-31 23:51:13.9220</td>
      <td>2019-01-01 00:08:21.7900</td>
      <td>423.0</td>
      <td>W 54 St &amp; 9 Ave</td>
      <td>40.765849</td>
      <td>-73.986905</td>
      <td>285.0</td>
      <td>Broadway &amp; E 14 St</td>
      <td>40.734546</td>
      <td>-73.990741</td>
      <td>28510</td>
      <td>Subscriber</td>
      <td>1981</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016499</th>
      <td>174</td>
      <td>2018-12-31 23:53:59.0720</td>
      <td>2018-12-31 23:56:53.4750</td>
      <td>260.0</td>
      <td>Broad St &amp; Bridge St</td>
      <td>40.703652</td>
      <td>-74.011678</td>
      <td>260.0</td>
      <td>Broad St &amp; Bridge St</td>
      <td>40.703652</td>
      <td>-74.011678</td>
      <td>33887</td>
      <td>Subscriber</td>
      <td>1980</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016500</th>
      <td>734</td>
      <td>2018-12-31 23:55:06.9910</td>
      <td>2019-01-01 00:07:21.2300</td>
      <td>336.0</td>
      <td>Sullivan St &amp; Washington Sq</td>
      <td>40.730477</td>
      <td>-73.999061</td>
      <td>379.0</td>
      <td>W 31 St &amp; 7 Ave</td>
      <td>40.749156</td>
      <td>-73.991600</td>
      <td>27111</td>
      <td>Subscriber</td>
      <td>1986</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016501</th>
      <td>2551</td>
      <td>2018-12-31 23:55:44.3070</td>
      <td>2019-01-01 00:38:15.7820</td>
      <td>3320.0</td>
      <td>Central Park West &amp; W 100 St</td>
      <td>40.794067</td>
      <td>-73.962868</td>
      <td>2006.0</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>16390</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1016502</th>
      <td>2376</td>
      <td>2018-12-31 23:56:52.8500</td>
      <td>2019-01-01 00:36:29.2860</td>
      <td>427.0</td>
      <td>Bus Slip &amp; State St</td>
      <td>40.701907</td>
      <td>-74.013942</td>
      <td>259.0</td>
      <td>South St &amp; Whitehall St</td>
      <td>40.701221</td>
      <td>-74.012342</td>
      <td>34398</td>
      <td>Subscriber</td>
      <td>1979</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1016503</th>
      <td>2758</td>
      <td>2018-12-31 23:58:29.2120</td>
      <td>2019-01-01 00:44:27.5170</td>
      <td>3320.0</td>
      <td>Central Park West &amp; W 100 St</td>
      <td>40.794067</td>
      <td>-73.962868</td>
      <td>281.0</td>
      <td>Grand Army Plaza &amp; Central Park S</td>
      <td>40.764397</td>
      <td>-73.973715</td>
      <td>30818</td>
      <td>Customer</td>
      <td>1969</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1016504</th>
      <td>2459</td>
      <td>2018-12-31 23:59:51.0850</td>
      <td>2019-01-01 00:40:50.8800</td>
      <td>128.0</td>
      <td>MacDougal St &amp; Prince St</td>
      <td>40.727103</td>
      <td>-74.002971</td>
      <td>402.0</td>
      <td>Broadway &amp; E 22 St</td>
      <td>40.740343</td>
      <td>-73.989551</td>
      <td>34775</td>
      <td>Subscriber</td>
      <td>1996</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>16842022 rows × 15 columns</p>
</div>




```python
citibike_2018.to_csv('citibike_2018.csv', sep = ',') 
```


```python

```
