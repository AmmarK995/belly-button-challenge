# belly-button-challenge

An interactive dashboard was built to showcase the different levels of navel bacteria amongst individuals across different locations, ethnicities, ages and genders. The sample data was sourced from the samples.json file, and the interactive dashboard itself was built using javascript.

The app.js file is primarily used to code and build the dashboard according to the requirements. And the D3 library is used in the app.js file to read in the samples.json data from the provided URL.

First, a bar chart was designed to display the top 10 OTUs in a given patient. The buildCharts(sample) function defined to help build the bar chart as it filters the sample data from samples.json. The sample.find function was used to extract the OTU IDs, labels and sample values from the sample data. And before the x and y values were defined for the desired chart, the slice (0,10) function was defined to only select the top 10 bacteria samples. The reverse function is also applied to adjust the order of the bacteria samples for the graph. Finally, the bar chart is plotted using the Plotly.newplot funciton.

Next a bubble chart was made to showcase the size of microbial diversity in the given samples. We let the x axis be defined by the OTU IDs, and the y axis was allocated the sample values, to showcase the size of each OTU. The text variable has been set to display the bacterial OTU labels and the marker color has been set to the OTU IDs. Once again, the Plotly.newplot funciton was used to plot this bubble chart.

Next the buildMetadata(sample) function was defined to showcase the individuals' demographic information, such as ethnicity, gender, age, location, etc. We use let the data.metadata funciton extract the relevant data from samples.json. We use the metadata.find fucntion to pull the data for the selected test subject, and where the Test subject ID matches in the sample, the data is stored in the result variable. Then in order to automate the data selection process every time a new test subject is selected in the dropdown, the d3.select function was used to define the metadataPanel variable and the metadataPanel.html("") function was used so that any previously selected data is cleared. Then the Object.entries(result) function converts the applicable metadata into an array and a loop function is used to dynamically create HTML elements and display the data.


The following tools were used for the dashboard:
- D3.js for data fetching and manipulation
- Plotly.js for interactive visualizations
- HTML for layout and styling
- GitHub Pages for deployment