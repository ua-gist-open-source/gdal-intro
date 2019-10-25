# Assignment: GDAL and OGR Intro
## Worth: 50 points
## Due: Monday, April 15, 11:59pm

## Objective: Use gdal to solve a number of geospatial problems


## Background

GDAL (http://www.gdal.org) is a very powerful library and command utility used to read, write, and transform raster and 
vector geospatial data. GDAL's sister project, OGR, is a library and set of utilities that reads, writes, and transforms
vector data. GDAL is an open source project released under the MIT license, allowing re-purposing for commercial use. As 
such, GDAL is used in both open source and commercial projects (e.g., ESRI's suite) for handling raster data.

As an open source project with lots of configuration options, including the ability to link proprietary libraries for
proprietary data formats, installation and configuration can be tricky so in this class we will use a docker container
which has pre-installed the libraries we need. This simplifies use in that it will run the same on a mac, windows, or linux,
but will require a bit more on the command line in order to access the right docker image, mount a volume, and of course 
run the command.

## Assignment: Part 1 (GDAL)
As you work through this assignment, compile your answers in a file named `answers.md` in a new branch on this repo named
`solution`. When you have completed the assignment, submit a `Pull Request` to merge with `master`. _Do not merge the branch yourself._

I would like you to peruse the list of GDAL programs on https://gdal.org/programs/index.html#raster-programs as well 
as the OGR programs on https://gdal.org/programs/ogrinfo.html/. Read the `Synopsis`, `Description`, and `Example` of each of 
the programs in the lists. 

### 0. Update your Windows PATH
gdal was installed in `C:\osgeo4w64` but windows will not know where these programs are unless we add them to our path. Follow [these instructions](http://www.kscodes.com/misc/how-to-set-path-in-windows-without-admin-rights/) to add `C:\OSGeo4W64\bin` to your `Path` Environment Variables.

### 1. From the GDAL and OGR Programs, find 4 programs, describe them, and compare them with other tools that perform similar functions that you are already familiar with. Add this to `answers.md`

To test `gdal`, [download this file](https://drive.google.com/open?id=0B-vzf2mGcaRzQlJ3cE9BSE1LNTQ), a shaded
relief of Canyonlands. Move the file to your working directory, then open a Windows `cmd` window and navigate to the
same directory.

Type:
```
gdalinfo test.tif
```
_Note: If you get something like `Command Not Found`, your environment may not have `gdal` in the `PATH`. If possible, add this directory to your path: `C:\osgeo4w64\bin` and try again. For this session only:_
```
SET PATH=%PATH%;C:\osgeo4w64\bin
```
After you run a successful `gdalinfo`, you should see a lot of text like starting with ```Driver: GTiff/GeoTIFF
Files: CANYrelief1-geo.tif```

### 2. Create a screenshot named `screenshot_canyon.png` of your `cmd` window after running `gdalinfo` on the shaded relief GeoTIFF

## Assignment: Part 2 (GDAL Tutorial)
Robert Simmon, an ex-NASA engineer and current Planeteer, wrote a great tutorial about getting started with some basic
use cases of gdal. You are going to read Parts 1 and 2, following the samples, and producing some minor tweaks due
to differences in your configuration (i.e., docker) and at my request.

Read Part 1 of the tutorial:
- [A Gentle Introduction to GDAL, Part 1](https://medium.com/planet-stories/a-gentle-introduction-to-gdal-part-1-a3253eb96082). 

Read and follow the examples but skip `Installing GDAL` since it is already installed for you.

Follow the tutorial for Part 1, which will produce a lower resolution `jpeg` version of the Canyonlands shaded relief image.

### 3. Add the `CANYrelief1.jpg` file you produced with `gdal_translate` to the `solution` branch.

Read Part 2 of the tutorial:
- [A Gentle Introduction to GDAL, Part 2: Map Projections & gdalwarp](https://medium.com/planet-stories/a-gentle-introduction-to-gdal-part-2-map-projections-gdalwarp-e05173bd710a)

For this assignment, follow the tutorial in part 2. When you have finished, revisit the last example and create a North Pole (Arctic) stereographic image. Name it `NE1_50M_SR_W_sh60_polarstereo_1400.png`

### 4. Add the `NE1_50M_SR_W_sh60_polarstereo_1400.png` file to the `solution` branch.

You are welcome to read Part 3 but it is not required for this assignment.

## Assignment: Part 2 (OGR)

Sara Safavi (Another Planeteer) wrote this great example tutorial for OGR: http://www.sarasafavi.com/intro-to-ogr-part-i-exploring-data.html. Follow the tutorial for Part I
- [Intro to OGR, Part I: Exploring Data](http://www.sarasafavi.com/intro-to-ogr-part-i-exploring-data.html)

### 5. Take a screenshot of the `ogrinfo` command with quiet output and name it `screenshot-ogrinfo-q.png`

Follow the tutorial for Part 2 up to *Creating a KML*.
- [Intro to OGR, Part II: Creating New Data](http://www.sarasafavi.com/intro-to-ogr-part-ii-creating-new-data.html)
Instead of Creating a KML you are going to create a GeoJSON-formatted file and commit it to this repo. GitHub has a nice 
feature of actually displaying GeoJSON files in an interactive map.

### 6. Use ogr2ogr to create `austinparks.geojson`

At this step: 
```
ogr2ogr -f "KML" austinparks.kml new_layer.shp -dsco DescriptionField='ADDRESS'
```
Change `KML` to `GeoJSON` and set the output name to `austinparks.geojson`

## Assignment Deliverables
- File named `answers.md` containing short answers
- Screenshot named `screenshot-docker-gdal.png`
- `gdal_translate` output named `CANYrelief.jpg`
- `gdalwarp/gdal_translate` output named `NE1_50M_SR_W_sh60_polarstereo_1400.png` of the North Pole
- `austinparks.geojson` - GeoJSON of Austin Parks

### 7. Turn in your work via GitHub Pull Request. 

Submit a *Pull request* to merge your `solution` branch with the `master` branch. _Do not merge it yourself_



