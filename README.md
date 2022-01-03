# PyBer_Analysis

## Overview of the Analysis

The purpose of the analysis was to create a summary DataFrame of the ride-sharing data by city type.  Then, using that DataFrame, create a multiple-line graph that shows the total weekly fares for each city type.  The resources utilized were Pandas and Matplotlib libraries as well as Jupyter Notebooks.

## Results

### Part 1

The first step to complete the analysis was to use the create a summary DataFrame of the ride-sharing data by city type.  To do so, I had to obtain each cell value by creating the following columns: "Total Rides", "Total Drivers", "Total Fares", "Average Fare Per Ride", and "Average Fare Per Driver".  For each column, data had to be imported from the initial data table and grouped by type of city (i.e. urban, suburban, and rural).  The resulting table is as follows:

![Summary DataFrame](https://github.com/amacancio/PyBer_Analysis/blob/main/PyBer_Analysis/Analysis/PyBer_Summary_DataFrame.png)

This DataFrame perfectly visualizes the differences between the types of cities.  The urban cities have 13 times more rides in comparison to rural cities (1,625 vs 125 rides), and the total fares in urban cities are 9 times higher than in rural areas ($39,854.38 vs $4.327.93).  Furthermore, the average fare per ride is 1.4 times less and average fare per driver is 3.4 times less in urban cities compare to rural cities ($24.53 vs $34.62 and $16.57 vs $55.49).  In essence, in the areas where there are fewer rides being taken, there are fewer drivers needed to supply the demand, and as such, each driver is able to charge a higher fare per ride.  The suburban cities are consistently in the middle, although numerically they find themselves closer to the rural areas than the urban areas.

### Part 2

The second step to complete the analysis was to create a multiple-line graph showing the total weekly fares for each city type.  To do this, I had to first create a new DataFrame using the type of city and the date as the indices and the sums of the fares as the values.  Then, after resetting the index, I created the following Pivot Table with the date as the index, the type of city as the columns, and the fares as the values.  

![Fare Sum Pivot Table](https://github.com/amacancio/PyBer_Analysis/blob/main/PyBer_Analysis/Analysis/Fare_Sum_Pivot_Table.png)

From that Pivot Table, I was able to use the loc function to limit the data to the following dates: 2019-01-01 to 2019-04-29.  Then, I used the resample function to display the sum of the fares for each week in the date range, categorized by city type.  Finally, using the object-oriented interface method, I created the multiple-line graph to display the data.

![PyBer Fare Summary Graph](https://github.com/amacancio/PyBer_Analysis/blob/main/PyBer_Analysis/Analysis/PyBer_fare_summary.png)

As you can see in the graph, the fare totals for urban cities demonstrated by the yellow line are significantly higer than the fare totals for the suburban cities (red line) and rural cities (blue line).  If we divide the graph into fifths, the rural fares occupy the bottom section, the suburban fares occupy the second and third sections, and the urban fares occupy the fifth section, which only a slight dip into the fourth section.  Furthermore, you can see the consistency in the fare totals over time for the rural cities versus the variance in totals over time for the suburban and urban cities, presumably based on increased population in those areas for the months leading into summer.

## Summary

In summary, profit by area seems to be dictated by the demand for rides in that area.  The rural cities generate more profit per ride, but the urban areas generate more profit overall.  The higher cost of the rides in the rural areas may be attributed to the distance of each ride, which is a factor that was not examined in this analysis.  In any case, the higher cost per ride means that expanding this area's ridership while maintaining the number of drivers would increase profit exponentially.

Secondly, the urban city areas account for the highest total fare and total rides, which means the necessary demand is present; however, the total number of drivers is greater than the total number of rides.  This saturation of drivers leads to the lower fare per ride and per driver, so reducing the number of drivers would increase the profit per ride.

Lastly, the suburban city type is performing admirably, but total fares seemed to vary widely over time.  Spikes in total fares occured in late February and mid-April.  Further analysis into why these spikes occured is needed, so that whatever factor caused the upward spike can be harnessed and the factor that caused the downward spike can be mitigated.
