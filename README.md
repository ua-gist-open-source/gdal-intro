# Assignment: Gdal Intro
## Worth: 40 points
## Due: Monday, April 15, 11:59pm

## Objective: Use gdal to solve a number of geospatial problems


## Background

https://github.com/geo-data/gdal-docker

https://gdal.org/programs/index.html#raster-programs
gdalinfo
gdal_calc
gdal_compare
gdal_warp
gdal_merge
gdal_rasterize
gdal_transform
ogrinfo
ogr2ogr
ogrmerge

https://gdal.org/programs/ogrinfo.html
## Prerequisites
1) Docker is installed

## Assignment

### 1) Pull the gdal docker container.



Run the gdal docker container to give yourself a quick test that you have a working container. The first time you
run it, docker will need to download the layers it needs:

```
docker run geodata/gdal ogr2ogr --version
```


_Deliverable: Take a screenshot of your GeoServer Welcome screen showing the 19 Layers. Name it `screenshot.png` and add it to a new GitHub branch named `solution`. 

### 7. Turn in your work via GitHub Pull Request. 

Submit a *Pull request* to merge your `solution` branch with the `master` branch. _Do not merge it yourself_



