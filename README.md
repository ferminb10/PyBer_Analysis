# PyBer_Analysis
Performing analysis on ride-sharing City data to uncover trends.
## Overview of Project
This weeks challenge helps us build upon our skills learned in the PyBer with Matplotlib module. For deliverables, the client wanted a summary DataFrame of the ride-sharing data by city type. Pandas and Matplotlib was used to create a multi-line graph that shows the total weekly fares for each city type. This report summarizes how the data differs by city type and how those differences can be used by decisionmakers at PyBer.

## Results
Using the Pandas groupby() function with the count() and sum() methods on PyBer DataFrame columns, the the total number of rides, total number of drivers, and the total fares were found for each city type. Then, the average fare per ride and per driver was calculated for each city type. Finally, these parameters were added to a new DataFrame and formatted into columns.

The differences in ride-sharing data among the different city types are that there are more total rides in Urban areas, then follows Suburban and Rural, respectfully. Ride-sharing data, shown in Figure 1, include the total rides, total drivers, total fares, average fare per ride and driver, and total fare by city type.
### Pyber Summary
![pyber_summary_df](https://user-images.githubusercontent.com/107658895/178622101-39e389c7-6189-404f-b665-547ba45b0dad.png)
##### Figure 1: Displays the summary for each city type.

The client wanted wanted to a visual showing a multiple-line chart of total fares for each city type through January 2019 to April 2019.

### Pyber Fare Summary Chart
![PyBer_fare_summary](https://user-images.githubusercontent.com/107658895/178627421-5c465a87-515e-43c6-8906-6e856428d361.png)
##### Figure 2: Displays the Total Fare by city type chart between January 2019 to April 2019.



## Summary
A major recommendation is to incentivize more drivers to work in rural areas since the average fare per driver ($55.49) is 3.35 times higher than in Urban areas ($16.57). Many drivers might not know this information this is why they might not want to drive to these city types. You can tell this city type needs the drivers since the amount of rides exceeds the number of drivers.  A second recommnendation would be to investigate the trendlines for the times of the year where traveling and vacations is most prominent like during the summer time. The final recommendation would be to incorperate the average fare times. The rural city types are a lot more open than Urban zones. This might be a key factor when thinking about the rising gas prices. The limitations of this dataset are that they only limit to a little more than a quarter of the year. It would also be interesting to see how the trendlines follow during the Summer, Fall and end of the year.
