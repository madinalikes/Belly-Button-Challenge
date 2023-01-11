# Belly-Button-Challenge

<img width="573" alt="image" src="https://user-images.githubusercontent.com/111404552/211166335-37c828f1-4ac2-4265-9280-9ef0c6850b3a.png">


## **Background**

In this assignment, an interactive dashboard was built to explore the Belly Button Biodiversity dataset, which catalogs the microbes that colonize human navels in JSON format.

The dataset reveals that a small handful of microbial species (also called operational taxonomic units, or OTUs, in the study) were present in more than 70% of people, while the rest were relatively rare.

Demographics information is dynamically populated based upon a user-selected test subject ID. A bar chart, bubble chart and a bonus gauge chart also update once the ID is changed. Code has been written using Plotly, JavaScript, HTML, CSS, and D3.js.

All CSS, JS and images required are under the static folder. The main HTML file index.html is in the root folder of the Github repo.


## **Plotly**
---
The ask was to retrieve test subject demographics, and draw a bar chart and bubble chart displaying each individual's samples. This was done as follows:

Read in samples.json using the D3 library

Retrieve metadata info for each test subject and display this in the form of an unordered list item as a key-value pair on the dashboard.

Get required data for plotting, including sample_values, otu_ids and otu_labels which were used to create a trace and plot the bar chart.

Since the task was to only plot the top 10 values, the three arrays were sliced and reversed to display the chart as below.

<img width="210" alt="image" src="https://user-images.githubusercontent.com/111404552/211131052-c6551d43-e990-4098-9b14-ad92ec3bc0ed.png">

The entire sample arrays were used to plot a bubble chart.

<img width="532" alt="image" src="https://user-images.githubusercontent.com/111404552/211131074-91a5b7a5-e4d4-47b6-8c58-1ac4f4f5b75c.png">

The bonus challenge was to create a gauge chart. Using the documentation, an indicator trace was created with wfreq as the value for plotting.

Any null values were given a value of zero.

The gauge chart accounts for weekly washing frequency values ranging from 0-9.

The default bar that indicates the value was set to transparent so that a needle pointer could be used on the chart.

To plot the pointer correctly, I referred to this source which explains the math behind the pointer angles.

<img width="187" alt="image" src="https://user-images.githubusercontent.com/111404552/211131091-054c2972-b374-40fd-a13d-8a4733efd18b.png">

>A function called plotCharts(id) was created that would take in a test subject ID as a parameter and plot all the above charts.

>A function called resetData() clears all the divs of the charts and demographic info.

>Another function init() calls the resetData() function, populates the dropdown menu with test subject IDs from the dataset and displays data of the first subject as a starting point.

>Everytime a new ID is selected from the dropdown (on change), an optionChanged(this.value) function is called, that resets the data once again and calls the plotCharts() function.



