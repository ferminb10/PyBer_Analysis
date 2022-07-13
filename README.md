# PyBer_Analysis
Performing analysis on ride-sharing City data to uncover trends.
## Overview of Project
This weeks challenge helps us build upon our skills learned in the PyBer with Matplotlib module. For deliverables, the client wanted a summary DataFrame of the ride-sharing data by city type. Pandas and Matplotlib was used to create a multi-line graph that shows the total weekly fares for each city type. This report summarizes how the data differs by city type and how those differences can be used by decisionmakers at PyBer.

## Results
Using the Pandas groupby() function with the count() and sum() methods on PyBer DataFrame columns, the the total number of rides, total number of drivers, and the total fares were found for each city type. Then, the average fare per ride and per driver was calculated for each city type. Finally, these parameters were added to a new DataFrame and formatted into columns.

### Pyber Summary
![pyber_summary_df](https://user-images.githubusercontent.com/107658895/178622101-39e389c7-6189-404f-b665-547ba45b0dad.png)
##### Figure 1: Displays the ride and driver summary for each city type.

### Pyber Fare Summary Chart
![PyBer_fare_summary](https://user-images.githubusercontent.com/107658895/178627421-5c465a87-515e-43c6-8906-6e856428d361.png)
##### Figure 2: Displays the Total Fare by city type chart between January 2019 to April 2019



## Summary

Based on the results, provide three business recommendations to the CEO for addressing any disparities among the city types. There is a statement summarizing three business recommendations to the CEO for addressing any disparities among the city types. (4 pt)
Based on the functionality of this script, it's propose can be used for other elections big or small. It would be an interesting parameter to see the geographical location of each person who voted and create a heat map. This will give valuable information of where to do more outreaching to get a more wholistic representation of the local population. The limitations of this dataset are that they only limit a few parameters. It would also be interesting to see the age groups and genders that participated in the election so that the parties can go about better strategizing for target audiences they struggled. 
