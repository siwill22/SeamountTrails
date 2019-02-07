# SeamountTrails

This repo contains code used as part of the recipe to make an animation of seamounts forming along hotspot trails in the Tasman Sea. 

See here: 

[![Tasman Sea youtube clip](http://img.youtube.com/vi/ueoTvirXFbc/0.jpg)](https://www.youtube.com/watch?v=ueoTvirXFbc?t=54 )

The reconstruction images are made using GPlates (to apply the colormap, add in the hotspot circles and trail markers, displat the time in the top left corner). The specific purpose of the code here is to create a series of paleobathymetry grids to load in to GPlates. In these grids, each seamount is masked out for times older than the seamount; each seamount is gradually built up at the time it is thought to have formed (based on radiometric dating and/or plate motion modelling).

### Required inputs:
   
- grid of present-day bathymetry (in netcdf format) 
- set of polygons around the edges of the seamounts, with ages assigned corresponding to the age of seamount formation (in a GPlates-readable format, ie shapefile, gpml or gmt)

### Outputs:
- set of paleobathymetry rasters (in netcdf format). These would then be loaded into GPlates using the 'import --> time-dependent raster' option

Once in GPlates, the time-dependent raster sequence can be linked to any reconstruction model by attaching to the static polygons for that model.

### Required python modules:
- numpy
- matplotlib
- xarray
- pygplates
- stripy
