

```python
import pandas as pd 
```


```python
df1 = pd.read_csv('JC-20161-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>362</td>
      <td>2016-01-01 00:02:52</td>
      <td>2016-01-01 00:08:54</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24647</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>200</td>
      <td>2016-01-01 00:18:22</td>
      <td>2016-01-01 00:21:42</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24605</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>202</td>
      <td>2016-01-01 00:18:25</td>
      <td>2016-01-01 00:21:47</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24689</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>248</td>
      <td>2016-01-01 00:23:13</td>
      <td>2016-01-01 00:27:21</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24693</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>903</td>
      <td>2016-01-01 01:03:20</td>
      <td>2016-01-01 01:18:24</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>24573</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
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
      <td>362</td>
      <td>2016-01-01 00:02:52</td>
      <td>2016-01-01 00:08:54</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24647</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>200</td>
      <td>2016-01-01 00:18:22</td>
      <td>2016-01-01 00:21:42</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24605</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>202</td>
      <td>2016-01-01 00:18:25</td>
      <td>2016-01-01 00:21:47</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24689</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>248</td>
      <td>2016-01-01 00:23:13</td>
      <td>2016-01-01 00:27:21</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24693</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>903</td>
      <td>2016-01-01 01:03:20</td>
      <td>2016-01-01 01:18:24</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>24573</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2 = pd.read_csv('JC-20162-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>361</td>
      <td>2016-02-01 00:31:18</td>
      <td>2016-02-01 00:37:19</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24393</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>297</td>
      <td>2016-02-01 01:55:05</td>
      <td>2016-02-01 02:00:02</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>24394</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1155</td>
      <td>2016-02-01 02:40:05</td>
      <td>2016-02-01 02:59:20</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>24676</td>
      <td>Subscriber</td>
      <td>1976.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1769</td>
      <td>2016-02-01 05:11:28</td>
      <td>2016-02-01 05:40:58</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24700</td>
      <td>Subscriber</td>
      <td>1974.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>935</td>
      <td>2016-02-01 05:48:24</td>
      <td>2016-02-01 06:03:59</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>24639</td>
      <td>Subscriber</td>
      <td>1974.0</td>
      <td>2</td>
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
      <td>361</td>
      <td>2016-02-01 00:31:18</td>
      <td>2016-02-01 00:37:19</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24393</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>297</td>
      <td>2016-02-01 01:55:05</td>
      <td>2016-02-01 02:00:02</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>24394</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1155</td>
      <td>2016-02-01 02:40:05</td>
      <td>2016-02-01 02:59:20</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>24676</td>
      <td>Subscriber</td>
      <td>1976.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1769</td>
      <td>2016-02-01 05:11:28</td>
      <td>2016-02-01 05:40:58</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24700</td>
      <td>Subscriber</td>
      <td>1974.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>935</td>
      <td>2016-02-01 05:48:24</td>
      <td>2016-02-01 06:03:59</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>24639</td>
      <td>Subscriber</td>
      <td>1974.0</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3 = pd.read_csv('JC-20163-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>326</td>
      <td>2016-03-01 00:00:04</td>
      <td>2016-03-01 00:05:31</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>24678</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>168</td>
      <td>2016-03-01 00:02:54</td>
      <td>2016-03-01 00:05:43</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24691</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>133</td>
      <td>2016-03-01 00:38:16</td>
      <td>2016-03-01 00:40:30</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24466</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>473</td>
      <td>2016-03-01 03:28:13</td>
      <td>2016-03-01 03:36:07</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>24414</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>246</td>
      <td>2016-03-01 04:38:22</td>
      <td>2016-03-01 04:42:28</td>
      <td>3205</td>
      <td>JC Medical Center</td>
      <td>40.716540</td>
      <td>-74.049638</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24675</td>
      <td>Subscriber</td>
      <td>1985.0</td>
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
      <td>326</td>
      <td>2016-03-01 00:00:04</td>
      <td>2016-03-01 00:05:31</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>24678</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>168</td>
      <td>2016-03-01 00:02:54</td>
      <td>2016-03-01 00:05:43</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24691</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>133</td>
      <td>2016-03-01 00:38:16</td>
      <td>2016-03-01 00:40:30</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24466</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>473</td>
      <td>2016-03-01 03:28:13</td>
      <td>2016-03-01 03:36:07</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>24414</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>246</td>
      <td>2016-03-01 04:38:22</td>
      <td>2016-03-01 04:42:28</td>
      <td>3205</td>
      <td>JC Medical Center</td>
      <td>40.716540</td>
      <td>-74.049638</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24675</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df4 = pd.read_csv('JC-201604-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2084</td>
      <td>2016-04-01 00:16:13</td>
      <td>2016-04-01 00:50:58</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24500</td>
      <td>Subscriber</td>
      <td>1979.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>324</td>
      <td>2016-04-01 00:32:48</td>
      <td>2016-04-01 00:38:13</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24475</td>
      <td>Subscriber</td>
      <td>1954.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>387</td>
      <td>2016-04-01 02:00:33</td>
      <td>2016-04-01 02:07:00</td>
      <td>3220</td>
      <td>5 Corners Library</td>
      <td>40.734961</td>
      <td>-74.059503</td>
      <td>3215</td>
      <td>Central Ave</td>
      <td>40.746730</td>
      <td>-74.049251</td>
      <td>24503</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>140</td>
      <td>2016-04-01 02:11:43</td>
      <td>2016-04-01 02:14:03</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>24446</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>142</td>
      <td>2016-04-01 02:18:01</td>
      <td>2016-04-01 02:20:23</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>24446</td>
      <td>Subscriber</td>
      <td>1981.0</td>
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
      <td>2084</td>
      <td>2016-04-01 00:16:13</td>
      <td>2016-04-01 00:50:58</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24500</td>
      <td>Subscriber</td>
      <td>1979.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>324</td>
      <td>2016-04-01 00:32:48</td>
      <td>2016-04-01 00:38:13</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24475</td>
      <td>Subscriber</td>
      <td>1954.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>387</td>
      <td>2016-04-01 02:00:33</td>
      <td>2016-04-01 02:07:00</td>
      <td>3220</td>
      <td>5 Corners Library</td>
      <td>40.734961</td>
      <td>-74.059503</td>
      <td>3215</td>
      <td>Central Ave</td>
      <td>40.746730</td>
      <td>-74.049251</td>
      <td>24503</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>140</td>
      <td>2016-04-01 02:11:43</td>
      <td>2016-04-01 02:14:03</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>24446</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>142</td>
      <td>2016-04-01 02:18:01</td>
      <td>2016-04-01 02:20:23</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>24446</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df5 = pd.read_csv('JC-201605-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>243</td>
      <td>2016-05-01 00:04:31</td>
      <td>2016-05-01 00:08:34</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>24507</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>118</td>
      <td>2016-05-01 00:06:47</td>
      <td>2016-05-01 00:08:46</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>24660</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2891</td>
      <td>2016-05-01 00:13:14</td>
      <td>2016-05-01 01:01:25</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>24687</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>303</td>
      <td>2016-05-01 00:19:32</td>
      <td>2016-05-01 00:24:35</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24551</td>
      <td>Subscriber</td>
      <td>1966.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>93</td>
      <td>2016-05-01 00:21:34</td>
      <td>2016-05-01 00:23:08</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>14717</td>
      <td>Subscriber</td>
      <td>1989.0</td>
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
      <td>243</td>
      <td>2016-05-01 00:04:31</td>
      <td>2016-05-01 00:08:34</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>24507</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>118</td>
      <td>2016-05-01 00:06:47</td>
      <td>2016-05-01 00:08:46</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>24660</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2891</td>
      <td>2016-05-01 00:13:14</td>
      <td>2016-05-01 01:01:25</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>24687</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>303</td>
      <td>2016-05-01 00:19:32</td>
      <td>2016-05-01 00:24:35</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24551</td>
      <td>Subscriber</td>
      <td>1966.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>93</td>
      <td>2016-05-01 00:21:34</td>
      <td>2016-05-01 00:23:08</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>14717</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df6 = pd.read_csv('JC-201606-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>669</td>
      <td>2016-06-01 00:00:37</td>
      <td>2016-06-01 00:11:46</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3190</td>
      <td>Garfield Ave Station</td>
      <td>40.710467</td>
      <td>-74.070039</td>
      <td>24486</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>945</td>
      <td>2016-06-01 00:14:54</td>
      <td>2016-06-01 00:30:40</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>24482</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>334</td>
      <td>2016-06-01 00:34:52</td>
      <td>2016-06-01 00:40:26</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24391</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>473</td>
      <td>2016-06-01 00:40:30</td>
      <td>2016-06-01 00:48:23</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>24626</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>551</td>
      <td>2016-06-01 00:50:06</td>
      <td>2016-06-01 00:59:17</td>
      <td>3220</td>
      <td>5 Corners Library</td>
      <td>40.734961</td>
      <td>-74.059503</td>
      <td>3197</td>
      <td>North St</td>
      <td>40.752559</td>
      <td>-74.044725</td>
      <td>24405</td>
      <td>Subscriber</td>
      <td>1987.0</td>
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
      <td>669</td>
      <td>2016-06-01 00:00:37</td>
      <td>2016-06-01 00:11:46</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3190</td>
      <td>Garfield Ave Station</td>
      <td>40.710467</td>
      <td>-74.070039</td>
      <td>24486</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>945</td>
      <td>2016-06-01 00:14:54</td>
      <td>2016-06-01 00:30:40</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>24482</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>334</td>
      <td>2016-06-01 00:34:52</td>
      <td>2016-06-01 00:40:26</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24391</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>473</td>
      <td>2016-06-01 00:40:30</td>
      <td>2016-06-01 00:48:23</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>24626</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>551</td>
      <td>2016-06-01 00:50:06</td>
      <td>2016-06-01 00:59:17</td>
      <td>3220</td>
      <td>5 Corners Library</td>
      <td>40.734961</td>
      <td>-74.059503</td>
      <td>3197</td>
      <td>North St</td>
      <td>40.752559</td>
      <td>-74.044725</td>
      <td>24405</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df7 = pd.read_csv('JC-201607-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>964</td>
      <td>2016-07-01 00:06:09</td>
      <td>2016-07-01 00:22:14</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>24706</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>472</td>
      <td>2016-07-01 00:06:44</td>
      <td>2016-07-01 00:14:37</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>24504</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>565</td>
      <td>2016-07-01 00:10:39</td>
      <td>2016-07-01 00:20:05</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>24655</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>413</td>
      <td>2016-07-01 00:17:22</td>
      <td>2016-07-01 00:24:15</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24446</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>436</td>
      <td>2016-07-01 00:37:31</td>
      <td>2016-07-01 00:44:48</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24408</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>2</td>
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
      <td>964</td>
      <td>2016-07-01 00:06:09</td>
      <td>2016-07-01 00:22:14</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>24706</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>472</td>
      <td>2016-07-01 00:06:44</td>
      <td>2016-07-01 00:14:37</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>24504</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>565</td>
      <td>2016-07-01 00:10:39</td>
      <td>2016-07-01 00:20:05</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>24655</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>413</td>
      <td>2016-07-01 00:17:22</td>
      <td>2016-07-01 00:24:15</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24446</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>436</td>
      <td>2016-07-01 00:37:31</td>
      <td>2016-07-01 00:44:48</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24408</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
df8 = pd.read_csv('JC-201608-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>165</td>
      <td>2016-08-01 00:09:40</td>
      <td>2016-08-01 00:12:25</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>3273</td>
      <td>Manila &amp; 1st</td>
      <td>40.721651</td>
      <td>-74.042884</td>
      <td>24679</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>705</td>
      <td>2016-08-01 01:45:08</td>
      <td>2016-08-01 01:56:53</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3206</td>
      <td>Hilltop</td>
      <td>40.731169</td>
      <td>-74.057574</td>
      <td>24530</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>854</td>
      <td>2016-08-01 02:22:26</td>
      <td>2016-08-01 02:36:41</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3190</td>
      <td>Garfield Ave Station</td>
      <td>40.710467</td>
      <td>-74.070039</td>
      <td>24649</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>211</td>
      <td>2016-08-01 03:05:10</td>
      <td>2016-08-01 03:08:41</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>24624</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>506</td>
      <td>2016-08-01 03:25:42</td>
      <td>2016-08-01 03:34:09</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>24624</td>
      <td>Subscriber</td>
      <td>1986.0</td>
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
      <td>165</td>
      <td>2016-08-01 00:09:40</td>
      <td>2016-08-01 00:12:25</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>3273</td>
      <td>Manila &amp; 1st</td>
      <td>40.721651</td>
      <td>-74.042884</td>
      <td>24679</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>705</td>
      <td>2016-08-01 01:45:08</td>
      <td>2016-08-01 01:56:53</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3206</td>
      <td>Hilltop</td>
      <td>40.731169</td>
      <td>-74.057574</td>
      <td>24530</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>854</td>
      <td>2016-08-01 02:22:26</td>
      <td>2016-08-01 02:36:41</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3190</td>
      <td>Garfield Ave Station</td>
      <td>40.710467</td>
      <td>-74.070039</td>
      <td>24649</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>211</td>
      <td>2016-08-01 03:05:10</td>
      <td>2016-08-01 03:08:41</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>24624</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>506</td>
      <td>2016-08-01 03:25:42</td>
      <td>2016-08-01 03:34:09</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>24624</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df9 = pd.read_csv('JC-201609-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>254</td>
      <td>2016-09-01 00:06:09</td>
      <td>2016-09-01 00:10:24</td>
      <td>3273</td>
      <td>Manila &amp; 1st</td>
      <td>40.721651</td>
      <td>-74.042884</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>26157</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>119</td>
      <td>2016-09-01 00:08:04</td>
      <td>2016-09-01 00:10:04</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>24493</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>425</td>
      <td>2016-09-01 00:14:14</td>
      <td>2016-09-01 00:21:19</td>
      <td>3206</td>
      <td>Hilltop</td>
      <td>40.731169</td>
      <td>-74.057574</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>40.737604</td>
      <td>-74.052478</td>
      <td>24464</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>304</td>
      <td>2016-09-01 00:15:15</td>
      <td>2016-09-01 00:20:20</td>
      <td>3220</td>
      <td>5 Corners Library</td>
      <td>40.734961</td>
      <td>-74.059503</td>
      <td>3212</td>
      <td>Christ Hospital</td>
      <td>40.734786</td>
      <td>-74.050444</td>
      <td>24698</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1775</td>
      <td>2016-09-01 00:16:37</td>
      <td>2016-09-01 00:46:13</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24626</td>
      <td>Subscriber</td>
      <td>1984.0</td>
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
      <td>254</td>
      <td>2016-09-01 00:06:09</td>
      <td>2016-09-01 00:10:24</td>
      <td>3273</td>
      <td>Manila &amp; 1st</td>
      <td>40.721651</td>
      <td>-74.042884</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>26157</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>119</td>
      <td>2016-09-01 00:08:04</td>
      <td>2016-09-01 00:10:04</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>24493</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>425</td>
      <td>2016-09-01 00:14:14</td>
      <td>2016-09-01 00:21:19</td>
      <td>3206</td>
      <td>Hilltop</td>
      <td>40.731169</td>
      <td>-74.057574</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>40.737604</td>
      <td>-74.052478</td>
      <td>24464</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>304</td>
      <td>2016-09-01 00:15:15</td>
      <td>2016-09-01 00:20:20</td>
      <td>3220</td>
      <td>5 Corners Library</td>
      <td>40.734961</td>
      <td>-74.059503</td>
      <td>3212</td>
      <td>Christ Hospital</td>
      <td>40.734786</td>
      <td>-74.050444</td>
      <td>24698</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1775</td>
      <td>2016-09-01 00:16:37</td>
      <td>2016-09-01 00:46:13</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24626</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df10 = pd.read_csv('JC-201610-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>183</td>
      <td>2016-10-01 00:00:38</td>
      <td>2016-10-01 00:03:41</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24510</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>379</td>
      <td>2016-10-01 00:04:57</td>
      <td>2016-10-01 00:11:17</td>
      <td>3273</td>
      <td>Manila &amp; 1st</td>
      <td>40.721651</td>
      <td>-74.042884</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>26152</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>414</td>
      <td>2016-10-01 00:05:18</td>
      <td>2016-10-01 00:12:13</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>26213</td>
      <td>Subscriber</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2411</td>
      <td>2016-10-01 00:15:23</td>
      <td>2016-10-01 00:55:35</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>26278</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>170</td>
      <td>2016-10-01 00:21:25</td>
      <td>2016-10-01 00:24:16</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>26152</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
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
      <td>183</td>
      <td>2016-10-01 00:00:38</td>
      <td>2016-10-01 00:03:41</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24510</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>379</td>
      <td>2016-10-01 00:04:57</td>
      <td>2016-10-01 00:11:17</td>
      <td>3273</td>
      <td>Manila &amp; 1st</td>
      <td>40.721651</td>
      <td>-74.042884</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>26152</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>414</td>
      <td>2016-10-01 00:05:18</td>
      <td>2016-10-01 00:12:13</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>26213</td>
      <td>Subscriber</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2411</td>
      <td>2016-10-01 00:15:23</td>
      <td>2016-10-01 00:55:35</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>26278</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>170</td>
      <td>2016-10-01 00:21:25</td>
      <td>2016-10-01 00:24:16</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>26152</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df11 = pd.read_csv('JC-201611-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>365</td>
      <td>2016-11-01 00:00:39</td>
      <td>2016-11-01 00:06:45</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>26217</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>349</td>
      <td>2016-11-01 00:05:14</td>
      <td>2016-11-01 00:11:04</td>
      <td>3220</td>
      <td>5 Corners Library</td>
      <td>40.734961</td>
      <td>-74.059503</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>24623</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2701</td>
      <td>2016-11-01 00:05:51</td>
      <td>2016-11-01 00:50:53</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>26314</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>313</td>
      <td>2016-11-01 00:10:48</td>
      <td>2016-11-01 00:16:01</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>22064</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>379</td>
      <td>2016-11-01 00:19:39</td>
      <td>2016-11-01 00:25:59</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24456</td>
      <td>Subscriber</td>
      <td>1986.0</td>
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
      <td>365</td>
      <td>2016-11-01 00:00:39</td>
      <td>2016-11-01 00:06:45</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>26217</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>349</td>
      <td>2016-11-01 00:05:14</td>
      <td>2016-11-01 00:11:04</td>
      <td>3220</td>
      <td>5 Corners Library</td>
      <td>40.734961</td>
      <td>-74.059503</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>24623</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2701</td>
      <td>2016-11-01 00:05:51</td>
      <td>2016-11-01 00:50:53</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>26314</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>313</td>
      <td>2016-11-01 00:10:48</td>
      <td>2016-11-01 00:16:01</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>22064</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>379</td>
      <td>2016-11-01 00:19:39</td>
      <td>2016-11-01 00:25:59</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24456</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df12 = pd.read_csv('JC-201612-citibike-tripdata.csv')
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
      <th>Trip Duration</th>
      <th>Start Time</th>
      <th>Stop Time</th>
      <th>Start Station ID</th>
      <th>Start Station Name</th>
      <th>Start Station Latitude</th>
      <th>Start Station Longitude</th>
      <th>End Station ID</th>
      <th>End Station Name</th>
      <th>End Station Latitude</th>
      <th>End Station Longitude</th>
      <th>Bike ID</th>
      <th>User Type</th>
      <th>Birth Year</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>204</td>
      <td>2016-12-01 00:33:31</td>
      <td>2016-12-01 00:36:55</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>24377</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>606</td>
      <td>2016-12-01 00:56:09</td>
      <td>2016-12-01 01:06:16</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3189</td>
      <td>West Side Light Rail</td>
      <td>40.714402</td>
      <td>-74.088772</td>
      <td>26273</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>185</td>
      <td>2016-12-01 01:14:22</td>
      <td>2016-12-01 01:17:27</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3205</td>
      <td>JC Medical Center</td>
      <td>40.716540</td>
      <td>-74.049638</td>
      <td>24555</td>
      <td>Subscriber</td>
      <td>1977.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>504</td>
      <td>2016-12-01 01:29:52</td>
      <td>2016-12-01 01:38:17</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3191</td>
      <td>Union St</td>
      <td>40.718211</td>
      <td>-74.083639</td>
      <td>26186</td>
      <td>Subscriber</td>
      <td>1954.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>672</td>
      <td>2016-12-01 01:47:14</td>
      <td>2016-12-01 01:58:27</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3190</td>
      <td>Garfield Ave Station</td>
      <td>40.710467</td>
      <td>-74.070039</td>
      <td>26170</td>
      <td>Subscriber</td>
      <td>1988.0</td>
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
      <td>204</td>
      <td>2016-12-01 00:33:31</td>
      <td>2016-12-01 00:36:55</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>24377</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>606</td>
      <td>2016-12-01 00:56:09</td>
      <td>2016-12-01 01:06:16</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3189</td>
      <td>West Side Light Rail</td>
      <td>40.714402</td>
      <td>-74.088772</td>
      <td>26273</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>185</td>
      <td>2016-12-01 01:14:22</td>
      <td>2016-12-01 01:17:27</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3205</td>
      <td>JC Medical Center</td>
      <td>40.716540</td>
      <td>-74.049638</td>
      <td>24555</td>
      <td>Subscriber</td>
      <td>1977.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>504</td>
      <td>2016-12-01 01:29:52</td>
      <td>2016-12-01 01:38:17</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3191</td>
      <td>Union St</td>
      <td>40.718211</td>
      <td>-74.083639</td>
      <td>26186</td>
      <td>Subscriber</td>
      <td>1954.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>672</td>
      <td>2016-12-01 01:47:14</td>
      <td>2016-12-01 01:58:27</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3190</td>
      <td>Garfield Ave Station</td>
      <td>40.710467</td>
      <td>-74.070039</td>
      <td>26170</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
jc_citibike_2016 = pd.concat([df1, df2, df3, df4, df5, df6, df7, df8, df9, df10, df11, df12])
jc_citibike_2016
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
      <td>362</td>
      <td>2016-01-01 00:02:52</td>
      <td>2016-01-01 00:08:54</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24647</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>200</td>
      <td>2016-01-01 00:18:22</td>
      <td>2016-01-01 00:21:42</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24605</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>202</td>
      <td>2016-01-01 00:18:25</td>
      <td>2016-01-01 00:21:47</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24689</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>248</td>
      <td>2016-01-01 00:23:13</td>
      <td>2016-01-01 00:27:21</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24693</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>903</td>
      <td>2016-01-01 01:03:20</td>
      <td>2016-01-01 01:18:24</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>24573</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>883</td>
      <td>2016-01-01 01:03:28</td>
      <td>2016-01-01 01:18:11</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>24442</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>445</td>
      <td>2016-01-01 01:07:45</td>
      <td>2016-01-01 01:15:11</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24510</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>7</th>
      <td>192</td>
      <td>2016-01-01 01:18:51</td>
      <td>2016-01-01 01:22:03</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24625</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8</th>
      <td>409</td>
      <td>2016-01-01 01:23:44</td>
      <td>2016-01-01 01:30:34</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>24429</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>9</th>
      <td>285</td>
      <td>2016-01-01 01:25:12</td>
      <td>2016-01-01 01:29:57</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>24407</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>10</th>
      <td>206</td>
      <td>2016-01-01 01:45:34</td>
      <td>2016-01-01 01:49:00</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>24377</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>11</th>
      <td>251</td>
      <td>2016-01-01 02:02:55</td>
      <td>2016-01-01 02:07:06</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24605</td>
      <td>Subscriber</td>
      <td>1976.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>12</th>
      <td>292</td>
      <td>2016-01-01 02:20:38</td>
      <td>2016-01-01 02:25:30</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>24721</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>13</th>
      <td>175</td>
      <td>2016-01-01 02:23:37</td>
      <td>2016-01-01 02:26:32</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24601</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>14</th>
      <td>769</td>
      <td>2016-01-01 02:28:58</td>
      <td>2016-01-01 02:41:47</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>24606</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15</th>
      <td>384</td>
      <td>2016-01-01 02:39:07</td>
      <td>2016-01-01 02:45:32</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24470</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>16</th>
      <td>364</td>
      <td>2016-01-01 02:39:28</td>
      <td>2016-01-01 02:45:33</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24542</td>
      <td>Subscriber</td>
      <td>1976.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>17</th>
      <td>326</td>
      <td>2016-01-01 02:47:39</td>
      <td>2016-01-01 02:53:05</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>24716</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>18</th>
      <td>341</td>
      <td>2016-01-01 02:53:35</td>
      <td>2016-01-01 02:59:17</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>24687</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>19</th>
      <td>634</td>
      <td>2016-01-01 02:54:56</td>
      <td>2016-01-01 03:05:30</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24675</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20</th>
      <td>331</td>
      <td>2016-01-01 03:02:35</td>
      <td>2016-01-01 03:08:06</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24687</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>21</th>
      <td>550</td>
      <td>2016-01-01 03:10:25</td>
      <td>2016-01-01 03:19:36</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>24531</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>22</th>
      <td>988</td>
      <td>2016-01-01 03:16:33</td>
      <td>2016-01-01 03:33:02</td>
      <td>3196</td>
      <td>Riverview Park</td>
      <td>40.744319</td>
      <td>-74.043991</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24662</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>23</th>
      <td>969</td>
      <td>2016-01-01 03:16:34</td>
      <td>2016-01-01 03:32:43</td>
      <td>3196</td>
      <td>Riverview Park</td>
      <td>40.744319</td>
      <td>-74.043991</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24563</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>24</th>
      <td>378</td>
      <td>2016-01-01 03:17:01</td>
      <td>2016-01-01 03:23:19</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24450</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>25</th>
      <td>368</td>
      <td>2016-01-01 03:17:13</td>
      <td>2016-01-01 03:23:21</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24627</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>26</th>
      <td>287</td>
      <td>2016-01-01 03:43:03</td>
      <td>2016-01-01 03:47:51</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>24471</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>27</th>
      <td>286</td>
      <td>2016-01-01 03:51:30</td>
      <td>2016-01-01 03:56:16</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>24407</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>28</th>
      <td>539</td>
      <td>2016-01-01 04:12:06</td>
      <td>2016-01-01 04:21:05</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3212</td>
      <td>Christ Hospital</td>
      <td>40.734786</td>
      <td>-74.050444</td>
      <td>24664</td>
      <td>Subscriber</td>
      <td>1966.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>29</th>
      <td>340</td>
      <td>2016-01-01 04:16:04</td>
      <td>2016-01-01 04:21:45</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>24493</td>
      <td>Subscriber</td>
      <td>1972.0</td>
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
      <th>15084</th>
      <td>251</td>
      <td>2016-12-31 19:30:47</td>
      <td>2016-12-31 19:34:58</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3273</td>
      <td>Manila &amp; 1st</td>
      <td>40.721651</td>
      <td>-74.042884</td>
      <td>24530</td>
      <td>Subscriber</td>
      <td>1973.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15085</th>
      <td>225</td>
      <td>2016-12-31 19:38:48</td>
      <td>2016-12-31 19:42:34</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24525</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15086</th>
      <td>260</td>
      <td>2016-12-31 19:53:28</td>
      <td>2016-12-31 19:57:49</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24641</td>
      <td>Subscriber</td>
      <td>1959.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15087</th>
      <td>627</td>
      <td>2016-12-31 19:58:11</td>
      <td>2016-12-31 20:08:38</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>24513</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15088</th>
      <td>597</td>
      <td>2016-12-31 19:58:38</td>
      <td>2016-12-31 20:08:36</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>24463</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15089</th>
      <td>75</td>
      <td>2016-12-31 20:07:34</td>
      <td>2016-12-31 20:08:50</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>24600</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15090</th>
      <td>76</td>
      <td>2016-12-31 20:12:18</td>
      <td>2016-12-31 20:13:34</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>24600</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15091</th>
      <td>440</td>
      <td>2016-12-31 20:12:26</td>
      <td>2016-12-31 20:19:47</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>24417</td>
      <td>Subscriber</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>15092</th>
      <td>391</td>
      <td>2016-12-31 20:17:20</td>
      <td>2016-12-31 20:23:52</td>
      <td>3281</td>
      <td>Leonard Gordon Park</td>
      <td>40.745910</td>
      <td>-74.057271</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>24408</td>
      <td>Subscriber</td>
      <td>1994.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15093</th>
      <td>287</td>
      <td>2016-12-31 20:18:53</td>
      <td>2016-12-31 20:23:41</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>24699</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15094</th>
      <td>158</td>
      <td>2016-12-31 20:24:55</td>
      <td>2016-12-31 20:27:33</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24457</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15095</th>
      <td>820</td>
      <td>2016-12-31 20:27:55</td>
      <td>2016-12-31 20:41:35</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>26200</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15096</th>
      <td>168</td>
      <td>2016-12-31 20:48:27</td>
      <td>2016-12-31 20:51:16</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3279</td>
      <td>Dixon Mills</td>
      <td>40.721630</td>
      <td>-74.049968</td>
      <td>26198</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15097</th>
      <td>267</td>
      <td>2016-12-31 20:52:51</td>
      <td>2016-12-31 20:57:19</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>26241</td>
      <td>Subscriber</td>
      <td>1966.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15098</th>
      <td>212</td>
      <td>2016-12-31 21:03:10</td>
      <td>2016-12-31 21:06:42</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>26163</td>
      <td>Subscriber</td>
      <td>1972.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15099</th>
      <td>1226</td>
      <td>2016-12-31 21:08:02</td>
      <td>2016-12-31 21:28:28</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>24535</td>
      <td>Subscriber</td>
      <td>1960.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15100</th>
      <td>304</td>
      <td>2016-12-31 21:12:05</td>
      <td>2016-12-31 21:17:10</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>3212</td>
      <td>Christ Hospital</td>
      <td>40.734786</td>
      <td>-74.050444</td>
      <td>24486</td>
      <td>Subscriber</td>
      <td>1969.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15101</th>
      <td>209</td>
      <td>2016-12-31 21:23:56</td>
      <td>2016-12-31 21:27:26</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24516</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15102</th>
      <td>463</td>
      <td>2016-12-31 21:41:17</td>
      <td>2016-12-31 21:49:00</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3220</td>
      <td>5 Corners Library</td>
      <td>40.734961</td>
      <td>-74.059503</td>
      <td>24426</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15103</th>
      <td>99</td>
      <td>2016-12-31 21:44:50</td>
      <td>2016-12-31 21:46:30</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>24622</td>
      <td>Subscriber</td>
      <td>1957.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15104</th>
      <td>216</td>
      <td>2016-12-31 21:48:33</td>
      <td>2016-12-31 21:52:09</td>
      <td>3205</td>
      <td>JC Medical Center</td>
      <td>40.716540</td>
      <td>-74.049638</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24590</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15105</th>
      <td>559</td>
      <td>2016-12-31 21:52:13</td>
      <td>2016-12-31 22:01:32</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>26431</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15106</th>
      <td>473</td>
      <td>2016-12-31 22:04:14</td>
      <td>2016-12-31 22:12:07</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3268</td>
      <td>Lafayette Park</td>
      <td>40.713464</td>
      <td>-74.062859</td>
      <td>24525</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15107</th>
      <td>242</td>
      <td>2016-12-31 23:02:01</td>
      <td>2016-12-31 23:06:03</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>26232</td>
      <td>Subscriber</td>
      <td>1958.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15108</th>
      <td>377</td>
      <td>2016-12-31 23:10:00</td>
      <td>2016-12-31 23:16:17</td>
      <td>3206</td>
      <td>Hilltop</td>
      <td>40.731169</td>
      <td>-74.057574</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>40.723659</td>
      <td>-74.064194</td>
      <td>24421</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15109</th>
      <td>557</td>
      <td>2016-12-31 23:10:16</td>
      <td>2016-12-31 23:19:33</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24465</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15110</th>
      <td>2749</td>
      <td>2016-12-31 23:29:39</td>
      <td>2017-01-01 00:15:29</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>24389</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>15111</th>
      <td>173</td>
      <td>2016-12-31 23:44:37</td>
      <td>2016-12-31 23:47:31</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>24641</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15112</th>
      <td>2424</td>
      <td>2016-12-31 23:44:50</td>
      <td>2017-01-01 00:25:14</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>26219</td>
      <td>Subscriber</td>
      <td>1960.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15113</th>
      <td>2419</td>
      <td>2016-12-31 23:44:50</td>
      <td>2017-01-01 00:25:10</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>24471</td>
      <td>Subscriber</td>
      <td>1956.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>247584 rows × 15 columns</p>
</div>




```python
jc_citibike_2016.to_csv('jc_citibike_2016.csv', sep = ',') 
```


```python

```
