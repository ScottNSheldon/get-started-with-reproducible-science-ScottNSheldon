---

# Get started with open reproducible science!

[Open reproducible science](https://www.earthdatascience.org/courses/intro-to-earth-data-science/open-reproducible-science/get-started-open-reproducible-science/) makes scientific methods, data and outcomes available to everyone. That means that *everyone* who wants should be able to **find**, **read**, **understand**, and **run** your workflows for themselves.

<img alt-text="Components of open science - accessible, reproducible, inclusive" src="https://www.earthdata.nasa.gov/s3fs-public/2021-11/Circle_Diagram_UPDATE_2.jpg?VersionId=pFRniRpjtgc_MEXUJKi9_sXLoMsSX.pB" width=500 />

 > Image from https://www.earthdata.nasa.gov/esds/open-science/oss-for-eso-workshops

Few if any science projects are 100% open and reproducible (yet!). However, members of the open science community have developed open source tools and practices that can help you move toward that goal. You will learn about many of those tools in [the Intro to Earth Data Science textbook](https://www.earthdatascience.org/courses/intro-to-earth-data-science/). Don't worry about learning all the tools at once -- we've picked a few for you to get started with.

1. Open reproducible science is science that uses accessible and transparent methodology with publicly available data that allows for collaboration in which anyone can process the data and reproduce the same outcome.
  2. Git and Github supports open reproducible science by allowing users to share code and allow others to fork off of a previously creaded repository. Individuals can access the data used to process data and can create their own repository using that data.
  3. This Juypter Notebook file does not have a machine-readable name. Machine readble names often do not contain spaces and instead dashes or underscores are used.

I can write clean code by:
  1. Using expressive names in the code to make it easier to read
  2. Write code that can be repeated rather than repeating code
  3. Using syntax standards to allow for readablility


Advantages of clean code include:
  1. It's easier for someone new to read and understand your code
  2. It is more efficient 
  3. It shows documentation much better


```python
#can't get this to work :(
import pandas as pd


```

Once you have run the cell above and imported `pandas`, **run the cell below**. It is a test cell that will tell you if you completed the task successfully. If a test cell isn't working the way you expect, check that you ran your code **immediately before** running the test.


```python
# DO NOT MODIFY THIS TEST CELL
points = 0
try:
    pd.DataFrame()
    points += 5
    print('\u2705 Great work! You correctly imported the pandas library.')
except:
    print('\u274C Oops - pandas was not imported correctly.')
print('You earned {} of 5 points for importing pandas'.format(points))
```

    ✅ Great work! You correctly imported the pandas library.
    You earned 5 of 5 points for importing pandas


1. Climate at a Glance is maintained by National Centers of Envrionmental Information at the request from NOAA. The data is taken outside the Rapid City Regional Airport and that station is part of the North American Dataset (NorthAm). The units of maximum temperature is taken in degrees farenheit.

2. NOAA National Centers for Environmental information, Climate at a Glance: City Time Series, published April 2023, retrieved on April 27, 2023 from https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/time-series


```python
rapid_city_temp_url = ("https://www.ncei.noaa.gov/access/monitoring"
                       "/climate-at-a-glance/city/time-series"
                       "/USW00024090/tmax/ann/2/1949-2023.csv")

rapid_city_temp_url
```




    'https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/time-series/USW00024090/tmax/ann/2/1949-2023.csv'




```python
# DO NOT MODIFY THIS TEST CELL
resp_url = _
points = 0

if type(resp_url)==str:
    points += 3
    print('\u2705 Great work! You correctly called your url variable.')
else:
    print('\u274C Oops - your url variable was not called correctly.')

if len(resp_url)==117:
    points += 3
    print('\u2705 Great work! Your url is the correct length.')
else:
    print('\u274C Oops - your url variable is not the correct length.')

print('You earned {} of 6 points for defining a url variable'.format(points))
```

    ✅ Great work! You correctly called your url variable.
    ✅ Great work! Your url is the correct length.
    You earned 6 of 6 points for defining a url variable



```python
#download
rapid_city_df = pd.read_csv(rapid_city_temp_url, header = 3, names = ['Date','Value'] )
rapid_city_df

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
      <th>Date</th>
      <th>Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>194912</td>
      <td>58.2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>195012</td>
      <td>55.4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>195112</td>
      <td>54.3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>195212</td>
      <td>59.1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>195312</td>
      <td>59.6</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>201812</td>
      <td>57.4</td>
    </tr>
    <tr>
      <th>70</th>
      <td>201912</td>
      <td>54.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>202012</td>
      <td>61.8</td>
    </tr>
    <tr>
      <th>72</th>
      <td>202112</td>
      <td>62.1</td>
    </tr>
    <tr>
      <th>73</th>
      <td>202212</td>
      <td>60.9</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [198562.0, 59.04]:
    points += 4
    print('\u2705 Great work! You correctly downloaded data.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for downloading data'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ✅ Great work! You correctly downloaded data.
    You earned 5 of 5 points for downloading data


  > HINT: Check out the `type()` function below - you can use it to check that your data is now in `DataFrame` type object


```python
# Check that the data was imported into a pandas DataFrame
type(rapid_city_df)
```




    pandas.core.frame.DataFrame




```python
# ncei has wacky years
rapid_city_df.iloc[:,0] = rapid_city_df.iloc[:,0] // 100
rapid_city_df

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
      <th>Date</th>
      <th>Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>58.2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>55.4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>54.3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>59.1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>59.6</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>57.4</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>54.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>61.8</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>62.1</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>60.9</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [1985.5, 59.04]:
    points += 4
    print('\u2705 Great work! You correctly cleaned up years.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for cleaning up years'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ✅ Great work! You correctly cleaned up years.
    You earned 5 of 5 points for cleaning up years


<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an EXTRA CHALLENGE? Modify the code to be **more expressive**.

Rewrite the code below to select columns by **name** instead of by **index**. You might find the [pandas User Guide section on slicing and dicing](https://pandas.pydata.org/docs/user_guide/indexing.html) to be useful. However - don't worry if you can't figure this out yet! We're going to talk a lot about how to use pandas `DataFrame`s. 

YOUR ANSWER HERE


```python
#convert to celcius
rapid_city_df.iloc[:,1] = (rapid_city_df.iloc[:,1] - 32) * 5 / 9
rapid_city_df

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
      <th>Date</th>
      <th>Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>14.555556</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>13.000000</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>12.388889</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>15.055556</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>15.333333</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>14.111111</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>12.611111</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>16.555556</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>16.722222</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>16.055556</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [1985.5, 15.02]:
    points += 4
    print('\u2705 Great work! You correctly converted to Celcius.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for converting to Celcius'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ✅ Great work! You correctly converted to Celcius.
    You earned 5 of 5 points for converting to Celcius


<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an **EXTRA CHALLENGE**?
  1. As you did above, rewrite the code to be more expressive
  2. Using the code below as a framework, write and apply a **function** that converts to Celcius.
     > **Functions** let you reuse code you have already written
  
  3. You should also rewrite this function name to be more expressive.
  
        ```python
        def convert(temperature):
            """Convert temperature to Celcius"""
            return temperature # Put your equation in here

        dataframe['temp_c'] = dataframe['temp_f'].apply(convert)
        ```


```python
rapid_city_df.plot(x='Date', y='Value',
                   xlabel='Date',
                   ylabel='Temperature (°C)',
                   title= 'Maximum Temperature of Rapid City, SD in Celcius')

```




    <Axes: title={'center': 'Maximum Temperature of Rapid City, SD in Celcius'}, xlabel='Date', ylabel='Temperature (°C)'>




    
![png](Get_Started_with_Open_Reproducible_Science_files/Get_Started_with_Open_Reproducible_Science_21_1.png)
    


**THIS ISN'T THE END! Don't forget to complete the next task where you will describe your plot**
    
<img src="https://www.nps.gov/pais/learn/nature/images/NPS-KempsRidley-Hatchlings.JPG" height=150 style="padding: 1em; border-style: solid; border-color: grey;" />

> Image source: https://www.nps.gov/pais/learn/nature/hatchlingreleases.htm

<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an **EXTRA CHALLENGE**?

There are many other things you can do to customize your plot. Take a look at the [pandas plotting galleries](https://pandas.pydata.org/docs/user_guide/visualization.html) and the [documentation of plot](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.plot.html) to see if there's other changes you want to make to your plot. Some possibilities include:
  * Remove the legend since there's only one data series
  * Increase the figure size
  * Increase the font size
  * Change the colors
  * Use a bar graph instead (usually we use lines for time series, but since this is annual it could go either way)
  * Add a trend line

## YOUR RAPID CITY PLOT HEADLINE HERE
Over the past 70 years, the maximum annual temperatures in Rapid City, SD have become more variable year to year with some of the lowest and highest years occuring the the past decade. However, the maximum annual temperature has be trending upwards to warmer temperatures which make indicate an impact of a rapidly changing climate.

**THIS ISN'T THE END EITHER! Don't forget to reproduce your analysis in a new location!**

<img src="https://static.independent.co.uk/s3fs-public/thumbnails/image/2008/12/26/20/107000.jpg" height=150 style="padding: 1em; border-style: solid; border-color: grey;" >

> Image source: https://www.independent.co.uk/climate-change/news/by-the-left-quick-march-the-emperor-penguins-migration-1212420.html

## Your turn: pick a new location and/or measurement to plot
Below, recreate the workflow you just did in a place that interests you OR with a different measurement. See the instructions above fore how to get your URL. You will need to make your own new Markdown and Code cells below this one.


```python
grand_junction_temp_url = ("https://www.ncei.noaa.gov/access/monitoring/"
                           "climate-at-a-glance/city/time-series/"
                           "USW00023066/tmax/12/12/1949-2023.csv")

grand_junction_temp_url
```




    'https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/time-series/USW00023066/tmax/12/12/1949-2023.csv'




```python
#download
grand_junction_df = pd.read_csv(grand_junction_temp_url, header = 3, names = ['Date','Value'])
grand_junction_df
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
      <th>Date</th>
      <th>Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>194912</td>
      <td>62.6</td>
    </tr>
    <tr>
      <th>1</th>
      <td>195012</td>
      <td>65.1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>195112</td>
      <td>62.5</td>
    </tr>
    <tr>
      <th>3</th>
      <td>195212</td>
      <td>63.6</td>
    </tr>
    <tr>
      <th>4</th>
      <td>195312</td>
      <td>64.8</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>201812</td>
      <td>68.1</td>
    </tr>
    <tr>
      <th>70</th>
      <td>201912</td>
      <td>65.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>202012</td>
      <td>68.1</td>
    </tr>
    <tr>
      <th>72</th>
      <td>202112</td>
      <td>68.0</td>
    </tr>
    <tr>
      <th>73</th>
      <td>202212</td>
      <td>66.6</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
type(grand_junction_df)
```




    pandas.core.frame.DataFrame




```python
grand_junction_df.iloc[:,0] = grand_junction_df.iloc[:,0] // 100
grand_junction_df
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
      <th>Date</th>
      <th>Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>62.6</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>65.1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>62.5</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>63.6</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>64.8</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>68.1</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>65.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>68.1</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>68.0</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>66.6</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
grand_junction_df.iloc[:,1] = (grand_junction_df.iloc[:,1] - 32) * 5 / 9
grand_junction_df
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
      <th>Date</th>
      <th>Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>17.000000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>18.388889</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>16.944444</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>17.555556</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>18.222222</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>20.055556</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>18.722222</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>20.055556</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>20.000000</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>19.222222</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
grand_junction_df.plot(x='Date', y='Value',
                   xlabel='Date',
                   ylabel='Temperature (°C)',
                   title= 'Maximum Temperature of Grand Junction, CO in Celcius')
```




    <Axes: title={'center': 'Maximum Temperature of Grand Junction, CO in Celcius'}, xlabel='Date', ylabel='Temperature (°C)'>




    
![png](Get_Started_with_Open_Reproducible_Science_files/Get_Started_with_Open_Reproducible_Science_31_1.png)
    


The maximum temperature of Grand Junction, CO has been trending upwards since the 1970s which could be an indication of the effect of a rapidly changing climate. Variability in the maximum annual temperature has changed in recent years, as in the 1950s to the mid-1980s, the temperature fluctuated often between highs and lows, however in recent years, there is a pattern where there are several warmer years occuring back to back before one or two cooler years. This pattern could coincide with ENSO patterns.
