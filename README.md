# SeamountTrails

This repo contains code used as part of the recipe to make an animation of seamounts forming along hotspot trails in the Tasman Sea. 

See here: https://www.youtube.com/watch?v=ueoTvirXFbc [reconstruction animation starts at 55 seconds]

The reconstruction images are made using GPlates. The specific purpose of the code here is to create a series of paleobathymetry grids where each seamounts is masked out for times older than the seamount; each seamount is gradually built up at the time it is thought to have formed (based on radiometric dating and/or plate motion modelling).

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
