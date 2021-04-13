# 6.859 a4-asylum-journeys
## Requests for Asylum by Syrian Refugees Visualization Writeup
Ahmed Elbashir & Belinda Shi

### Design Rationale
	Our visualization represented the increase in outflow of asylees from Syria during the refugee crisis that began with the Syrian Civil War. Our primary visualization is a map with paths drawn from Syria to countries where requests for asylum were made in a particular year. Mousing over a country provides a tooltip with statistics on the requests for asylum that year, and a slider allows you to change the year being viewed. A line chart above the map visualizes the total number of asylum requests over time, and a blue ball traverses the line and matches up with the year selected on the slider. Our dataset recorded yearly requests for asylum broken down by country of origin and country of asylum for the past 20 years.
	For our visual encodings, we chose to represent this data on a map as it is the most natural and familiar way to visualize data on a country-level, with paths outgoing from Syria being easy to follow and representing migrant flow well. The line chart also supplemented the map visualization with a readily perceptible visual of the number of asylees over time, showing where the crisis peaked. We chose to animate the paths because it catches the attention of the viewer, shows the directionality of travel if the asylum requests are granted and asylees go to the new country, and we chose to have the lines re-appear on every year selection to emphasize that the data changes from year to year. Initially, we made the thickness of the lines proportional to the number of asylum requests to visualize magnitude, but we found this was difficult to discern and instead switched to coloring in the countries with greater intensity depending on the number of asylum requests they decided on. 
	Our use of color was deliberate, as we chose our dark green color for the paths and highlighted countries to be the green in the Syrian flag, and made the line chart dark green to match. The default gray of the map placed the focus on the paths and the countries that did receive more asylum requests. When we chose to color in countries based on the number of asylum requests, our output ranged from the default unfilled gray to the dark green of the paths, and we changed our scaling back and forth from linear to logarithmic. Ultimately, because linear scaling resulted in almost all countries appearing gray with imperceptible differences with the exception of Germany and Sweden in a span of about 2 years where the asylum requests spike to a level nearly 3x that of all other records, we chose to use logarithmic scaling and accepted that it could be numerically misleading in exchange for a much more satisfying effect of shading in of the world as time increases with still noticeable differences in color where the magnitude changes are the most extreme. We also animated the transition in color of countries, as we believe the slow color fade portrayed the feeling of changing request numbers through time.
	For interactive elements, we used a slider to let them choose the year to visualize to see how the scale of the crisis changed over time, and we used mouseover countries to make the tooltip appear. Originally it required mousing over the paths, which we changed because it was difficult to do, and we decided to use mouseover instead of mouse click as we thought it was more natural and burdened the user to discover the interaction less. We have “Slide to change the year” text when the page initially loads to explain that interaction element. After the prototype, we also added the ability to scroll and drag through the map, greatly enhancing the ability to differentiate requests made in Europe and in other geographic regions with clusters of small countries. 
	We considered several alternatives while designing this visualization, some of which we’ve already discussed. We considered including more countries or crises and allowing the user to select one of a few, as was suggested in our feedback, but decided the visualization was more powerful with a narrower scope and greater focus. We also considered including further visualizations in the tooltip based on the asylum request status, such as a pie chart of the status requests, but felt it would be misleading 
### Development Process
	Overall, Ahmed worked on the map paths, the country coloring, and the tooltip interaction, and Belinda worked on the data manipulation, slider, line chart, and animation. We needed to add a geojson file to our repository in order to get the shapes of countries, as well as a supplementary dataset that includes the midpoints of each country. We joined the midpoint data with our main dataset through three letter country codes. Then we filtered the asylum data to only include asylees from Syria, and aggregated the number of requests for each destination country per year, since there are different rows for different types of requests. In total, we spent about 12 hours each, for a total of 24 hours, developing our application, and the aspect that took the most time was joining and aggregating the data to result in the format we needed.
	

