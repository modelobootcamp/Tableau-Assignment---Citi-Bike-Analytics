

```python
import pandas as pd 
```


```python
df1 = pd.read_csv('JC-201701-citibike-tripdata.csv')
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
      <td>148</td>
      <td>2017-01-01 00:21:32</td>
      <td>2017-01-01 00:24:01</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>24575</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1283</td>
      <td>2017-01-01 00:24:35</td>
      <td>2017-01-01 00:45:58</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3198</td>
      <td>Heights Elevator</td>
      <td>40.748716</td>
      <td>-74.040443</td>
      <td>24723</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>372</td>
      <td>2017-01-01 00:38:19</td>
      <td>2017-01-01 00:44:31</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>24620</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1513</td>
      <td>2017-01-01 00:38:37</td>
      <td>2017-01-01 01:03:50</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3271</td>
      <td>Danforth Light Rail</td>
      <td>40.692640</td>
      <td>-74.088012</td>
      <td>24668</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>639</td>
      <td>2017-01-01 01:47:52</td>
      <td>2017-01-01 01:58:31</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>26167</td>
      <td>Subscriber</td>
      <td>1993.0</td>
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
      <td>148</td>
      <td>2017-01-01 00:21:32</td>
      <td>2017-01-01 00:24:01</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>24575</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1283</td>
      <td>2017-01-01 00:24:35</td>
      <td>2017-01-01 00:45:58</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3198</td>
      <td>Heights Elevator</td>
      <td>40.748716</td>
      <td>-74.040443</td>
      <td>24723</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>372</td>
      <td>2017-01-01 00:38:19</td>
      <td>2017-01-01 00:44:31</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>24620</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1513</td>
      <td>2017-01-01 00:38:37</td>
      <td>2017-01-01 01:03:50</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3271</td>
      <td>Danforth Light Rail</td>
      <td>40.692640</td>
      <td>-74.088012</td>
      <td>24668</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>639</td>
      <td>2017-01-01 01:47:52</td>
      <td>2017-01-01 01:58:31</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>26167</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2 = pd.read_csv('201702-citibike-tripdata.csv')
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
      <td>1087</td>
      <td>2017-02-01 00:00:13</td>
      <td>2017-02-01 00:18:20</td>
      <td>345</td>
      <td>W 13 St &amp; 6 Ave</td>
      <td>40.736494</td>
      <td>-73.997044</td>
      <td>305</td>
      <td>E 58 St &amp; 3 Ave</td>
      <td>40.760958</td>
      <td>-73.967245</td>
      <td>17432</td>
      <td>Subscriber</td>
      <td>1966.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>704</td>
      <td>2017-02-01 00:00:31</td>
      <td>2017-02-01 00:12:15</td>
      <td>3295</td>
      <td>Central Park W &amp; W 96 St</td>
      <td>40.791270</td>
      <td>-73.964839</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>20621</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>212</td>
      <td>2017-02-01 00:00:34</td>
      <td>2017-02-01 00:04:06</td>
      <td>336</td>
      <td>Sullivan St &amp; Washington Sq</td>
      <td>40.730477</td>
      <td>-73.999061</td>
      <td>439</td>
      <td>E 4 St &amp; 2 Ave</td>
      <td>40.726281</td>
      <td>-73.989780</td>
      <td>16826</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1140</td>
      <td>2017-02-01 00:00:44</td>
      <td>2017-02-01 00:19:44</td>
      <td>484</td>
      <td>W 44 St &amp; 5 Ave</td>
      <td>40.755003</td>
      <td>-73.980144</td>
      <td>3295</td>
      <td>Central Park W &amp; W 96 St</td>
      <td>40.791270</td>
      <td>-73.964839</td>
      <td>27052</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>320</td>
      <td>2017-02-01 00:00:42</td>
      <td>2017-02-01 00:06:02</td>
      <td>490</td>
      <td>8 Ave &amp; W 33 St</td>
      <td>40.751551</td>
      <td>-73.993934</td>
      <td>3431</td>
      <td>E 35 St &amp; 3 Ave</td>
      <td>40.746524</td>
      <td>-73.977885</td>
      <td>25238</td>
      <td>Subscriber</td>
      <td>1987.0</td>
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
      <td>1087</td>
      <td>2017-02-01 00:00:13</td>
      <td>2017-02-01 00:18:20</td>
      <td>345</td>
      <td>W 13 St &amp; 6 Ave</td>
      <td>40.736494</td>
      <td>-73.997044</td>
      <td>305</td>
      <td>E 58 St &amp; 3 Ave</td>
      <td>40.760958</td>
      <td>-73.967245</td>
      <td>17432</td>
      <td>Subscriber</td>
      <td>1966.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>704</td>
      <td>2017-02-01 00:00:31</td>
      <td>2017-02-01 00:12:15</td>
      <td>3295</td>
      <td>Central Park W &amp; W 96 St</td>
      <td>40.791270</td>
      <td>-73.964839</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>20621</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>212</td>
      <td>2017-02-01 00:00:34</td>
      <td>2017-02-01 00:04:06</td>
      <td>336</td>
      <td>Sullivan St &amp; Washington Sq</td>
      <td>40.730477</td>
      <td>-73.999061</td>
      <td>439</td>
      <td>E 4 St &amp; 2 Ave</td>
      <td>40.726281</td>
      <td>-73.989780</td>
      <td>16826</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1140</td>
      <td>2017-02-01 00:00:44</td>
      <td>2017-02-01 00:19:44</td>
      <td>484</td>
      <td>W 44 St &amp; 5 Ave</td>
      <td>40.755003</td>
      <td>-73.980144</td>
      <td>3295</td>
      <td>Central Park W &amp; W 96 St</td>
      <td>40.791270</td>
      <td>-73.964839</td>
      <td>27052</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>320</td>
      <td>2017-02-01 00:00:42</td>
      <td>2017-02-01 00:06:02</td>
      <td>490</td>
      <td>8 Ave &amp; W 33 St</td>
      <td>40.751551</td>
      <td>-73.993934</td>
      <td>3431</td>
      <td>E 35 St &amp; 3 Ave</td>
      <td>40.746524</td>
      <td>-73.977885</td>
      <td>25238</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3 = pd.read_csv('201703-citibike-tripdata.csv')
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
      <td>1893</td>
      <td>2017-03-01 00:00:32</td>
      <td>2017-03-01 00:32:06</td>
      <td>2009</td>
      <td>Catherine St &amp; Monroe St</td>
      <td>40.711174</td>
      <td>-73.996826</td>
      <td>527</td>
      <td>E 33 St &amp; 2 Ave</td>
      <td>40.744023</td>
      <td>-73.976056</td>
      <td>27291</td>
      <td>Subscriber</td>
      <td>1973.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>223</td>
      <td>2017-03-01 00:01:09</td>
      <td>2017-03-01 00:04:53</td>
      <td>127</td>
      <td>Barrow St &amp; Hudson St</td>
      <td>40.731724</td>
      <td>-74.006744</td>
      <td>284</td>
      <td>Greenwich Ave &amp; 8 Ave</td>
      <td>40.739017</td>
      <td>-74.002638</td>
      <td>19387</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1665</td>
      <td>2017-03-01 00:01:27</td>
      <td>2017-03-01 00:29:12</td>
      <td>174</td>
      <td>E 25 St &amp; 1 Ave</td>
      <td>40.738177</td>
      <td>-73.977387</td>
      <td>307</td>
      <td>Canal St &amp; Rutgers St</td>
      <td>40.714275</td>
      <td>-73.989900</td>
      <td>15809</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>100</td>
      <td>2017-03-01 00:01:29</td>
      <td>2017-03-01 00:03:10</td>
      <td>316</td>
      <td>Fulton St &amp; William St</td>
      <td>40.709560</td>
      <td>-74.006536</td>
      <td>306</td>
      <td>Cliff St &amp; Fulton St</td>
      <td>40.708235</td>
      <td>-74.005301</td>
      <td>18956</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1229</td>
      <td>2017-03-01 00:01:33</td>
      <td>2017-03-01 00:22:02</td>
      <td>536</td>
      <td>1 Ave &amp; E 30 St</td>
      <td>40.741444</td>
      <td>-73.975361</td>
      <td>259</td>
      <td>South St &amp; Whitehall St</td>
      <td>40.701221</td>
      <td>-74.012342</td>
      <td>25728</td>
      <td>Subscriber</td>
      <td>1963.0</td>
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
      <td>1893</td>
      <td>2017-03-01 00:00:32</td>
      <td>2017-03-01 00:32:06</td>
      <td>2009</td>
      <td>Catherine St &amp; Monroe St</td>
      <td>40.711174</td>
      <td>-73.996826</td>
      <td>527</td>
      <td>E 33 St &amp; 2 Ave</td>
      <td>40.744023</td>
      <td>-73.976056</td>
      <td>27291</td>
      <td>Subscriber</td>
      <td>1973.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>223</td>
      <td>2017-03-01 00:01:09</td>
      <td>2017-03-01 00:04:53</td>
      <td>127</td>
      <td>Barrow St &amp; Hudson St</td>
      <td>40.731724</td>
      <td>-74.006744</td>
      <td>284</td>
      <td>Greenwich Ave &amp; 8 Ave</td>
      <td>40.739017</td>
      <td>-74.002638</td>
      <td>19387</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1665</td>
      <td>2017-03-01 00:01:27</td>
      <td>2017-03-01 00:29:12</td>
      <td>174</td>
      <td>E 25 St &amp; 1 Ave</td>
      <td>40.738177</td>
      <td>-73.977387</td>
      <td>307</td>
      <td>Canal St &amp; Rutgers St</td>
      <td>40.714275</td>
      <td>-73.989900</td>
      <td>15809</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>100</td>
      <td>2017-03-01 00:01:29</td>
      <td>2017-03-01 00:03:10</td>
      <td>316</td>
      <td>Fulton St &amp; William St</td>
      <td>40.709560</td>
      <td>-74.006536</td>
      <td>306</td>
      <td>Cliff St &amp; Fulton St</td>
      <td>40.708235</td>
      <td>-74.005301</td>
      <td>18956</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1229</td>
      <td>2017-03-01 00:01:33</td>
      <td>2017-03-01 00:22:02</td>
      <td>536</td>
      <td>1 Ave &amp; E 30 St</td>
      <td>40.741444</td>
      <td>-73.975361</td>
      <td>259</td>
      <td>South St &amp; Whitehall St</td>
      <td>40.701221</td>
      <td>-74.012342</td>
      <td>25728</td>
      <td>Subscriber</td>
      <td>1963.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df4 = pd.read_csv('201704-citibike-tripdata.csv')
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
      <td>195</td>
      <td>2017-04-01 00:00:58</td>
      <td>2017-04-01 00:04:14</td>
      <td>217</td>
      <td>Old Fulton St</td>
      <td>40.702772</td>
      <td>-73.993836</td>
      <td>430</td>
      <td>York St &amp; Jay St</td>
      <td>40.701485</td>
      <td>-73.986569</td>
      <td>25454</td>
      <td>Subscriber</td>
      <td>1966.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>585</td>
      <td>2017-04-01 00:01:54</td>
      <td>2017-04-01 00:11:40</td>
      <td>490</td>
      <td>8 Ave &amp; W 33 St</td>
      <td>40.751551</td>
      <td>-73.993934</td>
      <td>3158</td>
      <td>W 63 St &amp; Broadway</td>
      <td>40.771639</td>
      <td>-73.982614</td>
      <td>25930</td>
      <td>Subscriber</td>
      <td>1995.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>665</td>
      <td>2017-04-01 00:01:56</td>
      <td>2017-04-01 00:13:01</td>
      <td>504</td>
      <td>1 Ave &amp; E 16 St</td>
      <td>40.732219</td>
      <td>-73.981656</td>
      <td>412</td>
      <td>Forsyth St &amp; Canal St</td>
      <td>40.715816</td>
      <td>-73.994224</td>
      <td>27110</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>262</td>
      <td>2017-04-01 00:02:24</td>
      <td>2017-04-01 00:06:47</td>
      <td>445</td>
      <td>E 10 St &amp; Avenue A</td>
      <td>40.727408</td>
      <td>-73.981420</td>
      <td>411</td>
      <td>E 6 St &amp; Avenue D</td>
      <td>40.722281</td>
      <td>-73.976687</td>
      <td>28392</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>134</td>
      <td>2017-04-01 00:02:36</td>
      <td>2017-04-01 00:04:50</td>
      <td>3423</td>
      <td>West Drive &amp; Prospect Park West</td>
      <td>40.661063</td>
      <td>-73.979453</td>
      <td>3300</td>
      <td>Prospect Park West &amp; 8 St</td>
      <td>40.665147</td>
      <td>-73.976376</td>
      <td>19316</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>2</td>
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
      <td>195</td>
      <td>2017-04-01 00:00:58</td>
      <td>2017-04-01 00:04:14</td>
      <td>217</td>
      <td>Old Fulton St</td>
      <td>40.702772</td>
      <td>-73.993836</td>
      <td>430</td>
      <td>York St &amp; Jay St</td>
      <td>40.701485</td>
      <td>-73.986569</td>
      <td>25454</td>
      <td>Subscriber</td>
      <td>1966.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>585</td>
      <td>2017-04-01 00:01:54</td>
      <td>2017-04-01 00:11:40</td>
      <td>490</td>
      <td>8 Ave &amp; W 33 St</td>
      <td>40.751551</td>
      <td>-73.993934</td>
      <td>3158</td>
      <td>W 63 St &amp; Broadway</td>
      <td>40.771639</td>
      <td>-73.982614</td>
      <td>25930</td>
      <td>Subscriber</td>
      <td>1995.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>665</td>
      <td>2017-04-01 00:01:56</td>
      <td>2017-04-01 00:13:01</td>
      <td>504</td>
      <td>1 Ave &amp; E 16 St</td>
      <td>40.732219</td>
      <td>-73.981656</td>
      <td>412</td>
      <td>Forsyth St &amp; Canal St</td>
      <td>40.715816</td>
      <td>-73.994224</td>
      <td>27110</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>262</td>
      <td>2017-04-01 00:02:24</td>
      <td>2017-04-01 00:06:47</td>
      <td>445</td>
      <td>E 10 St &amp; Avenue A</td>
      <td>40.727408</td>
      <td>-73.981420</td>
      <td>411</td>
      <td>E 6 St &amp; Avenue D</td>
      <td>40.722281</td>
      <td>-73.976687</td>
      <td>28392</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>134</td>
      <td>2017-04-01 00:02:36</td>
      <td>2017-04-01 00:04:50</td>
      <td>3423</td>
      <td>West Drive &amp; Prospect Park West</td>
      <td>40.661063</td>
      <td>-73.979453</td>
      <td>3300</td>
      <td>Prospect Park West &amp; 8 St</td>
      <td>40.665147</td>
      <td>-73.976376</td>
      <td>19316</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
df5 = pd.read_csv('201705-citibike-tripdata.csv')
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
      <td>254</td>
      <td>2017-05-01 00:00:13</td>
      <td>2017-05-01 00:04:27</td>
      <td>511</td>
      <td>E 14 St &amp; Avenue B</td>
      <td>40.729387</td>
      <td>-73.977724</td>
      <td>394</td>
      <td>E 9 St &amp; Avenue C</td>
      <td>40.725213</td>
      <td>-73.977688</td>
      <td>27695</td>
      <td>Subscriber</td>
      <td>1996.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>248</td>
      <td>2017-05-01 00:00:19</td>
      <td>2017-05-01 00:04:28</td>
      <td>511</td>
      <td>E 14 St &amp; Avenue B</td>
      <td>40.729387</td>
      <td>-73.977724</td>
      <td>394</td>
      <td>E 9 St &amp; Avenue C</td>
      <td>40.725213</td>
      <td>-73.977688</td>
      <td>15869</td>
      <td>Subscriber</td>
      <td>1996.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1120</td>
      <td>2017-05-01 00:00:19</td>
      <td>2017-05-01 00:19:00</td>
      <td>242</td>
      <td>Carlton Ave &amp; Flushing Ave</td>
      <td>40.697787</td>
      <td>-73.973736</td>
      <td>3083</td>
      <td>Bushwick Ave &amp; Powers St</td>
      <td>40.712477</td>
      <td>-73.941000</td>
      <td>18700</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>212</td>
      <td>2017-05-01 00:00:24</td>
      <td>2017-05-01 00:03:56</td>
      <td>168</td>
      <td>W 18 St &amp; 6 Ave</td>
      <td>40.739713</td>
      <td>-73.994564</td>
      <td>116</td>
      <td>W 17 St &amp; 8 Ave</td>
      <td>40.741776</td>
      <td>-74.001497</td>
      <td>24981</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>686</td>
      <td>2017-05-01 00:00:29</td>
      <td>2017-05-01 00:11:55</td>
      <td>494</td>
      <td>W 26 St &amp; 8 Ave</td>
      <td>40.747348</td>
      <td>-73.997236</td>
      <td>527</td>
      <td>E 33 St &amp; 2 Ave</td>
      <td>40.744023</td>
      <td>-73.976056</td>
      <td>25407</td>
      <td>Subscriber</td>
      <td>1964.0</td>
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
      <td>254</td>
      <td>2017-05-01 00:00:13</td>
      <td>2017-05-01 00:04:27</td>
      <td>511</td>
      <td>E 14 St &amp; Avenue B</td>
      <td>40.729387</td>
      <td>-73.977724</td>
      <td>394</td>
      <td>E 9 St &amp; Avenue C</td>
      <td>40.725213</td>
      <td>-73.977688</td>
      <td>27695</td>
      <td>Subscriber</td>
      <td>1996.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>248</td>
      <td>2017-05-01 00:00:19</td>
      <td>2017-05-01 00:04:28</td>
      <td>511</td>
      <td>E 14 St &amp; Avenue B</td>
      <td>40.729387</td>
      <td>-73.977724</td>
      <td>394</td>
      <td>E 9 St &amp; Avenue C</td>
      <td>40.725213</td>
      <td>-73.977688</td>
      <td>15869</td>
      <td>Subscriber</td>
      <td>1996.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1120</td>
      <td>2017-05-01 00:00:19</td>
      <td>2017-05-01 00:19:00</td>
      <td>242</td>
      <td>Carlton Ave &amp; Flushing Ave</td>
      <td>40.697787</td>
      <td>-73.973736</td>
      <td>3083</td>
      <td>Bushwick Ave &amp; Powers St</td>
      <td>40.712477</td>
      <td>-73.941000</td>
      <td>18700</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>212</td>
      <td>2017-05-01 00:00:24</td>
      <td>2017-05-01 00:03:56</td>
      <td>168</td>
      <td>W 18 St &amp; 6 Ave</td>
      <td>40.739713</td>
      <td>-73.994564</td>
      <td>116</td>
      <td>W 17 St &amp; 8 Ave</td>
      <td>40.741776</td>
      <td>-74.001497</td>
      <td>24981</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>686</td>
      <td>2017-05-01 00:00:29</td>
      <td>2017-05-01 00:11:55</td>
      <td>494</td>
      <td>W 26 St &amp; 8 Ave</td>
      <td>40.747348</td>
      <td>-73.997236</td>
      <td>527</td>
      <td>E 33 St &amp; 2 Ave</td>
      <td>40.744023</td>
      <td>-73.976056</td>
      <td>25407</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df6 = pd.read_csv('201706-citibike-tripdata.csv')
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
      <td>1397</td>
      <td>2017-06-01 00:00:02</td>
      <td>2017-06-01 00:23:19</td>
      <td>515</td>
      <td>W 43 St &amp; 10 Ave</td>
      <td>40.760094</td>
      <td>-73.994618</td>
      <td>3285</td>
      <td>W 87 St  &amp; Amsterdam Ave</td>
      <td>40.788390</td>
      <td>-73.974700</td>
      <td>26642</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1103</td>
      <td>2017-06-01 00:00:13</td>
      <td>2017-06-01 00:18:37</td>
      <td>488</td>
      <td>W 39 St &amp; 9 Ave</td>
      <td>40.756458</td>
      <td>-73.993722</td>
      <td>297</td>
      <td>E 15 St &amp; 3 Ave</td>
      <td>40.734232</td>
      <td>-73.986923</td>
      <td>25656</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1810</td>
      <td>2017-06-01 00:00:20</td>
      <td>2017-06-01 00:30:31</td>
      <td>461</td>
      <td>E 20 St &amp; 2 Ave</td>
      <td>40.735877</td>
      <td>-73.982050</td>
      <td>465</td>
      <td>Broadway &amp; W 41 St</td>
      <td>40.755136</td>
      <td>-73.986580</td>
      <td>21023</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1760</td>
      <td>2017-06-01 00:00:24</td>
      <td>2017-06-01 00:29:45</td>
      <td>2009</td>
      <td>Catherine St &amp; Monroe St</td>
      <td>40.711174</td>
      <td>-73.996826</td>
      <td>527</td>
      <td>E 33 St &amp; 2 Ave</td>
      <td>40.744023</td>
      <td>-73.976056</td>
      <td>25718</td>
      <td>Subscriber</td>
      <td>1973.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2165</td>
      <td>2017-06-01 00:00:33</td>
      <td>2017-06-01 00:36:38</td>
      <td>360</td>
      <td>William St &amp; Pine St</td>
      <td>40.707179</td>
      <td>-74.008873</td>
      <td>474</td>
      <td>5 Ave &amp; E 29 St</td>
      <td>40.745168</td>
      <td>-73.986831</td>
      <td>18691</td>
      <td>Subscriber</td>
      <td>1985.0</td>
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
      <td>1397</td>
      <td>2017-06-01 00:00:02</td>
      <td>2017-06-01 00:23:19</td>
      <td>515</td>
      <td>W 43 St &amp; 10 Ave</td>
      <td>40.760094</td>
      <td>-73.994618</td>
      <td>3285</td>
      <td>W 87 St  &amp; Amsterdam Ave</td>
      <td>40.788390</td>
      <td>-73.974700</td>
      <td>26642</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1103</td>
      <td>2017-06-01 00:00:13</td>
      <td>2017-06-01 00:18:37</td>
      <td>488</td>
      <td>W 39 St &amp; 9 Ave</td>
      <td>40.756458</td>
      <td>-73.993722</td>
      <td>297</td>
      <td>E 15 St &amp; 3 Ave</td>
      <td>40.734232</td>
      <td>-73.986923</td>
      <td>25656</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1810</td>
      <td>2017-06-01 00:00:20</td>
      <td>2017-06-01 00:30:31</td>
      <td>461</td>
      <td>E 20 St &amp; 2 Ave</td>
      <td>40.735877</td>
      <td>-73.982050</td>
      <td>465</td>
      <td>Broadway &amp; W 41 St</td>
      <td>40.755136</td>
      <td>-73.986580</td>
      <td>21023</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1760</td>
      <td>2017-06-01 00:00:24</td>
      <td>2017-06-01 00:29:45</td>
      <td>2009</td>
      <td>Catherine St &amp; Monroe St</td>
      <td>40.711174</td>
      <td>-73.996826</td>
      <td>527</td>
      <td>E 33 St &amp; 2 Ave</td>
      <td>40.744023</td>
      <td>-73.976056</td>
      <td>25718</td>
      <td>Subscriber</td>
      <td>1973.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2165</td>
      <td>2017-06-01 00:00:33</td>
      <td>2017-06-01 00:36:38</td>
      <td>360</td>
      <td>William St &amp; Pine St</td>
      <td>40.707179</td>
      <td>-74.008873</td>
      <td>474</td>
      <td>5 Ave &amp; E 29 St</td>
      <td>40.745168</td>
      <td>-73.986831</td>
      <td>18691</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df7 = pd.read_csv('201707-citibike-tripdata.csv')
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
      <td>364</td>
      <td>2017-07-01 00:00:00</td>
      <td>2017-07-01 00:06:05</td>
      <td>539</td>
      <td>Metropolitan Ave &amp; Bedford Ave</td>
      <td>40.715348</td>
      <td>-73.960241</td>
      <td>3107</td>
      <td>Bedford Ave &amp; Nassau Ave</td>
      <td>40.723117</td>
      <td>-73.952123</td>
      <td>14744</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2142</td>
      <td>2017-07-01 00:00:03</td>
      <td>2017-07-01 00:35:46</td>
      <td>293</td>
      <td>Lafayette St &amp; E 8 St</td>
      <td>40.730207</td>
      <td>-73.991026</td>
      <td>3425</td>
      <td>2 Ave  &amp; E 104 St</td>
      <td>40.789210</td>
      <td>-73.943708</td>
      <td>19587</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>328</td>
      <td>2017-07-01 00:00:08</td>
      <td>2017-07-01 00:05:37</td>
      <td>3242</td>
      <td>Schermerhorn St &amp; Court St</td>
      <td>40.691029</td>
      <td>-73.991834</td>
      <td>3397</td>
      <td>Court St &amp; Nelson St</td>
      <td>40.676395</td>
      <td>-73.998699</td>
      <td>27937</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2530</td>
      <td>2017-07-01 00:00:11</td>
      <td>2017-07-01 00:42:22</td>
      <td>2002</td>
      <td>Wythe Ave &amp; Metropolitan Ave</td>
      <td>40.716887</td>
      <td>-73.963198</td>
      <td>398</td>
      <td>Atlantic Ave &amp; Furman St</td>
      <td>40.691652</td>
      <td>-73.999979</td>
      <td>26066</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2534</td>
      <td>2017-07-01 00:00:15</td>
      <td>2017-07-01 00:42:29</td>
      <td>2002</td>
      <td>Wythe Ave &amp; Metropolitan Ave</td>
      <td>40.716887</td>
      <td>-73.963198</td>
      <td>398</td>
      <td>Atlantic Ave &amp; Furman St</td>
      <td>40.691652</td>
      <td>-73.999979</td>
      <td>29408</td>
      <td>Subscriber</td>
      <td>1982.0</td>
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
      <td>364</td>
      <td>2017-07-01 00:00:00</td>
      <td>2017-07-01 00:06:05</td>
      <td>539</td>
      <td>Metropolitan Ave &amp; Bedford Ave</td>
      <td>40.715348</td>
      <td>-73.960241</td>
      <td>3107</td>
      <td>Bedford Ave &amp; Nassau Ave</td>
      <td>40.723117</td>
      <td>-73.952123</td>
      <td>14744</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2142</td>
      <td>2017-07-01 00:00:03</td>
      <td>2017-07-01 00:35:46</td>
      <td>293</td>
      <td>Lafayette St &amp; E 8 St</td>
      <td>40.730207</td>
      <td>-73.991026</td>
      <td>3425</td>
      <td>2 Ave  &amp; E 104 St</td>
      <td>40.789210</td>
      <td>-73.943708</td>
      <td>19587</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>328</td>
      <td>2017-07-01 00:00:08</td>
      <td>2017-07-01 00:05:37</td>
      <td>3242</td>
      <td>Schermerhorn St &amp; Court St</td>
      <td>40.691029</td>
      <td>-73.991834</td>
      <td>3397</td>
      <td>Court St &amp; Nelson St</td>
      <td>40.676395</td>
      <td>-73.998699</td>
      <td>27937</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2530</td>
      <td>2017-07-01 00:00:11</td>
      <td>2017-07-01 00:42:22</td>
      <td>2002</td>
      <td>Wythe Ave &amp; Metropolitan Ave</td>
      <td>40.716887</td>
      <td>-73.963198</td>
      <td>398</td>
      <td>Atlantic Ave &amp; Furman St</td>
      <td>40.691652</td>
      <td>-73.999979</td>
      <td>26066</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2534</td>
      <td>2017-07-01 00:00:15</td>
      <td>2017-07-01 00:42:29</td>
      <td>2002</td>
      <td>Wythe Ave &amp; Metropolitan Ave</td>
      <td>40.716887</td>
      <td>-73.963198</td>
      <td>398</td>
      <td>Atlantic Ave &amp; Furman St</td>
      <td>40.691652</td>
      <td>-73.999979</td>
      <td>29408</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
df8 = pd.read_csv('201708-citibike-tripdata.csv')
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
      <td>2110</td>
      <td>2017-08-01 00:00:00</td>
      <td>2017-08-01 00:35:11</td>
      <td>470</td>
      <td>W 20 St &amp; 8 Ave</td>
      <td>40.743453</td>
      <td>-74.000040</td>
      <td>3289</td>
      <td>W 90 St &amp; Amsterdam Ave</td>
      <td>40.790179</td>
      <td>-73.972889</td>
      <td>20954</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>160</td>
      <td>2017-08-01 00:00:10</td>
      <td>2017-08-01 00:02:51</td>
      <td>348</td>
      <td>W Broadway &amp; Spring St</td>
      <td>40.724910</td>
      <td>-74.001547</td>
      <td>151</td>
      <td>Cleveland Pl &amp; Spring St</td>
      <td>40.722104</td>
      <td>-73.997249</td>
      <td>15164</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1644</td>
      <td>2017-08-01 00:00:17</td>
      <td>2017-08-01 00:27:41</td>
      <td>3165</td>
      <td>Central Park West &amp; W 72 St</td>
      <td>40.775794</td>
      <td>-73.976206</td>
      <td>3320</td>
      <td>Central Park West &amp; W 100 St</td>
      <td>40.793393</td>
      <td>-73.963556</td>
      <td>17540</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>323</td>
      <td>2017-08-01 00:00:27</td>
      <td>2017-08-01 00:05:51</td>
      <td>389</td>
      <td>Broadway &amp; Berry St</td>
      <td>40.710446</td>
      <td>-73.965251</td>
      <td>3073</td>
      <td>Division Ave &amp; Hooper St</td>
      <td>40.706913</td>
      <td>-73.954417</td>
      <td>18705</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>109</td>
      <td>2017-08-01 00:00:41</td>
      <td>2017-08-01 00:02:31</td>
      <td>3145</td>
      <td>E 84 St &amp; Park Ave</td>
      <td>40.778627</td>
      <td>-73.957721</td>
      <td>3147</td>
      <td>E 85 St &amp; 3 Ave</td>
      <td>40.778012</td>
      <td>-73.954071</td>
      <td>27975</td>
      <td>Subscriber</td>
      <td>1983.0</td>
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
      <td>2110</td>
      <td>2017-08-01 00:00:00</td>
      <td>2017-08-01 00:35:11</td>
      <td>470</td>
      <td>W 20 St &amp; 8 Ave</td>
      <td>40.743453</td>
      <td>-74.000040</td>
      <td>3289</td>
      <td>W 90 St &amp; Amsterdam Ave</td>
      <td>40.790179</td>
      <td>-73.972889</td>
      <td>20954</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>160</td>
      <td>2017-08-01 00:00:10</td>
      <td>2017-08-01 00:02:51</td>
      <td>348</td>
      <td>W Broadway &amp; Spring St</td>
      <td>40.724910</td>
      <td>-74.001547</td>
      <td>151</td>
      <td>Cleveland Pl &amp; Spring St</td>
      <td>40.722104</td>
      <td>-73.997249</td>
      <td>15164</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1644</td>
      <td>2017-08-01 00:00:17</td>
      <td>2017-08-01 00:27:41</td>
      <td>3165</td>
      <td>Central Park West &amp; W 72 St</td>
      <td>40.775794</td>
      <td>-73.976206</td>
      <td>3320</td>
      <td>Central Park West &amp; W 100 St</td>
      <td>40.793393</td>
      <td>-73.963556</td>
      <td>17540</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>323</td>
      <td>2017-08-01 00:00:27</td>
      <td>2017-08-01 00:05:51</td>
      <td>389</td>
      <td>Broadway &amp; Berry St</td>
      <td>40.710446</td>
      <td>-73.965251</td>
      <td>3073</td>
      <td>Division Ave &amp; Hooper St</td>
      <td>40.706913</td>
      <td>-73.954417</td>
      <td>18705</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>109</td>
      <td>2017-08-01 00:00:41</td>
      <td>2017-08-01 00:02:31</td>
      <td>3145</td>
      <td>E 84 St &amp; Park Ave</td>
      <td>40.778627</td>
      <td>-73.957721</td>
      <td>3147</td>
      <td>E 85 St &amp; 3 Ave</td>
      <td>40.778012</td>
      <td>-73.954071</td>
      <td>27975</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df9 = pd.read_csv('201709-citibike-tripdata.csv')
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
      <td>362</td>
      <td>2017-09-01 00:00:17</td>
      <td>2017-09-01 00:06:19</td>
      <td>3331</td>
      <td>Riverside Dr &amp; W 104 St</td>
      <td>40.801343</td>
      <td>-73.971146</td>
      <td>3328</td>
      <td>W 100 St &amp; Manhattan Ave</td>
      <td>40.795000</td>
      <td>-73.964500</td>
      <td>14530</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>188</td>
      <td>2017-09-01 00:00:21</td>
      <td>2017-09-01 00:03:30</td>
      <td>3101</td>
      <td>N 12 St &amp; Bedford Ave</td>
      <td>40.720798</td>
      <td>-73.954847</td>
      <td>3100</td>
      <td>Nassau Ave &amp; Newell St</td>
      <td>40.724813</td>
      <td>-73.947526</td>
      <td>15475</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>305</td>
      <td>2017-09-01 00:00:25</td>
      <td>2017-09-01 00:05:30</td>
      <td>3140</td>
      <td>1 Ave &amp; E 78 St</td>
      <td>40.771404</td>
      <td>-73.953517</td>
      <td>3141</td>
      <td>1 Ave &amp; E 68 St</td>
      <td>40.765005</td>
      <td>-73.958185</td>
      <td>30346</td>
      <td>Subscriber</td>
      <td>1969.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>223</td>
      <td>2017-09-01 00:00:52</td>
      <td>2017-09-01 00:04:36</td>
      <td>236</td>
      <td>St Marks Pl &amp; 2 Ave</td>
      <td>40.728419</td>
      <td>-73.987140</td>
      <td>473</td>
      <td>Rivington St &amp; Chrystie St</td>
      <td>40.721101</td>
      <td>-73.991925</td>
      <td>28056</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>758</td>
      <td>2017-09-01 00:01:01</td>
      <td>2017-09-01 00:13:40</td>
      <td>3427</td>
      <td>Lafayette St &amp; Jersey St</td>
      <td>40.724305</td>
      <td>-73.996010</td>
      <td>3431</td>
      <td>E 35 St &amp; 3 Ave</td>
      <td>40.746524</td>
      <td>-73.977885</td>
      <td>25413</td>
      <td>Subscriber</td>
      <td>1987.0</td>
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
      <td>362</td>
      <td>2017-09-01 00:00:17</td>
      <td>2017-09-01 00:06:19</td>
      <td>3331</td>
      <td>Riverside Dr &amp; W 104 St</td>
      <td>40.801343</td>
      <td>-73.971146</td>
      <td>3328</td>
      <td>W 100 St &amp; Manhattan Ave</td>
      <td>40.795000</td>
      <td>-73.964500</td>
      <td>14530</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>188</td>
      <td>2017-09-01 00:00:21</td>
      <td>2017-09-01 00:03:30</td>
      <td>3101</td>
      <td>N 12 St &amp; Bedford Ave</td>
      <td>40.720798</td>
      <td>-73.954847</td>
      <td>3100</td>
      <td>Nassau Ave &amp; Newell St</td>
      <td>40.724813</td>
      <td>-73.947526</td>
      <td>15475</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>305</td>
      <td>2017-09-01 00:00:25</td>
      <td>2017-09-01 00:05:30</td>
      <td>3140</td>
      <td>1 Ave &amp; E 78 St</td>
      <td>40.771404</td>
      <td>-73.953517</td>
      <td>3141</td>
      <td>1 Ave &amp; E 68 St</td>
      <td>40.765005</td>
      <td>-73.958185</td>
      <td>30346</td>
      <td>Subscriber</td>
      <td>1969.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>223</td>
      <td>2017-09-01 00:00:52</td>
      <td>2017-09-01 00:04:36</td>
      <td>236</td>
      <td>St Marks Pl &amp; 2 Ave</td>
      <td>40.728419</td>
      <td>-73.987140</td>
      <td>473</td>
      <td>Rivington St &amp; Chrystie St</td>
      <td>40.721101</td>
      <td>-73.991925</td>
      <td>28056</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>758</td>
      <td>2017-09-01 00:01:01</td>
      <td>2017-09-01 00:13:40</td>
      <td>3427</td>
      <td>Lafayette St &amp; Jersey St</td>
      <td>40.724305</td>
      <td>-73.996010</td>
      <td>3431</td>
      <td>E 35 St &amp; 3 Ave</td>
      <td>40.746524</td>
      <td>-73.977885</td>
      <td>25413</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df10 = pd.read_csv('201710-citibike-tripdata.csv')
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
      <td>457</td>
      <td>2017-10-01 00:00:00</td>
      <td>2017-10-01 00:07:38</td>
      <td>479</td>
      <td>9 Ave &amp; W 45 St</td>
      <td>40.760193</td>
      <td>-73.991255</td>
      <td>478</td>
      <td>11 Ave &amp; W 41 St</td>
      <td>40.760301</td>
      <td>-73.998842</td>
      <td>30951</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>6462</td>
      <td>2017-10-01 00:00:20</td>
      <td>2017-10-01 01:48:03</td>
      <td>279</td>
      <td>Peck Slip &amp; Front St</td>
      <td>40.707873</td>
      <td>-74.001670</td>
      <td>307</td>
      <td>Canal St &amp; Rutgers St</td>
      <td>40.714275</td>
      <td>-73.989900</td>
      <td>14809</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>761</td>
      <td>2017-10-01 00:00:27</td>
      <td>2017-10-01 00:13:09</td>
      <td>504</td>
      <td>1 Ave &amp; E 16 St</td>
      <td>40.732219</td>
      <td>-73.981656</td>
      <td>350</td>
      <td>Clinton St &amp; Grand St</td>
      <td>40.715595</td>
      <td>-73.987030</td>
      <td>28713</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1193</td>
      <td>2017-10-01 00:00:29</td>
      <td>2017-10-01 00:20:22</td>
      <td>3236</td>
      <td>W 42 St &amp; Dyer Ave</td>
      <td>40.758985</td>
      <td>-73.993800</td>
      <td>3233</td>
      <td>E 48 St &amp; 5 Ave</td>
      <td>40.757246</td>
      <td>-73.978059</td>
      <td>16008</td>
      <td>Customer</td>
      <td>1992.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2772</td>
      <td>2017-10-01 00:00:32</td>
      <td>2017-10-01 00:46:44</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>469</td>
      <td>Broadway &amp; W 53 St</td>
      <td>40.763441</td>
      <td>-73.982681</td>
      <td>14556</td>
      <td>Customer</td>
      <td>NaN</td>
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
      <td>457</td>
      <td>2017-10-01 00:00:00</td>
      <td>2017-10-01 00:07:38</td>
      <td>479</td>
      <td>9 Ave &amp; W 45 St</td>
      <td>40.760193</td>
      <td>-73.991255</td>
      <td>478</td>
      <td>11 Ave &amp; W 41 St</td>
      <td>40.760301</td>
      <td>-73.998842</td>
      <td>30951</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>6462</td>
      <td>2017-10-01 00:00:20</td>
      <td>2017-10-01 01:48:03</td>
      <td>279</td>
      <td>Peck Slip &amp; Front St</td>
      <td>40.707873</td>
      <td>-74.001670</td>
      <td>307</td>
      <td>Canal St &amp; Rutgers St</td>
      <td>40.714275</td>
      <td>-73.989900</td>
      <td>14809</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>761</td>
      <td>2017-10-01 00:00:27</td>
      <td>2017-10-01 00:13:09</td>
      <td>504</td>
      <td>1 Ave &amp; E 16 St</td>
      <td>40.732219</td>
      <td>-73.981656</td>
      <td>350</td>
      <td>Clinton St &amp; Grand St</td>
      <td>40.715595</td>
      <td>-73.987030</td>
      <td>28713</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1193</td>
      <td>2017-10-01 00:00:29</td>
      <td>2017-10-01 00:20:22</td>
      <td>3236</td>
      <td>W 42 St &amp; Dyer Ave</td>
      <td>40.758985</td>
      <td>-73.993800</td>
      <td>3233</td>
      <td>E 48 St &amp; 5 Ave</td>
      <td>40.757246</td>
      <td>-73.978059</td>
      <td>16008</td>
      <td>Customer</td>
      <td>1992.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2772</td>
      <td>2017-10-01 00:00:32</td>
      <td>2017-10-01 00:46:44</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>469</td>
      <td>Broadway &amp; W 53 St</td>
      <td>40.763441</td>
      <td>-73.982681</td>
      <td>14556</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df11 = pd.read_csv('201711-citibike-tripdata.csv')
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
      <td>297</td>
      <td>2017-11-01 00:00:01</td>
      <td>2017-11-01 00:04:59</td>
      <td>418</td>
      <td>Front St &amp; Gold St</td>
      <td>40.702240</td>
      <td>-73.982578</td>
      <td>414</td>
      <td>Pearl St &amp; Anchorage Pl</td>
      <td>40.702819</td>
      <td>-73.987658</td>
      <td>24753</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>269</td>
      <td>2017-11-01 00:00:01</td>
      <td>2017-11-01 00:04:30</td>
      <td>3556</td>
      <td>24 St &amp; 41 Ave</td>
      <td>40.752709</td>
      <td>-73.939740</td>
      <td>3126</td>
      <td>44 Dr &amp; Jackson Ave</td>
      <td>40.747182</td>
      <td>-73.943264</td>
      <td>19063</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>285</td>
      <td>2017-11-01 00:00:04</td>
      <td>2017-11-01 00:04:50</td>
      <td>275</td>
      <td>Washington Ave &amp; Greene Ave</td>
      <td>40.686501</td>
      <td>-73.965633</td>
      <td>3429</td>
      <td>Hanson Pl &amp; Ashland Pl</td>
      <td>40.685068</td>
      <td>-73.977908</td>
      <td>29131</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>478</td>
      <td>2017-11-01 00:00:13</td>
      <td>2017-11-01 00:08:11</td>
      <td>3545</td>
      <td>Broadway &amp; W 122 St</td>
      <td>40.812056</td>
      <td>-73.961255</td>
      <td>3316</td>
      <td>W 104 St &amp; Amsterdam Ave</td>
      <td>40.798994</td>
      <td>-73.966217</td>
      <td>32841</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>574</td>
      <td>2017-11-01 00:00:20</td>
      <td>2017-11-01 00:09:54</td>
      <td>458</td>
      <td>11 Ave &amp; W 27 St</td>
      <td>40.751396</td>
      <td>-74.005226</td>
      <td>434</td>
      <td>9 Ave &amp; W 18 St</td>
      <td>40.743174</td>
      <td>-74.003664</td>
      <td>17697</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>2</td>
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
      <td>297</td>
      <td>2017-11-01 00:00:01</td>
      <td>2017-11-01 00:04:59</td>
      <td>418</td>
      <td>Front St &amp; Gold St</td>
      <td>40.702240</td>
      <td>-73.982578</td>
      <td>414</td>
      <td>Pearl St &amp; Anchorage Pl</td>
      <td>40.702819</td>
      <td>-73.987658</td>
      <td>24753</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>269</td>
      <td>2017-11-01 00:00:01</td>
      <td>2017-11-01 00:04:30</td>
      <td>3556</td>
      <td>24 St &amp; 41 Ave</td>
      <td>40.752709</td>
      <td>-73.939740</td>
      <td>3126</td>
      <td>44 Dr &amp; Jackson Ave</td>
      <td>40.747182</td>
      <td>-73.943264</td>
      <td>19063</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>285</td>
      <td>2017-11-01 00:00:04</td>
      <td>2017-11-01 00:04:50</td>
      <td>275</td>
      <td>Washington Ave &amp; Greene Ave</td>
      <td>40.686501</td>
      <td>-73.965633</td>
      <td>3429</td>
      <td>Hanson Pl &amp; Ashland Pl</td>
      <td>40.685068</td>
      <td>-73.977908</td>
      <td>29131</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>478</td>
      <td>2017-11-01 00:00:13</td>
      <td>2017-11-01 00:08:11</td>
      <td>3545</td>
      <td>Broadway &amp; W 122 St</td>
      <td>40.812056</td>
      <td>-73.961255</td>
      <td>3316</td>
      <td>W 104 St &amp; Amsterdam Ave</td>
      <td>40.798994</td>
      <td>-73.966217</td>
      <td>32841</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>574</td>
      <td>2017-11-01 00:00:20</td>
      <td>2017-11-01 00:09:54</td>
      <td>458</td>
      <td>11 Ave &amp; W 27 St</td>
      <td>40.751396</td>
      <td>-74.005226</td>
      <td>434</td>
      <td>9 Ave &amp; W 18 St</td>
      <td>40.743174</td>
      <td>-74.003664</td>
      <td>17697</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
df12 = pd.read_csv('201712-citibike-tripdata.csv')
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
      <td>256</td>
      <td>2017-12-01 00:00:00</td>
      <td>2017-12-01 00:04:17</td>
      <td>324</td>
      <td>DeKalb Ave &amp; Hudson Ave</td>
      <td>40.689888</td>
      <td>-73.981013</td>
      <td>262</td>
      <td>Washington Park</td>
      <td>40.691782</td>
      <td>-73.973730</td>
      <td>18858</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>325</td>
      <td>2017-12-01 00:00:17</td>
      <td>2017-12-01 00:05:43</td>
      <td>470</td>
      <td>W 20 St &amp; 8 Ave</td>
      <td>40.743453</td>
      <td>-74.000040</td>
      <td>490</td>
      <td>8 Ave &amp; W 33 St</td>
      <td>40.751551</td>
      <td>-73.993934</td>
      <td>19306</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>967</td>
      <td>2017-12-01 00:00:19</td>
      <td>2017-12-01 00:16:26</td>
      <td>347</td>
      <td>Greenwich St &amp; W Houston St</td>
      <td>40.728846</td>
      <td>-74.008591</td>
      <td>504</td>
      <td>1 Ave &amp; E 16 St</td>
      <td>40.732219</td>
      <td>-73.981656</td>
      <td>28250</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>125</td>
      <td>2017-12-01 00:00:20</td>
      <td>2017-12-01 00:02:26</td>
      <td>3077</td>
      <td>Stagg St &amp; Union Ave</td>
      <td>40.708771</td>
      <td>-73.950953</td>
      <td>3454</td>
      <td>Leonard St &amp; Maujer St</td>
      <td>40.710369</td>
      <td>-73.947060</td>
      <td>25834</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>451</td>
      <td>2017-12-01 00:00:28</td>
      <td>2017-12-01 00:08:00</td>
      <td>368</td>
      <td>Carmine St &amp; 6 Ave</td>
      <td>40.730386</td>
      <td>-74.002150</td>
      <td>326</td>
      <td>E 11 St &amp; 1 Ave</td>
      <td>40.729538</td>
      <td>-73.984267</td>
      <td>14769</td>
      <td>Subscriber</td>
      <td>1986.0</td>
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
      <td>256</td>
      <td>2017-12-01 00:00:00</td>
      <td>2017-12-01 00:04:17</td>
      <td>324</td>
      <td>DeKalb Ave &amp; Hudson Ave</td>
      <td>40.689888</td>
      <td>-73.981013</td>
      <td>262</td>
      <td>Washington Park</td>
      <td>40.691782</td>
      <td>-73.973730</td>
      <td>18858</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>325</td>
      <td>2017-12-01 00:00:17</td>
      <td>2017-12-01 00:05:43</td>
      <td>470</td>
      <td>W 20 St &amp; 8 Ave</td>
      <td>40.743453</td>
      <td>-74.000040</td>
      <td>490</td>
      <td>8 Ave &amp; W 33 St</td>
      <td>40.751551</td>
      <td>-73.993934</td>
      <td>19306</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>967</td>
      <td>2017-12-01 00:00:19</td>
      <td>2017-12-01 00:16:26</td>
      <td>347</td>
      <td>Greenwich St &amp; W Houston St</td>
      <td>40.728846</td>
      <td>-74.008591</td>
      <td>504</td>
      <td>1 Ave &amp; E 16 St</td>
      <td>40.732219</td>
      <td>-73.981656</td>
      <td>28250</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>125</td>
      <td>2017-12-01 00:00:20</td>
      <td>2017-12-01 00:02:26</td>
      <td>3077</td>
      <td>Stagg St &amp; Union Ave</td>
      <td>40.708771</td>
      <td>-73.950953</td>
      <td>3454</td>
      <td>Leonard St &amp; Maujer St</td>
      <td>40.710369</td>
      <td>-73.947060</td>
      <td>25834</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>451</td>
      <td>2017-12-01 00:00:28</td>
      <td>2017-12-01 00:08:00</td>
      <td>368</td>
      <td>Carmine St &amp; 6 Ave</td>
      <td>40.730386</td>
      <td>-74.002150</td>
      <td>326</td>
      <td>E 11 St &amp; 1 Ave</td>
      <td>40.729538</td>
      <td>-73.984267</td>
      <td>14769</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
citibike_2017 = pd.concat([df1, df2, df3, df4, df5, df6, df7, df8, df9, df10, df11, df12])
citibike_2017
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
      <td>148</td>
      <td>2017-01-01 00:21:32</td>
      <td>2017-01-01 00:24:01</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>24575</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1283</td>
      <td>2017-01-01 00:24:35</td>
      <td>2017-01-01 00:45:58</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3198</td>
      <td>Heights Elevator</td>
      <td>40.748716</td>
      <td>-74.040443</td>
      <td>24723</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>372</td>
      <td>2017-01-01 00:38:19</td>
      <td>2017-01-01 00:44:31</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>24620</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1513</td>
      <td>2017-01-01 00:38:37</td>
      <td>2017-01-01 01:03:50</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3271</td>
      <td>Danforth Light Rail</td>
      <td>40.692640</td>
      <td>-74.088012</td>
      <td>24668</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>639</td>
      <td>2017-01-01 01:47:52</td>
      <td>2017-01-01 01:58:31</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>26167</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>5</th>
      <td>258</td>
      <td>2017-01-01 01:56:29</td>
      <td>2017-01-01 02:00:48</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>24604</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>6</th>
      <td>663</td>
      <td>2017-01-01 02:12:34</td>
      <td>2017-01-01 02:23:38</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>3206</td>
      <td>Hilltop</td>
      <td>40.731169</td>
      <td>-74.057574</td>
      <td>24641</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>7</th>
      <td>567</td>
      <td>2017-01-01 02:15:52</td>
      <td>2017-01-01 02:25:20</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24513</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8</th>
      <td>551</td>
      <td>2017-01-01 02:16:03</td>
      <td>2017-01-01 02:25:15</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24463</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>9</th>
      <td>573</td>
      <td>2017-01-01 02:22:17</td>
      <td>2017-01-01 02:31:50</td>
      <td>3212</td>
      <td>Christ Hospital</td>
      <td>40.734786</td>
      <td>-74.050444</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>40.723659</td>
      <td>-74.064194</td>
      <td>24486</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>10</th>
      <td>535</td>
      <td>2017-01-01 02:22:59</td>
      <td>2017-01-01 02:31:55</td>
      <td>3212</td>
      <td>Christ Hospital</td>
      <td>40.734786</td>
      <td>-74.050444</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>40.723659</td>
      <td>-74.064194</td>
      <td>24520</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>11</th>
      <td>224</td>
      <td>2017-01-01 02:23:53</td>
      <td>2017-01-01 02:27:37</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>24512</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>12</th>
      <td>1699</td>
      <td>2017-01-01 02:33:12</td>
      <td>2017-01-01 03:01:31</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>24513</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>13</th>
      <td>350</td>
      <td>2017-01-01 02:37:31</td>
      <td>2017-01-01 02:43:22</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>24409</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>14</th>
      <td>346</td>
      <td>2017-01-01 03:09:09</td>
      <td>2017-01-01 03:14:56</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24513</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15</th>
      <td>367</td>
      <td>2017-01-01 03:16:35</td>
      <td>2017-01-01 03:22:42</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>24699</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>16</th>
      <td>148</td>
      <td>2017-01-01 03:24:02</td>
      <td>2017-01-01 03:26:30</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24513</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>17</th>
      <td>204</td>
      <td>2017-01-01 03:52:29</td>
      <td>2017-01-01 03:55:53</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>24442</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>18</th>
      <td>33726</td>
      <td>2017-01-01 04:35:14</td>
      <td>2017-01-01 13:57:20</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>26281</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>19</th>
      <td>591</td>
      <td>2017-01-01 04:35:36</td>
      <td>2017-01-01 04:45:27</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>26194</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>20</th>
      <td>454</td>
      <td>2017-01-01 05:17:42</td>
      <td>2017-01-01 05:25:16</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>24555</td>
      <td>Subscriber</td>
      <td>1972.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>21</th>
      <td>217</td>
      <td>2017-01-01 05:25:35</td>
      <td>2017-01-01 05:29:13</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>40.723659</td>
      <td>-74.064194</td>
      <td>24408</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>22</th>
      <td>107</td>
      <td>2017-01-01 06:29:15</td>
      <td>2017-01-01 06:31:03</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>24681</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>23</th>
      <td>453</td>
      <td>2017-01-01 07:08:01</td>
      <td>2017-01-01 07:15:34</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>26163</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>24</th>
      <td>447</td>
      <td>2017-01-01 07:12:53</td>
      <td>2017-01-01 07:20:20</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>26431</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>25</th>
      <td>730</td>
      <td>2017-01-01 07:38:57</td>
      <td>2017-01-01 07:51:08</td>
      <td>3281</td>
      <td>Leonard Gordon Park</td>
      <td>40.745910</td>
      <td>-74.057271</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>24495</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>26</th>
      <td>435</td>
      <td>2017-01-01 07:55:19</td>
      <td>2017-01-01 08:02:35</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24390</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>27</th>
      <td>458</td>
      <td>2017-01-01 08:16:36</td>
      <td>2017-01-01 08:24:15</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3280</td>
      <td>Astor Place</td>
      <td>40.719282</td>
      <td>-74.071262</td>
      <td>26255</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>28</th>
      <td>258</td>
      <td>2017-01-01 08:24:36</td>
      <td>2017-01-01 08:28:54</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>26308</td>
      <td>Subscriber</td>
      <td>1977.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>29</th>
      <td>537</td>
      <td>2017-01-01 08:56:28</td>
      <td>2017-01-01 09:05:26</td>
      <td>3196</td>
      <td>Riverview Park</td>
      <td>40.744319</td>
      <td>-74.043991</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>26234</td>
      <td>Subscriber</td>
      <td>1983.0</td>
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
      <th>889937</th>
      <td>1287</td>
      <td>2017-12-31 23:40:35</td>
      <td>2018-01-01 00:02:02</td>
      <td>531</td>
      <td>Forsyth St &amp; Broome St</td>
      <td>40.718939</td>
      <td>-73.992663</td>
      <td>498</td>
      <td>Broadway &amp; W 32 St</td>
      <td>40.748549</td>
      <td>-73.988084</td>
      <td>19064</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889938</th>
      <td>1279</td>
      <td>2017-12-31 23:40:35</td>
      <td>2018-01-01 00:01:55</td>
      <td>531</td>
      <td>Forsyth St &amp; Broome St</td>
      <td>40.718939</td>
      <td>-73.992663</td>
      <td>498</td>
      <td>Broadway &amp; W 32 St</td>
      <td>40.748549</td>
      <td>-73.988084</td>
      <td>32939</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>889939</th>
      <td>482</td>
      <td>2017-12-31 23:40:38</td>
      <td>2017-12-31 23:48:41</td>
      <td>379</td>
      <td>W 31 St &amp; 7 Ave</td>
      <td>40.749156</td>
      <td>-73.991600</td>
      <td>507</td>
      <td>E 25 St &amp; 2 Ave</td>
      <td>40.739126</td>
      <td>-73.979738</td>
      <td>16313</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889940</th>
      <td>1303</td>
      <td>2017-12-31 23:40:49</td>
      <td>2018-01-01 00:02:33</td>
      <td>531</td>
      <td>Forsyth St &amp; Broome St</td>
      <td>40.718939</td>
      <td>-73.992663</td>
      <td>498</td>
      <td>Broadway &amp; W 32 St</td>
      <td>40.748549</td>
      <td>-73.988084</td>
      <td>28788</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889941</th>
      <td>322</td>
      <td>2017-12-31 23:41:35</td>
      <td>2017-12-31 23:46:58</td>
      <td>499</td>
      <td>Broadway &amp; W 60 St</td>
      <td>40.769155</td>
      <td>-73.981918</td>
      <td>3165</td>
      <td>Central Park West &amp; W 72 St</td>
      <td>40.775794</td>
      <td>-73.976206</td>
      <td>19080</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889942</th>
      <td>1461</td>
      <td>2017-12-31 23:42:45</td>
      <td>2018-01-01 00:07:07</td>
      <td>3135</td>
      <td>E 75 St &amp; 3 Ave</td>
      <td>40.771129</td>
      <td>-73.957723</td>
      <td>3135</td>
      <td>E 75 St &amp; 3 Ave</td>
      <td>40.771129</td>
      <td>-73.957723</td>
      <td>33034</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889943</th>
      <td>257</td>
      <td>2017-12-31 23:43:23</td>
      <td>2017-12-31 23:47:40</td>
      <td>349</td>
      <td>Rivington St &amp; Ridge St</td>
      <td>40.718502</td>
      <td>-73.983299</td>
      <td>401</td>
      <td>Allen St &amp; Rivington St</td>
      <td>40.720196</td>
      <td>-73.989978</td>
      <td>30823</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889944</th>
      <td>347</td>
      <td>2017-12-31 23:43:57</td>
      <td>2017-12-31 23:49:44</td>
      <td>3637</td>
      <td>Fulton St &amp; Waverly Ave</td>
      <td>40.683239</td>
      <td>-73.965996</td>
      <td>120</td>
      <td>Lexington Ave &amp; Classon Ave</td>
      <td>40.686768</td>
      <td>-73.959282</td>
      <td>25776</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889945</th>
      <td>87</td>
      <td>2017-12-31 23:44:23</td>
      <td>2017-12-31 23:45:50</td>
      <td>515</td>
      <td>W 43 St &amp; 10 Ave</td>
      <td>40.760094</td>
      <td>-73.994618</td>
      <td>3236</td>
      <td>W 42 St &amp; Dyer Ave</td>
      <td>40.758985</td>
      <td>-73.993800</td>
      <td>29177</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889946</th>
      <td>177</td>
      <td>2017-12-31 23:45:29</td>
      <td>2017-12-31 23:48:26</td>
      <td>3429</td>
      <td>Hanson Pl &amp; Ashland Pl</td>
      <td>40.685068</td>
      <td>-73.977908</td>
      <td>3419</td>
      <td>Douglass St &amp; 4 Ave</td>
      <td>40.679279</td>
      <td>-73.981540</td>
      <td>33045</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889947</th>
      <td>225</td>
      <td>2017-12-31 23:45:43</td>
      <td>2017-12-31 23:49:29</td>
      <td>3260</td>
      <td>Mercer St &amp; Bleecker St</td>
      <td>40.727064</td>
      <td>-73.996621</td>
      <td>403</td>
      <td>E 2 St &amp; 2 Ave</td>
      <td>40.725029</td>
      <td>-73.990697</td>
      <td>31102</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889948</th>
      <td>531</td>
      <td>2017-12-31 23:46:10</td>
      <td>2017-12-31 23:55:02</td>
      <td>423</td>
      <td>W 54 St &amp; 9 Ave</td>
      <td>40.765849</td>
      <td>-73.986905</td>
      <td>448</td>
      <td>W 37 St &amp; 10 Ave</td>
      <td>40.756604</td>
      <td>-73.997901</td>
      <td>19007</td>
      <td>Subscriber</td>
      <td>1955.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>889949</th>
      <td>184</td>
      <td>2017-12-31 23:46:15</td>
      <td>2017-12-31 23:49:20</td>
      <td>3431</td>
      <td>E 35 St &amp; 3 Ave</td>
      <td>40.746524</td>
      <td>-73.977885</td>
      <td>472</td>
      <td>E 32 St &amp; Park Ave</td>
      <td>40.745712</td>
      <td>-73.981948</td>
      <td>33182</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889950</th>
      <td>189</td>
      <td>2017-12-31 23:46:43</td>
      <td>2017-12-31 23:49:52</td>
      <td>504</td>
      <td>1 Ave &amp; E 16 St</td>
      <td>40.732219</td>
      <td>-73.981656</td>
      <td>487</td>
      <td>E 20 St &amp; FDR Drive</td>
      <td>40.733143</td>
      <td>-73.975739</td>
      <td>31315</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889951</th>
      <td>313</td>
      <td>2017-12-31 23:47:24</td>
      <td>2017-12-31 23:52:37</td>
      <td>513</td>
      <td>W 56 St &amp; 10 Ave</td>
      <td>40.768254</td>
      <td>-73.988639</td>
      <td>3236</td>
      <td>W 42 St &amp; Dyer Ave</td>
      <td>40.758985</td>
      <td>-73.993800</td>
      <td>26542</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889952</th>
      <td>788</td>
      <td>2017-12-31 23:47:55</td>
      <td>2018-01-01 00:01:04</td>
      <td>2008</td>
      <td>Little West St &amp; 1 Pl</td>
      <td>40.705693</td>
      <td>-74.016777</td>
      <td>249</td>
      <td>Harrison St &amp; Hudson St</td>
      <td>40.718710</td>
      <td>-74.009001</td>
      <td>30785</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889953</th>
      <td>263</td>
      <td>2017-12-31 23:48:35</td>
      <td>2017-12-31 23:52:58</td>
      <td>3086</td>
      <td>Graham Ave &amp; Conselyea St</td>
      <td>40.715143</td>
      <td>-73.944507</td>
      <td>3106</td>
      <td>Driggs Ave &amp; N Henry St</td>
      <td>40.723250</td>
      <td>-73.943080</td>
      <td>31022</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>889954</th>
      <td>487</td>
      <td>2017-12-31 23:48:39</td>
      <td>2017-12-31 23:56:47</td>
      <td>3077</td>
      <td>Stagg St &amp; Union Ave</td>
      <td>40.708771</td>
      <td>-73.950953</td>
      <td>389</td>
      <td>Broadway &amp; Berry St</td>
      <td>40.710446</td>
      <td>-73.965251</td>
      <td>25366</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889955</th>
      <td>1323</td>
      <td>2017-12-31 23:48:48</td>
      <td>2018-01-01 00:10:52</td>
      <td>236</td>
      <td>St Marks Pl &amp; 2 Ave</td>
      <td>40.728419</td>
      <td>-73.987140</td>
      <td>430</td>
      <td>York St &amp; Jay St</td>
      <td>40.701485</td>
      <td>-73.986569</td>
      <td>31643</td>
      <td>Subscriber</td>
      <td>1996.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889956</th>
      <td>952</td>
      <td>2017-12-31 23:49:16</td>
      <td>2018-01-01 00:05:08</td>
      <td>455</td>
      <td>1 Ave &amp; E 44 St</td>
      <td>40.750020</td>
      <td>-73.969053</td>
      <td>3238</td>
      <td>E 80 St &amp; 2 Ave</td>
      <td>40.773914</td>
      <td>-73.954395</td>
      <td>31959</td>
      <td>Subscriber</td>
      <td>1953.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889957</th>
      <td>411</td>
      <td>2017-12-31 23:49:34</td>
      <td>2017-12-31 23:56:25</td>
      <td>3288</td>
      <td>E 88 St &amp; 1 Ave</td>
      <td>40.778301</td>
      <td>-73.948813</td>
      <td>3292</td>
      <td>5 Ave &amp; E 93 St</td>
      <td>40.785785</td>
      <td>-73.957481</td>
      <td>26930</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889958</th>
      <td>433</td>
      <td>2017-12-31 23:49:36</td>
      <td>2017-12-31 23:56:50</td>
      <td>3288</td>
      <td>E 88 St &amp; 1 Ave</td>
      <td>40.778301</td>
      <td>-73.948813</td>
      <td>3292</td>
      <td>5 Ave &amp; E 93 St</td>
      <td>40.785785</td>
      <td>-73.957481</td>
      <td>31549</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889959</th>
      <td>606</td>
      <td>2017-12-31 23:50:04</td>
      <td>2018-01-01 00:00:11</td>
      <td>515</td>
      <td>W 43 St &amp; 10 Ave</td>
      <td>40.760094</td>
      <td>-73.994618</td>
      <td>494</td>
      <td>W 26 St &amp; 8 Ave</td>
      <td>40.747348</td>
      <td>-73.997236</td>
      <td>32812</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889960</th>
      <td>1088</td>
      <td>2017-12-31 23:50:08</td>
      <td>2018-01-01 00:08:16</td>
      <td>296</td>
      <td>Division St &amp; Bowery</td>
      <td>40.714131</td>
      <td>-73.997047</td>
      <td>174</td>
      <td>E 25 St &amp; 1 Ave</td>
      <td>40.738177</td>
      <td>-73.977387</td>
      <td>24875</td>
      <td>Subscriber</td>
      <td>1979.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>889961</th>
      <td>429</td>
      <td>2017-12-31 23:52:25</td>
      <td>2017-12-31 23:59:34</td>
      <td>447</td>
      <td>8 Ave &amp; W 52 St</td>
      <td>40.763707</td>
      <td>-73.985162</td>
      <td>3172</td>
      <td>W 74 St &amp; Columbus Ave</td>
      <td>40.778567</td>
      <td>-73.977550</td>
      <td>29712</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889962</th>
      <td>397</td>
      <td>2017-12-31 23:54:22</td>
      <td>2018-01-01 00:01:00</td>
      <td>3417</td>
      <td>Baltic St &amp; 5 Ave</td>
      <td>40.679577</td>
      <td>-73.978550</td>
      <td>3418</td>
      <td>Plaza St West &amp; Flatbush Ave</td>
      <td>40.675021</td>
      <td>-73.971115</td>
      <td>30841</td>
      <td>Subscriber</td>
      <td>1957.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>889963</th>
      <td>332</td>
      <td>2017-12-31 23:54:44</td>
      <td>2018-01-01 00:00:16</td>
      <td>3236</td>
      <td>W 42 St &amp; Dyer Ave</td>
      <td>40.758985</td>
      <td>-73.993800</td>
      <td>513</td>
      <td>W 56 St &amp; 10 Ave</td>
      <td>40.768254</td>
      <td>-73.988639</td>
      <td>30417</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889964</th>
      <td>565</td>
      <td>2017-12-31 23:56:07</td>
      <td>2018-01-01 00:05:33</td>
      <td>254</td>
      <td>W 11 St &amp; 6 Ave</td>
      <td>40.735324</td>
      <td>-73.998004</td>
      <td>411</td>
      <td>E 6 St &amp; Avenue D</td>
      <td>40.722281</td>
      <td>-73.976687</td>
      <td>16125</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>889965</th>
      <td>1659</td>
      <td>2017-12-31 23:57:16</td>
      <td>2018-01-01 00:24:56</td>
      <td>495</td>
      <td>W 47 St &amp; 10 Ave</td>
      <td>40.762699</td>
      <td>-73.993012</td>
      <td>3163</td>
      <td>Central Park West &amp; W 68 St</td>
      <td>40.773407</td>
      <td>-73.977825</td>
      <td>33328</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>889966</th>
      <td>1279</td>
      <td>2017-12-31 23:58:56</td>
      <td>2018-01-01 00:20:16</td>
      <td>3135</td>
      <td>E 75 St &amp; 3 Ave</td>
      <td>40.771129</td>
      <td>-73.957723</td>
      <td>3143</td>
      <td>5 Ave &amp; E 78 St</td>
      <td>40.776321</td>
      <td>-73.964274</td>
      <td>31023</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>15650907 rows × 15 columns</p>
</div>




```python
citibike_2017.to_csv('citibike_2017.csv', sep = ',') 
```


```python

```
