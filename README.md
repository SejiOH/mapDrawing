# mapDrawing

<b><h4>Let's draw a map with R and Python.</b></h4>

Drawing a map is one of the powerful visualization tools.<br>
We can add texts, numbers(probably they are statistically meaningful figures), images and so on.<br>
We can express indicators by coloring on a map.

So here we are going to make these outputs step by step.<br>
<a href=#mapR>1. Draw a map with R</a><br>
<a href=#mapPython>2. Draw a map with Python</a><br>
<a href=#references>3. References</a>

<b><h4 id=mapR>1.Draw a map with R</h4></b>
There are various datasets to draw a map in R.<br>
Especially, packages like 'maps' and 'mapdata' are useful to practice it.<br>

Prerequites are:
<pre><code>
library(tidyverse)
library(filesstrings)
library(magrittr)
library(RColorBrewer)
library(maps)
library(mapdata)
</code></pre>

Let's set a working directory as we do usually.<br>
If you do not want create a directory, then skip the first line.
<pre><code>
create_dir("D:/working_directory")
setwd("D:/working_directory")
getwd()
dir()
</code></pre>

If you want to check what datasets are in the each package, write this.
<pre><code>
data(package="maps")
data(package="mapdata")
</code></pre>

At first, we draw a world map.
<pre><code>
world_map <- map_data("world")
head(world_map)
world_map_plot <- ggplot(world_map, aes(long, lat, group=group))+
geom_polygon(fill="white", colour="gray")+ggtitle("the World Map")
</code></pre>

Then color the map by regions.
<pre><code>
world_map_by_region_plot <- ggplot(world_map, aes(long, lat, group=group, fill=region))+
geom_polygon(show.legend=FALSE)+ggtitle("the World Map colored by regions")
</code></pre>

<b><h4 id=mapPython>2. Draw a map with Python</h4></b>

<b><h4 id=references>3. References</h4></b>
Lecture 6: Map Visualization (Part B) http://www.statsoft.org/wp-content/uploads/2016/09/Lecture6b_ShowDataOnMap.html
Lecture 6: Map Visualization http://www.statsoft.org/wp-content/uploads/2016/09/Lecture6a_DisplayMap.html
STAT3622 Data Visualization http://www.statsoft.org/teaching/stat3622/
