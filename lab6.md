Lab 6 Writeup

Below are the map images created by following the instructions presented in part 1.

![lab6part1.1](lab6part1.1.png)

![lab6part1.2](lab6part1.2.png)

![lab6part1.3](lab6part1.3.png)

![lab6part1.4](lab6part1.4.png)

![lab6part1.5](lab6part1.5.png)

![lab6part1.6](lab6part1.6.png)

![lab6part1.7](lab6part1.7.png)

![lab6part1.8](lab6part1.8.png)

![lab6part1.9](lab6part1.9.png)

![lab6part1.10](lab6part1.10.png)

![lab6part1.11](lab6part1.11.png)

![lab6part1.12](lab6part1.12.png)

![lab6part1.13](lab6part1.13.png)

![lab6part1.14](lab6part1.14.png)

![lab6part1.15](lab6part1.15.png)

![lab6part1.16](lab6part1.16.png)

![lab6part1.17](lab6part1.17.png)

![lab6part1.18](lab6part1.18.png)

For part two, I choose to spatially analyze where elderly people live in Baltimore. I first created a new table entry to represent the total population of people over 65 by multiplying the values from the column with the percentage of people over 65 with the values from the column with the total population. I then created a Moran's I Cluster Map with a significance filter of 0.05 and 99999 permutations. The map image can be seen below. It shows that not very many old people live near the harbor, *except* near the very tip, where we see a high-low area, indicating that this area does have an above average number of old people, but the areas around it do not, as we can see from the map. Other areas with statistically high amounts of old people can be seen near the northern corners of the city limits. All other areas of the city have statistically insignificant amounts of old people, or are not clustered enough to appear on the map.

![lab6part2](lab6part2.png)

For part 3, I decided to try my hand at creating a conditional map using the data set and shapefiles I have been using for my projects. I added the property shapefile with usegroup, objectid, and yearbuild columns. I then created a conditional map with no vertical variable and usegroup as the horizontal variable, with the maps themselves displaying yearbuild. This resulted in ten mini maps, seen below, each showing the age of different types of buildings in Baltimore. This is a really cool image, as it shows both what kinds of buildings exist in what areas of baltimore, but also traces their development as new buildings of that type get built. I am proud that it shows such deep data analysis with such a simple map type and display. My only complaints are that the maps are very very tiny. If I could stack 5 of the maps on top of the other 5, they would be easier to view. Unfortunately, I was unable to figure out how to do that. My other complaint is that I am not certain what all the usegroup identifiers mean, and have been unable to find out the appropriate key.

![lab6part3](lab6part3.png)
