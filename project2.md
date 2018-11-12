###Project 2: Building Age in Baltimore

For this project, I decided to continue my theme from project 1 and look at the age of properties in Baltimore. I have displayed here a gif showing the oldest building year in each area of a hex grid as well as the buildings in each year range. Together, the images show urban development in the city, highlighting areas with modern buildings and areas with older ones. Some trends to notice are that many of the oldest buildings are found near the city center and the newest are most common along the waterfront in the harbor.

![Building Age in Baltimore GIF]
(jfreck.github.io/blob/master/project2gif.gif)

**Steps to completion**

• Property polygons queried to only show year_build and usegroup "select objectid, year_build, usegroup, ST_Buffer(GEOMETRY, 0) from property2 where year_build>0"

• Create centroids and hex grid (600 meters)

• Join Attributes by Location (Summary) - join centroids to hex grid using year_build min.

• Take each hex and display them in 8 categories, with building polygons for each year range showing up as well.

• In map view, add a textbox with the year range, then export as an image 9 times, progressively adding each category into each layer.

• Combine the images together into an animated gif (I used GIMP).
I was easily able to create a very nice gif without any python whatsoever, and I believe that doing any of what I did through python would be much more complicated and convoluted.
