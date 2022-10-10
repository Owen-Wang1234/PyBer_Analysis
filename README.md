# PyBer_Analysis

## Project Overview
The senior levels in PyBer have requested an analysis of the collected city and ride data to present findings and recommendations to the CEO.

The data covers the first four months and later of 2019 and includes the following:
1. The cities
2. Their types (Urban, Suburban, or Rural)
3. The number of drivers in each city
4. The time the rides took place
5. The corresponding ID numbers of those rides
6. The fares collected for those rides.

The analysis includes statistical summaries, plots of analytical results, and the recommendations based on them.

## Resources
- Data Sources:
  1. city_data.csv
  2. ride_data.csv

- Software: This analysis was run within the "PythonData" environment, which uses the following:
  1. Python 3.7.13
  2. Jupyter Notebook 6.4.8
  3. Pandas 1.3.5
  4. Numpy 1.21.5
  5. Matplotlib 3.5.1

## Analysis Results

### Analysis Process
The data files were imported into data frames and checked for quality; neither of them had any null values. With the quality assured, the city and ride data were merged into a united data frame from which three data frames were extracted - one for each city type.

With these three data frames, the first chart assembled was a scatter plot mapping the ride count, the average fare, and the driver count for each city. The data for this plot came from taking the ride counts, the average fares, and the driver counts from each of the three data frames while they were grouped by the city name. Next, summary descriptions were taken from the three data frames using Pandas and Numpy, focusing on the ride counts, the average fares, and the driver counts. These were then collected to build a series of box-and-whisker plots. Afterwards, the fares, the ride counts, and the driver counts were all added up for each city type; and these sums were plotted in pie charts to show the percentage distribution by city type.

For the Challenge portion, the whole 2019 data was first summarized by using the sums of rides, driver counts, and fares to calculate the overall average fare per ride and overall average fare per driver for each city type. Then, the fares were all organized by date and city type and then resampled into a weekly basis from the beginning of January 1, 2019 to the end of April 27, 2019. The results were plotted in a line chart depicting the total fare over the first four months of 2019 by city type.

### Charts and Findings

#### Scatter Plot
The first chart is the scatter plot mapping the ride count, the average fare, and the driver count for each city:

![Scatter Plot for Ride Count, Average Fare, and Driver Count Per City](https://github.com/Owen-Wang1234/PyBer_Analysis/blob/main/analysis/Fig1.png)

The ride count is at the x-axis and the average fare is at the y-axis; although the note is not visible in the figure, that note does mention that the driver count determines the size of the data points. The rural cities take up the left side of the ride counts with average fares scattered across the value range. The suburban cities cover both the middle sector of the ride counts and the middle sector of the average fare value range. The urban cities are in the middle and right side of the graph and stay in the lower half of the fare value range. The three groups overlap inside the 10 - 15 rides per city range and the $25 - $30 average fare per city range. Although the three groups have varying numbers of drivers per city, the rural cities generally trend toward fewer drivers while urban cities generally trend toward more drivers.

#### Box-and-Whisker Plots
The first box-and-whisker plot covers some statistics about the ride counts for each city type.

![Box-and-Whisker Plot for the Ride Counts by City Type](https://github.com/Owen-Wang1234/PyBer_Analysis/blob/main/analysis/Fig2.png)

With the chart and some statistical analysis, the ride count summary is:

| City Type | Mean | Median | Mode | Min | Max |
| --- | ---: | ---: | --- | ---: | ---: |
| Urban | 24.62 | 24 | 22 and 25 (7 times each) | 12 | 39 |
| Suburban | 17.36 | 17 | 17 (7 times) | 9 | 27 |
| Rural | 6.94 | 6 | 6 (5 times) | 3 | 12 |

- One point of interest is that the Urban group has an outlier in the maximum value of 39 rides. The city with this value is West Angela.
- Despite that outlier, the mean values come quite close to the median values; primarily because the mode either matches the median or is close enough to the median to pull the average.
- The urban group has the mean and median values almost **four** times as large as those of the rural group. The suburban group has those values almost **three** times as large as the rural values. The suburban group has those values almost **70.83%** of those of the urban group.

The next box-and-whisker plot covers some statistics about the ride fares for each city type.

![Box-and-Whisker Plot for the Ride Fares by City Type](https://github.com/Owen-Wang1234/PyBer_Analysis/blob/main/analysis/Fig3.png)

With the chart and some statistical analysis, the ride fare summary is:

| City Type | Mean | Median | Mode | Min | Max |
| --- | ---: | ---: | --- | ---: | ---: |
| Urban | $24.53 | $24.64 | $22.86 (5 times) | $4.05 | $44.97 |
| Suburban | $30.97 | $30.75 | $17.99 (3 times) | $12.05 | $49.96 |
| Rural | $34.62 | $37.05 | $37.05 (2 times) | $10.11 | $58.55 |

- The mean values come fairly close to the median values, but one interesting observation is that the suburban mode is not near the mean or median compared to the urban mode and the rural mode. One theory is that there are a fair number of high value fares that skewed the mean and median away.
- The rural group has the greatest average, median, and maximum fare values, and the urban group has the lowest average, median, and maximum fare values. Interestingly the urban group has the lowest minimum fare value, which might be a result of that ride only traveling a few blocks.

The last box-and-whisker plot covers some statistics about the driver counts for each city type.

![Box-and-Whisker Plot for the Driver Counts by City Type](https://github.com/Owen-Wang1234/PyBer_Analysis/blob/main/analysis/Fig4.png)

With the chart and some statistical analysis, the driver count summary is:

| City Type | Mean | Median | Mode | Min | Max |
| --- | ---: | ---: | --- | ---: | ---: |
| Urban | 37 | 37 | 39 (86 times) | 3 | 73 |
| Suburban | 14 | 16 | 20 (79 times) | 1 | 25 |
| Rural | 4 | 4 | 1 (32 times) | 1 | 9 |

- The statistic calculations here reflect the weighted statistics involving the driver count and ride count of each city.
- The mean values nearly match the median values except for the suburban group.
- The mean and median values for the urban group is nearly **nine** times as large as those of the rural group. The suburban group has those values almost **four** times as large as the rural values. The suburban group has those values almost **40%** of those of the urban group.

#### Pie Charts
The fares, ride count, and driver count are all added up while grouped by city type, and the results are plotted into these pie charts.

![Pie Chart for the Percentage of Total Fares by City Type](https://github.com/Owen-Wang1234/PyBer_Analysis/blob/main/analysis/Fig5.png)

![Pie Chart for the Percentage of Total Rides by City Type](https://github.com/Owen-Wang1234/PyBer_Analysis/blob/main/analysis/Fig6.png)

![Pie Chart for the Percentage of Total Drivers by City Type](https://github.com/Owen-Wang1234/PyBer_Analysis/blob/main/analysis/Fig7.png)

Prior to creating the pie charts, one thing of note is that there are 66 Urban cities, 36 Suburban cities, and 18 Rural cities for a total of 120 cities. The resulting distributions are summarized as so:

| | Urban | Suburban | Rural | 'Total' |
| ---: | ---: | ---: | ---: | ---: |
| Cities | 66 | 36 | 18 | '120' |
| | 55% | 30% | 15% | '100%' |
| Fares | $39,854.38 | $19,356.33 | $4,327.93 | '$63,538.64' |
| | 62.7% | 30.5% | 6.8% | '100%' |
| Rides | 1,625 | 625 | 125 | '2,375' |
| | 68.4% | 26.3% | 5.3% | '100%' |
| Drivers | 2,405 | 490 | 78 | '2,973' |
| | 80.9% | 16.5% | 2.6% | '100%' |

## General Summary