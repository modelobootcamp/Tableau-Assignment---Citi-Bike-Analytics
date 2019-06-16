

```python
import pandas as pd 
```


```python
df1 = pd.read_csv('201601-citibike-tripdata.csv')
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
      <td>923</td>
      <td>1/1/2016 00:00:41</td>
      <td>1/1/2016 00:16:04</td>
      <td>268</td>
      <td>Howard St &amp; Centre St</td>
      <td>40.719105</td>
      <td>-73.999733</td>
      <td>3002</td>
      <td>South End Ave &amp; Liberty St</td>
      <td>40.711512</td>
      <td>-74.015756</td>
      <td>22285</td>
      <td>Subscriber</td>
      <td>1958.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>379</td>
      <td>1/1/2016 00:00:45</td>
      <td>1/1/2016 00:07:04</td>
      <td>476</td>
      <td>E 31 St &amp; 3 Ave</td>
      <td>40.743943</td>
      <td>-73.979661</td>
      <td>498</td>
      <td>Broadway &amp; W 32 St</td>
      <td>40.748549</td>
      <td>-73.988084</td>
      <td>17827</td>
      <td>Subscriber</td>
      <td>1969.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>589</td>
      <td>1/1/2016 00:00:48</td>
      <td>1/1/2016 00:10:37</td>
      <td>489</td>
      <td>10 Ave &amp; W 28 St</td>
      <td>40.750664</td>
      <td>-74.001768</td>
      <td>284</td>
      <td>Greenwich Ave &amp; 8 Ave</td>
      <td>40.739017</td>
      <td>-74.002638</td>
      <td>21997</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>889</td>
      <td>1/1/2016 00:01:06</td>
      <td>1/1/2016 00:15:56</td>
      <td>268</td>
      <td>Howard St &amp; Centre St</td>
      <td>40.719105</td>
      <td>-73.999733</td>
      <td>3002</td>
      <td>South End Ave &amp; Liberty St</td>
      <td>40.711512</td>
      <td>-74.015756</td>
      <td>22794</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1480</td>
      <td>1/1/2016 00:01:12</td>
      <td>1/1/2016 00:25:52</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>14562</td>
      <td>Subscriber</td>
      <td>1952.0</td>
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
      <td>923</td>
      <td>1/1/2016 00:00:41</td>
      <td>1/1/2016 00:16:04</td>
      <td>268</td>
      <td>Howard St &amp; Centre St</td>
      <td>40.719105</td>
      <td>-73.999733</td>
      <td>3002</td>
      <td>South End Ave &amp; Liberty St</td>
      <td>40.711512</td>
      <td>-74.015756</td>
      <td>22285</td>
      <td>Subscriber</td>
      <td>1958.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>379</td>
      <td>1/1/2016 00:00:45</td>
      <td>1/1/2016 00:07:04</td>
      <td>476</td>
      <td>E 31 St &amp; 3 Ave</td>
      <td>40.743943</td>
      <td>-73.979661</td>
      <td>498</td>
      <td>Broadway &amp; W 32 St</td>
      <td>40.748549</td>
      <td>-73.988084</td>
      <td>17827</td>
      <td>Subscriber</td>
      <td>1969.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>589</td>
      <td>1/1/2016 00:00:48</td>
      <td>1/1/2016 00:10:37</td>
      <td>489</td>
      <td>10 Ave &amp; W 28 St</td>
      <td>40.750664</td>
      <td>-74.001768</td>
      <td>284</td>
      <td>Greenwich Ave &amp; 8 Ave</td>
      <td>40.739017</td>
      <td>-74.002638</td>
      <td>21997</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>889</td>
      <td>1/1/2016 00:01:06</td>
      <td>1/1/2016 00:15:56</td>
      <td>268</td>
      <td>Howard St &amp; Centre St</td>
      <td>40.719105</td>
      <td>-73.999733</td>
      <td>3002</td>
      <td>South End Ave &amp; Liberty St</td>
      <td>40.711512</td>
      <td>-74.015756</td>
      <td>22794</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1480</td>
      <td>1/1/2016 00:01:12</td>
      <td>1/1/2016 00:25:52</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>14562</td>
      <td>Subscriber</td>
      <td>1952.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2 = pd.read_csv('201602-citibike-tripdata.csv')
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
      <td>461</td>
      <td>2/1/2016 00:00:08</td>
      <td>2/1/2016 00:07:49</td>
      <td>480</td>
      <td>W 53 St &amp; 10 Ave</td>
      <td>40.766697</td>
      <td>-73.990617</td>
      <td>524</td>
      <td>W 43 St &amp; 6 Ave</td>
      <td>40.755273</td>
      <td>-73.983169</td>
      <td>23292</td>
      <td>Subscriber</td>
      <td>1966.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>297</td>
      <td>2/1/2016 00:00:56</td>
      <td>2/1/2016 00:05:53</td>
      <td>463</td>
      <td>9 Ave &amp; W 16 St</td>
      <td>40.742065</td>
      <td>-74.004432</td>
      <td>380</td>
      <td>W 4 St &amp; 7 Ave S</td>
      <td>40.734011</td>
      <td>-74.002939</td>
      <td>15329</td>
      <td>Subscriber</td>
      <td>1977.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>280</td>
      <td>2/1/2016 00:01:00</td>
      <td>2/1/2016 00:05:40</td>
      <td>3134</td>
      <td>3 Ave &amp; E 62 St</td>
      <td>40.763126</td>
      <td>-73.965269</td>
      <td>3141</td>
      <td>1 Ave &amp; E 68 St</td>
      <td>40.765005</td>
      <td>-73.958185</td>
      <td>22927</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>662</td>
      <td>2/1/2016 00:01:00</td>
      <td>2/1/2016 00:12:02</td>
      <td>537</td>
      <td>Lexington Ave &amp; E 24 St</td>
      <td>40.740259</td>
      <td>-73.984092</td>
      <td>428</td>
      <td>E 3 St &amp; 1 Ave</td>
      <td>40.724677</td>
      <td>-73.987834</td>
      <td>20903</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>355</td>
      <td>2/1/2016 00:01:41</td>
      <td>2/1/2016 00:07:36</td>
      <td>284</td>
      <td>Greenwich Ave &amp; 8 Ave</td>
      <td>40.739017</td>
      <td>-74.002638</td>
      <td>521</td>
      <td>8 Ave &amp; W 31 St</td>
      <td>40.750967</td>
      <td>-73.994442</td>
      <td>23228</td>
      <td>Subscriber</td>
      <td>1978.0</td>
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
      <td>461</td>
      <td>2/1/2016 00:00:08</td>
      <td>2/1/2016 00:07:49</td>
      <td>480</td>
      <td>W 53 St &amp; 10 Ave</td>
      <td>40.766697</td>
      <td>-73.990617</td>
      <td>524</td>
      <td>W 43 St &amp; 6 Ave</td>
      <td>40.755273</td>
      <td>-73.983169</td>
      <td>23292</td>
      <td>Subscriber</td>
      <td>1966.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>297</td>
      <td>2/1/2016 00:00:56</td>
      <td>2/1/2016 00:05:53</td>
      <td>463</td>
      <td>9 Ave &amp; W 16 St</td>
      <td>40.742065</td>
      <td>-74.004432</td>
      <td>380</td>
      <td>W 4 St &amp; 7 Ave S</td>
      <td>40.734011</td>
      <td>-74.002939</td>
      <td>15329</td>
      <td>Subscriber</td>
      <td>1977.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>280</td>
      <td>2/1/2016 00:01:00</td>
      <td>2/1/2016 00:05:40</td>
      <td>3134</td>
      <td>3 Ave &amp; E 62 St</td>
      <td>40.763126</td>
      <td>-73.965269</td>
      <td>3141</td>
      <td>1 Ave &amp; E 68 St</td>
      <td>40.765005</td>
      <td>-73.958185</td>
      <td>22927</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>662</td>
      <td>2/1/2016 00:01:00</td>
      <td>2/1/2016 00:12:02</td>
      <td>537</td>
      <td>Lexington Ave &amp; E 24 St</td>
      <td>40.740259</td>
      <td>-73.984092</td>
      <td>428</td>
      <td>E 3 St &amp; 1 Ave</td>
      <td>40.724677</td>
      <td>-73.987834</td>
      <td>20903</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>355</td>
      <td>2/1/2016 00:01:41</td>
      <td>2/1/2016 00:07:36</td>
      <td>284</td>
      <td>Greenwich Ave &amp; 8 Ave</td>
      <td>40.739017</td>
      <td>-74.002638</td>
      <td>521</td>
      <td>8 Ave &amp; W 31 St</td>
      <td>40.750967</td>
      <td>-73.994442</td>
      <td>23228</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3 = pd.read_csv('201603-citibike-tripdata.csv')
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
      <td>1491</td>
      <td>3/1/2016 06:52:42</td>
      <td>3/1/2016 07:17:33</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>427</td>
      <td>Bus Slip &amp; State St</td>
      <td>40.701907</td>
      <td>-74.013942</td>
      <td>23914</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1044</td>
      <td>3/1/2016 07:05:50</td>
      <td>3/1/2016 07:23:15</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>254</td>
      <td>W 11 St &amp; 6 Ave</td>
      <td>40.735324</td>
      <td>-73.998004</td>
      <td>23697</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>714</td>
      <td>3/1/2016 07:15:05</td>
      <td>3/1/2016 07:26:59</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>493</td>
      <td>W 45 St &amp; 6 Ave</td>
      <td>40.756800</td>
      <td>-73.982912</td>
      <td>21447</td>
      <td>Subscriber</td>
      <td>1960.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>329</td>
      <td>3/1/2016 07:26:04</td>
      <td>3/1/2016 07:31:34</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>478</td>
      <td>11 Ave &amp; W 41 St</td>
      <td>40.760301</td>
      <td>-73.998842</td>
      <td>22351</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1871</td>
      <td>3/1/2016 07:31:30</td>
      <td>3/1/2016 08:02:41</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>151</td>
      <td>Cleveland Pl &amp; Spring St</td>
      <td>40.722104</td>
      <td>-73.997249</td>
      <td>20985</td>
      <td>Subscriber</td>
      <td>1978.0</td>
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
      <td>1491</td>
      <td>3/1/2016 06:52:42</td>
      <td>3/1/2016 07:17:33</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>427</td>
      <td>Bus Slip &amp; State St</td>
      <td>40.701907</td>
      <td>-74.013942</td>
      <td>23914</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1044</td>
      <td>3/1/2016 07:05:50</td>
      <td>3/1/2016 07:23:15</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>254</td>
      <td>W 11 St &amp; 6 Ave</td>
      <td>40.735324</td>
      <td>-73.998004</td>
      <td>23697</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>714</td>
      <td>3/1/2016 07:15:05</td>
      <td>3/1/2016 07:26:59</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>493</td>
      <td>W 45 St &amp; 6 Ave</td>
      <td>40.756800</td>
      <td>-73.982912</td>
      <td>21447</td>
      <td>Subscriber</td>
      <td>1960.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>329</td>
      <td>3/1/2016 07:26:04</td>
      <td>3/1/2016 07:31:34</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>478</td>
      <td>11 Ave &amp; W 41 St</td>
      <td>40.760301</td>
      <td>-73.998842</td>
      <td>22351</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1871</td>
      <td>3/1/2016 07:31:30</td>
      <td>3/1/2016 08:02:41</td>
      <td>72</td>
      <td>W 52 St &amp; 11 Ave</td>
      <td>40.767272</td>
      <td>-73.993929</td>
      <td>151</td>
      <td>Cleveland Pl &amp; Spring St</td>
      <td>40.722104</td>
      <td>-73.997249</td>
      <td>20985</td>
      <td>Subscriber</td>
      <td>1978.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df4 = pd.read_csv('201604-citibike-tripdata.csv')
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
      <td>496</td>
      <td>4/1/2016 00:00:26</td>
      <td>4/1/2016 00:08:42</td>
      <td>254</td>
      <td>W 11 St &amp; 6 Ave</td>
      <td>40.735324</td>
      <td>-73.998004</td>
      <td>236</td>
      <td>St Marks Pl &amp; 2 Ave</td>
      <td>40.728419</td>
      <td>-73.987140</td>
      <td>19704</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>104</td>
      <td>4/1/2016 00:00:27</td>
      <td>4/1/2016 00:02:12</td>
      <td>311</td>
      <td>Norfolk St &amp; Broome St</td>
      <td>40.717227</td>
      <td>-73.988021</td>
      <td>350</td>
      <td>Clinton St &amp; Grand St</td>
      <td>40.715595</td>
      <td>-73.987030</td>
      <td>21555</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>128</td>
      <td>4/1/2016 00:00:30</td>
      <td>4/1/2016 00:02:38</td>
      <td>3064</td>
      <td>Myrtle Ave &amp; Lewis Ave</td>
      <td>40.696820</td>
      <td>-73.937569</td>
      <td>3059</td>
      <td>Pulaski St &amp; Marcus Garvey Blvd</td>
      <td>40.693398</td>
      <td>-73.939877</td>
      <td>17430</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1197</td>
      <td>4/1/2016 00:00:34</td>
      <td>4/1/2016 00:20:31</td>
      <td>3156</td>
      <td>E 72 St &amp; York Ave</td>
      <td>40.766638</td>
      <td>-73.953483</td>
      <td>490</td>
      <td>8 Ave &amp; W 33 St</td>
      <td>40.751551</td>
      <td>-73.993934</td>
      <td>17413</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>419</td>
      <td>4/1/2016 00:00:46</td>
      <td>4/1/2016 00:07:46</td>
      <td>116</td>
      <td>W 17 St &amp; 8 Ave</td>
      <td>40.741776</td>
      <td>-74.001497</td>
      <td>405</td>
      <td>Washington St &amp; Gansevoort St</td>
      <td>40.739323</td>
      <td>-74.008119</td>
      <td>16714</td>
      <td>Subscriber</td>
      <td>1982.0</td>
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
      <td>496</td>
      <td>4/1/2016 00:00:26</td>
      <td>4/1/2016 00:08:42</td>
      <td>254</td>
      <td>W 11 St &amp; 6 Ave</td>
      <td>40.735324</td>
      <td>-73.998004</td>
      <td>236</td>
      <td>St Marks Pl &amp; 2 Ave</td>
      <td>40.728419</td>
      <td>-73.987140</td>
      <td>19704</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>104</td>
      <td>4/1/2016 00:00:27</td>
      <td>4/1/2016 00:02:12</td>
      <td>311</td>
      <td>Norfolk St &amp; Broome St</td>
      <td>40.717227</td>
      <td>-73.988021</td>
      <td>350</td>
      <td>Clinton St &amp; Grand St</td>
      <td>40.715595</td>
      <td>-73.987030</td>
      <td>21555</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>128</td>
      <td>4/1/2016 00:00:30</td>
      <td>4/1/2016 00:02:38</td>
      <td>3064</td>
      <td>Myrtle Ave &amp; Lewis Ave</td>
      <td>40.696820</td>
      <td>-73.937569</td>
      <td>3059</td>
      <td>Pulaski St &amp; Marcus Garvey Blvd</td>
      <td>40.693398</td>
      <td>-73.939877</td>
      <td>17430</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1197</td>
      <td>4/1/2016 00:00:34</td>
      <td>4/1/2016 00:20:31</td>
      <td>3156</td>
      <td>E 72 St &amp; York Ave</td>
      <td>40.766638</td>
      <td>-73.953483</td>
      <td>490</td>
      <td>8 Ave &amp; W 33 St</td>
      <td>40.751551</td>
      <td>-73.993934</td>
      <td>17413</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>419</td>
      <td>4/1/2016 00:00:46</td>
      <td>4/1/2016 00:07:46</td>
      <td>116</td>
      <td>W 17 St &amp; 8 Ave</td>
      <td>40.741776</td>
      <td>-74.001497</td>
      <td>405</td>
      <td>Washington St &amp; Gansevoort St</td>
      <td>40.739323</td>
      <td>-74.008119</td>
      <td>16714</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
df5 = pd.read_csv('201605-citibike-tripdata.csv')
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
      <td>538</td>
      <td>5/1/2016 00:00:03</td>
      <td>5/1/2016 00:09:02</td>
      <td>536</td>
      <td>1 Ave &amp; E 30 St</td>
      <td>40.741444</td>
      <td>-73.975361</td>
      <td>497</td>
      <td>E 17 St &amp; Broadway</td>
      <td>40.737050</td>
      <td>-73.990093</td>
      <td>23097</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>224</td>
      <td>5/1/2016 00:00:04</td>
      <td>5/1/2016 00:03:49</td>
      <td>361</td>
      <td>Allen St &amp; Hester St</td>
      <td>40.716059</td>
      <td>-73.991908</td>
      <td>340</td>
      <td>Madison St &amp; Clinton St</td>
      <td>40.712690</td>
      <td>-73.987763</td>
      <td>23631</td>
      <td>Subscriber</td>
      <td>1977.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>328</td>
      <td>5/1/2016 00:00:14</td>
      <td>5/1/2016 00:05:43</td>
      <td>301</td>
      <td>E 2 St &amp; Avenue B</td>
      <td>40.722174</td>
      <td>-73.983688</td>
      <td>311</td>
      <td>Norfolk St &amp; Broome St</td>
      <td>40.717227</td>
      <td>-73.988021</td>
      <td>23049</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1196</td>
      <td>5/1/2016 00:00:20</td>
      <td>5/1/2016 00:20:17</td>
      <td>3141</td>
      <td>1 Ave &amp; E 68 St</td>
      <td>40.765005</td>
      <td>-73.958185</td>
      <td>237</td>
      <td>E 11 St &amp; 2 Ave</td>
      <td>40.730473</td>
      <td>-73.986724</td>
      <td>19019</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>753</td>
      <td>5/1/2016 00:00:26</td>
      <td>5/1/2016 00:13:00</td>
      <td>492</td>
      <td>W 33 St &amp; 7 Ave</td>
      <td>40.750200</td>
      <td>-73.990931</td>
      <td>228</td>
      <td>E 48 St &amp; 3 Ave</td>
      <td>40.754601</td>
      <td>-73.971879</td>
      <td>16437</td>
      <td>Subscriber</td>
      <td>1981.0</td>
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
      <td>538</td>
      <td>5/1/2016 00:00:03</td>
      <td>5/1/2016 00:09:02</td>
      <td>536</td>
      <td>1 Ave &amp; E 30 St</td>
      <td>40.741444</td>
      <td>-73.975361</td>
      <td>497</td>
      <td>E 17 St &amp; Broadway</td>
      <td>40.737050</td>
      <td>-73.990093</td>
      <td>23097</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>224</td>
      <td>5/1/2016 00:00:04</td>
      <td>5/1/2016 00:03:49</td>
      <td>361</td>
      <td>Allen St &amp; Hester St</td>
      <td>40.716059</td>
      <td>-73.991908</td>
      <td>340</td>
      <td>Madison St &amp; Clinton St</td>
      <td>40.712690</td>
      <td>-73.987763</td>
      <td>23631</td>
      <td>Subscriber</td>
      <td>1977.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>328</td>
      <td>5/1/2016 00:00:14</td>
      <td>5/1/2016 00:05:43</td>
      <td>301</td>
      <td>E 2 St &amp; Avenue B</td>
      <td>40.722174</td>
      <td>-73.983688</td>
      <td>311</td>
      <td>Norfolk St &amp; Broome St</td>
      <td>40.717227</td>
      <td>-73.988021</td>
      <td>23049</td>
      <td>Subscriber</td>
      <td>1980.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1196</td>
      <td>5/1/2016 00:00:20</td>
      <td>5/1/2016 00:20:17</td>
      <td>3141</td>
      <td>1 Ave &amp; E 68 St</td>
      <td>40.765005</td>
      <td>-73.958185</td>
      <td>237</td>
      <td>E 11 St &amp; 2 Ave</td>
      <td>40.730473</td>
      <td>-73.986724</td>
      <td>19019</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>753</td>
      <td>5/1/2016 00:00:26</td>
      <td>5/1/2016 00:13:00</td>
      <td>492</td>
      <td>W 33 St &amp; 7 Ave</td>
      <td>40.750200</td>
      <td>-73.990931</td>
      <td>228</td>
      <td>E 48 St &amp; 3 Ave</td>
      <td>40.754601</td>
      <td>-73.971879</td>
      <td>16437</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df6 = pd.read_csv('201606-citibike-tripdata.csv')
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
      <td>1470</td>
      <td>6/1/2016 00:00:18</td>
      <td>6/1/2016 00:24:48</td>
      <td>380</td>
      <td>W 4 St &amp; 7 Ave S</td>
      <td>40.734011</td>
      <td>-74.002939</td>
      <td>3236</td>
      <td>W 42 St &amp; Dyer Ave</td>
      <td>40.758985</td>
      <td>-73.993800</td>
      <td>19859</td>
      <td>Subscriber</td>
      <td>1972.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>229</td>
      <td>6/1/2016 00:00:20</td>
      <td>6/1/2016 00:04:09</td>
      <td>3092</td>
      <td>Berry St &amp; N 8 St</td>
      <td>40.719009</td>
      <td>-73.958525</td>
      <td>3103</td>
      <td>N 11 St &amp; Wythe Ave</td>
      <td>40.721533</td>
      <td>-73.957824</td>
      <td>16233</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>344</td>
      <td>6/1/2016 00:00:21</td>
      <td>6/1/2016 00:06:06</td>
      <td>449</td>
      <td>W 52 St &amp; 9 Ave</td>
      <td>40.764618</td>
      <td>-73.987895</td>
      <td>469</td>
      <td>Broadway &amp; W 53 St</td>
      <td>40.763441</td>
      <td>-73.982681</td>
      <td>22397</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1120</td>
      <td>6/1/2016 00:00:28</td>
      <td>6/1/2016 00:19:09</td>
      <td>522</td>
      <td>E 51 St &amp; Lexington Ave</td>
      <td>40.757148</td>
      <td>-73.972078</td>
      <td>401</td>
      <td>Allen St &amp; Rivington St</td>
      <td>40.720196</td>
      <td>-73.989978</td>
      <td>16231</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>229</td>
      <td>6/1/2016 00:00:53</td>
      <td>6/1/2016 00:04:42</td>
      <td>335</td>
      <td>Washington Pl &amp; Broadway</td>
      <td>40.729039</td>
      <td>-73.994046</td>
      <td>285</td>
      <td>Broadway &amp; E 14 St</td>
      <td>40.734546</td>
      <td>-73.990741</td>
      <td>15400</td>
      <td>Subscriber</td>
      <td>1989.0</td>
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
      <td>1470</td>
      <td>6/1/2016 00:00:18</td>
      <td>6/1/2016 00:24:48</td>
      <td>380</td>
      <td>W 4 St &amp; 7 Ave S</td>
      <td>40.734011</td>
      <td>-74.002939</td>
      <td>3236</td>
      <td>W 42 St &amp; Dyer Ave</td>
      <td>40.758985</td>
      <td>-73.993800</td>
      <td>19859</td>
      <td>Subscriber</td>
      <td>1972.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>229</td>
      <td>6/1/2016 00:00:20</td>
      <td>6/1/2016 00:04:09</td>
      <td>3092</td>
      <td>Berry St &amp; N 8 St</td>
      <td>40.719009</td>
      <td>-73.958525</td>
      <td>3103</td>
      <td>N 11 St &amp; Wythe Ave</td>
      <td>40.721533</td>
      <td>-73.957824</td>
      <td>16233</td>
      <td>Subscriber</td>
      <td>1967.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>344</td>
      <td>6/1/2016 00:00:21</td>
      <td>6/1/2016 00:06:06</td>
      <td>449</td>
      <td>W 52 St &amp; 9 Ave</td>
      <td>40.764618</td>
      <td>-73.987895</td>
      <td>469</td>
      <td>Broadway &amp; W 53 St</td>
      <td>40.763441</td>
      <td>-73.982681</td>
      <td>22397</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1120</td>
      <td>6/1/2016 00:00:28</td>
      <td>6/1/2016 00:19:09</td>
      <td>522</td>
      <td>E 51 St &amp; Lexington Ave</td>
      <td>40.757148</td>
      <td>-73.972078</td>
      <td>401</td>
      <td>Allen St &amp; Rivington St</td>
      <td>40.720196</td>
      <td>-73.989978</td>
      <td>16231</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>229</td>
      <td>6/1/2016 00:00:53</td>
      <td>6/1/2016 00:04:42</td>
      <td>335</td>
      <td>Washington Pl &amp; Broadway</td>
      <td>40.729039</td>
      <td>-73.994046</td>
      <td>285</td>
      <td>Broadway &amp; E 14 St</td>
      <td>40.734546</td>
      <td>-73.990741</td>
      <td>15400</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df7 = pd.read_csv('201607-citibike-tripdata.csv')
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
      <td>704</td>
      <td>7/1/2016 00:00:02</td>
      <td>7/1/2016 00:11:47</td>
      <td>459</td>
      <td>W 20 St &amp; 11 Ave</td>
      <td>40.746745</td>
      <td>-74.007756</td>
      <td>347</td>
      <td>Greenwich St &amp; W Houston St</td>
      <td>40.728846</td>
      <td>-74.008591</td>
      <td>17431</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>492</td>
      <td>7/1/2016 00:00:18</td>
      <td>7/1/2016 00:08:31</td>
      <td>293</td>
      <td>Lafayette St &amp; E 8 St</td>
      <td>40.730287</td>
      <td>-73.990765</td>
      <td>466</td>
      <td>W 25 St &amp; 6 Ave</td>
      <td>40.743954</td>
      <td>-73.991449</td>
      <td>24159</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>191</td>
      <td>7/1/2016 00:00:19</td>
      <td>7/1/2016 00:03:31</td>
      <td>3090</td>
      <td>N 8 St &amp; Driggs Ave</td>
      <td>40.717746</td>
      <td>-73.956001</td>
      <td>3107</td>
      <td>Bedford Ave &amp; Nassau Ave</td>
      <td>40.723117</td>
      <td>-73.952123</td>
      <td>16345</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>687</td>
      <td>7/1/2016 00:00:24</td>
      <td>7/1/2016 00:11:52</td>
      <td>459</td>
      <td>W 20 St &amp; 11 Ave</td>
      <td>40.746745</td>
      <td>-74.007756</td>
      <td>347</td>
      <td>Greenwich St &amp; W Houston St</td>
      <td>40.728846</td>
      <td>-74.008591</td>
      <td>25210</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>609</td>
      <td>7/1/2016 00:00:31</td>
      <td>7/1/2016 00:10:40</td>
      <td>284</td>
      <td>Greenwich Ave &amp; 8 Ave</td>
      <td>40.739017</td>
      <td>-74.002638</td>
      <td>212</td>
      <td>W 16 St &amp; The High Line</td>
      <td>40.743349</td>
      <td>-74.006818</td>
      <td>15514</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
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
      <td>704</td>
      <td>7/1/2016 00:00:02</td>
      <td>7/1/2016 00:11:47</td>
      <td>459</td>
      <td>W 20 St &amp; 11 Ave</td>
      <td>40.746745</td>
      <td>-74.007756</td>
      <td>347</td>
      <td>Greenwich St &amp; W Houston St</td>
      <td>40.728846</td>
      <td>-74.008591</td>
      <td>17431</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>492</td>
      <td>7/1/2016 00:00:18</td>
      <td>7/1/2016 00:08:31</td>
      <td>293</td>
      <td>Lafayette St &amp; E 8 St</td>
      <td>40.730287</td>
      <td>-73.990765</td>
      <td>466</td>
      <td>W 25 St &amp; 6 Ave</td>
      <td>40.743954</td>
      <td>-73.991449</td>
      <td>24159</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>191</td>
      <td>7/1/2016 00:00:19</td>
      <td>7/1/2016 00:03:31</td>
      <td>3090</td>
      <td>N 8 St &amp; Driggs Ave</td>
      <td>40.717746</td>
      <td>-73.956001</td>
      <td>3107</td>
      <td>Bedford Ave &amp; Nassau Ave</td>
      <td>40.723117</td>
      <td>-73.952123</td>
      <td>16345</td>
      <td>Subscriber</td>
      <td>1986.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>687</td>
      <td>7/1/2016 00:00:24</td>
      <td>7/1/2016 00:11:52</td>
      <td>459</td>
      <td>W 20 St &amp; 11 Ave</td>
      <td>40.746745</td>
      <td>-74.007756</td>
      <td>347</td>
      <td>Greenwich St &amp; W Houston St</td>
      <td>40.728846</td>
      <td>-74.008591</td>
      <td>25210</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>609</td>
      <td>7/1/2016 00:00:31</td>
      <td>7/1/2016 00:10:40</td>
      <td>284</td>
      <td>Greenwich Ave &amp; 8 Ave</td>
      <td>40.739017</td>
      <td>-74.002638</td>
      <td>212</td>
      <td>W 16 St &amp; The High Line</td>
      <td>40.743349</td>
      <td>-74.006818</td>
      <td>15514</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df8 = pd.read_csv('201608-citibike-tripdata.csv')
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
      <td>288</td>
      <td>8/1/2016 00:01:22</td>
      <td>8/1/2016 00:06:11</td>
      <td>302</td>
      <td>Avenue D &amp; E 3 St</td>
      <td>40.720828</td>
      <td>-73.977932</td>
      <td>428</td>
      <td>E 3 St &amp; 1 Ave</td>
      <td>40.724677</td>
      <td>-73.987834</td>
      <td>16920</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>457</td>
      <td>8/1/2016 00:01:43</td>
      <td>8/1/2016 00:09:21</td>
      <td>285</td>
      <td>Broadway &amp; E 14 St</td>
      <td>40.734546</td>
      <td>-73.990741</td>
      <td>432</td>
      <td>E 7 St &amp; Avenue A</td>
      <td>40.726218</td>
      <td>-73.983799</td>
      <td>20084</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>278</td>
      <td>8/1/2016 00:02:10</td>
      <td>8/1/2016 00:06:49</td>
      <td>539</td>
      <td>Metropolitan Ave &amp; Bedford Ave</td>
      <td>40.715348</td>
      <td>-73.960241</td>
      <td>3096</td>
      <td>Union Ave &amp; N 12 St</td>
      <td>40.719240</td>
      <td>-73.952420</td>
      <td>18380</td>
      <td>Subscriber</td>
      <td>1971.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>862</td>
      <td>8/1/2016 00:02:13</td>
      <td>8/1/2016 00:16:36</td>
      <td>280</td>
      <td>E 10 St &amp; 5 Ave</td>
      <td>40.733320</td>
      <td>-73.995101</td>
      <td>280</td>
      <td>E 10 St &amp; 5 Ave</td>
      <td>40.733320</td>
      <td>-73.995101</td>
      <td>24101</td>
      <td>Subscriber</td>
      <td>1995.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>407</td>
      <td>8/1/2016 00:02:21</td>
      <td>8/1/2016 00:09:09</td>
      <td>161</td>
      <td>LaGuardia Pl &amp; W 3 St</td>
      <td>40.729170</td>
      <td>-73.998102</td>
      <td>428</td>
      <td>E 3 St &amp; 1 Ave</td>
      <td>40.724677</td>
      <td>-73.987834</td>
      <td>18949</td>
      <td>Subscriber</td>
      <td>1993.0</td>
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
      <td>288</td>
      <td>8/1/2016 00:01:22</td>
      <td>8/1/2016 00:06:11</td>
      <td>302</td>
      <td>Avenue D &amp; E 3 St</td>
      <td>40.720828</td>
      <td>-73.977932</td>
      <td>428</td>
      <td>E 3 St &amp; 1 Ave</td>
      <td>40.724677</td>
      <td>-73.987834</td>
      <td>16920</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>457</td>
      <td>8/1/2016 00:01:43</td>
      <td>8/1/2016 00:09:21</td>
      <td>285</td>
      <td>Broadway &amp; E 14 St</td>
      <td>40.734546</td>
      <td>-73.990741</td>
      <td>432</td>
      <td>E 7 St &amp; Avenue A</td>
      <td>40.726218</td>
      <td>-73.983799</td>
      <td>20084</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>278</td>
      <td>8/1/2016 00:02:10</td>
      <td>8/1/2016 00:06:49</td>
      <td>539</td>
      <td>Metropolitan Ave &amp; Bedford Ave</td>
      <td>40.715348</td>
      <td>-73.960241</td>
      <td>3096</td>
      <td>Union Ave &amp; N 12 St</td>
      <td>40.719240</td>
      <td>-73.952420</td>
      <td>18380</td>
      <td>Subscriber</td>
      <td>1971.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>862</td>
      <td>8/1/2016 00:02:13</td>
      <td>8/1/2016 00:16:36</td>
      <td>280</td>
      <td>E 10 St &amp; 5 Ave</td>
      <td>40.733320</td>
      <td>-73.995101</td>
      <td>280</td>
      <td>E 10 St &amp; 5 Ave</td>
      <td>40.733320</td>
      <td>-73.995101</td>
      <td>24101</td>
      <td>Subscriber</td>
      <td>1995.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>407</td>
      <td>8/1/2016 00:02:21</td>
      <td>8/1/2016 00:09:09</td>
      <td>161</td>
      <td>LaGuardia Pl &amp; W 3 St</td>
      <td>40.729170</td>
      <td>-73.998102</td>
      <td>428</td>
      <td>E 3 St &amp; 1 Ave</td>
      <td>40.724677</td>
      <td>-73.987834</td>
      <td>18949</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df9 = pd.read_csv('201609-citibike-tripdata.csv')
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
      <td>975</td>
      <td>9/1/2016 00:00:02</td>
      <td>9/1/2016 00:16:18</td>
      <td>312</td>
      <td>Allen St &amp; Stanton St</td>
      <td>40.722055</td>
      <td>-73.989111</td>
      <td>313</td>
      <td>Washington Ave &amp; Park Ave</td>
      <td>40.696102</td>
      <td>-73.967510</td>
      <td>22609</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1220</td>
      <td>9/1/2016 00:00:04</td>
      <td>9/1/2016 00:20:25</td>
      <td>316</td>
      <td>Fulton St &amp; William St</td>
      <td>40.709560</td>
      <td>-74.006536</td>
      <td>239</td>
      <td>Willoughby St &amp; Fleet St</td>
      <td>40.691966</td>
      <td>-73.981302</td>
      <td>16966</td>
      <td>Subscriber</td>
      <td>1977.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>308</td>
      <td>9/1/2016 00:00:19</td>
      <td>9/1/2016 00:05:27</td>
      <td>479</td>
      <td>9 Ave &amp; W 45 St</td>
      <td>40.760193</td>
      <td>-73.991255</td>
      <td>448</td>
      <td>W 37 St &amp; 10 Ave</td>
      <td>40.756604</td>
      <td>-73.997901</td>
      <td>25601</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>250</td>
      <td>9/1/2016 00:00:25</td>
      <td>9/1/2016 00:04:35</td>
      <td>297</td>
      <td>E 15 St &amp; 3 Ave</td>
      <td>40.734232</td>
      <td>-73.986923</td>
      <td>487</td>
      <td>E 20 St &amp; FDR Drive</td>
      <td>40.733143</td>
      <td>-73.975739</td>
      <td>22094</td>
      <td>Subscriber</td>
      <td>1953.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>439</td>
      <td>9/1/2016 00:00:25</td>
      <td>9/1/2016 00:07:45</td>
      <td>494</td>
      <td>W 26 St &amp; 8 Ave</td>
      <td>40.747348</td>
      <td>-73.997236</td>
      <td>533</td>
      <td>Broadway &amp; W 39 St</td>
      <td>40.752996</td>
      <td>-73.987216</td>
      <td>16319</td>
      <td>Subscriber</td>
      <td>1985.0</td>
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
      <td>975</td>
      <td>9/1/2016 00:00:02</td>
      <td>9/1/2016 00:16:18</td>
      <td>312</td>
      <td>Allen St &amp; Stanton St</td>
      <td>40.722055</td>
      <td>-73.989111</td>
      <td>313</td>
      <td>Washington Ave &amp; Park Ave</td>
      <td>40.696102</td>
      <td>-73.967510</td>
      <td>22609</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1220</td>
      <td>9/1/2016 00:00:04</td>
      <td>9/1/2016 00:20:25</td>
      <td>316</td>
      <td>Fulton St &amp; William St</td>
      <td>40.709560</td>
      <td>-74.006536</td>
      <td>239</td>
      <td>Willoughby St &amp; Fleet St</td>
      <td>40.691966</td>
      <td>-73.981302</td>
      <td>16966</td>
      <td>Subscriber</td>
      <td>1977.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>308</td>
      <td>9/1/2016 00:00:19</td>
      <td>9/1/2016 00:05:27</td>
      <td>479</td>
      <td>9 Ave &amp; W 45 St</td>
      <td>40.760193</td>
      <td>-73.991255</td>
      <td>448</td>
      <td>W 37 St &amp; 10 Ave</td>
      <td>40.756604</td>
      <td>-73.997901</td>
      <td>25601</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>250</td>
      <td>9/1/2016 00:00:25</td>
      <td>9/1/2016 00:04:35</td>
      <td>297</td>
      <td>E 15 St &amp; 3 Ave</td>
      <td>40.734232</td>
      <td>-73.986923</td>
      <td>487</td>
      <td>E 20 St &amp; FDR Drive</td>
      <td>40.733143</td>
      <td>-73.975739</td>
      <td>22094</td>
      <td>Subscriber</td>
      <td>1953.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>439</td>
      <td>9/1/2016 00:00:25</td>
      <td>9/1/2016 00:07:45</td>
      <td>494</td>
      <td>W 26 St &amp; 8 Ave</td>
      <td>40.747348</td>
      <td>-73.997236</td>
      <td>533</td>
      <td>Broadway &amp; W 39 St</td>
      <td>40.752996</td>
      <td>-73.987216</td>
      <td>16319</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df10 = pd.read_csv('201610-citibike-tripdata.csv')
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
      <td>328</td>
      <td>2016-10-01 00:00:07</td>
      <td>2016-10-01 00:05:35</td>
      <td>471</td>
      <td>Grand St &amp; Havemeyer St</td>
      <td>40.712868</td>
      <td>-73.956981</td>
      <td>3077</td>
      <td>Stagg St &amp; Union Ave</td>
      <td>40.708771</td>
      <td>-73.950953</td>
      <td>25254</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>398</td>
      <td>2016-10-01 00:00:11</td>
      <td>2016-10-01 00:06:49</td>
      <td>3147</td>
      <td>E 85 St &amp; 3 Ave</td>
      <td>40.778012</td>
      <td>-73.954071</td>
      <td>3140</td>
      <td>1 Ave &amp; E 78 St</td>
      <td>40.771404</td>
      <td>-73.953517</td>
      <td>17810</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>430</td>
      <td>2016-10-01 00:00:14</td>
      <td>2016-10-01 00:07:25</td>
      <td>345</td>
      <td>W 13 St &amp; 6 Ave</td>
      <td>40.736494</td>
      <td>-73.997044</td>
      <td>470</td>
      <td>W 20 St &amp; 8 Ave</td>
      <td>40.743453</td>
      <td>-74.000040</td>
      <td>20940</td>
      <td>Subscriber</td>
      <td>1965.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>351</td>
      <td>2016-10-01 00:00:21</td>
      <td>2016-10-01 00:06:12</td>
      <td>3307</td>
      <td>West End Ave &amp; W 94 St</td>
      <td>40.794165</td>
      <td>-73.974124</td>
      <td>3357</td>
      <td>W 106 St &amp; Amsterdam Ave</td>
      <td>40.800836</td>
      <td>-73.966449</td>
      <td>19086</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2693</td>
      <td>2016-10-01 00:00:21</td>
      <td>2016-10-01 00:45:15</td>
      <td>3428</td>
      <td>8 Ave &amp; W 16 St</td>
      <td>40.740983</td>
      <td>-74.001702</td>
      <td>3323</td>
      <td>W 106 St &amp; Central Park West</td>
      <td>40.798186</td>
      <td>-73.960591</td>
      <td>26502</td>
      <td>Subscriber</td>
      <td>1991.0</td>
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
      <td>328</td>
      <td>2016-10-01 00:00:07</td>
      <td>2016-10-01 00:05:35</td>
      <td>471</td>
      <td>Grand St &amp; Havemeyer St</td>
      <td>40.712868</td>
      <td>-73.956981</td>
      <td>3077</td>
      <td>Stagg St &amp; Union Ave</td>
      <td>40.708771</td>
      <td>-73.950953</td>
      <td>25254</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>398</td>
      <td>2016-10-01 00:00:11</td>
      <td>2016-10-01 00:06:49</td>
      <td>3147</td>
      <td>E 85 St &amp; 3 Ave</td>
      <td>40.778012</td>
      <td>-73.954071</td>
      <td>3140</td>
      <td>1 Ave &amp; E 78 St</td>
      <td>40.771404</td>
      <td>-73.953517</td>
      <td>17810</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>430</td>
      <td>2016-10-01 00:00:14</td>
      <td>2016-10-01 00:07:25</td>
      <td>345</td>
      <td>W 13 St &amp; 6 Ave</td>
      <td>40.736494</td>
      <td>-73.997044</td>
      <td>470</td>
      <td>W 20 St &amp; 8 Ave</td>
      <td>40.743453</td>
      <td>-74.000040</td>
      <td>20940</td>
      <td>Subscriber</td>
      <td>1965.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>351</td>
      <td>2016-10-01 00:00:21</td>
      <td>2016-10-01 00:06:12</td>
      <td>3307</td>
      <td>West End Ave &amp; W 94 St</td>
      <td>40.794165</td>
      <td>-73.974124</td>
      <td>3357</td>
      <td>W 106 St &amp; Amsterdam Ave</td>
      <td>40.800836</td>
      <td>-73.966449</td>
      <td>19086</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2693</td>
      <td>2016-10-01 00:00:21</td>
      <td>2016-10-01 00:45:15</td>
      <td>3428</td>
      <td>8 Ave &amp; W 16 St</td>
      <td>40.740983</td>
      <td>-74.001702</td>
      <td>3323</td>
      <td>W 106 St &amp; Central Park West</td>
      <td>40.798186</td>
      <td>-73.960591</td>
      <td>26502</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df11 = pd.read_csv('201611-citibike-tripdata.csv')
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
      <td>331</td>
      <td>2016-11-01 00:00:08</td>
      <td>2016-11-01 00:05:40</td>
      <td>324</td>
      <td>DeKalb Ave &amp; Hudson Ave</td>
      <td>40.689888</td>
      <td>-73.981013</td>
      <td>419</td>
      <td>Carlton Ave &amp; Park Ave</td>
      <td>40.695807</td>
      <td>-73.973556</td>
      <td>21959</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>740</td>
      <td>2016-11-01 00:00:08</td>
      <td>2016-11-01 00:12:29</td>
      <td>161</td>
      <td>LaGuardia Pl &amp; W 3 St</td>
      <td>40.729170</td>
      <td>-73.998102</td>
      <td>265</td>
      <td>Stanton St &amp; Chrystie St</td>
      <td>40.722293</td>
      <td>-73.991475</td>
      <td>20172</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>229</td>
      <td>2016-11-01 00:00:11</td>
      <td>2016-11-01 00:04:00</td>
      <td>3074</td>
      <td>Montrose Ave &amp; Bushwick Ave</td>
      <td>40.707678</td>
      <td>-73.940162</td>
      <td>3068</td>
      <td>Humboldt St &amp; Varet St</td>
      <td>40.703172</td>
      <td>-73.940636</td>
      <td>22995</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>155</td>
      <td>2016-11-01 00:00:18</td>
      <td>2016-11-01 00:02:53</td>
      <td>3357</td>
      <td>W 106 St &amp; Amsterdam Ave</td>
      <td>40.800836</td>
      <td>-73.966449</td>
      <td>3323</td>
      <td>W 106 St &amp; Central Park West</td>
      <td>40.798186</td>
      <td>-73.960591</td>
      <td>22022</td>
      <td>Subscriber</td>
      <td>1973.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>772</td>
      <td>2016-11-01 00:00:23</td>
      <td>2016-11-01 00:13:15</td>
      <td>346</td>
      <td>Bank St &amp; Hudson St</td>
      <td>40.736529</td>
      <td>-74.006180</td>
      <td>432</td>
      <td>E 7 St &amp; Avenue A</td>
      <td>40.726218</td>
      <td>-73.983799</td>
      <td>17324</td>
      <td>Subscriber</td>
      <td>1988.0</td>
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
      <td>331</td>
      <td>2016-11-01 00:00:08</td>
      <td>2016-11-01 00:05:40</td>
      <td>324</td>
      <td>DeKalb Ave &amp; Hudson Ave</td>
      <td>40.689888</td>
      <td>-73.981013</td>
      <td>419</td>
      <td>Carlton Ave &amp; Park Ave</td>
      <td>40.695807</td>
      <td>-73.973556</td>
      <td>21959</td>
      <td>Subscriber</td>
      <td>1981.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>740</td>
      <td>2016-11-01 00:00:08</td>
      <td>2016-11-01 00:12:29</td>
      <td>161</td>
      <td>LaGuardia Pl &amp; W 3 St</td>
      <td>40.729170</td>
      <td>-73.998102</td>
      <td>265</td>
      <td>Stanton St &amp; Chrystie St</td>
      <td>40.722293</td>
      <td>-73.991475</td>
      <td>20172</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>229</td>
      <td>2016-11-01 00:00:11</td>
      <td>2016-11-01 00:04:00</td>
      <td>3074</td>
      <td>Montrose Ave &amp; Bushwick Ave</td>
      <td>40.707678</td>
      <td>-73.940162</td>
      <td>3068</td>
      <td>Humboldt St &amp; Varet St</td>
      <td>40.703172</td>
      <td>-73.940636</td>
      <td>22995</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>155</td>
      <td>2016-11-01 00:00:18</td>
      <td>2016-11-01 00:02:53</td>
      <td>3357</td>
      <td>W 106 St &amp; Amsterdam Ave</td>
      <td>40.800836</td>
      <td>-73.966449</td>
      <td>3323</td>
      <td>W 106 St &amp; Central Park West</td>
      <td>40.798186</td>
      <td>-73.960591</td>
      <td>22022</td>
      <td>Subscriber</td>
      <td>1973.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>772</td>
      <td>2016-11-01 00:00:23</td>
      <td>2016-11-01 00:13:15</td>
      <td>346</td>
      <td>Bank St &amp; Hudson St</td>
      <td>40.736529</td>
      <td>-74.006180</td>
      <td>432</td>
      <td>E 7 St &amp; Avenue A</td>
      <td>40.726218</td>
      <td>-73.983799</td>
      <td>17324</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df12 = pd.read_csv('201612-citibike-tripdata.csv')
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
      <td>528</td>
      <td>2016-12-01 00:00:04</td>
      <td>2016-12-01 00:08:52</td>
      <td>499</td>
      <td>Broadway &amp; W 60 St</td>
      <td>40.769155</td>
      <td>-73.981918</td>
      <td>228</td>
      <td>E 48 St &amp; 3 Ave</td>
      <td>40.754601</td>
      <td>-73.971879</td>
      <td>26931</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>218</td>
      <td>2016-12-01 00:00:28</td>
      <td>2016-12-01 00:04:06</td>
      <td>3418</td>
      <td>Plaza St West &amp; Flatbush Ave</td>
      <td>40.675021</td>
      <td>-73.971115</td>
      <td>3358</td>
      <td>Garfield Pl &amp; 8 Ave</td>
      <td>40.671198</td>
      <td>-73.974841</td>
      <td>27122</td>
      <td>Subscriber</td>
      <td>1955.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>399</td>
      <td>2016-12-01 00:00:39</td>
      <td>2016-12-01 00:07:19</td>
      <td>297</td>
      <td>E 15 St &amp; 3 Ave</td>
      <td>40.734232</td>
      <td>-73.986923</td>
      <td>345</td>
      <td>W 13 St &amp; 6 Ave</td>
      <td>40.736494</td>
      <td>-73.997044</td>
      <td>19352</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>254</td>
      <td>2016-12-01 00:00:44</td>
      <td>2016-12-01 00:04:59</td>
      <td>405</td>
      <td>Washington St &amp; Gansevoort St</td>
      <td>40.739323</td>
      <td>-74.008119</td>
      <td>358</td>
      <td>Christopher St &amp; Greenwich St</td>
      <td>40.732916</td>
      <td>-74.007114</td>
      <td>20015</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1805</td>
      <td>2016-12-01 00:00:54</td>
      <td>2016-12-01 00:31:00</td>
      <td>279</td>
      <td>Peck Slip &amp; Front St</td>
      <td>40.707873</td>
      <td>-74.001670</td>
      <td>279</td>
      <td>Peck Slip &amp; Front St</td>
      <td>40.707873</td>
      <td>-74.001670</td>
      <td>23148</td>
      <td>Subscriber</td>
      <td>1989.0</td>
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
      <td>528</td>
      <td>2016-12-01 00:00:04</td>
      <td>2016-12-01 00:08:52</td>
      <td>499</td>
      <td>Broadway &amp; W 60 St</td>
      <td>40.769155</td>
      <td>-73.981918</td>
      <td>228</td>
      <td>E 48 St &amp; 3 Ave</td>
      <td>40.754601</td>
      <td>-73.971879</td>
      <td>26931</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>218</td>
      <td>2016-12-01 00:00:28</td>
      <td>2016-12-01 00:04:06</td>
      <td>3418</td>
      <td>Plaza St West &amp; Flatbush Ave</td>
      <td>40.675021</td>
      <td>-73.971115</td>
      <td>3358</td>
      <td>Garfield Pl &amp; 8 Ave</td>
      <td>40.671198</td>
      <td>-73.974841</td>
      <td>27122</td>
      <td>Subscriber</td>
      <td>1955.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>399</td>
      <td>2016-12-01 00:00:39</td>
      <td>2016-12-01 00:07:19</td>
      <td>297</td>
      <td>E 15 St &amp; 3 Ave</td>
      <td>40.734232</td>
      <td>-73.986923</td>
      <td>345</td>
      <td>W 13 St &amp; 6 Ave</td>
      <td>40.736494</td>
      <td>-73.997044</td>
      <td>19352</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>254</td>
      <td>2016-12-01 00:00:44</td>
      <td>2016-12-01 00:04:59</td>
      <td>405</td>
      <td>Washington St &amp; Gansevoort St</td>
      <td>40.739323</td>
      <td>-74.008119</td>
      <td>358</td>
      <td>Christopher St &amp; Greenwich St</td>
      <td>40.732916</td>
      <td>-74.007114</td>
      <td>20015</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1805</td>
      <td>2016-12-01 00:00:54</td>
      <td>2016-12-01 00:31:00</td>
      <td>279</td>
      <td>Peck Slip &amp; Front St</td>
      <td>40.707873</td>
      <td>-74.001670</td>
      <td>279</td>
      <td>Peck Slip &amp; Front St</td>
      <td>40.707873</td>
      <td>-74.001670</td>
      <td>23148</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
citibike_2016 = pd.concat([df1, df2, df3, df4, df5, df6, df7, df8, df9, df10, df11, df12])
citibike_2016
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
      <td>923</td>
      <td>1/1/2016 00:00:41</td>
      <td>1/1/2016 00:16:04</td>
      <td>268</td>
      <td>Howard St &amp; Centre St</td>
      <td>40.719105</td>
      <td>-73.999733</td>
      <td>3002</td>
      <td>South End Ave &amp; Liberty St</td>
      <td>40.711512</td>
      <td>-74.015756</td>
      <td>22285</td>
      <td>Subscriber</td>
      <td>1958.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>379</td>
      <td>1/1/2016 00:00:45</td>
      <td>1/1/2016 00:07:04</td>
      <td>476</td>
      <td>E 31 St &amp; 3 Ave</td>
      <td>40.743943</td>
      <td>-73.979661</td>
      <td>498</td>
      <td>Broadway &amp; W 32 St</td>
      <td>40.748549</td>
      <td>-73.988084</td>
      <td>17827</td>
      <td>Subscriber</td>
      <td>1969.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>589</td>
      <td>1/1/2016 00:00:48</td>
      <td>1/1/2016 00:10:37</td>
      <td>489</td>
      <td>10 Ave &amp; W 28 St</td>
      <td>40.750664</td>
      <td>-74.001768</td>
      <td>284</td>
      <td>Greenwich Ave &amp; 8 Ave</td>
      <td>40.739017</td>
      <td>-74.002638</td>
      <td>21997</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>889</td>
      <td>1/1/2016 00:01:06</td>
      <td>1/1/2016 00:15:56</td>
      <td>268</td>
      <td>Howard St &amp; Centre St</td>
      <td>40.719105</td>
      <td>-73.999733</td>
      <td>3002</td>
      <td>South End Ave &amp; Liberty St</td>
      <td>40.711512</td>
      <td>-74.015756</td>
      <td>22794</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1480</td>
      <td>1/1/2016 00:01:12</td>
      <td>1/1/2016 00:25:52</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>2006</td>
      <td>Central Park S &amp; 6 Ave</td>
      <td>40.765909</td>
      <td>-73.976342</td>
      <td>14562</td>
      <td>Subscriber</td>
      <td>1952.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>5</th>
      <td>332</td>
      <td>1/1/2016 00:01:19</td>
      <td>1/1/2016 00:06:51</td>
      <td>3104</td>
      <td>Kent Ave &amp; N 7 St</td>
      <td>40.720577</td>
      <td>-73.961502</td>
      <td>389</td>
      <td>Broadway &amp; Berry St</td>
      <td>40.710446</td>
      <td>-73.965251</td>
      <td>15788</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2321</td>
      <td>1/1/2016 00:01:27</td>
      <td>1/1/2016 00:40:08</td>
      <td>3167</td>
      <td>Amsterdam Ave &amp; W 73 St</td>
      <td>40.779668</td>
      <td>-73.980930</td>
      <td>3164</td>
      <td>Columbus Ave &amp; W 72 St</td>
      <td>40.777057</td>
      <td>-73.978985</td>
      <td>24183</td>
      <td>Subscriber</td>
      <td>1963.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>7</th>
      <td>694</td>
      <td>1/1/2016 00:02:18</td>
      <td>1/1/2016 00:13:53</td>
      <td>268</td>
      <td>Howard St &amp; Centre St</td>
      <td>40.719105</td>
      <td>-73.999733</td>
      <td>497</td>
      <td>E 17 St &amp; Broadway</td>
      <td>40.737050</td>
      <td>-73.990093</td>
      <td>15747</td>
      <td>Subscriber</td>
      <td>1996.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1376</td>
      <td>1/1/2016 00:03:12</td>
      <td>1/1/2016 00:26:09</td>
      <td>527</td>
      <td>E 33 St &amp; 2 Ave</td>
      <td>40.744023</td>
      <td>-73.976056</td>
      <td>259</td>
      <td>South St &amp; Whitehall St</td>
      <td>40.701221</td>
      <td>-74.012342</td>
      <td>23933</td>
      <td>Subscriber</td>
      <td>1963.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>9</th>
      <td>615</td>
      <td>1/1/2016 00:03:43</td>
      <td>1/1/2016 00:13:59</td>
      <td>432</td>
      <td>E 7 St &amp; Avenue A</td>
      <td>40.726218</td>
      <td>-73.983799</td>
      <td>311</td>
      <td>Norfolk St &amp; Broome St</td>
      <td>40.717227</td>
      <td>-73.988021</td>
      <td>23993</td>
      <td>Subscriber</td>
      <td>1971.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1770</td>
      <td>1/1/2016 00:04:43</td>
      <td>1/1/2016 00:34:14</td>
      <td>3226</td>
      <td>W 82 St &amp; Central Park West</td>
      <td>40.782750</td>
      <td>-73.971370</td>
      <td>509</td>
      <td>9 Ave &amp; W 22 St</td>
      <td>40.745497</td>
      <td>-74.001971</td>
      <td>22541</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>11</th>
      <td>525</td>
      <td>1/1/2016 00:05:40</td>
      <td>1/1/2016 00:14:25</td>
      <td>331</td>
      <td>Pike St &amp; Monroe St</td>
      <td>40.711731</td>
      <td>-73.991930</td>
      <td>236</td>
      <td>St Marks Pl &amp; 2 Ave</td>
      <td>40.728419</td>
      <td>-73.987140</td>
      <td>22193</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>12</th>
      <td>667</td>
      <td>1/1/2016 00:05:41</td>
      <td>1/1/2016 00:16:49</td>
      <td>444</td>
      <td>Broadway &amp; W 24 St</td>
      <td>40.742354</td>
      <td>-73.989151</td>
      <td>490</td>
      <td>8 Ave &amp; W 33 St</td>
      <td>40.751551</td>
      <td>-73.993934</td>
      <td>18665</td>
      <td>Subscriber</td>
      <td>1964.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>13</th>
      <td>240</td>
      <td>1/1/2016 00:06:35</td>
      <td>1/1/2016 00:10:36</td>
      <td>3165</td>
      <td>Central Park West &amp; W 72 St</td>
      <td>40.775794</td>
      <td>-73.976206</td>
      <td>3168</td>
      <td>Central Park West &amp; W 85 St</td>
      <td>40.784727</td>
      <td>-73.969617</td>
      <td>22174</td>
      <td>Subscriber</td>
      <td>1976.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>14</th>
      <td>539</td>
      <td>1/1/2016 00:07:39</td>
      <td>1/1/2016 00:16:39</td>
      <td>3117</td>
      <td>Franklin St &amp; Dupont St</td>
      <td>40.735640</td>
      <td>-73.958660</td>
      <td>3104</td>
      <td>Kent Ave &amp; N 7 St</td>
      <td>40.720577</td>
      <td>-73.961502</td>
      <td>15061</td>
      <td>Subscriber</td>
      <td>1989.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1245</td>
      <td>1/1/2016 00:08:17</td>
      <td>1/1/2016 00:29:03</td>
      <td>442</td>
      <td>W 27 St &amp; 7 Ave</td>
      <td>40.746647</td>
      <td>-73.993915</td>
      <td>545</td>
      <td>E 23 St &amp; 1 Ave</td>
      <td>40.736502</td>
      <td>-73.978095</td>
      <td>24071</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>16</th>
      <td>479</td>
      <td>1/1/2016 00:08:42</td>
      <td>1/1/2016 00:16:42</td>
      <td>3117</td>
      <td>Franklin St &amp; Dupont St</td>
      <td>40.735640</td>
      <td>-73.958660</td>
      <td>3104</td>
      <td>Kent Ave &amp; N 7 St</td>
      <td>40.720577</td>
      <td>-73.961502</td>
      <td>23563</td>
      <td>Subscriber</td>
      <td>1993.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>17</th>
      <td>888</td>
      <td>1/1/2016 00:08:47</td>
      <td>1/1/2016 00:23:36</td>
      <td>284</td>
      <td>Greenwich Ave &amp; 8 Ave</td>
      <td>40.739017</td>
      <td>-74.002638</td>
      <td>439</td>
      <td>E 4 St &amp; 2 Ave</td>
      <td>40.726281</td>
      <td>-73.989780</td>
      <td>15082</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>18</th>
      <td>398</td>
      <td>1/1/2016 00:09:19</td>
      <td>1/1/2016 00:15:58</td>
      <td>483</td>
      <td>E 12 St &amp; 3 Ave</td>
      <td>40.732233</td>
      <td>-73.988900</td>
      <td>483</td>
      <td>E 12 St &amp; 3 Ave</td>
      <td>40.732233</td>
      <td>-73.988900</td>
      <td>15721</td>
      <td>Subscriber</td>
      <td>1972.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>19</th>
      <td>858</td>
      <td>1/1/2016 00:09:31</td>
      <td>1/1/2016 00:23:49</td>
      <td>532</td>
      <td>S 5 Pl &amp; S 4 St</td>
      <td>40.710451</td>
      <td>-73.960876</td>
      <td>401</td>
      <td>Allen St &amp; Rivington St</td>
      <td>40.720196</td>
      <td>-73.989978</td>
      <td>17057</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>20</th>
      <td>839</td>
      <td>1/1/2016 00:09:55</td>
      <td>1/1/2016 00:23:54</td>
      <td>532</td>
      <td>S 5 Pl &amp; S 4 St</td>
      <td>40.710451</td>
      <td>-73.960876</td>
      <td>401</td>
      <td>Allen St &amp; Rivington St</td>
      <td>40.720196</td>
      <td>-73.989978</td>
      <td>17109</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>21</th>
      <td>719</td>
      <td>1/1/2016 00:10:00</td>
      <td>1/1/2016 00:21:59</td>
      <td>3116</td>
      <td>Huron St &amp; Franklin St</td>
      <td>40.732660</td>
      <td>-73.958260</td>
      <td>3126</td>
      <td>44 Dr &amp; Jackson Ave</td>
      <td>40.747182</td>
      <td>-73.943264</td>
      <td>16624</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>22</th>
      <td>110</td>
      <td>1/1/2016 00:10:24</td>
      <td>1/1/2016 00:12:15</td>
      <td>439</td>
      <td>E 4 St &amp; 2 Ave</td>
      <td>40.726281</td>
      <td>-73.989780</td>
      <td>439</td>
      <td>E 4 St &amp; 2 Ave</td>
      <td>40.726281</td>
      <td>-73.989780</td>
      <td>24021</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>23</th>
      <td>280</td>
      <td>1/1/2016 00:10:29</td>
      <td>1/1/2016 00:15:09</td>
      <td>512</td>
      <td>W 29 St &amp; 9 Ave</td>
      <td>40.750073</td>
      <td>-73.998393</td>
      <td>466</td>
      <td>W 25 St &amp; 6 Ave</td>
      <td>40.743954</td>
      <td>-73.991449</td>
      <td>23144</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>24</th>
      <td>937</td>
      <td>1/1/2016 00:10:45</td>
      <td>1/1/2016 00:26:22</td>
      <td>387</td>
      <td>Centre St &amp; Chambers St</td>
      <td>40.712733</td>
      <td>-74.004607</td>
      <td>503</td>
      <td>E 20 St &amp; Park Ave</td>
      <td>40.738274</td>
      <td>-73.987520</td>
      <td>23650</td>
      <td>Subscriber</td>
      <td>1982.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>25</th>
      <td>2038</td>
      <td>1/1/2016 00:10:50</td>
      <td>1/1/2016 00:44:49</td>
      <td>3143</td>
      <td>5 Ave &amp; E 78 St</td>
      <td>40.776829</td>
      <td>-73.963888</td>
      <td>479</td>
      <td>9 Ave &amp; W 45 St</td>
      <td>40.760193</td>
      <td>-73.991255</td>
      <td>19804</td>
      <td>Subscriber</td>
      <td>1963.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>26</th>
      <td>2023</td>
      <td>1/1/2016 00:11:15</td>
      <td>1/1/2016 00:44:58</td>
      <td>3143</td>
      <td>5 Ave &amp; E 78 St</td>
      <td>40.776829</td>
      <td>-73.963888</td>
      <td>479</td>
      <td>9 Ave &amp; W 45 St</td>
      <td>40.760193</td>
      <td>-73.991255</td>
      <td>14769</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>27</th>
      <td>743</td>
      <td>1/1/2016 00:11:42</td>
      <td>1/1/2016 00:24:05</td>
      <td>531</td>
      <td>Forsyth St &amp; Broome St</td>
      <td>40.718939</td>
      <td>-73.992663</td>
      <td>2003</td>
      <td>1 Ave &amp; E 18 St</td>
      <td>40.733812</td>
      <td>-73.980544</td>
      <td>21624</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>28</th>
      <td>1236</td>
      <td>1/1/2016 00:12:14</td>
      <td>1/1/2016 00:32:50</td>
      <td>3231</td>
      <td>E 67 St &amp; Park Ave</td>
      <td>40.767801</td>
      <td>-73.965921</td>
      <td>3231</td>
      <td>E 67 St &amp; Park Ave</td>
      <td>40.767801</td>
      <td>-73.965921</td>
      <td>16475</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>29</th>
      <td>662</td>
      <td>1/1/2016 00:12:16</td>
      <td>1/1/2016 00:23:19</td>
      <td>3175</td>
      <td>W 70 St &amp; Amsterdam Ave</td>
      <td>40.777480</td>
      <td>-73.982886</td>
      <td>3166</td>
      <td>Riverside Dr &amp; W 72 St</td>
      <td>40.780578</td>
      <td>-73.985624</td>
      <td>22560</td>
      <td>Subscriber</td>
      <td>1976.0</td>
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
      <th>812162</th>
      <td>1534</td>
      <td>2016-12-31 23:45:48</td>
      <td>2017-01-01 00:11:22</td>
      <td>3372</td>
      <td>E 74 St &amp; 1 Ave</td>
      <td>40.768974</td>
      <td>-73.954823</td>
      <td>505</td>
      <td>6 Ave &amp; W 33 St</td>
      <td>40.749013</td>
      <td>-73.988484</td>
      <td>25231</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812163</th>
      <td>870</td>
      <td>2016-12-31 23:46:35</td>
      <td>2017-01-01 00:01:05</td>
      <td>383</td>
      <td>Greenwich Ave &amp; Charles St</td>
      <td>40.735238</td>
      <td>-74.000271</td>
      <td>383</td>
      <td>Greenwich Ave &amp; Charles St</td>
      <td>40.735238</td>
      <td>-74.000271</td>
      <td>26764</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812164</th>
      <td>191</td>
      <td>2016-12-31 23:46:46</td>
      <td>2016-12-31 23:49:58</td>
      <td>3241</td>
      <td>Monroe St &amp; Tompkins Ave</td>
      <td>40.686203</td>
      <td>-73.944694</td>
      <td>344</td>
      <td>Monroe St &amp; Bedford Ave</td>
      <td>40.685144</td>
      <td>-73.953809</td>
      <td>19072</td>
      <td>Subscriber</td>
      <td>1984.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812165</th>
      <td>519</td>
      <td>2016-12-31 23:46:50</td>
      <td>2016-12-31 23:55:29</td>
      <td>438</td>
      <td>St Marks Pl &amp; 1 Ave</td>
      <td>40.727791</td>
      <td>-73.985649</td>
      <td>247</td>
      <td>Perry St &amp; Bleecker St</td>
      <td>40.735354</td>
      <td>-74.004831</td>
      <td>24936</td>
      <td>Subscriber</td>
      <td>1962.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812166</th>
      <td>549722</td>
      <td>2016-12-31 23:47:26</td>
      <td>2017-01-07 08:29:28</td>
      <td>322</td>
      <td>Clinton St &amp; Tillary St</td>
      <td>40.696192</td>
      <td>-73.991218</td>
      <td>3411</td>
      <td>Bond St &amp; Bergen St</td>
      <td>40.684967</td>
      <td>-73.986208</td>
      <td>14545</td>
      <td>Subscriber</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>812167</th>
      <td>346</td>
      <td>2016-12-31 23:47:26</td>
      <td>2016-12-31 23:53:12</td>
      <td>322</td>
      <td>Clinton St &amp; Tillary St</td>
      <td>40.696192</td>
      <td>-73.991218</td>
      <td>3411</td>
      <td>Bond St &amp; Bergen St</td>
      <td>40.684967</td>
      <td>-73.986208</td>
      <td>16692</td>
      <td>Subscriber</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>812168</th>
      <td>197</td>
      <td>2016-12-31 23:47:30</td>
      <td>2016-12-31 23:50:48</td>
      <td>3113</td>
      <td>Greenpoint Ave &amp; Manhattan Ave</td>
      <td>40.730260</td>
      <td>-73.953940</td>
      <td>3117</td>
      <td>Franklin St &amp; Dupont St</td>
      <td>40.735640</td>
      <td>-73.958660</td>
      <td>26972</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812169</th>
      <td>1806</td>
      <td>2016-12-31 23:48:29</td>
      <td>2017-01-01 00:18:35</td>
      <td>3311</td>
      <td>Columbia St &amp; Kane St</td>
      <td>40.687632</td>
      <td>-74.001626</td>
      <td>3311</td>
      <td>Columbia St &amp; Kane St</td>
      <td>40.687632</td>
      <td>-74.001626</td>
      <td>16738</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>812170</th>
      <td>1768</td>
      <td>2016-12-31 23:48:51</td>
      <td>2017-01-01 00:18:20</td>
      <td>2008</td>
      <td>Little West St &amp; 1 Pl</td>
      <td>40.705693</td>
      <td>-74.016777</td>
      <td>2008</td>
      <td>Little West St &amp; 1 Pl</td>
      <td>40.705693</td>
      <td>-74.016777</td>
      <td>16818</td>
      <td>Customer</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>812171</th>
      <td>1855</td>
      <td>2016-12-31 23:48:49</td>
      <td>2017-01-01 00:19:45</td>
      <td>2008</td>
      <td>Little West St &amp; 1 Pl</td>
      <td>40.705693</td>
      <td>-74.016777</td>
      <td>2008</td>
      <td>Little West St &amp; 1 Pl</td>
      <td>40.705693</td>
      <td>-74.016777</td>
      <td>21258</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>812172</th>
      <td>419</td>
      <td>2016-12-31 23:48:58</td>
      <td>2016-12-31 23:55:57</td>
      <td>491</td>
      <td>E 24 St &amp; Park Ave S</td>
      <td>40.740964</td>
      <td>-73.986022</td>
      <td>236</td>
      <td>St Marks Pl &amp; 2 Ave</td>
      <td>40.728419</td>
      <td>-73.987140</td>
      <td>14929</td>
      <td>Subscriber</td>
      <td>1992.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812173</th>
      <td>781</td>
      <td>2016-12-31 23:49:22</td>
      <td>2017-01-01 00:02:24</td>
      <td>368</td>
      <td>Carmine St &amp; 6 Ave</td>
      <td>40.730386</td>
      <td>-74.002150</td>
      <td>488</td>
      <td>W 39 St &amp; 9 Ave</td>
      <td>40.756458</td>
      <td>-73.993722</td>
      <td>27178</td>
      <td>Subscriber</td>
      <td>1968.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812174</th>
      <td>88</td>
      <td>2016-12-31 23:49:42</td>
      <td>2016-12-31 23:51:10</td>
      <td>3146</td>
      <td>E 81 St &amp; 3 Ave</td>
      <td>40.775730</td>
      <td>-73.956753</td>
      <td>3147</td>
      <td>E 85 St &amp; 3 Ave</td>
      <td>40.778012</td>
      <td>-73.954071</td>
      <td>27134</td>
      <td>Subscriber</td>
      <td>1974.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812175</th>
      <td>227</td>
      <td>2016-12-31 23:50:23</td>
      <td>2016-12-31 23:54:11</td>
      <td>499</td>
      <td>Broadway &amp; W 60 St</td>
      <td>40.769155</td>
      <td>-73.981918</td>
      <td>3164</td>
      <td>Columbus Ave &amp; W 72 St</td>
      <td>40.777057</td>
      <td>-73.978985</td>
      <td>25196</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812176</th>
      <td>1473</td>
      <td>2016-12-31 23:50:39</td>
      <td>2017-01-01 00:15:13</td>
      <td>3134</td>
      <td>3 Ave &amp; E 62 St</td>
      <td>40.763126</td>
      <td>-73.965269</td>
      <td>345</td>
      <td>W 13 St &amp; 6 Ave</td>
      <td>40.736494</td>
      <td>-73.997044</td>
      <td>20153</td>
      <td>Subscriber</td>
      <td>1953.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812177</th>
      <td>316</td>
      <td>2016-12-31 23:51:27</td>
      <td>2016-12-31 23:56:43</td>
      <td>161</td>
      <td>LaGuardia Pl &amp; W 3 St</td>
      <td>40.729170</td>
      <td>-73.998102</td>
      <td>438</td>
      <td>St Marks Pl &amp; 1 Ave</td>
      <td>40.727791</td>
      <td>-73.985649</td>
      <td>26790</td>
      <td>Subscriber</td>
      <td>1958.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812178</th>
      <td>983</td>
      <td>2016-12-31 23:51:29</td>
      <td>2017-01-01 00:07:53</td>
      <td>513</td>
      <td>W 56 St &amp; 10 Ave</td>
      <td>40.768254</td>
      <td>-73.988639</td>
      <td>509</td>
      <td>9 Ave &amp; W 22 St</td>
      <td>40.745497</td>
      <td>-74.001971</td>
      <td>17504</td>
      <td>Subscriber</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>812179</th>
      <td>275</td>
      <td>2016-12-31 23:51:55</td>
      <td>2016-12-31 23:56:31</td>
      <td>539</td>
      <td>Metropolitan Ave &amp; Bedford Ave</td>
      <td>40.715348</td>
      <td>-73.960241</td>
      <td>3091</td>
      <td>Frost St &amp; Meeker St</td>
      <td>40.717640</td>
      <td>-73.948820</td>
      <td>24819</td>
      <td>Subscriber</td>
      <td>1991.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>812180</th>
      <td>2182</td>
      <td>2016-12-31 23:52:04</td>
      <td>2017-01-01 00:28:26</td>
      <td>3360</td>
      <td>Amsterdam Ave &amp; W 79 St</td>
      <td>40.782939</td>
      <td>-73.978652</td>
      <td>3162</td>
      <td>W 78 St &amp; Broadway</td>
      <td>40.783400</td>
      <td>-73.980931</td>
      <td>26842</td>
      <td>Subscriber</td>
      <td>1975.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>812181</th>
      <td>128</td>
      <td>2016-12-31 23:52:34</td>
      <td>2016-12-31 23:54:42</td>
      <td>3438</td>
      <td>E 76 St &amp; 3 Ave</td>
      <td>40.772249</td>
      <td>-73.958421</td>
      <td>3372</td>
      <td>E 74 St &amp; 1 Ave</td>
      <td>40.768974</td>
      <td>-73.954823</td>
      <td>23151</td>
      <td>Subscriber</td>
      <td>1965.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812182</th>
      <td>1126</td>
      <td>2016-12-31 23:52:54</td>
      <td>2017-01-01 00:11:41</td>
      <td>312</td>
      <td>Allen St &amp; Stanton St</td>
      <td>40.722055</td>
      <td>-73.989111</td>
      <td>312</td>
      <td>Allen St &amp; Stanton St</td>
      <td>40.722055</td>
      <td>-73.989111</td>
      <td>23952</td>
      <td>Subscriber</td>
      <td>1997.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812183</th>
      <td>1089</td>
      <td>2016-12-31 23:53:23</td>
      <td>2017-01-01 00:11:33</td>
      <td>3171</td>
      <td>Amsterdam Ave &amp; W 82 St</td>
      <td>40.785247</td>
      <td>-73.976673</td>
      <td>3165</td>
      <td>Central Park West &amp; W 72 St</td>
      <td>40.775794</td>
      <td>-73.976206</td>
      <td>16115</td>
      <td>Subscriber</td>
      <td>1969.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812184</th>
      <td>750</td>
      <td>2016-12-31 23:53:28</td>
      <td>2017-01-01 00:05:58</td>
      <td>3113</td>
      <td>Greenpoint Ave &amp; Manhattan Ave</td>
      <td>40.730260</td>
      <td>-73.953940</td>
      <td>3093</td>
      <td>N 6 St &amp; Bedford Ave</td>
      <td>40.717452</td>
      <td>-73.958509</td>
      <td>24939</td>
      <td>Subscriber</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812185</th>
      <td>1258</td>
      <td>2016-12-31 23:53:42</td>
      <td>2017-01-01 00:14:41</td>
      <td>334</td>
      <td>W 20 St &amp; 7 Ave</td>
      <td>40.742388</td>
      <td>-73.997262</td>
      <td>488</td>
      <td>W 39 St &amp; 9 Ave</td>
      <td>40.756458</td>
      <td>-73.993722</td>
      <td>26811</td>
      <td>Subscriber</td>
      <td>1988.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812186</th>
      <td>121</td>
      <td>2016-12-31 23:55:50</td>
      <td>2016-12-31 23:57:52</td>
      <td>3236</td>
      <td>W 42 St &amp; Dyer Ave</td>
      <td>40.758985</td>
      <td>-73.993800</td>
      <td>478</td>
      <td>11 Ave &amp; W 41 St</td>
      <td>40.760301</td>
      <td>-73.998842</td>
      <td>25923</td>
      <td>Subscriber</td>
      <td>1987.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812187</th>
      <td>441</td>
      <td>2016-12-31 23:56:15</td>
      <td>2017-01-01 00:03:36</td>
      <td>284</td>
      <td>Greenwich Ave &amp; 8 Ave</td>
      <td>40.739017</td>
      <td>-74.002638</td>
      <td>336</td>
      <td>Sullivan St &amp; Washington Sq</td>
      <td>40.730477</td>
      <td>-73.999061</td>
      <td>16185</td>
      <td>Subscriber</td>
      <td>1974.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>812188</th>
      <td>1026</td>
      <td>2016-12-31 23:56:19</td>
      <td>2017-01-01 00:13:26</td>
      <td>281</td>
      <td>Grand Army Plaza &amp; Central Park S</td>
      <td>40.764397</td>
      <td>-73.973715</td>
      <td>3143</td>
      <td>5 Ave &amp; E 78 St</td>
      <td>40.776829</td>
      <td>-73.963888</td>
      <td>18267</td>
      <td>NaN</td>
      <td>1983.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812189</th>
      <td>1747</td>
      <td>2016-12-31 23:56:35</td>
      <td>2017-01-01 00:25:43</td>
      <td>3424</td>
      <td>E 106 St &amp; Lexington Ave</td>
      <td>40.791976</td>
      <td>-73.945993</td>
      <td>3295</td>
      <td>Central Park W &amp; W 96 St</td>
      <td>40.791270</td>
      <td>-73.964839</td>
      <td>19899</td>
      <td>Subscriber</td>
      <td>1970.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>812190</th>
      <td>951</td>
      <td>2016-12-31 23:59:31</td>
      <td>2017-01-01 00:15:23</td>
      <td>3158</td>
      <td>W 63 St &amp; Broadway</td>
      <td>40.771639</td>
      <td>-73.982614</td>
      <td>3169</td>
      <td>Riverside Dr &amp; W 82 St</td>
      <td>40.787209</td>
      <td>-73.981281</td>
      <td>16866</td>
      <td>Subscriber</td>
      <td>1961.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>812191</th>
      <td>1322</td>
      <td>2016-12-31 23:59:56</td>
      <td>2017-01-01 00:21:58</td>
      <td>3263</td>
      <td>Cooper Square &amp; E 7 St</td>
      <td>40.729236</td>
      <td>-73.990868</td>
      <td>498</td>
      <td>Broadway &amp; W 32 St</td>
      <td>40.748549</td>
      <td>-73.988084</td>
      <td>25793</td>
      <td>Subscriber</td>
      <td>1985.0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>13845655 rows × 15 columns</p>
</div>




```python
citibike_2016.to_csv('citibike_2016.csv', sep = ',') 
```


```python

```
