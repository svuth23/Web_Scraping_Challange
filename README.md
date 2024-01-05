# Web_Scraping_Challange
## MARS News And  Weather Data

### This Analysis project is divided in to two parts. 
Deliverable 1: Scrape titles and preview text from Mars news articles.
Deliverable 2: Scrape and analyse Mars weather data, which exists in a table.

### external links/sites/data used are:
for part 1 program : https://static.bc-edx.com/data/web/mars_news/index.html
for part 2  program : https://static.bc-edx.com/data/web/mars_facts/temperature.html

# Relevant libraries
from splinter import Browser
from bs4 import BeautifulSoup
import matplotlib
import pandas 

# Part 1: Scrape Titles and Preview Text from Mars News
1. visit the Mars news siteLinks to an external site.. Inspect the page to identify which elements to scrape.
2.Create a Beautiful Soup object and use it to extract text elements from the website.
Extract the titles and preview text of the news articles that you scraped. Store the scraping results in Python data structures as follows:
Store each title-and-preview pair in a Python dictionary and, give each dictionary two keys: title and preview.
The result looks like :

{'title': "NASA's MAVEN Observes Martian Light Show Caused by Major Solar Storm", 
 'preview': "For the first time in its eight years orbiting Mars, NASA’s MAVEN mission witnessed two different types of ultraviolet aurorae simultaneously, the result of solar storms that began on Aug. 27."}

3.Store all the dictionaries in a Python list.
4.Print the list in your notebook.

# part2:
#### steps to get results
### Step 1: Visit the Website
 Inspect the page to identify which elements to scrape.
# https://static.bc-edx.com/data/web/mars_facts/temperature.html

### Step 2: Scrape the Table
Create a Beautiful Soup object and use it to scrape the data in the HTML table.
 Create a Beautiful Soup Object
 Extract all rows of data


### Step 3: Store the Data
Assemble the scraped data into a Pandas DataFrame. The columns should have the same headings as the table on the website. Here’s an explanation of the column headings:

id: the identification number of a single transmission from the Curiosity rover
terrestrial_date: the date on Earth
sol: the number of elapsed sols (Martian days) since Curiosity landed on Mars
ls: the solar longitude
month: the Martian month
min_temp: the minimum temperature, in Celsius, of a single Martian day (sol)
pressure: The atmospheric pressure at Curiosity's location

Create an empty list,Loop through the scraped data to create a list of rows.
Create a Pandas DataFrame by using the list of rows and a list of the column names.
Confirm DataFrame was created successfully

### Step 4: Prepare Data for Analysis
Examine the data types that are currently associated with each column. If necessary, cast (or convert) the data to the appropriate datetime, int, or float data types.
### Step 5: Analyse the Data
Analyse your dataset by using Pandas functions to answer the following questions:
### 1. How many months are there on Mars?
month
1     174
2     178
3     192
4     194
5     149
6     147
7     142
8     141
9     134
10    112
11    138
12    166
Name: month, dtype: int64
### 2. How many Martian days' worth of data are there?
1867
### 3. What is the average low temperature by month?
Find the average the minimum daily temperature for all of the months.
Plot the results as a bar chart.
month
1    -77.160920
2    -79.932584
3    -83.307292
4    -82.747423
5    -79.308725
6    -75.299320
7    -72.281690
8    -68.382979
9    -69.171642
10   -71.982143
11   -71.985507
12   -74.451807
Name: min_temp, dtype: float64
### Plot the average temperature by month
![image](https://github.com/svuth23/Web_Scraping_Challange/assets/136966712/c32cd60f-9e25-4768-b48a-b5ce9239b5b0)

### Identify the coldest and hottest months in Curiosity's location
Plot the results as a bar chart.
![image](https://github.com/svuth23/Web_Scraping_Challange/assets/136966712/86c6e6a3-ce2d-469b-95a3-88724017499e)


#### 4. Average pressure by Martian month
Which months have the lowest and the highest atmospheric pressure on Mars? To answer this question:
Find the average the daily atmospheric pressure of all the months.
month
1     862.488506
2     889.455056
3     877.322917
4     806.329897
5     748.557047
6     745.054422
7     795.105634
8     873.829787
9     913.305970
10    887.312500
11    857.014493
12    842.156627
Name: pressure, dtype: float64
### Plot the average pressure by month
![image](https://github.com/svuth23/Web_Scraping_Challange/assets/136966712/62e60f02-5650-4e10-948c-6baa8371983e)

### 5. How many terrestrial (earth) days are there in a Martian year?
To answer this question:
Consider how many days elapse on Earth in the time that Mars circles the Sun once.
Visually estimate the result by plotting the daily minimum temperature.
![image](https://github.com/svuth23/Web_Scraping_Challange/assets/136966712/d0d6c34f-266a-4030-9f1b-f4f6c0a84e20)

On average, the third month has the coldest minimum temperature on Mars, and the eighth month is the warmest. But it is always very cold there in human terms!
Atmospheric pressure is, on average, lowest in the sixth month and highest in the ninth.
The distance from peak to peak is roughly 1425-750, or 675 days. A year on Mars appears to be about 675 days from the plot. Internet search confirms that a Mars year is equivalent to 687 earth days.

# Step 6: Save the Data
Export the DataFrame to a CSV file.
Mars details
