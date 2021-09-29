# Bike-Ridership

Visual analysis of Boston’s bicycle sharing system

<font size="5">**Visualization Technique**</font>

As a frequent user of Boston's bicycle sharing system, known as Bluebikes, I have always been interested in the data about ridership. A company named Motivate operates this network of bikes across the Boston area. Users walk up to a docking station, pay and unlock the bicycle, then ride it to a destination and dock in another station. 

Motivate publishes monthly data about each ride, from start time, end time, duration and more. I'm curious about ridership patterns and how they differ by day and hour. After patterns are identified, the next steps could include building a prediction model to determine optimal bicycle allocation. Knowing how many bicycles are needed at stations at certain hours throughout the week would ensure supply meets demand. 

For this visualization I have chosen a heatmap. A heatmap is a data visualization technique that displays numeric tabular data as a color-encoded matrix, where the color of each cell depends upon its value. Heatmaps are great for identifying trends in large amounts of data at a glance, particularly when the data is ordered and there is clustering. Heatmaps should not be used when comparing multiple groups of observations. In this case, comparing ridership data in June vs July.

<font size="5">**Visualization Library**</font>

The library I have chosen to visualize the heatmap with is Seaborn. This library generates lovely heatmaps and offers a great balance between effort and beauty. Right out of the box the heatmap is plotted with an excellent color scheme and style parameters which allow for more effective visuals and thus analysis. It's declarative nature allows for more focus on what the elements of the plot mean, rather than how to draw them. It is also closely integrated with pandas data structures in the Jupyter Notebook. One can easily build a plot referencing columns from a DataFrame. Seaborn alone cannot build interactive visualiztions which poses limitations. Though I am not creating an interactive visualiztion and that is partly why I opted for Seaborn over other libraries such as Bokeh and Plotly. Seaborn provides necessary emphasis on aesthetics for heatmaps, as well as ease of creation.

Seaborn is an open-source [Python](https://www.python.org/downloads/) visualization library built on top of matplotlib. 

To install Seaborn, type the following command:

`pip install seaborn`

(Note: The following are required dependencies: numpy, scipy, pandas, matplotlib)

<font size="5">**Demonstration**</font>

The data comes from [June 2019](https://s3.amazonaws.com/hubway-data/index.html) on the [Bluebikes website](https://www.bluebikes.com/system-data). I wanted to select a warm month and prior to COVID-19, both in an effort to capture a large dataset. It includes the following variables:

- Trip Duration (seconds)
- Start Time and Date
- Stop Time and Date
- Start Station Name & ID
- End Station Name & ID
- Bike ID
- User Type (Casual = Single Trip or Day Pass user; Member = Annual or Monthly Member)
- Birth Year
- Gender, self-reported by member (Zero=unknown; 1=male; 2=female)

The website states that data has been processed to remove trips that are taken by staff as they service and inspect the system; and any trips that were below 60 seconds in length (potentially false starts or users trying to re-dock a bike to ensure it was secure).

For this visualization we will be focusing on Trip Duration (seconds) as a means for building the neccesary pivot table, and Start Time and Date which will ultimately serve as both the x and y-axis.

Let's get to it...
