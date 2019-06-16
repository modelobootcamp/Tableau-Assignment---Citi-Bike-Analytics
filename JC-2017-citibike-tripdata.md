

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
df2 = pd.read_csv('JC-201702-citibike-tripdata.csv')
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
      <td>435</td>
      <td>2017-02-01 00:06:33</td>
      <td>2017-02-01 00:13:49</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>24493</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>779</td>
      <td>2017-02-01 01:02:21</td>
      <td>2017-02-01 01:15:21</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3189</td>
      <td>West Side Light Rail</td>
      <td>40.714402</td>
      <td>-74.088772</td>
      <td>26232</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>145</td>
      <td>2017-02-01 01:56:05</td>
      <td>2017-02-01 01:58:30</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>24511</td>
      <td>Subscriber</td>
      <td>1972.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>184</td>
      <td>2017-02-01 04:38:42</td>
      <td>2017-02-01 04:41:46</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24535</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>197</td>
      <td>2017-02-01 04:42:22</td>
      <td>2017-02-01 04:45:39</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26255</td>
      <td>Subscriber</td>
      <td>1963.0</td>
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
      <td>435</td>
      <td>2017-02-01 00:06:33</td>
      <td>2017-02-01 00:13:49</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>24493</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>779</td>
      <td>2017-02-01 01:02:21</td>
      <td>2017-02-01 01:15:21</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3189</td>
      <td>West Side Light Rail</td>
      <td>40.714402</td>
      <td>-74.088772</td>
      <td>26232</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>145</td>
      <td>2017-02-01 01:56:05</td>
      <td>2017-02-01 01:58:30</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>24511</td>
      <td>Subscriber</td>
      <td>1972.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>184</td>
      <td>2017-02-01 04:38:42</td>
      <td>2017-02-01 04:41:46</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24535</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>197</td>
      <td>2017-02-01 04:42:22</td>
      <td>2017-02-01 04:45:39</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>26255</td>
      <td>Subscriber</td>
      <td>1963.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3 = pd.read_csv('JC-201703-citibike-tripdata.csv')
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
      <td>1076</td>
      <td>2017-03-01 00:03:02</td>
      <td>2017-03-01 00:20:58</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>40.737604</td>
      <td>-74.052478</td>
      <td>26283</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>978</td>
      <td>2017-03-01 00:09:02</td>
      <td>2017-03-01 00:25:20</td>
      <td>3220</td>
      <td>5 Corners Library</td>
      <td>40.734961</td>
      <td>-74.059503</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>24559</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1789</td>
      <td>2017-03-01 00:28:11</td>
      <td>2017-03-01 00:58:00</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24559</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>613</td>
      <td>2017-03-01 00:52:30</td>
      <td>2017-03-01 01:02:44</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3189</td>
      <td>West Side Light Rail</td>
      <td>40.714402</td>
      <td>-74.088772</td>
      <td>26261</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2418</td>
      <td>2017-03-01 00:54:40</td>
      <td>2017-03-01 01:34:59</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>26277</td>
      <td>Subscriber</td>
      <td>1975.0</td>
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
      <td>1076</td>
      <td>2017-03-01 00:03:02</td>
      <td>2017-03-01 00:20:58</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>40.737604</td>
      <td>-74.052478</td>
      <td>26283</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>978</td>
      <td>2017-03-01 00:09:02</td>
      <td>2017-03-01 00:25:20</td>
      <td>3220</td>
      <td>5 Corners Library</td>
      <td>40.734961</td>
      <td>-74.059503</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>24559</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1789</td>
      <td>2017-03-01 00:28:11</td>
      <td>2017-03-01 00:58:00</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>24559</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>613</td>
      <td>2017-03-01 00:52:30</td>
      <td>2017-03-01 01:02:44</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3189</td>
      <td>West Side Light Rail</td>
      <td>40.714402</td>
      <td>-74.088772</td>
      <td>26261</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2418</td>
      <td>2017-03-01 00:54:40</td>
      <td>2017-03-01 01:34:59</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>26277</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df4 = pd.read_csv('JC-201704-citibike-tripdata.csv')
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
      <td>252</td>
      <td>2017-04-01 00:14:36</td>
      <td>2017-04-01 00:18:48</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>26238</td>
      <td>Subscriber</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>452</td>
      <td>2017-04-01 00:15:47</td>
      <td>2017-04-01 00:23:20</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>26186</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>465</td>
      <td>2017-04-01 00:46:27</td>
      <td>2017-04-01 00:54:13</td>
      <td>3271</td>
      <td>Danforth Light Rail</td>
      <td>40.692640</td>
      <td>-74.088012</td>
      <td>3216</td>
      <td>Columbia Park</td>
      <td>40.697030</td>
      <td>-74.096937</td>
      <td>24659</td>
      <td>Subscriber</td>
      <td>1996.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>417</td>
      <td>2017-04-01 00:47:15</td>
      <td>2017-04-01 00:54:13</td>
      <td>3271</td>
      <td>Danforth Light Rail</td>
      <td>40.692640</td>
      <td>-74.088012</td>
      <td>3216</td>
      <td>Columbia Park</td>
      <td>40.697030</td>
      <td>-74.096937</td>
      <td>24471</td>
      <td>Subscriber</td>
      <td>1994.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>391</td>
      <td>2017-04-01 01:13:12</td>
      <td>2017-04-01 01:19:44</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>24624</td>
      <td>Subscriber</td>
      <td>1983.0</td>
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
      <td>252</td>
      <td>2017-04-01 00:14:36</td>
      <td>2017-04-01 00:18:48</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>26238</td>
      <td>Subscriber</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>452</td>
      <td>2017-04-01 00:15:47</td>
      <td>2017-04-01 00:23:20</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>26186</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>465</td>
      <td>2017-04-01 00:46:27</td>
      <td>2017-04-01 00:54:13</td>
      <td>3271</td>
      <td>Danforth Light Rail</td>
      <td>40.692640</td>
      <td>-74.088012</td>
      <td>3216</td>
      <td>Columbia Park</td>
      <td>40.697030</td>
      <td>-74.096937</td>
      <td>24659</td>
      <td>Subscriber</td>
      <td>1996.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>417</td>
      <td>2017-04-01 00:47:15</td>
      <td>2017-04-01 00:54:13</td>
      <td>3271</td>
      <td>Danforth Light Rail</td>
      <td>40.692640</td>
      <td>-74.088012</td>
      <td>3216</td>
      <td>Columbia Park</td>
      <td>40.697030</td>
      <td>-74.096937</td>
      <td>24471</td>
      <td>Subscriber</td>
      <td>1994.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>391</td>
      <td>2017-04-01 01:13:12</td>
      <td>2017-04-01 01:19:44</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>24624</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df5 = pd.read_csv('JC-201705-citibike-tripdata.csv')
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
      <td>347</td>
      <td>2017-05-01 00:03:19</td>
      <td>2017-05-01 00:09:06</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>26177</td>
      <td>Subscriber</td>
      <td>1958.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>108</td>
      <td>2017-05-01 00:16:04</td>
      <td>2017-05-01 00:17:53</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>26266</td>
      <td>Subscriber</td>
      <td>1963.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>165</td>
      <td>2017-05-01 00:29:59</td>
      <td>2017-05-01 00:32:44</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>26168</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>289</td>
      <td>2017-05-01 00:30:47</td>
      <td>2017-05-01 00:35:36</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>3205</td>
      <td>JC Medical Center</td>
      <td>40.716540</td>
      <td>-74.049638</td>
      <td>26273</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>115</td>
      <td>2017-05-01 00:41:14</td>
      <td>2017-05-01 00:43:09</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>26293</td>
      <td>Subscriber</td>
      <td>1983.0</td>
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
      <td>347</td>
      <td>2017-05-01 00:03:19</td>
      <td>2017-05-01 00:09:06</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>3214</td>
      <td>Essex Light Rail</td>
      <td>40.712774</td>
      <td>-74.036486</td>
      <td>26177</td>
      <td>Subscriber</td>
      <td>1958.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>108</td>
      <td>2017-05-01 00:16:04</td>
      <td>2017-05-01 00:17:53</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>26266</td>
      <td>Subscriber</td>
      <td>1963.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>165</td>
      <td>2017-05-01 00:29:59</td>
      <td>2017-05-01 00:32:44</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>26168</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>289</td>
      <td>2017-05-01 00:30:47</td>
      <td>2017-05-01 00:35:36</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>3205</td>
      <td>JC Medical Center</td>
      <td>40.716540</td>
      <td>-74.049638</td>
      <td>26273</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>115</td>
      <td>2017-05-01 00:41:14</td>
      <td>2017-05-01 00:43:09</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>26293</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df6 = pd.read_csv('JC-201706-citibike-tripdata.csv')
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
      <td>499</td>
      <td>2017-06-01 00:01:39</td>
      <td>2017-06-01 00:09:59</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>29590</td>
      <td>Subscriber</td>
      <td>1979.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>507</td>
      <td>2017-06-01 00:06:39</td>
      <td>2017-06-01 00:15:07</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3277</td>
      <td>Communipaw &amp; Berry Lane</td>
      <td>40.714358</td>
      <td>-74.066611</td>
      <td>29453</td>
      <td>Subscriber</td>
      <td>1969.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>768</td>
      <td>2017-06-01 00:44:43</td>
      <td>2017-06-01 00:57:31</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3189</td>
      <td>West Side Light Rail</td>
      <td>40.714402</td>
      <td>-74.088772</td>
      <td>26193</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>101</td>
      <td>2017-06-01 01:12:55</td>
      <td>2017-06-01 01:14:36</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>29284</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>265</td>
      <td>2017-06-01 01:14:00</td>
      <td>2017-06-01 01:18:25</td>
      <td>3273</td>
      <td>Manila &amp; 1st</td>
      <td>40.721651</td>
      <td>-74.042884</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>29645</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>2</td>
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
      <td>499</td>
      <td>2017-06-01 00:01:39</td>
      <td>2017-06-01 00:09:59</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>29590</td>
      <td>Subscriber</td>
      <td>1979.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>507</td>
      <td>2017-06-01 00:06:39</td>
      <td>2017-06-01 00:15:07</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3277</td>
      <td>Communipaw &amp; Berry Lane</td>
      <td>40.714358</td>
      <td>-74.066611</td>
      <td>29453</td>
      <td>Subscriber</td>
      <td>1969.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>768</td>
      <td>2017-06-01 00:44:43</td>
      <td>2017-06-01 00:57:31</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3189</td>
      <td>West Side Light Rail</td>
      <td>40.714402</td>
      <td>-74.088772</td>
      <td>26193</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>101</td>
      <td>2017-06-01 01:12:55</td>
      <td>2017-06-01 01:14:36</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>29284</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>265</td>
      <td>2017-06-01 01:14:00</td>
      <td>2017-06-01 01:18:25</td>
      <td>3273</td>
      <td>Manila &amp; 1st</td>
      <td>40.721651</td>
      <td>-74.042884</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>29645</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
df7 = pd.read_csv('JC-201707-citibike-tripdata.csv')
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
      <td>340</td>
      <td>2017-07-01 00:00:08</td>
      <td>2017-07-01 00:05:48</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29643</td>
      <td>Subscriber</td>
      <td>1994.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>439</td>
      <td>2017-07-01 00:02:35</td>
      <td>2017-07-01 00:09:55</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>29585</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>186</td>
      <td>2017-07-01 00:04:33</td>
      <td>2017-07-01 00:07:40</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>29219</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>442</td>
      <td>2017-07-01 00:05:53</td>
      <td>2017-07-01 00:13:15</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>29497</td>
      <td>Subscriber</td>
      <td>1969.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>170</td>
      <td>2017-07-01 00:07:54</td>
      <td>2017-07-01 00:10:45</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>29483</td>
      <td>Subscriber</td>
      <td>1986.0</td>
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
      <td>340</td>
      <td>2017-07-01 00:00:08</td>
      <td>2017-07-01 00:05:48</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>29643</td>
      <td>Subscriber</td>
      <td>1994.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>439</td>
      <td>2017-07-01 00:02:35</td>
      <td>2017-07-01 00:09:55</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>29585</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>186</td>
      <td>2017-07-01 00:04:33</td>
      <td>2017-07-01 00:07:40</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>29219</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>442</td>
      <td>2017-07-01 00:05:53</td>
      <td>2017-07-01 00:13:15</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>29497</td>
      <td>Subscriber</td>
      <td>1969.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>170</td>
      <td>2017-07-01 00:07:54</td>
      <td>2017-07-01 00:10:45</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>29483</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df8 = pd.read_csv('JC-201708 citibike-tripdata.csv')
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
      <td>1314</td>
      <td>2017-08-01 00:03:05</td>
      <td>2017-08-01 00:24:59</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>26293</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>221</td>
      <td>2017-08-01 00:06:25</td>
      <td>2017-08-01 00:10:06</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>26314</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>185</td>
      <td>2017-08-01 00:42:28</td>
      <td>2017-08-01 00:45:33</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3269</td>
      <td>Brunswick &amp; 6th</td>
      <td>40.726012</td>
      <td>-74.050389</td>
      <td>26196</td>
      <td>Subscriber</td>
      <td>1972.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>72</td>
      <td>2017-08-01 00:45:06</td>
      <td>2017-08-01 00:46:18</td>
      <td>3269</td>
      <td>Brunswick &amp; 6th</td>
      <td>40.726012</td>
      <td>-74.050389</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>29521</td>
      <td>Subscriber</td>
      <td>1996.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>499</td>
      <td>2017-08-01 01:12:10</td>
      <td>2017-08-01 01:20:30</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3268</td>
      <td>Lafayette Park</td>
      <td>40.713464</td>
      <td>-74.062859</td>
      <td>29634</td>
      <td>Subscriber</td>
      <td>1984.0</td>
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
      <td>1314</td>
      <td>2017-08-01 00:03:05</td>
      <td>2017-08-01 00:24:59</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>26293</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>221</td>
      <td>2017-08-01 00:06:25</td>
      <td>2017-08-01 00:10:06</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>26314</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>185</td>
      <td>2017-08-01 00:42:28</td>
      <td>2017-08-01 00:45:33</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3269</td>
      <td>Brunswick &amp; 6th</td>
      <td>40.726012</td>
      <td>-74.050389</td>
      <td>26196</td>
      <td>Subscriber</td>
      <td>1972.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>72</td>
      <td>2017-08-01 00:45:06</td>
      <td>2017-08-01 00:46:18</td>
      <td>3269</td>
      <td>Brunswick &amp; 6th</td>
      <td>40.726012</td>
      <td>-74.050389</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>29521</td>
      <td>Subscriber</td>
      <td>1996.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>499</td>
      <td>2017-08-01 01:12:10</td>
      <td>2017-08-01 01:20:30</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>3268</td>
      <td>Lafayette Park</td>
      <td>40.713464</td>
      <td>-74.062859</td>
      <td>29634</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df9 = pd.read_csv('JC-201709-citibike-tripdata.csv')
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
      <td>364</td>
      <td>2017-09-01 00:02:01</td>
      <td>2017-09-01 00:08:05</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>29670</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>357</td>
      <td>2017-09-01 00:08:12</td>
      <td>2017-09-01 00:14:09</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>26163</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>432</td>
      <td>2017-09-01 00:10:12</td>
      <td>2017-09-01 00:17:24</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3280</td>
      <td>Astor Place</td>
      <td>40.719282</td>
      <td>-74.071262</td>
      <td>26273</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>934</td>
      <td>2017-09-01 00:10:11</td>
      <td>2017-09-01 00:25:46</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>40.737604</td>
      <td>-74.052478</td>
      <td>26297</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>932</td>
      <td>2017-09-01 00:10:16</td>
      <td>2017-09-01 00:25:48</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>40.737604</td>
      <td>-74.052478</td>
      <td>29247</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>2</td>
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
      <td>364</td>
      <td>2017-09-01 00:02:01</td>
      <td>2017-09-01 00:08:05</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>29670</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>357</td>
      <td>2017-09-01 00:08:12</td>
      <td>2017-09-01 00:14:09</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>26163</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>432</td>
      <td>2017-09-01 00:10:12</td>
      <td>2017-09-01 00:17:24</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3280</td>
      <td>Astor Place</td>
      <td>40.719282</td>
      <td>-74.071262</td>
      <td>26273</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>934</td>
      <td>2017-09-01 00:10:11</td>
      <td>2017-09-01 00:25:46</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>40.737604</td>
      <td>-74.052478</td>
      <td>26297</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>932</td>
      <td>2017-09-01 00:10:16</td>
      <td>2017-09-01 00:25:48</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>40.737604</td>
      <td>-74.052478</td>
      <td>29247</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
df10 = pd.read_csv('JC-201710-citibike-tripdata.csv')
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
      <td>410</td>
      <td>2017-10-01 00:03:08</td>
      <td>2017-10-01 00:09:59</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>26187</td>
      <td>Subscriber</td>
      <td>1976.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>412</td>
      <td>2017-10-01 00:03:13</td>
      <td>2017-10-01 00:10:06</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>31768</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>274</td>
      <td>2017-10-01 00:24:07</td>
      <td>2017-10-01 00:28:42</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>26311</td>
      <td>Subscriber</td>
      <td>1979.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2198</td>
      <td>2017-10-01 00:31:03</td>
      <td>2017-10-01 01:07:42</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>31709</td>
      <td>Subscriber</td>
      <td>1994.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>166</td>
      <td>2017-10-01 00:34:09</td>
      <td>2017-10-01 00:36:56</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>31759</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>2</td>
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
      <td>410</td>
      <td>2017-10-01 00:03:08</td>
      <td>2017-10-01 00:09:59</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>26187</td>
      <td>Subscriber</td>
      <td>1976.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>412</td>
      <td>2017-10-01 00:03:13</td>
      <td>2017-10-01 00:10:06</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>3192</td>
      <td>Liberty Light Rail</td>
      <td>40.711242</td>
      <td>-74.055701</td>
      <td>31768</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>274</td>
      <td>2017-10-01 00:24:07</td>
      <td>2017-10-01 00:28:42</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>26311</td>
      <td>Subscriber</td>
      <td>1979.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2198</td>
      <td>2017-10-01 00:31:03</td>
      <td>2017-10-01 01:07:42</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>31709</td>
      <td>Subscriber</td>
      <td>1994.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>166</td>
      <td>2017-10-01 00:34:09</td>
      <td>2017-10-01 00:36:56</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>31759</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
df11 = pd.read_csv('JC-201711-citibike-tripdata.csv')
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
      <td>370</td>
      <td>2017-11-01 00:04:26</td>
      <td>2017-11-01 00:10:37</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>40.719252</td>
      <td>-74.034234</td>
      <td>31817</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>96</td>
      <td>2017-11-01 00:05:45</td>
      <td>2017-11-01 00:07:22</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>26307</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>73</td>
      <td>2017-11-01 00:09:49</td>
      <td>2017-11-01 00:11:03</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>31864</td>
      <td>Subscriber</td>
      <td>1974.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>162</td>
      <td>2017-11-01 00:14:04</td>
      <td>2017-11-01 00:16:47</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>26314</td>
      <td>Subscriber</td>
      <td>1979.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>214</td>
      <td>2017-11-01 00:23:38</td>
      <td>2017-11-01 00:27:13</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>31772</td>
      <td>Subscriber</td>
      <td>1982.0</td>
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
      <td>370</td>
      <td>2017-11-01 00:04:26</td>
      <td>2017-11-01 00:10:37</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>40.719252</td>
      <td>-74.034234</td>
      <td>31817</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>96</td>
      <td>2017-11-01 00:05:45</td>
      <td>2017-11-01 00:07:22</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>26307</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>73</td>
      <td>2017-11-01 00:09:49</td>
      <td>2017-11-01 00:11:03</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>31864</td>
      <td>Subscriber</td>
      <td>1974.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>162</td>
      <td>2017-11-01 00:14:04</td>
      <td>2017-11-01 00:16:47</td>
      <td>3275</td>
      <td>Columbus Drive</td>
      <td>40.718355</td>
      <td>-74.038914</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>26314</td>
      <td>Subscriber</td>
      <td>1979.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>214</td>
      <td>2017-11-01 00:23:38</td>
      <td>2017-11-01 00:27:13</td>
      <td>3276</td>
      <td>Marin Light Rail</td>
      <td>40.714584</td>
      <td>-74.042817</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>31772</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df12 = pd.read_csv('JC-201712-citibike-tripdata.csv')
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
      <td>452</td>
      <td>2017-12-01 00:00:59</td>
      <td>2017-12-01 00:08:32</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>29607</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>159</td>
      <td>2017-12-01 00:04:42</td>
      <td>2017-12-01 00:07:21</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>26269</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>175</td>
      <td>2017-12-01 00:17:00</td>
      <td>2017-12-01 00:19:55</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3205</td>
      <td>JC Medical Center</td>
      <td>40.716540</td>
      <td>-74.049638</td>
      <td>26269</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>455</td>
      <td>2017-12-01 00:50:22</td>
      <td>2017-12-01 00:57:57</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3191</td>
      <td>Union St</td>
      <td>40.718211</td>
      <td>-74.083639</td>
      <td>31929</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>670</td>
      <td>2017-12-01 00:55:03</td>
      <td>2017-12-01 01:06:13</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3189</td>
      <td>West Side Light Rail</td>
      <td>40.714402</td>
      <td>-74.088772</td>
      <td>26274</td>
      <td>Subscriber</td>
      <td>1962.0</td>
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
      <td>452</td>
      <td>2017-12-01 00:00:59</td>
      <td>2017-12-01 00:08:32</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>29607</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>159</td>
      <td>2017-12-01 00:04:42</td>
      <td>2017-12-01 00:07:21</td>
      <td>3187</td>
      <td>Warren St</td>
      <td>40.721124</td>
      <td>-74.038051</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>26269</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>175</td>
      <td>2017-12-01 00:17:00</td>
      <td>2017-12-01 00:19:55</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3205</td>
      <td>JC Medical Center</td>
      <td>40.716540</td>
      <td>-74.049638</td>
      <td>26269</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>455</td>
      <td>2017-12-01 00:50:22</td>
      <td>2017-12-01 00:57:57</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3191</td>
      <td>Union St</td>
      <td>40.718211</td>
      <td>-74.083639</td>
      <td>31929</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>670</td>
      <td>2017-12-01 00:55:03</td>
      <td>2017-12-01 01:06:13</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3189</td>
      <td>West Side Light Rail</td>
      <td>40.714402</td>
      <td>-74.088772</td>
      <td>26274</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
jc_citibike_2017 = pd.concat([df1, df2, df3, df4, df5, df6, df7, df8, df9, df10, df11, df12])
jc_citibike_2017
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
      <th>15868</th>
      <td>200</td>
      <td>2017-12-31 18:22:05</td>
      <td>2017-12-31 18:25:26</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>31716</td>
      <td>Subscriber</td>
      <td>1957.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15869</th>
      <td>521</td>
      <td>2017-12-31 18:29:32</td>
      <td>2017-12-31 18:38:13</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>31772</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15870</th>
      <td>690</td>
      <td>2017-12-31 18:33:38</td>
      <td>2017-12-31 18:45:09</td>
      <td>3272</td>
      <td>Jersey &amp; 3rd</td>
      <td>40.723332</td>
      <td>-74.045953</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>31716</td>
      <td>Subscriber</td>
      <td>1957.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15871</th>
      <td>179</td>
      <td>2017-12-31 18:52:09</td>
      <td>2017-12-31 18:55:08</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>31840</td>
      <td>Subscriber</td>
      <td>1979.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15872</th>
      <td>1084</td>
      <td>2017-12-31 18:55:20</td>
      <td>2017-12-31 19:13:24</td>
      <td>3210</td>
      <td>Pershing Field</td>
      <td>40.742677</td>
      <td>-74.051789</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>40.737604</td>
      <td>-74.052478</td>
      <td>31766</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15873</th>
      <td>227</td>
      <td>2017-12-31 19:00:06</td>
      <td>2017-12-31 19:03:53</td>
      <td>3209</td>
      <td>Brunswick St</td>
      <td>40.724176</td>
      <td>-74.050656</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>29590</td>
      <td>Subscriber</td>
      <td>1994.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15874</th>
      <td>141</td>
      <td>2017-12-31 19:10:22</td>
      <td>2017-12-31 19:12:43</td>
      <td>3184</td>
      <td>Paulus Hook</td>
      <td>40.714145</td>
      <td>-74.033552</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>31861</td>
      <td>Subscriber</td>
      <td>1999.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15875</th>
      <td>432</td>
      <td>2017-12-31 19:28:03</td>
      <td>2017-12-31 19:35:16</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>40.728745</td>
      <td>-74.032108</td>
      <td>3183</td>
      <td>Exchange Place</td>
      <td>40.716247</td>
      <td>-74.033459</td>
      <td>31929</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15876</th>
      <td>1090</td>
      <td>2017-12-31 19:30:26</td>
      <td>2017-12-31 19:48:37</td>
      <td>3280</td>
      <td>Astor Place</td>
      <td>40.719282</td>
      <td>-74.071262</td>
      <td>3481</td>
      <td>York St</td>
      <td>40.716490</td>
      <td>-74.041050</td>
      <td>31760</td>
      <td>Subscriber</td>
      <td>1953.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15877</th>
      <td>1084</td>
      <td>2017-12-31 19:31:17</td>
      <td>2017-12-31 19:49:21</td>
      <td>3280</td>
      <td>Astor Place</td>
      <td>40.719282</td>
      <td>-74.071262</td>
      <td>3481</td>
      <td>York St</td>
      <td>40.716490</td>
      <td>-74.041050</td>
      <td>31808</td>
      <td>Subscriber</td>
      <td>1960.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15878</th>
      <td>262</td>
      <td>2017-12-31 20:00:09</td>
      <td>2017-12-31 20:04:32</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>40.723659</td>
      <td>-74.064194</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>31940</td>
      <td>Subscriber</td>
      <td>1994.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15879</th>
      <td>598</td>
      <td>2017-12-31 20:08:32</td>
      <td>2017-12-31 20:18:30</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>40.723659</td>
      <td>-74.064194</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>26212</td>
      <td>Subscriber</td>
      <td>1976.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15880</th>
      <td>455</td>
      <td>2017-12-31 20:16:57</td>
      <td>2017-12-31 20:24:33</td>
      <td>3281</td>
      <td>Leonard Gordon Park</td>
      <td>40.745910</td>
      <td>-74.057271</td>
      <td>3640</td>
      <td>Journal Square</td>
      <td>40.733670</td>
      <td>-74.062500</td>
      <td>32795</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15881</th>
      <td>358</td>
      <td>2017-12-31 20:25:06</td>
      <td>2017-12-31 20:31:04</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>31938</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15882</th>
      <td>354</td>
      <td>2017-12-31 20:25:06</td>
      <td>2017-12-31 20:31:01</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>29604</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15883</th>
      <td>387</td>
      <td>2017-12-31 20:25:13</td>
      <td>2017-12-31 20:31:41</td>
      <td>3279</td>
      <td>Dixon Mills</td>
      <td>40.721630</td>
      <td>-74.049968</td>
      <td>3279</td>
      <td>Dixon Mills</td>
      <td>40.721630</td>
      <td>-74.049968</td>
      <td>31833</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15884</th>
      <td>259</td>
      <td>2017-12-31 20:27:04</td>
      <td>2017-12-31 20:31:23</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>31920</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15885</th>
      <td>142</td>
      <td>2017-12-31 20:28:06</td>
      <td>2017-12-31 20:30:29</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3481</td>
      <td>York St</td>
      <td>40.716490</td>
      <td>-74.041050</td>
      <td>31716</td>
      <td>Subscriber</td>
      <td>1974.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15886</th>
      <td>288</td>
      <td>2017-12-31 20:30:30</td>
      <td>2017-12-31 20:35:18</td>
      <td>3278</td>
      <td>Monmouth and 6th</td>
      <td>40.725685</td>
      <td>-74.048790</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>29622</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15887</th>
      <td>207</td>
      <td>2017-12-31 20:33:52</td>
      <td>2017-12-31 20:37:19</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>40.725340</td>
      <td>-74.067622</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>29634</td>
      <td>Subscriber</td>
      <td>1990.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15888</th>
      <td>1525</td>
      <td>2017-12-31 20:35:35</td>
      <td>2017-12-31 21:01:00</td>
      <td>3267</td>
      <td>Morris Canal</td>
      <td>40.712419</td>
      <td>-74.038526</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>40.724605</td>
      <td>-74.078406</td>
      <td>31918</td>
      <td>Subscriber</td>
      <td>1960.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15889</th>
      <td>672</td>
      <td>2017-12-31 20:57:37</td>
      <td>2017-12-31 21:08:50</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>31709</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15890</th>
      <td>345</td>
      <td>2017-12-31 21:06:52</td>
      <td>2017-12-31 21:12:38</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>40.719252</td>
      <td>-74.034234</td>
      <td>3202</td>
      <td>Newport PATH</td>
      <td>40.727224</td>
      <td>-74.033759</td>
      <td>31762</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15891</th>
      <td>267</td>
      <td>2017-12-31 21:38:07</td>
      <td>2017-12-31 21:42:35</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>3213</td>
      <td>Van Vorst Park</td>
      <td>40.718489</td>
      <td>-74.047727</td>
      <td>26212</td>
      <td>Subscriber</td>
      <td>1976.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15892</th>
      <td>339</td>
      <td>2017-12-31 21:45:19</td>
      <td>2017-12-31 21:50:59</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3203</td>
      <td>Hamilton Park</td>
      <td>40.727596</td>
      <td>-74.044247</td>
      <td>31767</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15893</th>
      <td>972</td>
      <td>2017-12-31 21:54:12</td>
      <td>2017-12-31 22:10:25</td>
      <td>3191</td>
      <td>Union St</td>
      <td>40.718211</td>
      <td>-74.083639</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>29644</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>15894</th>
      <td>382</td>
      <td>2017-12-31 22:10:18</td>
      <td>2017-12-31 22:16:41</td>
      <td>3280</td>
      <td>Astor Place</td>
      <td>40.719282</td>
      <td>-74.071262</td>
      <td>3268</td>
      <td>Lafayette Park</td>
      <td>40.713464</td>
      <td>-74.062859</td>
      <td>31799</td>
      <td>Subscriber</td>
      <td>1994.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15895</th>
      <td>93</td>
      <td>2017-12-31 22:55:10</td>
      <td>2017-12-31 22:56:43</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>40.719586</td>
      <td>-74.043117</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>40.717733</td>
      <td>-74.043845</td>
      <td>31920</td>
      <td>Subscriber</td>
      <td>1957.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15896</th>
      <td>186</td>
      <td>2017-12-31 23:20:54</td>
      <td>2017-12-31 23:24:00</td>
      <td>3270</td>
      <td>Jersey &amp; 6th St</td>
      <td>40.725289</td>
      <td>-74.045572</td>
      <td>3211</td>
      <td>Newark Ave</td>
      <td>40.721525</td>
      <td>-74.046305</td>
      <td>31925</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15897</th>
      <td>422</td>
      <td>2017-12-31 23:33:55</td>
      <td>2017-12-31 23:40:57</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>40.730743</td>
      <td>-74.063784</td>
      <td>3280</td>
      <td>Astor Place</td>
      <td>40.719282</td>
      <td>-74.071262</td>
      <td>31709</td>
      <td>Subscriber</td>
      <td>1979.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>294928 rows × 15 columns</p>
</div>




```python
jc_citibike_2017.to_csv('jc_citibike_2017.csv', sep = ',') 
```


```python

```
