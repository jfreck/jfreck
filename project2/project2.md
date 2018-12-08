---
title: Project 2
feature_image: "Project2Feature.png"
feature_text: |
  ## Project 2
  Building Age and Urban Modernization
  
---

***Further Examining Building Age and Urban Development in Baltimore***

For this project, I decided to continue my theme from project 1 and look at the age of properties in Baltimore. I have displayed here a gif showing the oldest building year in each area of a hex grid as well as the buildings in each year range. Together, the images show urban development in the city, highlighting areas with modern buildings and areas with older ones. Some trends to notice are that many of the oldest buildings are found near the city center and the newest are most common along the waterfront in the harbor.

#### Building Age in Baltimore

![project2gif](project2gif.gif)

**Steps to completion**
* Add Property Shapefile.
* Property polygons queried to only show year_build and usegroup "select objectid, year_build, usegroup, ST_Buffer(GEOMETRY, 0) from property2 where year_build>0"
* Create centroids of properties.
* Create hex grid (600 meters).
* Join Attributes by Location (Summary) - join centroids to hex grid using year_build min.
* Take each hex and display them in 8 categories, with building polygons for each year range showing up as well.
* Add Stamen Toner Basemap and Baltimore City Border shapefile.
* In map view, add a textbox with the year range, then export as an image 9 times, progressively adding each category into each layer. Adding building shape layer parts was done by filtering the layer, each time changing the following expression to match the desired year range: "year_build <= YEAR"
* Combine the images together into an animated gif (I used GIMP).

I was easily able to create a very nice gif without any python whatsoever, and I believe that doing any of what I did through python would be much more complicated and convoluted.

However, in order to perform a small amount of python in this project, I did change the color of the building shape layer to red using python. This probably doesn't count, but I couldn't get anything else to work, and I don't know enough about python to troubleshoot anything. I think I could have filtered the building layer using python, but I could not figure out how to change the sample code I found in the "developer cookbook" because I don't know what any of the code means or what it does. I have provided below the code I used to change the color, as well as the sample code I would have liked to use, in hopes that you might confirm it's potential use and that it is indeed what I think it is. Even if it is, it was much easier to just do it in the qgis console rather than bother with python, but I understand that is not the nature of the assignment.

**Changing Building Shape Layer to Red** (What I did)
```Python
layer = iface.activeLayer()
renderer = layer.renderer()
symbol = renderer.symbol()
symbol.setColor(QColor(Qt.red))
iface.mapCanvas().refresh()
layer.triggerRepaint()
iface.layerTreeView().refreshLayerSymbology(layer.id())
```

**Sample Code for Filtering by Expression** (What I would have liked to do, but perhaps would have been too complex)
```python
def where(layer, exp):
  print "Where"
  exp = QgsExpression(exp)
  if exp.hasParserError():
    raise Exception(exp.parserErrorString())
  exp.prepare(layer.pendingFields())
  for feature in layer.getFeatures():
    value = exp.evaluate(feature)
    if exp.hasEvalError():
      raise ValueError(exp.evalErrorString())
    if bool(value):
      yield feature

layer = qgis.utils.iface.activeLayer()
for f in where(layer, 'Test > 1.0'):
  print f + " Matches expression"
```
