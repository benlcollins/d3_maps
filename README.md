# d3 Maps

## What is this?

This repo is a collection of working files as I continue my data explorations with d3.

The UK map is a straight forward run through of Mike Bostock's excellent "Let's Make a Map" tutorial, found here: http://bost.ocks.org/mike/map/

The US map is my own version of this map, based off the Bostock map, but using US data. I created this from the command line using the following modified commands:

```
ogr2ogr -f GeoJSON -where "ADM0_A3 IN ('USA')" subunits2.json ne_10m_admin_0_map_subunits.shp

ogr2ogr -f GeoJSON -where "ISO_A2 = 'US' AND SCALERANK < 4" places2.json ne_10m_populated_places.shp

topojson -o usa.json --id-property SU_A3 --properties name=NAME -- subunits2.json places2.json
```

The World map is a zoomable, scalable world map, with selected cities marked. It's based off the following d3noob tutorial: http://www.d3noob.org/2013/03/a-simple-d3js-map-explained.html